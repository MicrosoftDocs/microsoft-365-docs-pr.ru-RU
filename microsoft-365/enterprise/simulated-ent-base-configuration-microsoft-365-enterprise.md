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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Это руководство по лаборатории тестирования поможет вам создать имитацию предприятия для Microsoft 365 корпоративный.
ms.openlocfilehash: 486429bf9e1c0a88c9beb01a092f968256c1fa77
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818499"
---
# <a name="the-simulated-enterprise-base-configuration"></a>Базовая конфигурация "имитация предприятия"

*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 корпоративный и Office 365 корпоративный.*

В этой статье вы найдете пошаговые инструкции по созданию упрощенной среды для Microsoft 365 корпоративный, которая включает:

- Пробная или платная подписка Microsoft 365 E5
- упрощенную интрасеть организации, подключенную к Интернету и состоящую из трех виртуальных машин в виртуальной сети Azure (DC1, APP1 и CLIENT1).
 
![Базовая конфигурация "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

Вы можете использовать полученную среду для тестирования функций [Microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise) с дополнительными [руководствами по лаборатории тестирования](m365-enterprise-test-lab-guides.md) или без них.

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Перейдите в раздел [Руководства по лаборатории тестирования Microsoft 365 корпоративный](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к данной теме.

## <a name="phase-1-create-a-simulated-intranet"></a>Этап 1. Создание имитированной интрасети

На этом этапе вы создаете имитацию интрасети в службах инфраструктуры Azure, которая включает контроллер домена Active Directory Domain Services (AD DS), сервер приложений и клиентский компьютер. 

Вы будете использовать эти компьютеры в дополнительных [Руководствах по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md) для настройки и демонстрации гибридных удостоверений и других возможностей.

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a>Способ 1. Создание имитированной интрасети с помощью шаблона Azure Resource Manager

In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet. ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.

Перед развертыванием шаблона ознакомьтесь со [страницей сведений шаблона (README)](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) и приготовьте приведенные ниже сведения.

- The public DNS domain name of your test environment (testlab.\<your public domain>). You'll need to enter this name in the **Domain Name field** of the **Custom deployment** page.
- A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.

После ознакомления с инструкциями нажмите **Развертывание в Azure** на [странице сведений шаблона (README)](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems), чтобы приступить к работе.

>[!Note]
>Для имитации интрасети, созданной на основе шаблона ARM, требуется платная подписка Azure.
>

Ниже показана итоговая конфигурация после завершения работы с шаблоном.

![Имитированная интрасеть в службах инфраструктуры Azure](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a>Способ 2. Создание имитированной интрасети с помощью Azure PowerShell

Этот способ предполагает использование Windows PowerShell и модуля Azure PowerShell для создания сетевой инфраструктуры, виртуальных машин и их конфигурации.

Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.

#### <a name="step-1-create-dc1"></a>Этап 1. Создание DC1

На этом этапе создается виртуальная сеть Azure и добавляется виртуальная машина DC1, которая является контроллером домена AD DS.

Сначала запустите командную строку Windows PowerShell на локальном компьютере.
  
> [!NOTE]
> The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). 
  
Войдите в свою учетную запись Azure с помощью указанной ниже команды.
  
```powershell
Connect-AzAccount
```

Получите имя подписки с помощью следующей команды.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Set your Azure subscription. Replace everything within the quotes, including the < and > characters, with the correct name.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Create your new resource group with these commands. Replace everything within the quotes, including the < and > characters, with the correct names.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group. Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.
  
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

Затем создайте виртуальную машину DC1 и настройте ее как контроллер домена для **testlab.**\<your public domain> Домен AD DS и DNS-сервер для виртуальных машин виртуальной сети TestLab. Например, если ваше имя публичного домена — **<span>contoso</span>.com**, виртуальная машина DC1 будет контроллером домена **<span>testlab</span>.contoso.com**.
  
Чтобы создать виртуальную машину Azure для DC1, укажите имя группы ресурсов и выполните приведенные ниже команды в командной строке PowerShell на локальном компьютере.
  
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

You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.
  
После этого подключитесь к виртуальной машине DC1.
  
1. На [портале Azure](https://portal.azure.com) выберите **Группы ресурсов >** [имя новой группы ресурсов] **> DC1 > Подключить**.
    
2. In the open pane, click **Download RDP file**. Open the DC1.rdp file that is downloaded, and then click **Connect**.
    
3. Укажите имя учетной записи локального администратора DC1:
    
   - Для Windows 7:
    
     In the **Windows Security** dialog box, click **Use another account**. In **User name**, type **DC1\\**[Local administrator account name].
    
   - Для Windows 8 и Windows 10:
    
     In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**. In **User name**, type **DC1\\**[Local administrator account name].
    
4. В поле **Пароль** укажите пароль к учетной записи локального администратора, а затем нажмите кнопку **ОК**.
    
5. Когда появится соответствующий запрос, нажмите кнопку **Да**.
    
После этого добавьте еще один диск с данными в качестве нового тома с буквой диска "F:", используя приведенные ниже команды в командной строке Windows PowerShell на уровне администратора в DC1.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Затем настройте DC1 как контроллер домена и DNS-сервер для домена **testlab.**\<your public domain> . Укажите имя своего общедоступного домена, удалите символы \< and >, а затем выполните указанные ниже команды в командной строке Windows PowerShell на уровне администратора в DC1.
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
You will need to specify a safe mode administrator password. Store this password in a secure location.
  
Обратите внимание, что на выполнение этих команд может потребоваться несколько минут.
  
После перезапуска виртуальной машины DC1 снова подключитесь к ней.
  
1. На [портале Azure](https://portal.azure.com) выберите элементы **Группы ресурсов >** [имя вашей группы ресурсов] ** DC1 > Подключить**.
    
2. Запустите скачанный файл DC1.rdp, а затем нажмите **Подключить**.
    
3. In **Windows Security**, click **Use another account**. In **User name**, type **TESTLAB\\**[Local administrator account name].
    
4. В поле **Пароль** укажите пароль к учетной записи локального администратора, а затем нажмите кнопку **ОК**.
    
5. Когда появится соответствующий запрос, нажмите кнопку **Да**.
    
Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers. Run this command at an administrator-level Windows PowerShell command prompt.
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

Note that this command prompts you to supply the User1 account password. Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password. Record the User1 account password and store it in a secured location.
  
Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

Закройте сеанс удаленного рабочего стола DC1 и подключитесь заново, используя учетную запись TESTLAB\\User1.
  
Чтобы разрешить трафик для средства Ping, выполните приведенную ниже команду в командной строке Windows PowerShell от имени администратора.
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

Это ваша текущая конфигурация.
  
![Шаг 1 базовой конфигурации "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a>Шаг 2. Настройка APP1

На этом этапе создается и настраивается сервер приложений APP1, который вначале выступает в качестве веб-сервера и сервера обмена файлами.

Чтобы создать виртуальную машину Azure для APP1, сначала укажите имя группы ресурсов, а затем выполните приведенные ниже команды в командной строке на локальном компьютере.
  
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

После этого подключитесь к виртуальной машине APP1, используя имя и пароль для учетной записи локального администратора APP1. Затем откройте командную строку Windows PowerShell.
  
Чтобы проверить разрешение имен и сетевое взаимодействие между APP1 и DC1, выполните команду **ping dc1.testlab.**\<your public domain name> и убедитесь что получено четыре ответа.
  
Затем присоедините виртуальную машину APP1 к домену TESTLAB, выполнив приведенные ниже команды в командной строке Windows PowerShell.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Обратите внимание, что после выполнения команды **Add-Computer** вам потребуется указать данные учетной записи домена TESTLAB\\User1.
  
После перезапуска сервера APP1 подключитесь к нему, используя учетную запись TESTLAB\\User1, а затем откройте командную строку Windows PowerShell от имени администратора.
  
После этого сделайте APP1 веб-сервером, выполнив приведенную ниже команду от имени администратора в командной строке Windows PowerShell на APP1.
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

Создайте общую папку и текстовый файл в папке на APP1 с помощью указанных ниже команд PowerShell.
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

Это ваша текущая конфигурация.
  
![Этап 2 базовой конфигурации "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a>Этап 3: настройка CLIENT1.

На этом этапе создается и настраивается виртуальная машина CLIENT1, которая выступает в качестве типичного ноутбука, планшета или настольного компьютера в интрасети.

> [!NOTE]  
> The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com). 
  
Чтобы создать виртуальную машину Azure для CLIENT1, сначала укажите имя группы ресурсов, а затем выполните приведенные ниже команды в командной строке на локальном компьютере.
  
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

После этого подключитесь к виртуальной машине CLIENT1, используя имя и пароль для учетной записи локального администратора CLIENT1. Затем откройте командную строку Windows PowerShell от имени администратора.
  
Чтобы проверить разрешение имен и сетевое взаимодействие между CLIENT1 и DC1, выполните команду **ping dc1.testlab.**\<your public domain name> в командной строке Windows PowerShell и убедитесь, что получено четыре ответа.
  
Затем присоедините виртуальную машину CLIENT1 к домену TESTLAB, выполнив приведенные ниже команды в командной строке Windows PowerShell.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Обратите внимание, что после выполнения команды **Add-Computer** вам потребуется указать данные учетной записи домена TESTLAB\\User1.
  
После перезапуска виртуальной машины CLIENT1 подключитесь к ней, используя учетную запись TESTLAB\\User1, а затем откройте командную строку Windows PowerShell от имени администратора.
  
Затем проверьте доступ к веб-ресурсам и общим файловым ресурсам на APP1 с CLIENT1.
  
1. В области дерева диспетчера серверов выберите **Локальный сервер**.
    
2. В поле **Свойства CLIENT1** выберите значение **Вкл.** для параметра **Конфигурация усиленной безопасности Internet Explorer**.
    
3. В разделе **Конфигурация усиленной безопасности Internet Explorer** для параметров **Администраторы** и **Пользователи** выберите значение **Выкл.** и нажмите кнопку **ОК**.
    
4. На начальном экране выберите **Internet Explorer** и нажмите кнопку **ОК**.
    
5. В адресной строке браузера введите **http<span>://</span>app1.testlab.**\<your public domain name>**/**, а затем нажмите клавишу ВВОД. Вы увидите страницу служб IIS по умолчанию для APP1.
    
6. Нажмите значок проводника на панели задач рабочего стола.
    
7. In the address bar, type **\\\\app1\\Files**, and then press ENTER. You should see a folder window with the contents of the Files shared folder.
    
8. In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.
    
9. Закройте окно **example.txt - Блокнот** и окно общей папки **Files**.
    
Это ваша текущая конфигурация.
  
![Этап 3 базовой конфигурации "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a>Этап 2. Создание подписки Microsoft 365 E5

На этом этапе создается новая подписка Microsoft 365 E5, связанная с новым клиентом Azure AD, независимым от производственной подписки. Это можно сделать двумя способами:

- Использовать пробную подписку Microsoft 365 E5. 

  Пробная подписка на Office 365 E5 действительна в течение 30 дней, и этот срок можно легко продлить до 60 дней. После окончания срока действия пробной подписки, необходимо оформить платную подписку или создать новую пробную подписку. Создание новой пробной подписки означает, что вы потеряете свою конфигурацию, которая может включать сложные сценарии.  

- Использовать отдельную производственную подписку на Microsoft 365 E5 с небольшим количеством лицензий.

  This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire. You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing. This is the recommended method.

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Оформление пробной подписки на Office 365 E5

На портале Azure подключитесь к компьютеру CLIENT1, используя учетную запись CORP\User1.

Чтобы создать пробную подписку на Office 365 E5, выполните инструкции из [этапа 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-office-365-e5-subscription) руководства по лаборатории тестирования простой базовой конфигурации.

Чтобы настроить новую пробную подписку на Office 365 E5, выполните инструкции из [этапа 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) руководства по лаборатории тестирования простой базовой конфигурации.

#### <a name="using-an-office-365-e5-test-environment"></a>Использование среды тестирования Office 365 E5

Если вам требуется только среда тестирования Office 365, на этом можно остановиться. 

См. [Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md) для получения дополнительных руководств по лаборатории тестирования, применимых одновременно к Office 365 и Microsoft 365.

### <a name="add-a-microsoft-365-e5-trial-subscription"></a>Добавление пробной подписки Microsoft 365 E5.

Чтобы получить пробную подписку на Microsoft 365 E5 и настроить учетные записи пользователей с лицензиями, выполните инструкции из [этапа 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) руководства по лаборатории тестирования простой базовой конфигурации.

  
## <a name="results"></a>Результаты

Теперь ваша тестовая среда содержит:
  
- Пробную подписку Microsoft 365 E5.
- Все подходящие учетные записи пользователей, готовые к использованию Microsoft 365 E5.
- Смоделированную и упрощенную интрасеть.
    
Это ваша окончательная конфигурация.
  
![Этап 2 базовой конфигурации "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
Теперь вы можете экспериментировать с дополнительными возможностями [Microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Дальнейшие действия

Ознакомьтесь с этими дополнительными комплектами руководств по лаборатории тестирования:
  
- [Идентификация](m365-enterprise-test-lab-guides.md#identity)
- [Управление мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Защита информации](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md)

[Развертывание Microsoft 365 корпоративный](deploy-microsoft-365-enterprise.md)

[Документация по Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365-enterprise/)
