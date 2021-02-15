---
title: Базовая конфигурация "имитация предприятия" для Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Используйте это руководство по лаборатории тестирования, чтобы создать среду тестирования имитированных предприятий для Microsoft 365 для предприятий.
ms.openlocfilehash: e66ec8c48e309daeb15aad5fcc475edcb2b8bb35
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487664"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="1c620-103">Базовая конфигурация "имитация предприятия"</span><span class="sxs-lookup"><span data-stu-id="1c620-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="1c620-104">*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 для предприятий и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="1c620-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="1c620-105">В этой статье описано, как создать упрощенную среду для Microsoft 365 для предприятий, которая включает:</span><span class="sxs-lookup"><span data-stu-id="1c620-105">This article describes how to create a simplified environment for Microsoft 365 for enterprise that includes:</span></span>

- <span data-ttu-id="1c620-106">Пробная или платная подписка Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1c620-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="1c620-107">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из трех виртуальных машин в виртуальной сети Azure (DC1, APP1 и CLIENT1).</span><span class="sxs-lookup"><span data-stu-id="1c620-107">A simplified organization intranet connected to the internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![Базовая конфигурация "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="1c620-109">Создание упрощенной тестовой среды состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="1c620-109">Creating a simplified test environment involves two phases:</span></span>
- [<span data-ttu-id="1c620-110">Этап 1. Создание имитированной интрасети</span><span class="sxs-lookup"><span data-stu-id="1c620-110">Phase 1: Create a simulated intranet</span></span>](#phase-1-create-a-simulated-intranet)
- [<span data-ttu-id="1c620-111">Этап 2. Создание подписки Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1c620-111">Phase 2: Create your Microsoft 365 E5 subscription</span></span>](#phase-2-create-your-microsoft-365-e5-subscription)

<span data-ttu-id="1c620-112">Вы можете использовать итоговую среду для тестирования функций и функций [](m365-enterprise-test-lab-guides.md) [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise) для предприятий с помощью дополнительных руководств по лаборатории тестирования или самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="1c620-112">You can use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="1c620-114">Чтобы получить визуальную карту всех статей в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="1c620-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="1c620-115">Этап 1. Создание имитированной интрасети</span><span class="sxs-lookup"><span data-stu-id="1c620-115">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="1c620-116">На этом этапе создайте имитированную интрасеть в службах инфраструктуры Azure, которая включает контроллер домена доменных служб Active Directory (AD DS), сервер приложений и клиентский компьютер.</span><span class="sxs-lookup"><span data-stu-id="1c620-116">In this phase, build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span>

<span data-ttu-id="1c620-117">Вы будете использовать эти компьютеры в дополнительных руководствах по лаборатории тестирования [Microsoft 365](m365-enterprise-test-lab-guides.md) для предприятий для настройки и демонстрации гибридных удостоверений и других возможностей.</span><span class="sxs-lookup"><span data-stu-id="1c620-117">You'll use these computers in additional [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="1c620-118">Способ 1. Создание имитированной интрасети с помощью шаблона Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="1c620-118">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="1c620-119">В этом методе используется шаблон Azure Resource Manager для создания имитированной интрасети.</span><span class="sxs-lookup"><span data-stu-id="1c620-119">In this method, you use an Azure Resource Manager template to build out the simulated intranet.</span></span> <span data-ttu-id="1c620-120">Шаблоны Azure Resource Manager содержат все инструкции по созданию сетевой инфраструктуры Azure, виртуальных машин и их конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1c620-120">Azure Resource Manager templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="1c620-121">Перед развертыванием шаблона прочитайте страницу [ШАБЛОНА README](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) и подготовьтесь к следующим сведениям:</span><span class="sxs-lookup"><span data-stu-id="1c620-121">Before deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="1c620-122">Имя публичного домена DNS тестовой среды (testlab). \<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="1c620-122">The public DNS domain name of your test environment (testlab.\<*your public domain*>).</span></span> <span data-ttu-id="1c620-123">Это имя будет вводиться в поле **"Доменное имя"** страницы **настраиваемого** развертывания.</span><span class="sxs-lookup"><span data-stu-id="1c620-123">You'll enter this name in the **Domain Name** field of the **Custom deployment** page.</span></span>
- <span data-ttu-id="1c620-p103">Префикс метки DNS для URL-адресов общедоступных IP-адресов виртуальных машин. Вам понадобится ввести эту метку в поле **Префикс метки DNS** на странице **Настраиваемое развертывание**.</span><span class="sxs-lookup"><span data-stu-id="1c620-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="1c620-126">После того как вы прочтете инструкции, выберите "Развернуть в **Azure"** на странице [README шаблона,](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) чтобы начать работу.</span><span class="sxs-lookup"><span data-stu-id="1c620-126">After you read through the instructions, select **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="1c620-127">Для имитации интрасети, построенной по шаблону Azure Resource Manager, требуется платная подписка azure.</span><span class="sxs-lookup"><span data-stu-id="1c620-127">The simulated intranet built by the Azure Resource Manager template requires a paid Azure subscription.</span></span>

<span data-ttu-id="1c620-128">После завершения работы шаблона конфигурация выглядит так:</span><span class="sxs-lookup"><span data-stu-id="1c620-128">After the template is complete, your configuration looks like this:</span></span>

![Имитированная интрасеть в службах инфраструктуры Azure](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="1c620-130">Способ 2. Создание имитированной интрасети с помощью Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c620-130">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="1c620-131">Этот способ предполагает использование Windows PowerShell и модуля Azure PowerShell для создания сетевой инфраструктуры, виртуальных машин и их конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1c620-131">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="1c620-p104">Используйте этот способ, если вы хотите получить возможность создания элементов инфраструктуры Azure шаг за шагом с помощью PowerShell. Затем можно настроить командные блоки PowerShell для самостоятельного развертывания других виртуальных машин в Azure.</span><span class="sxs-lookup"><span data-stu-id="1c620-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="1c620-134">Этап 1. Создание DC1</span><span class="sxs-lookup"><span data-stu-id="1c620-134">Step 1: Create DC1</span></span>

<span data-ttu-id="1c620-135">На этом этапе создается виртуальная сеть Azure и добавляется виртуальная машина DC1, которая является контроллером домена для домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="1c620-135">In this step, you create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="1c620-136">Сначала запустите командную строку Windows PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1c620-136">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c620-p105">Для приведенных ниже последовательностей команд используется последняя версия Azure PowerShell. См. статью [Общие сведения об Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="1c620-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="1c620-139">Войдите в свою учетную запись Azure с помощью указанной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="1c620-139">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="1c620-140">Получите имя подписки с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="1c620-140">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="1c620-141">Укажите свою подписку Azure.</span><span class="sxs-lookup"><span data-stu-id="1c620-141">Set your Azure subscription.</span></span> <span data-ttu-id="1c620-142">Замените все в кавычках, включая угловые скобки ("<" и ">"), правильным именем.</span><span class="sxs-lookup"><span data-stu-id="1c620-142">Replace everything within the quotation marks, including the angle brackets ("<" and ">"), with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="1c620-p107">Затем создайте группу ресурсов для лаборатории тестирования "имитация предприятия". Чтобы определить уникальное имя группы ресурсов, используйте указанную ниже команду для вывода списка имеющихся групп ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1c620-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="1c620-145">Создайте группу ресурсов с помощью следующих команд.</span><span class="sxs-lookup"><span data-stu-id="1c620-145">Create your new resource group with these commands.</span></span> <span data-ttu-id="1c620-146">Замените все кавычек, включая угловые скобки, правильными именами.</span><span class="sxs-lookup"><span data-stu-id="1c620-146">Replace everything within the quotation marks, including the angle brackets, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="1c620-147">Затем создайте виртуальную сеть TestLab, в которой будет работать подсеть корпоративной сети имитированной корпоративной среды, и защитите ее с помощью группы безопасности сети.</span><span class="sxs-lookup"><span data-stu-id="1c620-147">Next, create the TestLab virtual network that will host the corporate network subnet of the simulated enterprise environment and protect it with a network security group.</span></span> <span data-ttu-id="1c620-148">Уполноможите имя группы ресурсов и запустите эти команды в командной командной области PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1c620-148">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="1c620-149">Затем создайте виртуальную машину DC1 и настройте ее как контроллер домена для **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="1c620-149">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain></span></span> <span data-ttu-id="1c620-150">Домен AD DS и DNS-сервер для виртуальных машин виртуальной сети TestLab.</span><span class="sxs-lookup"><span data-stu-id="1c620-150">AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="1c620-151">Например, если ваше имя публичного домена — **<span>contoso</span>.com**, виртуальная машина DC1 будет контроллером домена **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="1c620-151">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="1c620-152">Чтобы создать виртуальную машину Azure для DC1, укажите имя группы ресурсов и выполните приведенные ниже команды в командной строке PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1c620-152">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="1c620-p111">Вам будет предложено ввести имя пользователя и пароль учетной записи локального администратора на DC1. Задайте надежный пароль и запишите его вместе с именем пользователя в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="1c620-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="1c620-155">Затем подключите виртуальную машину DC1:</span><span class="sxs-lookup"><span data-stu-id="1c620-155">Next, connect to the DC1 virtual machine:</span></span>
  
1. <span data-ttu-id="1c620-156">На [портале Azure](https://portal.azure.com)выберите группы **ресурсов** > <***имя*** новой группы ресурсов> > **DC1**  >  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="1c620-156">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <***the name of your new resource group***> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="1c620-157">На открытой области выберите **"Загрузить RDP-файл".**</span><span class="sxs-lookup"><span data-stu-id="1c620-157">In the open pane, select **Download RDP file**.</span></span> <span data-ttu-id="1c620-158">Откройте скачаный файл DC1.rdp и выберите **"Подключиться".**</span><span class="sxs-lookup"><span data-stu-id="1c620-158">Open the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="1c620-159">Укажите имя учетной записи локального администратора DC1:</span><span class="sxs-lookup"><span data-stu-id="1c620-159">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="1c620-160">Для Windows 7:</span><span class="sxs-lookup"><span data-stu-id="1c620-160">For Windows 7:</span></span>
    
     <span data-ttu-id="1c620-161">В **диалоговом окне "Безопасность Windows"** выберите **"Использовать другую учетную запись".**</span><span class="sxs-lookup"><span data-stu-id="1c620-161">In the **Windows Security** dialog box, select **Use another account**.</span></span> <span data-ttu-id="1c620-162">Введите **имя учетной** **записи локального \\** администратора DC1 <  в>.</span><span class="sxs-lookup"><span data-stu-id="1c620-162">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
   - <span data-ttu-id="1c620-163">Для Windows 8 и Windows 10:</span><span class="sxs-lookup"><span data-stu-id="1c620-163">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="1c620-164">В **диалоговом окне "Безопасность Windows"** выберите "Дополнительные **варианты"** и выберите **"Использовать другую учетную запись".**</span><span class="sxs-lookup"><span data-stu-id="1c620-164">In the **Windows Security** dialog box, select **More choices**, and then select **Use a different account**.</span></span> <span data-ttu-id="1c620-165">Введите **имя учетной** **записи локального \\** администратора DC1 <  в>.</span><span class="sxs-lookup"><span data-stu-id="1c620-165">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="1c620-166">Введите **пароль** учетной записи локального администратора и выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="1c620-166">In **Password**, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="1c620-167">При запросе выберите **"Да".**</span><span class="sxs-lookup"><span data-stu-id="1c620-167">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="1c620-168">После этого добавьте еще один диск с данными в качестве нового тома с буквой диска "F:", используя приведенные ниже команды в командной строке Windows PowerShell на уровне администратора в DC1.</span><span class="sxs-lookup"><span data-stu-id="1c620-168">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="1c620-169">Затем настройте DC1 как контроллер домена и DNS-сервер для домена **testlab.**\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="1c620-169">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<*your public domain*></span></span> <span data-ttu-id="1c620-170">.</span><span class="sxs-lookup"><span data-stu-id="1c620-170">domain.</span></span> <span data-ttu-id="1c620-171">Укажите свое имя публичного домена, удалите угловые скобки и затем запустите эти команды в командной Windows PowerShell на DC1.</span><span class="sxs-lookup"><span data-stu-id="1c620-171">Specify your public domain name, remove the angle brackets, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="1c620-p116">Потребуется указать пароль администратора для безопасного режима. Храните этот пароль в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="1c620-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="1c620-174">Обратите внимание, что на выполнение этих команд может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="1c620-174">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="1c620-175">После перезапуска виртуальной машины DC1 снова подключитесь к ней.</span><span class="sxs-lookup"><span data-stu-id="1c620-175">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="1c620-176">На [портале Azure выберите](https://portal.azure.com) **группы** ресурсов > <*имя* группы ресурсов> > **DC1**  >  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="1c620-176">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <*your resource group name*> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="1c620-177">Запустите скачаный файл DC1.rdp и выберите **"Подключиться".**</span><span class="sxs-lookup"><span data-stu-id="1c620-177">Run the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="1c620-178">В **Windows Security** выберите **"Использовать другую учетную запись".**</span><span class="sxs-lookup"><span data-stu-id="1c620-178">In **Windows Security**, select **Use another account**.</span></span> <span data-ttu-id="1c620-179">Введите **имя учетной** **записи локального \\** администратора TESTLAB <  в>.</span><span class="sxs-lookup"><span data-stu-id="1c620-179">In **User name**, enter **TESTLAB\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="1c620-180">В поле **"Пароль"** введите пароль учетной записи локального администратора и выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="1c620-180">In the **Password** box, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="1c620-181">При запросе выберите **"Да".**</span><span class="sxs-lookup"><span data-stu-id="1c620-181">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="1c620-182">Затем создайте учетную запись пользователя в Active Directory, которая будет использоваться при входе на рядовые компьютеры домена TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="1c620-182">Next, create a user account in Active Directory that will be used when signing in to TESTLAB domain member computers.</span></span> <span data-ttu-id="1c620-183">От имени администратора выполните указанную ниже команду в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c620-183">Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="1c620-184">Обратите внимание на то, что при выполнении этой команды вам будет предложено ввести пароль учетной записи User1.</span><span class="sxs-lookup"><span data-stu-id="1c620-184">Note that this command prompts you to supply the User1 account password.</span></span> <span data-ttu-id="1c620-185">Эта учетная запись будет использоваться для подключений к удаленному рабочему столу для всех компьютеров- членов домена TESTLAB, поэтому выберите надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="1c620-185">This account will be used for remote desktop connections for all TESTLAB domain member computers, so choose a strong password.</span></span> <span data-ttu-id="1c620-186">Запишите пароль к учетной записи User1 и храните его в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="1c620-186">Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="1c620-p120">Затем сделайте новую учетную запись User1 учетной записью администратора домена, предприятия и схемы. От имени администратора выполните приведенную ниже команду в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c620-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="1c620-189">Закройте сеанс удаленного рабочего стола DC1 и подключитесь заново, используя учетную запись TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="1c620-189">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="1c620-190">Чтобы разрешить трафик для средства Ping, выполните приведенную ниже команду в командной строке Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="1c620-190">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="1c620-191">Текущая конфигурация выглядит так:</span><span class="sxs-lookup"><span data-stu-id="1c620-191">Your current configuration looks like this:</span></span>
  
![Шаг 1 базовой конфигурации "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="1c620-193">Шаг 2. Настройка APP1</span><span class="sxs-lookup"><span data-stu-id="1c620-193">Step 2: Configure APP1</span></span>

<span data-ttu-id="1c620-194">На этом этапе создается и настраивается сервер приложений APP1, который вначале выступает в качестве веб-сервера и сервера обмена файлами.</span><span class="sxs-lookup"><span data-stu-id="1c620-194">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="1c620-195">Чтобы создать виртуальную машину Azure для APP1, сначала укажите имя группы ресурсов, а затем выполните приведенные ниже команды в командной строке на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1c620-195">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="1c620-196">После этого подключитесь к виртуальной машине APP1, используя имя и пароль для учетной записи локального администратора APP1. Затем откройте командную строку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c620-196">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="1c620-197">Чтобы проверить разрешение имен и сетевое взаимодействие между APP1 и DC1, выполните команду **ping dc1.testlab.**\<*your public domain name*></span><span class="sxs-lookup"><span data-stu-id="1c620-197">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="1c620-198">и убедитесь что получено четыре ответа.</span><span class="sxs-lookup"><span data-stu-id="1c620-198">command and verify that there are four replies.</span></span>
  
<span data-ttu-id="1c620-199">Затем присоедините виртуальную машину APP1 к домену TESTLAB, выполнив приведенные ниже команды в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c620-199">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="1c620-200">Обратите внимание, что после запуска команды **Add-Computer** необходимо предоставить учетные данные учетной записи домена TESTLAB \\ User1.</span><span class="sxs-lookup"><span data-stu-id="1c620-200">Note that you after you run the **Add-Computer** command, you must supply the TESTLAB\\User1 domain account credentials.</span></span>
  
<span data-ttu-id="1c620-201">После перезапуска сервера APP1 подключитесь к нему, используя учетную запись TESTLAB\\User1, а затем откройте командную строку Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="1c620-201">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="1c620-202">После этого сделайте APP1 веб-сервером, выполнив приведенную ниже команду от имени администратора в командной строке Windows PowerShell на APP1.</span><span class="sxs-lookup"><span data-stu-id="1c620-202">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="1c620-203">Создайте общую папку и текстовый файл в папке на APP1 с помощью указанных ниже команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c620-203">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="1c620-204">Текущая конфигурация выглядит так:</span><span class="sxs-lookup"><span data-stu-id="1c620-204">Your current configuration looks like this:</span></span>
  
![Этап 2 базовой конфигурации "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="1c620-206">Этап 3: настройка CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="1c620-206">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="1c620-207">На этом этапе создается и настраивается виртуальная машина CLIENT1, которая выступает в качестве типичного ноутбука, планшета или настольного компьютера в интрасети.</span><span class="sxs-lookup"><span data-stu-id="1c620-207">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="1c620-p122">Приведенный ниже набор команд создает виртуальную машину CLIENT1 под управлением Windows Server 2016 Datacenter. Это возможно благодаря подпискам на Azure любых типов. Если у вас есть подписка на Azure с Visual Studio, вы можете создать виртуальную машину CLIENT1 под управлением Windows 10 на [портале Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="1c620-p122">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span>
  
<span data-ttu-id="1c620-210">Чтобы создать виртуальную машину Azure для CLIENT1, в заполните имя группы ресурсов и запустите эти команды в командной командной области на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1c620-210">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="1c620-211">После этого подключитесь к виртуальной машине CLIENT1, используя имя и пароль для учетной записи локального администратора CLIENT1. Затем откройте командную строку Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="1c620-211">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="1c620-212">Чтобы проверить разрешение имен и сетевое взаимодействие между CLIENT1 и DC1, выполните команду **ping dc1.testlab.**\<*your public domain name*></span><span class="sxs-lookup"><span data-stu-id="1c620-212">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="1c620-213">в командной строке Windows PowerShell и убедитесь, что получено четыре ответа.</span><span class="sxs-lookup"><span data-stu-id="1c620-213">command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="1c620-214">Затем присоедините виртуальную машину CLIENT1 к домену TESTLAB, выполнив приведенные ниже команды в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c620-214">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="1c620-215">Обратите внимание, что после выполнения команды **Add-Computer** вам потребуется указать данные учетной записи домена TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="1c620-215">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="1c620-216">После перезапуска виртуальной машины CLIENT1 подключитесь к ней, используя учетную запись TESTLAB\\User1, а затем откройте командную строку Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="1c620-216">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="1c620-217">Затем проверьте доступ к веб-ресурсам и общим файловым ресурсам на APP1 с CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="1c620-217">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="1c620-218">В диспетчере серверов в области дерева выберите **локальный сервер.**</span><span class="sxs-lookup"><span data-stu-id="1c620-218">In Server Manager, in the tree pane, select **Local Server**.</span></span>
    
2. <span data-ttu-id="1c620-219">In **Properties for CLIENT1**, select **On** next to **IE Enhanced Security Configuration**.</span><span class="sxs-lookup"><span data-stu-id="1c620-219">In **Properties for CLIENT1**, select **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="1c620-220">В **конфигурации усиленной безопасности Internet Explorer** выберите  "Выключите" для администраторов и **пользователей,** а затем выберите  "ОК". </span><span class="sxs-lookup"><span data-stu-id="1c620-220">In **Internet Explorer Enhanced Security Configuration**, select **Off** for **Administrators** and **Users**, and then select **OK**.</span></span>
    
4. <span data-ttu-id="1c620-221">На экране "Начните" выберите **Internet Explorer** и выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="1c620-221">From the Start screen, select **Internet Explorer**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="1c620-222">В адресной панели введите **http <span>://</span>app1.testab.** \<*your public domain name*> **/** и нажмите ввод . </span><span class="sxs-lookup"><span data-stu-id="1c620-222">In the address bar, enter **http <span>://</span>app1.testab.**\<*your public domain name*>**/**, and then press **Enter**.</span></span> <span data-ttu-id="1c620-223">Вы увидите страницу служб IIS по умолчанию для APP1.</span><span class="sxs-lookup"><span data-stu-id="1c620-223">You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="1c620-224">На панели задач рабочего стола выберите значок проводника.</span><span class="sxs-lookup"><span data-stu-id="1c620-224">On the desktop taskbar, select the File Explorer icon.</span></span>
    
7. <span data-ttu-id="1c620-225">В адресной панели введите **\\ \\ app1 \\ Files** и нажмите **ввод**.</span><span class="sxs-lookup"><span data-stu-id="1c620-225">In the address bar, enter **\\\\app1\\Files**, and then press **Enter**.</span></span> <span data-ttu-id="1c620-226">Вы увидите окно папки с содержимым общей папки Files.</span><span class="sxs-lookup"><span data-stu-id="1c620-226">You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="1c620-p126">В окне общей папки **Files** дважды щелкните файл **Example.txt**. Вы увидите содержимое файла Example.txt.</span><span class="sxs-lookup"><span data-stu-id="1c620-p126">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="1c620-229">Закройте окно **example.txt - Блокнот** и окно общей папки **Files**.</span><span class="sxs-lookup"><span data-stu-id="1c620-229">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="1c620-230">Текущая конфигурация выглядит так:</span><span class="sxs-lookup"><span data-stu-id="1c620-230">Your current configuration looks like this:</span></span>
  
![Этап 3 базовой конфигурации "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="1c620-232">Этап 2. Создание подписки Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1c620-232">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="1c620-233">На этом этапе создается новая подписка Microsoft 365 E5, связанная с новым клиентом Azure AD, независимым от производственной подписки.</span><span class="sxs-lookup"><span data-stu-id="1c620-233">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription.</span></span> <span data-ttu-id="1c620-234">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="1c620-234">You can do this in two ways:</span></span>

- <span data-ttu-id="1c620-235">Использовать пробную подписку Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="1c620-235">Use a trial subscription of Microsoft 365 E5.</span></span>

  <span data-ttu-id="1c620-236">Пробная подписка на Office 365 E5 действительна в течение 30 дней, и этот срок можно легко продлить до 60 дней.</span><span class="sxs-lookup"><span data-stu-id="1c620-236">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days.</span></span> <span data-ttu-id="1c620-237">После окончания срока действия пробной подписки, необходимо оформить платную подписку или создать новую пробную подписку.</span><span class="sxs-lookup"><span data-stu-id="1c620-237">When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription.</span></span> <span data-ttu-id="1c620-238">Создание новой пробной подписки означает, что вы потеряете свою конфигурацию, которая может включать сложные сценарии.</span><span class="sxs-lookup"><span data-stu-id="1c620-238">Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="1c620-239">Использовать отдельную производственную подписку на Microsoft 365 E5 с небольшим количеством лицензий.</span><span class="sxs-lookup"><span data-stu-id="1c620-239">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="1c620-240">Это дополнительные затраты, но гарантирует, что у вас есть рабочая тестовая среда, срок действия которой не истек; в нем можно попробовать функции, конфигурации и сценарии.</span><span class="sxs-lookup"><span data-stu-id="1c620-240">This is an additional cost, but ensures that you have a working test environment that doesn't expire; in it, you can try features, configurations, and scenarios.</span></span> <span data-ttu-id="1c620-241">Вы можете использовать в долгосрочной перспективе ту же тестовую среду для подтверждения концепции, демонстрации для коллег и управления, а также для разработки и тестирования приложений.</span><span class="sxs-lookup"><span data-stu-id="1c620-241">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span></span> <span data-ttu-id="1c620-242">Это рекомендуемый метод.</span><span class="sxs-lookup"><span data-stu-id="1c620-242">This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="1c620-243">Оформление пробной подписки на Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="1c620-243">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="1c620-244">На портале Azure подключите клиент CLIENT1 с помощью учетной записи CORP\User1.</span><span class="sxs-lookup"><span data-stu-id="1c620-244">From the Azure portal, connect to CLIENT1 with the CORP\User1 account.</span></span>

<span data-ttu-id="1c620-245">Чтобы создать пробную подписку на Office 365 E5, выполните инструкции из [этапа 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) руководства по лаборатории тестирования простой базовой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1c620-245">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="1c620-246">Чтобы настроить новую пробную подписку на Office 365 E5, выполните инструкции из [этапа 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) руководства по лаборатории тестирования простой базовой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1c620-246">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="1c620-247">Использование среды тестирования Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="1c620-247">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="1c620-248">Если вам нужна только тестовая среда Office 365, прочитать оставшуюся часть этой статьи не нужно.</span><span class="sxs-lookup"><span data-stu-id="1c620-248">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="1c620-249">Дополнительные руководства по лаборатории тестирования, применимые к Microsoft 365 и Office 365, см. в руководстве по лаборатории тестирования [Microsoft 365 для предприятий.](m365-enterprise-test-lab-guides.md)</span><span class="sxs-lookup"><span data-stu-id="1c620-249">For additional Test Lab Guides that apply to both Microsoft 365 and Office 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="1c620-250">Добавление пробной подписки Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="1c620-250">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="1c620-251">Чтобы добавить пробную подписку microsoft 365 E5 и настроить учетные записи пользователей с лицензиями, выполните инструкции на этапе [3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) руководства по лаборатории тестирования для облегченной базовой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1c620-251">To add a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="1c620-252">Результаты</span><span class="sxs-lookup"><span data-stu-id="1c620-252">Results</span></span>

<span data-ttu-id="1c620-253">Теперь ваша тестовая среда содержит:</span><span class="sxs-lookup"><span data-stu-id="1c620-253">Your test environment now has:</span></span>
  
- <span data-ttu-id="1c620-254">Пробную подписку Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="1c620-254">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="1c620-255">Все подходящие учетные записи пользователей, готовые к использованию Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="1c620-255">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="1c620-256">Смоделированную и упрощенную интрасеть.</span><span class="sxs-lookup"><span data-stu-id="1c620-256">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="1c620-257">Окончательная конфигурация выглядит так:</span><span class="sxs-lookup"><span data-stu-id="1c620-257">Your final configuration looks like this:</span></span>
  
![Этап 2 базовой конфигурации "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="1c620-259">Теперь вы готовы поэкспериментировать с дополнительными функциями [Microsoft 365 для предприятий.](https://www.microsoft.com/microsoft-365/enterprise)</span><span class="sxs-lookup"><span data-stu-id="1c620-259">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="1c620-260">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="1c620-260">Next steps</span></span>

<span data-ttu-id="1c620-261">Ознакомьтесь с этими дополнительными комплектами руководств по лаборатории тестирования:</span><span class="sxs-lookup"><span data-stu-id="1c620-261">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="1c620-262">Идентификация</span><span class="sxs-lookup"><span data-stu-id="1c620-262">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="1c620-263">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="1c620-263">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="1c620-264">Защита информации</span><span class="sxs-lookup"><span data-stu-id="1c620-264">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="1c620-265">См. также</span><span class="sxs-lookup"><span data-stu-id="1c620-265">See also</span></span>

[<span data-ttu-id="1c620-266">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1c620-266">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1c620-267">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1c620-267">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="1c620-268">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1c620-268">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
