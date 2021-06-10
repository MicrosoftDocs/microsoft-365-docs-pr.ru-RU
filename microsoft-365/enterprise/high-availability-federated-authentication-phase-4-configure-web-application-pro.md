---
title: Высокая доступность федерационной проверки подлинности Фаза 4 Настройка прокси-серверов веб-приложений
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
description: Сводка. Настройте прокси-серверы веб-приложения для федерарной проверки подлинности высокой доступности для Microsoft 365 в Microsoft Azure.
ms.openlocfilehash: 95d73d05f2eef087e606df14db180b24c69d5932
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929076"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a><span data-ttu-id="2da5e-103">Этап 4. Федеративная проверка подлинности для обеспечения высокой доступности: настройка прокси веб-приложений</span><span class="sxs-lookup"><span data-stu-id="2da5e-103">High availability federated authentication Phase 4: Configure web application proxies</span></span>

<span data-ttu-id="2da5e-104">На этом этапе развертывания высокой доступности для Microsoft 365 федерарной проверки подлинности в службах инфраструктуры Azure создается внутренний балансировщик нагрузки и два сервера AD FS.</span><span class="sxs-lookup"><span data-stu-id="2da5e-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="2da5e-105">Перед переходом на этап [5: Настройка федерационной](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)проверки подлинности для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2da5e-105">You must complete this phase before moving on to [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="2da5e-106">См. в рублях Развертывание [федерарной](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) проверки подлинности с высокой доступностью для Microsoft 365 в Azure для всех этапов.</span><span class="sxs-lookup"><span data-stu-id="2da5e-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a><span data-ttu-id="2da5e-107">Создание балансировки нагрузки, относящаяся к Интернету, в Azure</span><span class="sxs-lookup"><span data-stu-id="2da5e-107">Create the Internet-facing load balancer in Azure</span></span>

<span data-ttu-id="2da5e-108">Необходимо создать балансировку нагрузки с подключением к Интернету, чтобы Azure равномерно распределяла входящий трафик проверки подлинности клиентов из Интернета между двумя прокси-серверами веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="2da5e-108">You must create an Internet-facing load balancer so that Azure distributes the incoming client authentication traffic from the Internet evenly among the two web application proxy servers.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2da5e-109">Для указанных ниже последовательностей команд используется последняя версия Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2da5e-109">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="2da5e-110">См. [начало работы с Azure PowerShell](/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="2da5e-110">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="2da5e-111">Если вы предоставили значения расположения и группы ресурсов, запустите в результате блок в командной Azure PowerShell или в ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2da5e-111">When you have supplied location and resource group values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="2da5e-112">Для создания готовых к запуску командных блоков PowerShell на основе настраиваемой настройки используйте Microsoft Excel [конфигурации.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)</span><span class="sxs-lookup"><span data-stu-id="2da5e-112">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

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

<span data-ttu-id="2da5e-113">Чтобы отобразить общедоступный IP-адрес, присвоенный вашему балансированию нагрузки с подключением к Интернету, запустите эти команды в командной Azure PowerShell на локальном компьютере:</span><span class="sxs-lookup"><span data-stu-id="2da5e-113">To display the public IP address assigned to your Internet-facing load balancer, run these commands at the Azure PowerShell command prompt on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a><span data-ttu-id="2da5e-114">Определение FQDN службы федерации и создание записей DNS</span><span class="sxs-lookup"><span data-stu-id="2da5e-114">Determine your federation service FQDN and create DNS records</span></span>

<span data-ttu-id="2da5e-115">Чтобы определить имя службы федерации в Интернете, необходимо определить имя службы федерации.</span><span class="sxs-lookup"><span data-stu-id="2da5e-115">You need to determine the DNS name to identify your federation service name on the Internet.</span></span> <span data-ttu-id="2da5e-116">Azure AD Подключение настраивает Microsoft 365 с этим именем в фазе 5, который станет частью URL-адреса, который Microsoft 365 для подключения клиентов для получения маркера безопасности.</span><span class="sxs-lookup"><span data-stu-id="2da5e-116">Azure AD Connect will configure Microsoft 365 with this name in Phase 5, which will become part of the URL that Microsoft 365 sends to connecting clients to get a security token.</span></span> <span data-ttu-id="2da5e-117">Пример : fs.contoso.com (fs означает службу федерации).</span><span class="sxs-lookup"><span data-stu-id="2da5e-117">An example is fs.contoso.com (fs stands for federation service).</span></span>
  
<span data-ttu-id="2da5e-118">После создания службы федерации FDQN создайте общедоступный домен DNS Запись для службы федерации FDQN, которая решается на общедоступный IP-адрес балансировки нагрузки в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2da5e-118">Once you have your federation service FDQN, create a public DNS domain A record for the federation service FDQN that resolves to the public IP address of the Azure Internet-facing load balancer.</span></span>
  
|<span data-ttu-id="2da5e-119">**Имя**</span><span class="sxs-lookup"><span data-stu-id="2da5e-119">**Name**</span></span>|<span data-ttu-id="2da5e-120">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="2da5e-120">**Type**</span></span>|<span data-ttu-id="2da5e-121">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="2da5e-121">**TTL**</span></span>|<span data-ttu-id="2da5e-122">**Значение**</span><span class="sxs-lookup"><span data-stu-id="2da5e-122">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2da5e-123">FDQN службы федерации</span><span class="sxs-lookup"><span data-stu-id="2da5e-123">federation service FDQN</span></span>  <br/> |<span data-ttu-id="2da5e-124">A</span><span class="sxs-lookup"><span data-stu-id="2da5e-124">A</span></span>  <br/> |<span data-ttu-id="2da5e-125">3600</span><span class="sxs-lookup"><span data-stu-id="2da5e-125">3600</span></span>  <br/> |<span data-ttu-id="2da5e-126">общедоступный IP-адрес балансира нагрузки, отображаемого командой **Write-Host** в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="2da5e-126">public IP address of the Azure Internet-facing load balancer (displayed by the **Write-Host** command in the previous section)</span></span> <br/> |
   
<span data-ttu-id="2da5e-127">Пример:</span><span class="sxs-lookup"><span data-stu-id="2da5e-127">Here is an example:</span></span>
  
|<span data-ttu-id="2da5e-128">**Имя**</span><span class="sxs-lookup"><span data-stu-id="2da5e-128">**Name**</span></span>|<span data-ttu-id="2da5e-129">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="2da5e-129">**Type**</span></span>|<span data-ttu-id="2da5e-130">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="2da5e-130">**TTL**</span></span>|<span data-ttu-id="2da5e-131">**Значение**</span><span class="sxs-lookup"><span data-stu-id="2da5e-131">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2da5e-132">fs.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2da5e-132">fs.contoso.com</span></span>  <br/> |<span data-ttu-id="2da5e-133">A</span><span class="sxs-lookup"><span data-stu-id="2da5e-133">A</span></span>  <br/> |<span data-ttu-id="2da5e-134">3600</span><span class="sxs-lookup"><span data-stu-id="2da5e-134">3600</span></span>  <br/> |<span data-ttu-id="2da5e-135">131.107.249.117</span><span class="sxs-lookup"><span data-stu-id="2da5e-135">131.107.249.117</span></span>  <br/> |
   
<span data-ttu-id="2da5e-136">Далее добавьте запись DNS-адресов в личное пространство имен DNS организации, которое решает проблему FQDN службы федерации, в частный IP-адрес, присвоенный внутреннему балансилю нагрузки для серверов AD FS (таблица I, пункт 4, столбец Value).</span><span class="sxs-lookup"><span data-stu-id="2da5e-136">Next, add a DNS address record to your organization's private DNS namespace that resolves your federation service FQDN to the private IP address assigned to the internal load balancer for the AD FS servers (Table I, item 4, Value column).</span></span>
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a><span data-ttu-id="2da5e-137">Создание виртуальных машин прокси-сервера веб-приложения в Azure</span><span class="sxs-lookup"><span data-stu-id="2da5e-137">Create the web application proxy server virtual machines in Azure</span></span>

<span data-ttu-id="2da5e-138">Используйте следующий блок Azure PowerShell для создания виртуальных машин для двух прокси-серверов веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="2da5e-138">Use the following block of Azure PowerShell commands to create the virtual machines for the two web application proxy servers.</span></span> 
  
<span data-ttu-id="2da5e-139">Обратите внимание, что Azure PowerShell командные наборы используют значения из следующих таблиц:</span><span class="sxs-lookup"><span data-stu-id="2da5e-139">Note that the following Azure PowerShell command sets use values from the following tables:</span></span>
  
- <span data-ttu-id="2da5e-140">таблица M (для виртуальных машин);</span><span class="sxs-lookup"><span data-stu-id="2da5e-140">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="2da5e-141">таблица R (для групп ресурсов);</span><span class="sxs-lookup"><span data-stu-id="2da5e-141">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="2da5e-142">таблица V (для параметров виртуальной сети);</span><span class="sxs-lookup"><span data-stu-id="2da5e-142">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="2da5e-143">таблица S (для подсетей);</span><span class="sxs-lookup"><span data-stu-id="2da5e-143">Table S, for your subnets</span></span>
    
- <span data-ttu-id="2da5e-144">таблица I (для статических IP-адресов);</span><span class="sxs-lookup"><span data-stu-id="2da5e-144">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="2da5e-145">таблица A (для групп доступности).</span><span class="sxs-lookup"><span data-stu-id="2da5e-145">Table A, for your availability sets</span></span>
    
<span data-ttu-id="2da5e-146">Напомним, что вы определили таблицу M в фазе [2:](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) Настройка контроллеров доменов и таблиц R, V, S, I и A на этапе [1: Настройка Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="2da5e-146">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
<span data-ttu-id="2da5e-147">Задав правильные значения, выполните полученный блок в командной строке Azure PowerShell или в интегрированной среде сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2da5e-147">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
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
> <span data-ttu-id="2da5e-148">Эти виртуальные машины предназначены для работы в интрасети, поэтому им не назначается общедоступный IP-адрес или метка доменного имени DNS и они не подключаются к Интернету.</span><span class="sxs-lookup"><span data-stu-id="2da5e-148">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet.</span></span> <span data-ttu-id="2da5e-149">Однако это также означает, что к ним невозможно подключиться с помощью портала Azure.</span><span class="sxs-lookup"><span data-stu-id="2da5e-149">However, this also means that you cannot connect to them from the Azure portal.</span></span> <span data-ttu-id="2da5e-150">Команда **Подключиться** недоступна при просмотре свойств виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="2da5e-150">The **Connect** option is unavailable when you view the properties of the virtual machine.</span></span> <span data-ttu-id="2da5e-151">Для подключения к виртуальной машине с помощью частного IP-адреса или имени DNS интрасети и учетных данных учетной записи локального администратора используйте вспомогательный инструмент удаленного рабочего стола или другой инструмент удаленного рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="2da5e-151">Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="2da5e-152">Здесь показана конфигурация, полученная в результате успешного выполнения этого этапа (с заполнителями вместо имен компьютеров).</span><span class="sxs-lookup"><span data-stu-id="2da5e-152">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="2da5e-153">**Этап 4. Балансировщик нагрузки с подключением к Интернету и прокси-серверы веб-приложений для инфраструктуры федерарной проверки подлинности высокой доступности в Azure**</span><span class="sxs-lookup"><span data-stu-id="2da5e-153">**Phase 4: The Internet-facing load balancer and web application proxy servers for your high availability federated authentication infrastructure in Azure**</span></span>

![Этап 4 высокой доступности Microsoft 365 федерарной инфраструктуры проверки подлинности в Azure с прокси-серверами веб-приложений](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a><span data-ttu-id="2da5e-155">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="2da5e-155">Next step</span></span>

<span data-ttu-id="2da5e-156">Используйте [этап 5. Настройка федерационной](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) проверки подлинности для Microsoft 365 для продолжения настройки этой рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="2da5e-156">Use [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2da5e-157">См. также</span><span class="sxs-lookup"><span data-stu-id="2da5e-157">See Also</span></span>

[<span data-ttu-id="2da5e-158">Развертывание федеративной проверки подлинности для обеспечения высокой доступности Microsoft 365 в Azure</span><span class="sxs-lookup"><span data-stu-id="2da5e-158">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="2da5e-159">Federated identity for your Microsoft 365 dev/test environment</span><span class="sxs-lookup"><span data-stu-id="2da5e-159">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="2da5e-160">Центр архитектуры и решений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2da5e-160">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)