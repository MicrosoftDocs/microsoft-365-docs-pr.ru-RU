---
title: Базовая конфигурация "имитация предприятия" для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Это руководство по лаборатории тестирования поможет вам создать имитацию предприятия для Microsoft 365 корпоративный.
ms.openlocfilehash: d674fcf4f1feeabf8c7f2d5aa1b23fc89435e6ca
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871023"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="44f75-103">Базовая конфигурация "имитация предприятия"</span><span class="sxs-lookup"><span data-stu-id="44f75-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="44f75-104">В этой статье вы найдете пошаговые инструкции по созданию упрощенной среды для Microsoft 365 корпоративный, которая включает:</span><span class="sxs-lookup"><span data-stu-id="44f75-104">This article provides you with step-by-step instructions to create a simplified environment for Microsoft 365 Enterprise that includes:</span></span>

- <span data-ttu-id="44f75-105">пробные или постоянные подписки на Office 365 E5 и EMS E5;</span><span class="sxs-lookup"><span data-stu-id="44f75-105">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="44f75-106">упрощенную интрасеть организации, подключенную к Интернету и состоящую из трех виртуальных машин в виртуальной сети Azure (DC1, APP1 и CLIENT1).</span><span class="sxs-lookup"><span data-stu-id="44f75-106">A simplified organization intranet connected to the Internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![Базовая конфигурация "имитация предприятия"](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="44f75-108">Вы можете использовать полученную среду для тестирования функций [Microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise) с дополнительными [руководствами по лаборатории тестирования](m365-enterprise-test-lab-guides.md) или без них.</span><span class="sxs-lookup"><span data-stu-id="44f75-108">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="44f75-110">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="44f75-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="44f75-111">Этап 1. Создание имитированной интрасети</span><span class="sxs-lookup"><span data-stu-id="44f75-111">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="44f75-112">На этом этапе вы создаете имитацию интрасети в службах инфраструктуры Azure, которая включает контроллер домена Windows Server Active Directory, сервер приложений и клиентский компьютер.</span><span class="sxs-lookup"><span data-stu-id="44f75-112">In this phase, you build a simulated intranet in Azure infrastructure services that includes a Windows Server Active Directory domain controller, an application server, and a client computer.</span></span> 

<span data-ttu-id="44f75-113">Вы будете использовать эти компьютеры в дополнительных [Руководствах по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md) для настройки и демонстрации гибридных удостоверений и других возможностей.</span><span class="sxs-lookup"><span data-stu-id="44f75-113">You'll use these computers in additional [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="44f75-114">Способ 1. Создание имитированной интрасети с помощью шаблона Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="44f75-114">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="44f75-p101">Этот способ предполагает использование шаблона Azure Resource Manager (ARM) для создания имитации интрасети. Шаблоны ARM содержат все необходимые инструкции для создания сетевой инфраструктуры, виртуальных машин и их конфигурации.</span><span class="sxs-lookup"><span data-stu-id="44f75-p101">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet. ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="44f75-117">Перед развертыванием шаблона ознакомьтесь со [страницей сведений шаблона (README)](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) и приготовьте приведенные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="44f75-117">Prior to deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="44f75-p102">DNS-имя общедоступного домена вашей тестовой среды (testlab.\<ваш общедоступный домен>). Вам понадобится ввести это имя в поле **Доменное имя** на странице **Настраиваемое развертывание**.</span><span class="sxs-lookup"><span data-stu-id="44f75-p102">The public DNS domain name of your test environment (testlab.\<your public domain>). You’ll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span></span>
- <span data-ttu-id="44f75-p103">Префикс метки DNS для URL-адресов общедоступных IP-адресов виртуальных машин. Вам понадобится ввести эту метку в поле **Префикс метки DNS** на странице **Настраиваемое развертывание**.</span><span class="sxs-lookup"><span data-stu-id="44f75-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You’ll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="44f75-122">После ознакомления с инструкциями нажмите **Развертывание в Azure** на [странице сведений шаблона (README)](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems), чтобы приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="44f75-122">After reading through the instructions, click **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="44f75-123">Для имитации интрасети, созданной на основе шаблона ARM, требуется платная подписка Azure.</span><span class="sxs-lookup"><span data-stu-id="44f75-123">The simulated intranet built by the ARM template requires a paid Azure subscription.</span></span>
>

<span data-ttu-id="44f75-124">Ниже показана итоговая конфигурация после завершения работы с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="44f75-124">Here is your configuration after the template is complete.</span></span>

![Имитированная интрасеть в службах инфраструктуры Azure](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="44f75-126">Способ 2. Создание имитированной интрасети с помощью Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="44f75-126">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="44f75-127">Этот способ предполагает использование Windows PowerShell и модуля Azure PowerShell для создания сетевой инфраструктуры, виртуальных машин и их конфигурации.</span><span class="sxs-lookup"><span data-stu-id="44f75-127">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="44f75-p104">Используйте этот способ, если вы хотите получить возможность создания элементов инфраструктуры Azure шаг за шагом с помощью PowerShell. Затем можно настроить командные блоки PowerShell для самостоятельного развертывания других виртуальных машин в Azure.</span><span class="sxs-lookup"><span data-stu-id="44f75-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="44f75-130">Этап 1. Создание DC1</span><span class="sxs-lookup"><span data-stu-id="44f75-130">Step 1: Create DC1</span></span>

<span data-ttu-id="44f75-131">На этом этапе создается виртуальная сеть Azure и добавляется виртуальная машина DC1, которая является контроллером домена Windows Server Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="44f75-131">In this step, we create an Azure virtual network and add DC1, a virtual machine that is a domain controller for a Windows Server Active Directory (AD) domain.</span></span>

<span data-ttu-id="44f75-132">Сначала запустите командную строку Windows PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="44f75-132">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="44f75-p105">Для приведенных ниже последовательностей команд используется последняя версия Azure PowerShell. См. статью [Общие сведения об Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="44f75-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="44f75-135">Войдите в свою учетную запись Azure с помощью указанной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="44f75-135">Sign in to your Azure account with the following command.</span></span>
  
```
Login-AzureRMAccount
```

<span data-ttu-id="44f75-136">Получите имя подписки с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="44f75-136">Get your subscription name using the following command.</span></span>
  
```
Get-AzureRMSubscription | Sort Name | Select Name
```

<span data-ttu-id="44f75-p106">Укажите свою подписку Azure. Замените текст в кавычках, в том числе символы < и >, правильным именем.</span><span class="sxs-lookup"><span data-stu-id="44f75-p106">Set your Azure subscription. Replace everything within the quotes, including the < and > characters, with the correct name.</span></span>
  
```
$subscr="<subscription name>"
Get-AzureRmSubscription -SubscriptionName $subscr | Select-AzureRmSubscription
```

<span data-ttu-id="44f75-p107">Затем создайте группу ресурсов для лаборатории тестирования "имитация предприятия". Чтобы определить уникальное имя группы ресурсов, используйте указанную ниже команду для вывода списка имеющихся групп ресурсов.</span><span class="sxs-lookup"><span data-stu-id="44f75-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```
Get-AzureRMResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="44f75-p108">Создайте группу ресурсов с помощью приведенных ниже команд. Замените все символы в кавычках (в том числе символы < и >) правильными именами.</span><span class="sxs-lookup"><span data-stu-id="44f75-p108">Create your new resource group with these commands. Replace everything within the quotes, including the < and > characters, with the correct names.</span></span>
  
```
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzureRMResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="44f75-p109">После этого создайте виртуальную сеть TestLab, в которой будет размещаться подсеть Corpnet моделируемой среды предприятия, и защитите ее с помощью группы сетевой безопасности. Укажите имя своей группы ресурсов и выполните эти команды в командной строке PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="44f75-p109">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group. Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```
$rgName="<name of your new resource group>"
$locName=(Get-AzureRmResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzureRMVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzureRMVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzureRMNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzureRMNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzureRMVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzureRMNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzureRMVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
```

<span data-ttu-id="44f75-p110">Затем создайте виртуальную машину DC1 и настройте ее как контроллер домена для домена Windows Server AD **testlab.**\<ваш публичный домен> и DNS-сервера для виртуальных машин виртуальной сети TestLab. Например, если имя вашего публичного домена — **<span>contoso</span>.com**, виртуальная машина DC1 будет контроллером домена **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="44f75-p110">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain> Windows Server AD domain and a DNS server for the virtual machines of the TestLab virtual network. For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="44f75-147">Чтобы создать виртуальную машину Azure для DC1, укажите имя группы ресурсов и выполните приведенные ниже команды в командной строке PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="44f75-147">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```
$rgName="<resource group name>"
$locName=(Get-AzureRmResourceGroup -Name $rgName).Location
$vnet=Get-AzureRMVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzureRMPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzureRMNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzureRMVMConfig -VMName DC1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzureRMVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzureRMVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzureRMVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzureRmVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
$diskConfig=New-AzureRmDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzureRmDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzureRmVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzureRMVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="44f75-p111">Вам будет предложено ввести имя пользователя и пароль учетной записи локального администратора на DC1. Задайте надежный пароль и запишите его вместе с именем пользователя в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="44f75-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="44f75-150">После этого подключитесь к виртуальной машине DC1.</span><span class="sxs-lookup"><span data-stu-id="44f75-150">Next, connect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="44f75-151">На [портале Azure](https://portal.azure.com) выберите **Группы ресурсов >** [имя новой группы ресурсов] **> DC1 > Подключить**.</span><span class="sxs-lookup"><span data-stu-id="44f75-151">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [the name of your new resource group] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="44f75-p112">В открытой области выберите элемент **Скачать RDP-файл**. Откройте скачанный файл DC1.rdp и нажмите **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="44f75-p112">In the open pane, click **Download RDP file**. Open the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="44f75-154">Укажите имя учетной записи локального администратора DC1:</span><span class="sxs-lookup"><span data-stu-id="44f75-154">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="44f75-155">Для Windows 7:</span><span class="sxs-lookup"><span data-stu-id="44f75-155">For Windows 7:</span></span>
    
     <span data-ttu-id="44f75-p113">В диалоговом окне **Безопасность Windows** выберите элемент **Использовать другую учетную запись**. В поле **Имя пользователя** введите **DC1\\**[имя локальной учетной записи администратора].</span><span class="sxs-lookup"><span data-stu-id="44f75-p113">In the **Windows Security** dialog box, click **Use another account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
   - <span data-ttu-id="44f75-158">Для Windows 8 и Windows 10:</span><span class="sxs-lookup"><span data-stu-id="44f75-158">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="44f75-p114">В диалоговом окне **Безопасность Windows** нажмите **Больше вариантов**, а затем — **Использовать другую учетную запись**. В поле **Имя пользователя** введите **DC1\\**[имя учетной записи локального администратора].</span><span class="sxs-lookup"><span data-stu-id="44f75-p114">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="44f75-161">В поле **Пароль** укажите пароль к учетной записи локального администратора, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="44f75-161">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="44f75-162">Когда появится соответствующий запрос, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="44f75-162">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="44f75-163">После этого добавьте еще один диск с данными в качестве нового тома с буквой диска "F:", используя приведенные ниже команды в командной строке Windows PowerShell на уровне администратора в DC1.</span><span class="sxs-lookup"><span data-stu-id="44f75-163">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="44f75-p115">Затем настройте DC1 в качестве контроллера домена и DNS-сервера для домена **testlab.**\<ваш публичный домен>. Укажите имя своего публичного домена, удалите символы \< и >, а затем выполните эти команды в командной строке Windows PowerShell от имени администратора на DC1.</span><span class="sxs-lookup"><span data-stu-id="44f75-p115">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<your public domain> domain. Specify your public domain name, remove the \< and > characters, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="44f75-p116">Потребуется указать пароль администратора для безопасного режима. Храните этот пароль в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="44f75-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="44f75-168">Обратите внимание, что на выполнение этих команд может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="44f75-168">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="44f75-169">После перезапуска виртуальной машины DC1 снова подключитесь к ней.</span><span class="sxs-lookup"><span data-stu-id="44f75-169">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="44f75-170">На [портале Azure](https://portal.azure.com) выберите элементы **Группы ресурсов >** [имя вашей группы ресурсов] \*\* DC1 > Подключить\*\*.</span><span class="sxs-lookup"><span data-stu-id="44f75-170">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [your resource group name] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="44f75-171">Запустите скачанный файл DC1.rdp, а затем нажмите **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="44f75-171">Run the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="44f75-p117">В разделе **Безопасность Windows** нажмите **Использовать другую учетную запись**. В поле **Имя пользователя** введите **TESTLAB\\**[имя учетной записи локального администратора].</span><span class="sxs-lookup"><span data-stu-id="44f75-p117">In **Windows Security**, click **Use another account**. In **User name**, type **TESTLAB\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="44f75-174">В поле **Пароль** укажите пароль к учетной записи локального администратора, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="44f75-174">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="44f75-175">Когда появится соответствующий запрос, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="44f75-175">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="44f75-p118">Затем создайте учетную запись пользователя в Active Directory, которая будет использоваться при входе в систему на компьютерах, входящих в домен TESTLAB. От имени администратора выполните указанную ниже команду в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44f75-p118">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers. Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="44f75-p119">Обратите внимание на то, что при выполнении этой команды вам будет предложено ввести пароль учетной записи User1. Так как эта учетная запись будет использоваться для подключения к удаленному рабочему столу для всех компьютеров, входящих в домен TESTLAB, используйте надежный пароль. Запишите пароль к учетной записи User1 и храните его в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="44f75-p119">Note that this command prompts you to supply the User1 account password. Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password. Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="44f75-p120">Затем сделайте новую учетную запись User1 учетной записью администратора домена, предприятия и схемы. От имени администратора выполните приведенную ниже команду в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44f75-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```
$yourDomain="<your public domain>"
$domainName = "testlab"+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="44f75-183">Закройте сеанс удаленного рабочего стола DC1 и подключитесь заново, используя учетную запись TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="44f75-183">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="44f75-184">Чтобы разрешить трафик для средства Ping, выполните приведенную ниже команду в командной строке Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="44f75-184">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="44f75-185">Это ваша текущая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="44f75-185">This is your current configuration.</span></span>
  
![Шаг 1 базовой конфигурации "имитация предприятия"](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="44f75-187">Шаг 2. Настройка APP1</span><span class="sxs-lookup"><span data-stu-id="44f75-187">Step 2: Configure APP1</span></span>

<span data-ttu-id="44f75-188">На этом этапе создается и настраивается сервер приложений APP1, который вначале выступает в качестве веб-сервера и сервера обмена файлами.</span><span class="sxs-lookup"><span data-stu-id="44f75-188">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="44f75-189">Чтобы создать виртуальную машину Azure для APP1, сначала укажите имя группы ресурсов, а затем выполните приведенные ниже команды в командной строке на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="44f75-189">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```
$rgName="<resource group name>"
$locName=(Get-AzureRmResourceGroup -Name $rgName).Location
$vnet=Get-AzureRMVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzureRMPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzureRMNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzureRMVMConfig -VMName APP1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzureRMVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzureRMVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzureRMVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzureRmVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzureRMVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="44f75-190">После этого подключитесь к виртуальной машине APP1, используя имя и пароль для учетной записи локального администратора APP1. Затем откройте командную строку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44f75-190">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="44f75-191">Чтобы проверить разрешение имен и сетевое подключение между APP1 и DC1, выполните команду **ping dc1.testlab.**\<имя вашего публичного домена> и убедитесь, что поступило четыре ответа.</span><span class="sxs-lookup"><span data-stu-id="44f75-191">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command and verify that there are four replies.</span></span>
  
<span data-ttu-id="44f75-192">Затем присоедините виртуальную машину APP1 к домену TESTLAB, выполнив приведенные ниже команды в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44f75-192">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

<span data-ttu-id="44f75-193">Обратите внимание, что после выполнения команды **Add-Computer** вам потребуется указать данные учетной записи домена TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="44f75-193">Note that you must supply the TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="44f75-194">После перезапуска сервера APP1 подключитесь к нему, используя учетную запись TESTLAB\\User1, а затем откройте командную строку Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="44f75-194">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="44f75-195">После этого сделайте APP1 веб-сервером, выполнив приведенную ниже команду от имени администратора в командной строке Windows PowerShell на APP1.</span><span class="sxs-lookup"><span data-stu-id="44f75-195">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="44f75-196">Создайте общую папку и текстовый файл в папке на APP1 с помощью указанных ниже команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44f75-196">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="44f75-197">Это ваша текущая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="44f75-197">This is your current configuration.</span></span>
  
![Этап 2 базовой конфигурации "имитация предприятия"](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="44f75-199">Этап 3: настройка CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="44f75-199">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="44f75-200">На этом этапе создается и настраивается виртуальная машина CLIENT1, которая выступает в качестве типичного ноутбука, планшета или настольного компьютера в интрасети.</span><span class="sxs-lookup"><span data-stu-id="44f75-200">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="44f75-p121">Приведенный ниже набор команд создает виртуальную машину CLIENT1 под управлением Windows Server 2016 Datacenter. Это возможно благодаря подпискам на Azure любых типов. Если у вас есть подписка на Azure с Visual Studio, то вы можете создать виртуальную машину CLIENT1 под управлением Windows 10 на [портале Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="44f75-p121">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have an Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span> 
  
<span data-ttu-id="44f75-203">Чтобы создать виртуальную машину Azure для CLIENT1, сначала укажите имя группы ресурсов, а затем выполните приведенные ниже команды в командной строке на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="44f75-203">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```
$rgName="<resource group name>"
$locName=(Get-AzureRmResourceGroup -Name $rgName).Location
$vnet=Get-AzureRMVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzureRMPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzureRMNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzureRMVMConfig -VMName CLIENT1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzureRMVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzureRMVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzureRMVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzureRmVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzureRMVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="44f75-204">После этого подключитесь к виртуальной машине CLIENT1, используя имя и пароль для учетной записи локального администратора CLIENT1. Затем откройте командную строку Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="44f75-204">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="44f75-205">Чтобы проверить разрешение имен и сетевое подключение между CLIENT1 и DC1, выполните команду **ping dc1.testlab.**\<имя вашего публичного домена> в командной строке Windows PowerShell и убедитесь, что поступило четыре ответа.</span><span class="sxs-lookup"><span data-stu-id="44f75-205">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="44f75-206">Затем присоедините виртуальную машину CLIENT1 к домену TESTLAB, выполнив приведенные ниже команды в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44f75-206">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

<span data-ttu-id="44f75-207">Обратите внимание, что после выполнения команды **Add-Computer** вам потребуется указать данные учетной записи домена TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="44f75-207">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="44f75-208">После перезапуска виртуальной машины CLIENT1 подключитесь к ней, используя учетную запись TESTLAB\\User1, а затем откройте командную строку Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="44f75-208">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="44f75-209">Затем проверьте доступ к веб-ресурсам и общим файловым ресурсам на APP1 с CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="44f75-209">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="44f75-210">В области дерева диспетчера серверов выберите **Локальный сервер**.</span><span class="sxs-lookup"><span data-stu-id="44f75-210">In Server Manager, in the tree pane, click **Local Server**.</span></span>
    
2. <span data-ttu-id="44f75-211">В поле **Свойства CLIENT1** выберите значение **Вкл.** для параметра **Конфигурация усиленной безопасности Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="44f75-211">In **Properties for CLIENT1**, click **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="44f75-212">В разделе **Конфигурация усиленной безопасности Internet Explorer** для параметров **Администраторы** и **Пользователи** выберите значение **Выкл.** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="44f75-212">In **Internet Explorer Enhanced Security Configuration**, click **Off** for **Administrators** and **Users**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="44f75-213">На начальном экране выберите **Internet Explorer** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="44f75-213">From the Start screen, click **Internet Explorer**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="44f75-p122">В адресной строке введите **http<span>://</span>app1.testab.**\<имя вашего публичного домена>**/** и нажмите клавишу ВВОД. Вы увидите веб-страницу служб IIS по умолчанию для APP1.</span><span class="sxs-lookup"><span data-stu-id="44f75-p122">In the Address bar, type **http<span>://</span>app1.testab.**\<your public domain name>**/**, and then press ENTER. You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="44f75-216">Нажмите значок проводника на панели задач рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="44f75-216">From the desktop taskbar, click the File Explorer icon.</span></span>
    
7. <span data-ttu-id="44f75-p123">В адресной строке браузера введите **\\\\app1\\Files**, а затем нажмите клавишу ВВОД. Откроется окно папки с содержимым общей папки Files.</span><span class="sxs-lookup"><span data-stu-id="44f75-p123">In the address bar, type **\\\\app1\\Files**, and then press ENTER. You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="44f75-p124">В окне общей папки **Files** дважды щелкните файл **Example.txt**. Вы увидите содержимое файла Example.txt.</span><span class="sxs-lookup"><span data-stu-id="44f75-p124">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="44f75-221">Закройте окно **example.txt - Блокнот** и окно общей папки **Files**.</span><span class="sxs-lookup"><span data-stu-id="44f75-221">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="44f75-222">Это ваша текущая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="44f75-222">This is your current configuration.</span></span>
  
![Этап 3 базовой конфигурации "имитация предприятия"](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-office-365-e5-and-ems-e5-subscriptions"></a><span data-ttu-id="44f75-224">Этап 2. Создание подписок на Office 365 E5 и EMS E5</span><span class="sxs-lookup"><span data-stu-id="44f75-224">Phase 2: Create your Office 365 E5 and EMS E5 subscriptions</span></span>

<span data-ttu-id="44f75-p125">На этом этапе создаются новые подписки на Office 365 E5 и EMS E5, связанные с новым общим клиентом Azure AD, независимым от производственной подписки. Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="44f75-p125">In this phase, you create new Office 365 E5 and EMS E5 subscriptions that use a new and common Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="44f75-227">Использование пробных подписок на Office 365 E5 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="44f75-227">Use trial subscriptions of Office 365 E5 and EMS E5.</span></span> 

  <span data-ttu-id="44f75-p126">Срок действия пробной подписки на Office 365 E5 — 30 дней, но его можно легко продлить до 60 дней. Срок действия пробной подписки на EMS E5 — 90 дней. Когда срок действия пробных подписок истечет, необходимо будет либо преобразовать их в платные, либо создать новые. В последнем случае вы потеряете свою конфигурацию, которая может включать сложные сценарии.</span><span class="sxs-lookup"><span data-stu-id="44f75-p126">The Office 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. The EMS E5 trial subscription is 90 days. When the trial subscriptions expire, you must either convert them to paid subscriptions or create new trial subscriptions. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  
- <span data-ttu-id="44f75-232">Использование отдельной производственной подписки на Microsoft 365 корпоративный с небольшим количеством лицензий.</span><span class="sxs-lookup"><span data-stu-id="44f75-232">Use a separate production subscription of Microsoft 365 Enterprise with a small number of licenses.</span></span>

  <span data-ttu-id="44f75-p127">Это дополнительные затраты, но в результате вы получите рабочую тестовую среду для тестирования функций, конфигураций и сценарий, срок действия которой не истечет. Вы можете использовать ту же среду тестирования для доказательства правильности концепций, демонстрации возможностей для коллег и руководства, а также разработки и тестирования приложений. Это рекомендуемый метод.</span><span class="sxs-lookup"><span data-stu-id="44f75-p127">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire. You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing. This is the recommended method.</span></span>

### <a name="use-trial-subscriptions"></a><span data-ttu-id="44f75-236">Использование пробных подписок</span><span class="sxs-lookup"><span data-stu-id="44f75-236">Use trial subscriptions</span></span>

<span data-ttu-id="44f75-237">Если необходимо использовать пробные подписки, выполните действия из этапов 2 и 3, описанных в статье [Среда разработки и тестирования Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="44f75-237">If you must use trial subscriptions, follow the steps in Phase 2 and Phase 3 of the [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>
  
<span data-ttu-id="44f75-238">Затем оформляется пробная подписка на EMS E5, которая добавляется в ту же организацию, что и подписка на Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="44f75-238">Next, you sign up for the EMS E5 trial subscription and add it to the same organization as your Office 365 E5 subscription.</span></span>
  
<span data-ttu-id="44f75-239">Для начала добавьте пробную подписку на EMS E5 и назначьте лицензию на EMS учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="44f75-239">First, add the EMS E5 trial subscription and assign an EMS license to your global administrator account.</span></span>
  
1. <span data-ttu-id="44f75-p128">С помощью приватного экземпляра веб-браузера войдите на портал Office 365, используя данные учетной записи глобального администратора. Сведения о том, как это сделать, см в статье [Вход в Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="44f75-p128">With a private instance of an Internet browser, sign in to the Office 365 portal with your global administrator account credentials. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="44f75-242">Выберите плитку **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="44f75-242">Click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="44f75-243">Открыв вкладку **Центр администрирования Office** в браузере, на панели навигации слева щелкните **Выставление счетов > Приобретение служб**.</span><span class="sxs-lookup"><span data-stu-id="44f75-243">On the **Office Admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>
    
4. <span data-ttu-id="44f75-p129">На странице **Приобретение служб** найдите элемент **Enterprise Mobility + Security E5**. Наведите на него указатель мыши и выберите **Начать бесплатный пробный период**.</span><span class="sxs-lookup"><span data-stu-id="44f75-p129">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>
    
5. <span data-ttu-id="44f75-246">На странице **Подтверждение заказа** нажмите кнопку **Попробовать**.</span><span class="sxs-lookup"><span data-stu-id="44f75-246">On the **Confirm your order** page, click **Try now**.</span></span>
    
6. <span data-ttu-id="44f75-247">На странице **Получение заказа** нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="44f75-247">On the **Order receipt** page, click **Continue**.</span></span>
    
7. <span data-ttu-id="44f75-248">На вкладке браузера **Центр администрирования Office 365** на панели навигации слева выберите **Пользователи > Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="44f75-248">On the **Office 365 Admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>
    
8. <span data-ttu-id="44f75-249">Выберите свою учетную запись глобального администратора и щелкните ссылку **Изменить** для параметра **Лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="44f75-249">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>
    
9. <span data-ttu-id="44f75-250">На панели **Лицензии на продукты** переведите переключатель **Enterprise Mobility + Security E5** в положение **Вкл.**, нажмите **Сохранить**, а затем дважды **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="44f75-250">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="44f75-251">Чтобы иметь постоянную среду тестирования, создайте новую постоянную подписку с небольшим количеством лицензий.</span><span class="sxs-lookup"><span data-stu-id="44f75-251">For a permanent test environment, create a new permanent subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="44f75-252">Затем повторите действия 8 и 9 из предыдущей процедуры для всех остальных учетных записей (User 2, User 3, User 4 и User 5).</span><span class="sxs-lookup"><span data-stu-id="44f75-252">Next, repeat steps 8 and 9 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
### <a name="results"></a><span data-ttu-id="44f75-253">Результаты</span><span class="sxs-lookup"><span data-stu-id="44f75-253">Results</span></span>

<span data-ttu-id="44f75-254">Теперь ваша тестовая среда содержит:</span><span class="sxs-lookup"><span data-stu-id="44f75-254">Your test environment now has:</span></span>
  
- <span data-ttu-id="44f75-255">пробные подписки на Office 365 корпоративный E5 и EMS E5 с одним и тем же клиентом Azure AD для всех учетных записей пользователей из списка;</span><span class="sxs-lookup"><span data-stu-id="44f75-255">Office 365 E5 Enterprise and EMS E5 trial subscriptions sharing the same Azure AD tenant with your list of user accounts.</span></span>
- <span data-ttu-id="44f75-256">все подходящие учетные записи пользователей (либо только глобального администратора или всех пяти пользователей), поддерживающие Office 365 E5 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="44f75-256">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Office 365 E5 and EMS E5.</span></span>
    
<span data-ttu-id="44f75-257">Это ваша окончательная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="44f75-257">This is your final configuration.</span></span>
  
![Этап 4 базовой конфигурации "имитация предприятия"](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="44f75-259">Теперь вы можете экспериментировать с дополнительными возможностями [Microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="44f75-259">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="44f75-260">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="44f75-260">Next steps</span></span>

<span data-ttu-id="44f75-261">Ознакомьтесь с этими дополнительными комплектами руководств по лаборатории тестирования:</span><span class="sxs-lookup"><span data-stu-id="44f75-261">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="44f75-262">Идентификация</span><span class="sxs-lookup"><span data-stu-id="44f75-262">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="44f75-263">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="44f75-263">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="44f75-264">Защита информации</span><span class="sxs-lookup"><span data-stu-id="44f75-264">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="44f75-265">См. также</span><span class="sxs-lookup"><span data-stu-id="44f75-265">See also</span></span>

[<span data-ttu-id="44f75-266">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="44f75-266">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="44f75-267">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="44f75-267">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="44f75-268">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="44f75-268">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
