---
title: Фаза федеративной проверки подлинности высокого уровня доступности 4 Настройка прокси-серверов веб-приложений
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
description: Сводка. Настройка прокси-серверов веб-приложений для федеративной проверки подлинности с высоким уровнем доступности для Microsoft 365 в Microsoft Azure.
ms.openlocfilehash: fd63274ffb9528cedb88fc2ba77834cfd56664d4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693343"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a><span data-ttu-id="2d128-103">Этап 4. Федеративная проверка подлинности для обеспечения высокой доступности: настройка прокси веб-приложений</span><span class="sxs-lookup"><span data-stu-id="2d128-103">High availability federated authentication Phase 4: Configure web application proxies</span></span>

<span data-ttu-id="2d128-104">На этом этапе развертывания высокой доступности для федеративной проверки подлинности Microsoft 365 в службах инфраструктуры Azure вы создадите внутренний балансировщик нагрузки и два сервера AD FS.</span><span class="sxs-lookup"><span data-stu-id="2d128-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="2d128-105">Необходимо выполнить этот этап, прежде чем переходить к [этапу 5: Настройка федеративной проверки подлинности для Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span><span class="sxs-lookup"><span data-stu-id="2d128-105">You must complete this phase before moving on to [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="2d128-106">[В статье Развертывание федеративной проверки подлинности с высоким уровнем доступности для Microsoft 365 в Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) для всех фаз.</span><span class="sxs-lookup"><span data-stu-id="2d128-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a><span data-ttu-id="2d128-107">Создание подсистемы балансировки сетевой нагрузки в Azure для выхода из Интернета</span><span class="sxs-lookup"><span data-stu-id="2d128-107">Create the Internet-facing load balancer in Azure</span></span>

<span data-ttu-id="2d128-108">Необходимо создать подсистему балансировки нагрузки с выходом в Интернет, чтобы Azure перегрузил входящий трафик проверки подлинности клиента из Интернета между двумя серверами прокси-сервера веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="2d128-108">You must create an Internet-facing load balancer so that Azure distributes the incoming client authentication traffic from the Internet evenly among the two web application proxy servers.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d128-109">Для указанных ниже последовательностей команд используется последняя версия Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d128-109">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="2d128-110">Ознакомьтесь [с статьей начало работы с Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="2d128-110">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="2d128-111">После того как вы задали значения расположения и группы ресурсов, запустите полученный блок в командной строки Azure PowerShell или в ИНТЕГРИРОВАНной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d128-111">When you have supplied location and resource group values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="2d128-112">Для создания блоков команд PowerShell, готовых к запуску, на основе настраиваемых параметров, используйте эту [книгу настройки Microsoft Excel](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span><span class="sxs-lookup"><span data-stu-id="2d128-112">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

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

<span data-ttu-id="2d128-113">Чтобы отобразить общедоступный IP-адрес, назначенный подсистеме балансировки нагрузки в Интернете, выполните следующие команды в командной строке Azure PowerShell на локальном компьютере:</span><span class="sxs-lookup"><span data-stu-id="2d128-113">To display the public IP address assigned to your Internet-facing load balancer, run these commands at the Azure PowerShell command prompt on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a><span data-ttu-id="2d128-114">Определение полного доменного имени и создание записей DNS для службы федерации</span><span class="sxs-lookup"><span data-stu-id="2d128-114">Determine your federation service FQDN and create DNS records</span></span>

<span data-ttu-id="2d128-115">Необходимо определить DNS-имя, чтобы определить имя службы федерации в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2d128-115">You need to determine the DNS name to identify your federation service name on the Internet.</span></span> <span data-ttu-id="2d128-116">Azure AD Connect настроит Microsoft 365 с таким именем на этапе 5, которое будет частью URL-адреса, который корпорация Майкрософт 365 отправляет клиентам для получения маркера безопасности.</span><span class="sxs-lookup"><span data-stu-id="2d128-116">Azure AD Connect will configure Microsoft 365 with this name in Phase 5, which will become part of the URL that Microsoft 365 sends to connecting clients to get a security token.</span></span> <span data-ttu-id="2d128-117">Например, fs.contoso.com (FS означает служба Федерации).</span><span class="sxs-lookup"><span data-stu-id="2d128-117">An example is fs.contoso.com (fs stands for federation service).</span></span>
  
<span data-ttu-id="2d128-118">После того как вы ФДКН службу федерации, создайте запись A общедоступного домена DNS для службы федерации ФДКН, которая разрешается в общедоступный IP-адрес подсистемы балансировки нагрузки Azure, доступного для выхода в Интернет.</span><span class="sxs-lookup"><span data-stu-id="2d128-118">Once you have your federation service FDQN, create a public DNS domain A record for the federation service FDQN that resolves to the public IP address of the Azure Internet-facing load balancer.</span></span>
  
|<span data-ttu-id="2d128-119">**Имя**</span><span class="sxs-lookup"><span data-stu-id="2d128-119">**Name**</span></span>|<span data-ttu-id="2d128-120">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="2d128-120">**Type**</span></span>|<span data-ttu-id="2d128-121">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="2d128-121">**TTL**</span></span>|<span data-ttu-id="2d128-122">**Значение**</span><span class="sxs-lookup"><span data-stu-id="2d128-122">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2d128-123">Служба федерации ФДКН</span><span class="sxs-lookup"><span data-stu-id="2d128-123">federation service FDQN</span></span>  <br/> |<span data-ttu-id="2d128-124">A</span><span class="sxs-lookup"><span data-stu-id="2d128-124">A</span></span>  <br/> |<span data-ttu-id="2d128-125">3600</span><span class="sxs-lookup"><span data-stu-id="2d128-125">3600</span></span>  <br/> |<span data-ttu-id="2d128-126">общедоступный IP-адрес балансировщика нагрузки с выходом в Интернет Azure (отображается с помощью команды **Write-Host** в предыдущем разделе)</span><span class="sxs-lookup"><span data-stu-id="2d128-126">public IP address of the Azure Internet-facing load balancer (displayed by the **Write-Host** command in the previous section)</span></span> <br/> |
   
<span data-ttu-id="2d128-127">Вот пример:</span><span class="sxs-lookup"><span data-stu-id="2d128-127">Here is an example:</span></span>
  
|<span data-ttu-id="2d128-128">**Имя**</span><span class="sxs-lookup"><span data-stu-id="2d128-128">**Name**</span></span>|<span data-ttu-id="2d128-129">**Type** (Тип)</span><span class="sxs-lookup"><span data-stu-id="2d128-129">**Type**</span></span>|<span data-ttu-id="2d128-130">**TTL** (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="2d128-130">**TTL**</span></span>|<span data-ttu-id="2d128-131">**Значение**</span><span class="sxs-lookup"><span data-stu-id="2d128-131">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2d128-132">fs.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d128-132">fs.contoso.com</span></span>  <br/> |<span data-ttu-id="2d128-133">A</span><span class="sxs-lookup"><span data-stu-id="2d128-133">A</span></span>  <br/> |<span data-ttu-id="2d128-134">3600</span><span class="sxs-lookup"><span data-stu-id="2d128-134">3600</span></span>  <br/> |<span data-ttu-id="2d128-135">131.107.249.117</span><span class="sxs-lookup"><span data-stu-id="2d128-135">131.107.249.117</span></span>  <br/> |
   
<span data-ttu-id="2d128-136">Затем добавьте запись DNS-адреса в личное пространство имен DNS организации, которая разрешает полное доменное имя службы Федерации к частному IP-адресу, назначенному внутреннему подсистеме балансировки нагрузки для серверов AD FS (таблица I, элемент 4, столбец "значение").</span><span class="sxs-lookup"><span data-stu-id="2d128-136">Next, add a DNS address record to your organization's private DNS namespace that resolves your federation service FQDN to the private IP address assigned to the internal load balancer for the AD FS servers (Table I, item 4, Value column).</span></span>
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a><span data-ttu-id="2d128-137">Создание виртуальных машин прокси-сервера веб-приложений в Azure</span><span class="sxs-lookup"><span data-stu-id="2d128-137">Create the web application proxy server virtual machines in Azure</span></span>

<span data-ttu-id="2d128-138">Используйте следующий блок команд Azure PowerShell, чтобы создать виртуальные машины для двух прокси-серверов веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="2d128-138">Use the following block of Azure PowerShell commands to create the virtual machines for the two web application proxy servers.</span></span> 
  
<span data-ttu-id="2d128-139">Обратите внимание на то, что следующие наборы команд Azure PowerShell используют значения из следующих таблиц:</span><span class="sxs-lookup"><span data-stu-id="2d128-139">Note that the following Azure PowerShell command sets use values from the following tables:</span></span>
  
- <span data-ttu-id="2d128-140">таблица M (для виртуальных машин);</span><span class="sxs-lookup"><span data-stu-id="2d128-140">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="2d128-141">таблица R (для групп ресурсов);</span><span class="sxs-lookup"><span data-stu-id="2d128-141">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="2d128-142">таблица V (для параметров виртуальной сети);</span><span class="sxs-lookup"><span data-stu-id="2d128-142">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="2d128-143">таблица S (для подсетей);</span><span class="sxs-lookup"><span data-stu-id="2d128-143">Table S, for your subnets</span></span>
    
- <span data-ttu-id="2d128-144">таблица I (для статических IP-адресов);</span><span class="sxs-lookup"><span data-stu-id="2d128-144">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="2d128-145">таблица A (для групп доступности).</span><span class="sxs-lookup"><span data-stu-id="2d128-145">Table A, for your availability sets</span></span>
    
<span data-ttu-id="2d128-146">Помните, что вы определили таблицу M на [этапе 2: Configure Domain Controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I и на [этапе 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="2d128-146">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
<span data-ttu-id="2d128-147">Задав правильные значения, выполните полученный блок в командной строке Azure PowerShell или в интегрированной среде сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d128-147">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
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
> <span data-ttu-id="2d128-148">Эти виртуальные машины предназначены для работы в интрасети, поэтому им не назначается общедоступный IP-адрес или метка доменного имени DNS и они не подключаются к Интернету.</span><span class="sxs-lookup"><span data-stu-id="2d128-148">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet.</span></span> <span data-ttu-id="2d128-149">Однако это также означает, что к ним невозможно подключиться с помощью портала Azure.</span><span class="sxs-lookup"><span data-stu-id="2d128-149">However, this also means that you cannot connect to them from the Azure portal.</span></span> <span data-ttu-id="2d128-150">Команда **Подключиться** недоступна при просмотре свойств виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="2d128-150">The **Connect** option is unavailable when you view the properties of the virtual machine.</span></span> <span data-ttu-id="2d128-151">Используйте подключение к удаленному рабочему столу или другой инструмент удаленного рабочего стола, чтобы подключиться к виртуальной машине, используя свой частный IP-адрес или DNS-имя интрасети, а также учетные данные локальной учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="2d128-151">Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="2d128-152">Здесь показана конфигурация, полученная в результате успешного выполнения этого этапа (с заполнителями вместо имен компьютеров).</span><span class="sxs-lookup"><span data-stu-id="2d128-152">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="2d128-153">**Этап 4: подсистема балансировки нагрузки на основе Интернета и прокси-серверы веб-приложений для инфраструктуры федеративной проверки подлинности с высоким уровнем доступности в Azure**</span><span class="sxs-lookup"><span data-stu-id="2d128-153">**Phase 4: The Internet-facing load balancer and web application proxy servers for your high availability federated authentication infrastructure in Azure**</span></span>

![Этап 4 из инфраструктуры федеративной проверки подлинности Microsoft 365 с высоким уровнем доступности в Azure с помощью прокси-серверов веб-приложений](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a><span data-ttu-id="2d128-155">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="2d128-155">Next step</span></span>

<span data-ttu-id="2d128-156">Используйте [этап 5: Настройка федеративной проверки подлинности для Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) , чтобы продолжить настройку этой рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="2d128-156">Use [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2d128-157">См. также</span><span class="sxs-lookup"><span data-stu-id="2d128-157">See Also</span></span>

[<span data-ttu-id="2d128-158">Развертывание федеративной проверки подлинности для обеспечения высокой доступности Microsoft 365 в Azure</span><span class="sxs-lookup"><span data-stu-id="2d128-158">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="2d128-159">Федеративная идентификация для среды разработки и тестирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d128-159">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="2d128-160">Центр архитектуры и решений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d128-160">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

