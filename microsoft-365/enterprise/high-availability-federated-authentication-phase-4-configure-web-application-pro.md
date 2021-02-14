---
title: Этап 4. Настройка прокси-серверов веб-приложений для федерационной проверки подлинности для высокой доступности
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 1c903173-67cd-47da-86d9-d333972dda80
description: Сводка. Настройте прокси-серверы веб-приложений для федерационной проверки подлинности с высоким уровнем доступности для Microsoft 365 в Microsoft Azure.
ms.openlocfilehash: fd63274ffb9528cedb88fc2ba77834cfd56664d4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693343"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a><span data-ttu-id="71d44-103">Этап 4. Федеративная проверка подлинности для обеспечения высокой доступности: настройка прокси веб-приложений</span><span class="sxs-lookup"><span data-stu-id="71d44-103">High availability federated authentication Phase 4: Configure web application proxies</span></span>

<span data-ttu-id="71d44-104">На этом этапе развертывания федераированной проверки подлинности Microsoft 365 с высоким уровнем доступности в службах инфраструктуры Azure создается внутренний балансировщик нагрузки и два сервера AD FS.</span><span class="sxs-lookup"><span data-stu-id="71d44-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="71d44-105">Перед переходом к этапу 5: настройка федерационной проверки подлинности [для Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)необходимо завершить этот этап.</span><span class="sxs-lookup"><span data-stu-id="71d44-105">You must complete this phase before moving on to [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="71d44-106">См. все этапы развертывания федерационной проверки подлинности с высоким уровнем доступности для [Microsoft 365](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) в Azure.</span><span class="sxs-lookup"><span data-stu-id="71d44-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a><span data-ttu-id="71d44-107">Создание балансировки нагрузки с доступом к Интернету в Azure</span><span class="sxs-lookup"><span data-stu-id="71d44-107">Create the Internet-facing load balancer in Azure</span></span>

<span data-ttu-id="71d44-108">Необходимо создать балансировку нагрузки с доступом к Интернету, чтобы Azure равномерно распределяла входящий трафик проверки подлинности клиентов из Интернета между двумя прокси-серверами веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="71d44-108">You must create an Internet-facing load balancer so that Azure distributes the incoming client authentication traffic from the Internet evenly among the two web application proxy servers.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71d44-109">Для указанных ниже последовательностей команд используется последняя версия Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71d44-109">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="71d44-110">См. ["Начало работы с Azure PowerShell".](https://docs.microsoft.com/powershell/azure/get-started-azureps)</span><span class="sxs-lookup"><span data-stu-id="71d44-110">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="71d44-111">После того как вы предоставили значения расположения и группы ресурсов, запустите итоговый блок в командной области Azure PowerShell или в isE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71d44-111">When you have supplied location and resource group values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="71d44-112">Чтобы создать готовые командные блоки PowerShell на основе пользовательских параметров, используйте эту книгу конфигурации [Microsoft Excel.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)</span><span class="sxs-lookup"><span data-stu-id="71d44-112">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up key variables
$locName="<your Azure location>"
$rgName="<Table R - Item 4 - Resource group name column>"

$publicIP=New-AzPublicIpAddress -ResourceGroupName $rgName -Name "WebProxyPublicIP" -Location $LocName -AllocationMethod "Static"
$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "WebAppProxyServers-LBFE" -PublicIpAddress $publicIP
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "WebAppProxyServers-LBBE"
$healthProbe=New-AzLoadBalancerProbeConfig -Name "WebServersProbe" -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "WebTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

<span data-ttu-id="71d44-113">Чтобы отобразить общедоступный IP-адрес, присвоенный вашему балансированию нагрузки с доступом к Интернету, запустите указанные здесь команды в командной командной области Azure PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="71d44-113">To display the public IP address assigned to your Internet-facing load balancer, run these commands at the Azure PowerShell command prompt on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a><span data-ttu-id="71d44-114">Определение FQDN службы федерации и создание записей DNS</span><span class="sxs-lookup"><span data-stu-id="71d44-114">Determine your federation service FQDN and create DNS records</span></span>

<span data-ttu-id="71d44-115">Необходимо определить DNS-имя для идентификации имени службы федерации в Интернете.</span><span class="sxs-lookup"><span data-stu-id="71d44-115">You need to determine the DNS name to identify your federation service name on the Internet.</span></span> <span data-ttu-id="71d44-116">Azure AD Connect настроит Microsoft 365 с этим именем на этапе 5, который станет частью URL-адреса, отправляемого Microsoft 365 подключающихся клиентов для получения маркера безопасности.</span><span class="sxs-lookup"><span data-stu-id="71d44-116">Azure AD Connect will configure Microsoft 365 with this name in Phase 5, which will become part of the URL that Microsoft 365 sends to connecting clients to get a security token.</span></span> <span data-ttu-id="71d44-117">Пример: fs.contoso.com (fs означает службу федерации).</span><span class="sxs-lookup"><span data-stu-id="71d44-117">An example is fs.contoso.com (fs stands for federation service).</span></span>
  
<span data-ttu-id="71d44-118">После создания FDQN службы федерации создайте общедоступный домен DNS-записи A для FDQN службы федерации, которая соединена с общедоступным IP-адресом службы балансировки нагрузки с доступом к Интернету в Azure.</span><span class="sxs-lookup"><span data-stu-id="71d44-118">Once you have your federation service FDQN, create a public DNS domain A record for the federation service FDQN that resolves to the public IP address of the Azure Internet-facing load balancer.</span></span>
  
|<span data-ttu-id="71d44-119">**Имя**</span><span class="sxs-lookup"><span data-stu-id="71d44-119">**Name**</span></span>|<span data-ttu-id="71d44-120">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="71d44-120">**Type**</span></span>|<span data-ttu-id="71d44-121">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="71d44-121">**TTL**</span></span>|<span data-ttu-id="71d44-122">**Значение**</span><span class="sxs-lookup"><span data-stu-id="71d44-122">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="71d44-123">FDQN службы федерации</span><span class="sxs-lookup"><span data-stu-id="71d44-123">federation service FDQN</span></span>  <br/> |<span data-ttu-id="71d44-124">A</span><span class="sxs-lookup"><span data-stu-id="71d44-124">A</span></span>  <br/> |<span data-ttu-id="71d44-125">3600</span><span class="sxs-lookup"><span data-stu-id="71d44-125">3600</span></span>  <br/> |<span data-ttu-id="71d44-126">общедоступный IP-адрес службы балансировки нагрузки с доступом к Интернету в Azure (отображается командой **write-Host** в предыдущем разделе)</span><span class="sxs-lookup"><span data-stu-id="71d44-126">public IP address of the Azure Internet-facing load balancer (displayed by the **Write-Host** command in the previous section)</span></span> <br/> |
   
<span data-ttu-id="71d44-127">Вот пример:</span><span class="sxs-lookup"><span data-stu-id="71d44-127">Here is an example:</span></span>
  
|<span data-ttu-id="71d44-128">**Имя**</span><span class="sxs-lookup"><span data-stu-id="71d44-128">**Name**</span></span>|<span data-ttu-id="71d44-129">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="71d44-129">**Type**</span></span>|<span data-ttu-id="71d44-130">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="71d44-130">**TTL**</span></span>|<span data-ttu-id="71d44-131">**Значение**</span><span class="sxs-lookup"><span data-stu-id="71d44-131">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="71d44-132">fs.contoso.com</span><span class="sxs-lookup"><span data-stu-id="71d44-132">fs.contoso.com</span></span>  <br/> |<span data-ttu-id="71d44-133">A</span><span class="sxs-lookup"><span data-stu-id="71d44-133">A</span></span>  <br/> |<span data-ttu-id="71d44-134">3600</span><span class="sxs-lookup"><span data-stu-id="71d44-134">3600</span></span>  <br/> |<span data-ttu-id="71d44-135">131.107.249.117</span><span class="sxs-lookup"><span data-stu-id="71d44-135">131.107.249.117</span></span>  <br/> |
   
<span data-ttu-id="71d44-136">Затем добавьте запись DNS-адреса в частное пространство имен DNS вашей организации, которое соединено с FQDN службы федерации в частный IP-адрес, присвоенный внутренней подстройке нагрузки для серверов AD FS (таблица I, элемент 4, столбец "Значение").</span><span class="sxs-lookup"><span data-stu-id="71d44-136">Next, add a DNS address record to your organization's private DNS namespace that resolves your federation service FQDN to the private IP address assigned to the internal load balancer for the AD FS servers (Table I, item 4, Value column).</span></span>
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a><span data-ttu-id="71d44-137">Создание виртуальных машин прокси-сервера веб-приложения в Azure</span><span class="sxs-lookup"><span data-stu-id="71d44-137">Create the web application proxy server virtual machines in Azure</span></span>

<span data-ttu-id="71d44-138">Используйте следующий блок команд Azure PowerShell для создания виртуальных машин для двух прокси-серверов веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="71d44-138">Use the following block of Azure PowerShell commands to create the virtual machines for the two web application proxy servers.</span></span> 
  
<span data-ttu-id="71d44-139">Обратите внимание, что в следующих наборах команд Azure PowerShell используются значения из следующих таблиц:</span><span class="sxs-lookup"><span data-stu-id="71d44-139">Note that the following Azure PowerShell command sets use values from the following tables:</span></span>
  
- <span data-ttu-id="71d44-140">таблица M (для виртуальных машин);</span><span class="sxs-lookup"><span data-stu-id="71d44-140">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="71d44-141">таблица R (для групп ресурсов);</span><span class="sxs-lookup"><span data-stu-id="71d44-141">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="71d44-142">таблица V (для параметров виртуальной сети);</span><span class="sxs-lookup"><span data-stu-id="71d44-142">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="71d44-143">таблица S (для подсетей);</span><span class="sxs-lookup"><span data-stu-id="71d44-143">Table S, for your subnets</span></span>
    
- <span data-ttu-id="71d44-144">таблица I (для статических IP-адресов);</span><span class="sxs-lookup"><span data-stu-id="71d44-144">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="71d44-145">таблица A (для групп доступности).</span><span class="sxs-lookup"><span data-stu-id="71d44-145">Table A, for your availability sets</span></span>
    
<span data-ttu-id="71d44-146">Помните, что вы определили таблицу M на этапе [2.](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) Настройка контроллеров домена и таблиц R, V, S, I и A на этапе [1. Настройка Azure.](high-availability-federated-authentication-phase-1-configure-azure.md)</span><span class="sxs-lookup"><span data-stu-id="71d44-146">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
<span data-ttu-id="71d44-147">Задав правильные значения, выполните полученный блок в командной строке Azure PowerShell или в интегрированной среде сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71d44-147">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 3 - Subnet name column>"
$avName="<Table A - Item 3 - Availability set name column>"
$rgNameTier="<Table R - Item 3 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first web application proxy server virtual machine
$vmName="<Table M - Item 6 - Virtual machine name column>"
$vmSize="<Table M - Item 6 - Minimum size column>"
$staticIP="<Table I - Item 7 - Value column>"
$diskStorageType="<Table M - Item 6 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second web application proxy virtual machine
$vmName="<Table M - Item 7 - Virtual machine name column>"
$vmSize="<Table M - Item 7 - Minimum size column>"
$staticIP="<Table I - Item 8 - Value column>"
$diskStorageType="<Table M - Item 7 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="71d44-148">Эти виртуальные машины предназначены для работы в интрасети, поэтому им не назначается общедоступный IP-адрес или метка доменного имени DNS и они не подключаются к Интернету.</span><span class="sxs-lookup"><span data-stu-id="71d44-148">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet.</span></span> <span data-ttu-id="71d44-149">Однако это также означает, что к ним невозможно подключиться с помощью портала Azure.</span><span class="sxs-lookup"><span data-stu-id="71d44-149">However, this also means that you cannot connect to them from the Azure portal.</span></span> <span data-ttu-id="71d44-150">Команда **Подключиться** недоступна при просмотре свойств виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="71d44-150">The **Connect** option is unavailable when you view the properties of the virtual machine.</span></span> <span data-ttu-id="71d44-151">Используйте метод доступа к удаленному рабочему столу или другое средство удаленного рабочего стола для подключения к виртуальной машине с помощью частного IP-адреса или DNS-имени интрасети и учетных данных локальной учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="71d44-151">Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="71d44-152">Здесь показана конфигурация, полученная в результате успешного выполнения этого этапа (с заполнителями вместо имен компьютеров).</span><span class="sxs-lookup"><span data-stu-id="71d44-152">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="71d44-153">**Этап 4. Подстановка нагрузки для Интернета и прокси-серверы веб-приложений для инфраструктуры федерационной проверки подлинности с высоким уровнем доступности в Azure**</span><span class="sxs-lookup"><span data-stu-id="71d44-153">**Phase 4: The Internet-facing load balancer and web application proxy servers for your high availability federated authentication infrastructure in Azure**</span></span>

![Этап 4 инфраструктуры федераированной проверки подлинности Microsoft 365 с высоким уровнем доступности в Azure с прокси-серверами веб-приложений](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a><span data-ttu-id="71d44-155">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="71d44-155">Next step</span></span>

<span data-ttu-id="71d44-156">Этап [5. Настройка федерационной](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) проверки подлинности для Microsoft 365 для продолжения настройки этой рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="71d44-156">Use [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="71d44-157">См. также</span><span class="sxs-lookup"><span data-stu-id="71d44-157">See Also</span></span>

[<span data-ttu-id="71d44-158">Развертывание федеративной проверки подлинности для обеспечения высокой доступности Microsoft 365 в Azure</span><span class="sxs-lookup"><span data-stu-id="71d44-158">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="71d44-159">Федератное удостоверение для среды тестирования и тестирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="71d44-159">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="71d44-160">Центр архитектуры и решений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="71d44-160">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

