---
title: Этап 2. Настройка контроллеров домена для федерационной проверки подлинности для высокой доступности
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
ms.assetid: 6b0eff4c-2c5e-4581-8393-a36f7b36a72f
description: Сводка. Настройте контроллеры домена и сервер синхронизации каталогов для федерарной проверки подлинности с высоким уровнем доступности для Microsoft 365 в Microsoft Azure.
ms.openlocfilehash: 1c3fd686ee553a57d66dcfd51a6045167a12de8a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693345"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a><span data-ttu-id="2e3dc-103">Этап 2. Федеративная проверка подлинности для обеспечения высокой доступности: настройка контроллеров домена</span><span class="sxs-lookup"><span data-stu-id="2e3dc-103">High availability federated authentication Phase 2: Configure domain controllers</span></span>

<span data-ttu-id="2e3dc-104">На этом этапе развертывания высокой доступности для федерационной проверки подлинности Microsoft 365 в службах инфраструктуры Azure настраиваются два контроллера домена и сервер синхронизации каталогов в виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you configure two domain controllers and the directory synchronization server in the Azure virtual network.</span></span> <span data-ttu-id="2e3dc-105">После этого проверку подлинности клиентов можно выполнять в виртуальной сети Azure, не отправляя трафик проверки подлинности через подключение VPN типа "сеть-сеть" к локальной сети.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-105">Client web requests for authentication can then be authenticated in the Azure virtual network, rather than sending that authentication traffic across the site-to-site VPN connection to your on-premises network.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2e3dc-106">Службы федерации Active Directory (AD FS) не могут использовать Azure Active Directory (Azure AD) вместо контроллеров домена доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="2e3dc-106">Active Directory Federation Services (AD FS) cannot use Azure Active Directory (Azure AD) as a substitute for Active Directory Domain Services (AD DS) domain controllers.</span></span> 
  
<span data-ttu-id="2e3dc-107">Этот этап необходимо завершить перед переходом к [этапу 3. Настройка серверов AD FS.](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)</span><span class="sxs-lookup"><span data-stu-id="2e3dc-107">You must complete this phase before moving on to [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="2e3dc-108">См. все этапы развертывания федерационной проверки подлинности с высоким уровнем доступности для [Microsoft 365](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) в Azure.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-108">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a><span data-ttu-id="2e3dc-109">Создание виртуальных машин контроллеров домена в Azure</span><span class="sxs-lookup"><span data-stu-id="2e3dc-109">Create the domain controller virtual machines in Azure</span></span>

<span data-ttu-id="2e3dc-110">Для начала необходимо заполнить столбец **Имя виртуальной машины** в таблице M и при необходимости изменить размеры виртуальных машин в столбце **Минимальный размер**.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-110">First, you need to fill out the **Virtual machine name** column of Table M and modify virtual machine sizes as needed in the **Minimum size** column.</span></span>
  
|<span data-ttu-id="2e3dc-111">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2e3dc-111">**Item**</span></span>|<span data-ttu-id="2e3dc-112">**Имя виртуальной машины**</span><span class="sxs-lookup"><span data-stu-id="2e3dc-112">**Virtual machine name**</span></span>|<span data-ttu-id="2e3dc-113">**Образ коллекции**</span><span class="sxs-lookup"><span data-stu-id="2e3dc-113">**Gallery image**</span></span>|<span data-ttu-id="2e3dc-114">**Тип хранилища**</span><span class="sxs-lookup"><span data-stu-id="2e3dc-114">**Storage type**</span></span>|<span data-ttu-id="2e3dc-115">**Минимальный размер**</span><span class="sxs-lookup"><span data-stu-id="2e3dc-115">**Minimum size**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2e3dc-116">1.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-116">1.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png) <span data-ttu-id="2e3dc-118"> (первый контроллер домена, например DC1)</span><span class="sxs-lookup"><span data-stu-id="2e3dc-118">(first domain controller, example DC1)</span></span>  <br/> |<span data-ttu-id="2e3dc-119">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="2e3dc-119">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="2e3dc-120">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="2e3dc-120">Standard_LRS</span></span>  <br/> |<span data-ttu-id="2e3dc-121">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="2e3dc-121">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="2e3dc-122">2.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-122">2.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png) <span data-ttu-id="2e3dc-124"> (второй контроллер домена, например DC2)</span><span class="sxs-lookup"><span data-stu-id="2e3dc-124">(second domain controller, example DC2)</span></span>  <br/> |<span data-ttu-id="2e3dc-125">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="2e3dc-125">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="2e3dc-126">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="2e3dc-126">Standard_LRS</span></span>  <br/> |<span data-ttu-id="2e3dc-127">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="2e3dc-127">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="2e3dc-128">3.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-128">3.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png) <span data-ttu-id="2e3dc-130">(сервер синхронизации каталогов, например DS1)</span><span class="sxs-lookup"><span data-stu-id="2e3dc-130">(directory synchronization server, example DS1)</span></span>  <br/> |<span data-ttu-id="2e3dc-131">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="2e3dc-131">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="2e3dc-132">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="2e3dc-132">Standard_LRS</span></span>  <br/> |<span data-ttu-id="2e3dc-133">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="2e3dc-133">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="2e3dc-134">4.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-134">4.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png) <span data-ttu-id="2e3dc-136">(первый сервер AD FS, например ADFS1)</span><span class="sxs-lookup"><span data-stu-id="2e3dc-136">(first AD FS server, example ADFS1)</span></span>  <br/> |<span data-ttu-id="2e3dc-137">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="2e3dc-137">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="2e3dc-138">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="2e3dc-138">Standard_LRS</span></span>  <br/> |<span data-ttu-id="2e3dc-139">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="2e3dc-139">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="2e3dc-140">5.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-140">5.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png) <span data-ttu-id="2e3dc-142">(второй сервер AD FS, например ADFS2)</span><span class="sxs-lookup"><span data-stu-id="2e3dc-142">(second AD FS server, example ADFS2)</span></span>  <br/> |<span data-ttu-id="2e3dc-143">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="2e3dc-143">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="2e3dc-144">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="2e3dc-144">Standard_LRS</span></span>  <br/> |<span data-ttu-id="2e3dc-145">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="2e3dc-145">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="2e3dc-146">6.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-146">6.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png) <span data-ttu-id="2e3dc-148">(первый прокси-сервер веб-приложения, например WEB1)</span><span class="sxs-lookup"><span data-stu-id="2e3dc-148">(first web application proxy server, example WEB1)</span></span>  <br/> |<span data-ttu-id="2e3dc-149">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="2e3dc-149">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="2e3dc-150">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="2e3dc-150">Standard_LRS</span></span>  <br/> |<span data-ttu-id="2e3dc-151">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="2e3dc-151">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="2e3dc-152">7.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-152">7.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png) <span data-ttu-id="2e3dc-154">(второй прокси-сервер веб-приложения, например WEB2)</span><span class="sxs-lookup"><span data-stu-id="2e3dc-154">(second web application proxy server, example WEB2)</span></span>  <br/> |<span data-ttu-id="2e3dc-155">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="2e3dc-155">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="2e3dc-156">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="2e3dc-156">Standard_LRS</span></span>  <br/> |<span data-ttu-id="2e3dc-157">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="2e3dc-157">Standard_D2</span></span>  <br/> |
   
 <span data-ttu-id="2e3dc-158">**Таблица M. Виртуальные машины для федерационной проверки подлинности с высоким уровнем доступности для Microsoft 365 в Azure**</span><span class="sxs-lookup"><span data-stu-id="2e3dc-158">**Table M - Virtual machines for the high availability federated authentication for Microsoft 365 in Azure**</span></span>
  
<span data-ttu-id="2e3dc-159">Полный список размеров виртуальных машин представлен в [этой статье](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-sizes).</span><span class="sxs-lookup"><span data-stu-id="2e3dc-159">For the complete list of virtual machine sizes, see [Sizes for virtual machines](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-sizes).</span></span>
  
<span data-ttu-id="2e3dc-160">Приведенный ниже блок команд Azure PowerShell создает виртуальные машины для двух контроллеров домена.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-160">The following Azure PowerShell command block creates the virtual machines for the two domain controllers.</span></span> <span data-ttu-id="2e3dc-161">Укажите значения переменных, удалив \< and > символы.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-161">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="2e3dc-162">Обратите внимание, что в этом блоке команд Azure PowerShell используются значения из следующих таблиц:</span><span class="sxs-lookup"><span data-stu-id="2e3dc-162">Note that this Azure PowerShell command block uses values from the following tables:</span></span>
  
- <span data-ttu-id="2e3dc-163">таблица M (для виртуальных машин);</span><span class="sxs-lookup"><span data-stu-id="2e3dc-163">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="2e3dc-164">таблица R (для групп ресурсов);</span><span class="sxs-lookup"><span data-stu-id="2e3dc-164">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="2e3dc-165">таблица V (для параметров виртуальной сети);</span><span class="sxs-lookup"><span data-stu-id="2e3dc-165">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="2e3dc-166">таблица S (для подсетей);</span><span class="sxs-lookup"><span data-stu-id="2e3dc-166">Table S, for your subnets</span></span>
    
- <span data-ttu-id="2e3dc-167">таблица I (для статических IP-адресов);</span><span class="sxs-lookup"><span data-stu-id="2e3dc-167">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="2e3dc-168">таблица A (для групп доступности).</span><span class="sxs-lookup"><span data-stu-id="2e3dc-168">Table A, for your availability sets</span></span>
    
<span data-ttu-id="2e3dc-169">Помните, что вы определили таблицы R, V, S, I и A на этапе [1. Настройка Azure.](high-availability-federated-authentication-phase-1-configure-azure.md)</span><span class="sxs-lookup"><span data-stu-id="2e3dc-169">Recall that you defined Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2e3dc-170">Для указанных ниже последовательностей команд используется последняя версия Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-170">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="2e3dc-171">См. ["Начало работы с Azure PowerShell".](https://docs.microsoft.com/powershell/azure/get-started-azureps)</span><span class="sxs-lookup"><span data-stu-id="2e3dc-171">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="2e3dc-172">Указав правильные значения, выполните полученный блок в командной строке Azure PowerShell или в интегрированной среде сценариев PowerShell (ISE) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-172">When you have supplied all the correct values, run the resulting block at the Azure PowerShell prompt or in the PowerShell Integrated Script Environment (ISE) on your local computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="2e3dc-173">Чтобы создать готовые к запуску блоки команд PowerShell на основе пользовательских параметров, используйте эту книгу конфигурации [Microsoft Excel.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)</span><span class="sxs-lookup"><span data-stu-id="2e3dc-173">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table S - Item 1 - Value column>"
$avName="<Table A - Item 1 - Availability set name column>"
$rgNameTier="<Table R - Item 1 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName 

# Create the first domain controller
$vmName="<Table M - Item 1 - Virtual machine name column>"
$vmSize="<Table M - Item 1 - Minimum size column>"
$staticIP="<Table I - Item 1 - Value column>"
$diskStorageType="<Table M - Item 1 - Storage type column>"
$diskSize=<size of the extra disk for Active Directory Domain Services (AD DS) data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second domain controller
$vmName="<Table M - Item 2 - Virtual machine name column>"
$vmSize="<Table M - Item 2 - Minimum size column>"
$staticIP="<Table I - Item 2 - Value column>"
$diskStorageType="<Table M - Item 2 - Storage type column>"
$diskSize=<size of the extra disk for AD DS data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the directory synchronization server
$vmName="<Table M - Item 3 - Virtual machine name column>"
$vmSize="<Table M - Item 3 - Minimum size column>"
$staticIP="<Table I - Item 3 - Value column>"
$diskStorageType="<Table M - Item 3 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the directory synchronization server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="2e3dc-p105">Эти виртуальные машины предназначены для работы в интрасети, поэтому им не назначается общедоступный IP-адрес или метка доменного имени DNS и они не подключаются к Интернету. Однако это также означает, что к ним невозможно подключиться с помощью портала Azure. Команда **Подключиться** недоступна при просмотре свойств виртуальной машины. Используйте программу "Подключение к удаленному рабочему столу" или другое аналогичное средство, чтобы подключиться к виртуальной машине по ее частному IP-адресу или DNS-имени интрасети.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-p105">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet. However, this also means that you cannot connect to them from the Azure portal. The **Connect** option is unavailable when you view the properties of the virtual machine. Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
## <a name="configure-the-first-domain-controller"></a><span data-ttu-id="2e3dc-178">Настройка первого контроллера домена</span><span class="sxs-lookup"><span data-stu-id="2e3dc-178">Configure the first domain controller</span></span>

<span data-ttu-id="2e3dc-p106">Используя любой клиент удаленного рабочего стола, создайте подключение к удаленному рабочему столу для виртуальной машины первого контроллера домена. Используйте DNS-имя интрасети или имя компьютера, а также учетные данные локального администратора.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-p106">Use the remote desktop client of your choice and create a remote desktop connection to the first domain controller virtual machine. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="2e3dc-181">Затем добавьте дополнительный диск с данными на первый контроллер домена с помощью этой команды из командной Windows PowerShell на первой виртуальной машине **контроллера домена:**</span><span class="sxs-lookup"><span data-stu-id="2e3dc-181">Next, add the extra data disk to the first domain controller with this command from a Windows PowerShell command prompt **on the first domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="2e3dc-182">Затем протестируйте соединение первого контроллера домена с расположениями в сети организации с помощью команды **ping** для имен и IP-адресов ресурсов в этой сети.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-182">Next, test the first domain controller's connectivity to locations on your organization network by using the **ping** command to ping names and IP addresses of resources on your organization network.</span></span>
  
<span data-ttu-id="2e3dc-p107">Это позволяет убедиться, что разрешение DNS-имен работает надлежащим образом (виртуальная машина правильно настроена с указанием локальных DNS-серверов), а в распределенную виртуальную сеть и из нее можно отправлять пакеты. В случае сбоя базового теста обратитесь в ИТ-отдел для устранения проблем с разрешением DNS-имен и доставкой пакетов.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-p107">This procedure ensures that DNS name resolution is working correctly (that the virtual machine is correctly configured with on-premises DNS servers) and that packets can be sent to and from the cross-premises virtual network. If this basic test fails, contact your IT department to troubleshoot the DNS name resolution and packet delivery issues.</span></span>
  
<span data-ttu-id="2e3dc-185">Затем в командной строке Windows PowerShell на первом контроллере домена выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="2e3dc-185">Next, from the Windows PowerShell command prompt on the first domain controller, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

<span data-ttu-id="2e3dc-p108">Вам будет предложено указать учетные данные администратора домена. Компьютер перезагрузится.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-p108">You will be prompted to supply the credentials of a domain administrator account. The computer will restart.</span></span>
  
## <a name="configure-the-second-domain-controller"></a><span data-ttu-id="2e3dc-188">Настройка второго контроллера домена</span><span class="sxs-lookup"><span data-stu-id="2e3dc-188">Configure the second domain controller</span></span>

<span data-ttu-id="2e3dc-p109">Используя любой клиент удаленного рабочего стола, создайте подключение к удаленному рабочему столу на виртуальной машине второго контроллера домена. Используйте DNS-имя интрасети или имя компьютера, а также учетные данные локального администратора.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-p109">Use the remote desktop client of your choice and create a remote desktop connection to the second domain controller virtual machine. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="2e3dc-191">Затем необходимо добавить дополнительный диск с данными на второй контроллер домена с помощью этой команды из командной Windows PowerShell на второй виртуальной машине контроллера **домена:**</span><span class="sxs-lookup"><span data-stu-id="2e3dc-191">Next, you need to add the extra data disk to the second domain controller with this command from a Windows PowerShell command prompt **on the second domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="2e3dc-192">Затем выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="2e3dc-192">Next, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

<span data-ttu-id="2e3dc-p110">Вам будет предложено указать учетные данные администратора домена. Компьютер перезагрузится.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-p110">You will be prompted to supply the credentials of a domain administrator account. The computer will restart.</span></span>
  
<span data-ttu-id="2e3dc-195">Теперь необходимо обновить DNS-серверы для виртуальной сети, чтобы служба Azure назначила виртуальным машинам IP-адреса двух новых контроллеров домена в качестве DNS-серверов.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-195">Next, you need to update the DNS servers for your virtual network so that Azure assigns virtual machines the IP addresses of the two new domain controllers to use as their DNS servers.</span></span> <span data-ttu-id="2e3dc-196">Заполните переменные и запустите эти команды в командной Windows PowerShell на локальном компьютере:</span><span class="sxs-lookup"><span data-stu-id="2e3dc-196">Fill in the variables and then run these commands from a Windows PowerShell command prompt on your local computer:</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$adrgName="<Table R - Item 1 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$onpremDNSIP1="<Table D - Item 1 - DNS server IP address column>"
$onpremDNSIP2="<Table D - Item 2 - DNS server IP address column>"
$staticIP1="<Table I - Item 1 - Value column>"
$staticIP2="<Table I - Item 2 - Value column>"
$firstDCName="<Table M - Item 1 - Virtual machine name column>"
$secondDCName="<Table M - Item 2 - Virtual machine name column>"

$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$vnet.DhcpOptions.DnsServers.Add($staticIP1)
$vnet.DhcpOptions.DnsServers.Add($staticIP2) 
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP1)
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP2) 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $adrgName -Name $firstDCName
Restart-AzVM -ResourceGroupName $adrgName -Name $secondDCName
```

<span data-ttu-id="2e3dc-p112">Обратите внимание, что мы перезагружаем два контроллера домена, чтобы они не были настроены с указанием локальных DNS-серверов. Так как они оба сами являются DNS-серверами, эти контроллеры были автоматически настроены с указанием локальных DNS-серверов пересылки при повышении до контроллеров домена.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-p112">Note that we restart the two domain controllers so that they are not configured with the on-premises DNS servers as DNS servers. Because they are both DNS servers themselves, they were automatically configured with the on-premises DNS servers as DNS forwarders when they were promoted to domain controllers.</span></span>
  
<span data-ttu-id="2e3dc-p113">После этого необходимо создать сайт репликации Active Directory, чтобы убедиться, что серверы в виртуальной сети Azure используют локальные контроллеры домена. Подключитесь к любому контроллеру домена, используя учетную запись администратора домена, и выполните следующие команды в командной строке Windows PowerShell с правами администратора:</span><span class="sxs-lookup"><span data-stu-id="2e3dc-p113">Next, we need to create an Active Directory replication site to ensure that servers in the Azure virtual network use the local domain controllers. Connect to either domain controller with a domain administrator account and run the following commands from an administrator-level Windows PowerShell prompt:</span></span>
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a><span data-ttu-id="2e3dc-201">Настройка сервера синхронизации каталогов</span><span class="sxs-lookup"><span data-stu-id="2e3dc-201">Configure the directory synchronization server</span></span>

<span data-ttu-id="2e3dc-202">Используйте клиент удаленного рабочего стола по вашему выбору и создайте подключение к удаленному рабочему столу виртуальной машины сервера синхронизации каталогов.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-202">Use the remote desktop client of your choice and create a remote desktop connection to the directory synchronization server virtual machine.</span></span> <span data-ttu-id="2e3dc-203">Используйте DNS-имя интрасети или имя компьютера, а также учетные данные локального администратора.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-203">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="2e3dc-204">Затем присоединить его к соответствующему домену AD DS, выдав следующие команды в Windows PowerShell командной Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-204">Next, join it to the appropriate AD DS domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="2e3dc-205">Здесь показана конфигурация, полученная в результате успешного выполнения этого этапа (с заполнителями вместо имен компьютеров).</span><span class="sxs-lookup"><span data-stu-id="2e3dc-205">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="2e3dc-206">**Этап 2. Контроллеры домена и сервер синхронизации каталогов для инфраструктуры федерационной проверки подлинности с высоким уровнем доступности в Azure**</span><span class="sxs-lookup"><span data-stu-id="2e3dc-206">**Phase 2: The domain controllers and directory synchronization server for your high availability federated authentication infrastructure in Azure**</span></span>

![Этап 2 инфраструктуры федераированной проверки подлинности Microsoft 365 с высоким уровнем доступности в Azure с контроллерами домена](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a><span data-ttu-id="2e3dc-208">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="2e3dc-208">Next step</span></span>

<span data-ttu-id="2e3dc-209">Этап [3. Настройка серверов AD FS](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) для продолжения настройки этой рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="2e3dc-209">Use [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2e3dc-210">См. также</span><span class="sxs-lookup"><span data-stu-id="2e3dc-210">See Also</span></span>

[<span data-ttu-id="2e3dc-211">Развертывание федеративной проверки подлинности для обеспечения высокой доступности Microsoft 365 в Azure</span><span class="sxs-lookup"><span data-stu-id="2e3dc-211">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="2e3dc-212">Федератное удостоверение для среды тестирования и тестирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e3dc-212">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="2e3dc-213">Центр архитектуры и решений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e3dc-213">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)


