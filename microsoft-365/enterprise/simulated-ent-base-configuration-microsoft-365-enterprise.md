---
title: Базовая конфигурация "имитация предприятия" для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Это руководство по лаборатории тестирования поможет вам создать имитацию предприятия для Microsoft 365 корпоративный.
ms.openlocfilehash: 98eb336a0f63f47b4b79de44c46fcd81f1d9c9f6
ms.sourcegitcommit: 2bdd7b535a7d2a4896df130b7047f8c85f4d47b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2019
ms.locfileid: "38711883"
---
# <a name="the-simulated-enterprise-base-configuration"></a>Базовая конфигурация "имитация предприятия"

*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 корпоративный и Office 365 корпоративный.*

В этой статье вы найдете пошаговые инструкции по созданию упрощенной среды для Microsoft 365 корпоративный, которая включает:

- Пробная или платная подписка Microsoft 365 E5
- упрощенную интрасеть организации, подключенную к Интернету и состоящую из трех виртуальных машин в виртуальной сети Azure (DC1, APP1 и CLIENT1).
 
![Базовая конфигурация "имитация предприятия"](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

Вы можете использовать полученную среду для тестирования функций [Microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise) с дополнительными [руководствами по лаборатории тестирования](m365-enterprise-test-lab-guides.md) или без них.

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Щелкните [здесь](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.

## <a name="phase-1-create-a-simulated-intranet"></a>Этап 1. Создание имитированной интрасети

На этом этапе вы создаете имитацию интрасети в службах инфраструктуры Azure, которая включает контроллер домена Active Directory Domain Services (AD DS), сервер приложений и клиентский компьютер. 

Вы будете использовать эти компьютеры в дополнительных [Руководствах по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md) для настройки и демонстрации гибридных удостоверений и других возможностей.

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a>Способ 1. Создание имитированной интрасети с помощью шаблона Azure Resource Manager

Этот способ предполагает использование шаблона Azure Resource Manager (ARM) для создания имитации интрасети. Шаблоны ARM содержат все необходимые инструкции для создания сетевой инфраструктуры, виртуальных машин и их конфигурации.

Перед развертыванием шаблона ознакомьтесь со [страницей сведений шаблона (README)](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) и приготовьте приведенные ниже сведения.

- DNS-имя общедоступного домена вашей тестовой среды (testlab.\<ваш общедоступный домен>). Вам понадобится ввести это имя в поле **Доменное имя** на странице **Настраиваемое развертывание**.
- Префикс метки DNS для URL-адресов общедоступных IP-адресов виртуальных машин. Вам понадобится ввести эту метку в поле **Префикс метки DNS** на странице **Настраиваемое развертывание**.

После ознакомления с инструкциями нажмите **Развертывание в Azure** на [странице сведений шаблона (README)](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems), чтобы приступить к работе.

>[!Note]
>Для имитации интрасети, созданной на основе шаблона ARM, требуется платная подписка Azure.
>

Ниже показана итоговая конфигурация после завершения работы с шаблоном.

![Имитированная интрасеть в службах инфраструктуры Azure](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a>Способ 2. Создание имитированной интрасети с помощью Azure PowerShell

Этот способ предполагает использование Windows PowerShell и модуля Azure PowerShell для создания сетевой инфраструктуры, виртуальных машин и их конфигурации.

Используйте этот способ, если вы хотите получить возможность создания элементов инфраструктуры Azure шаг за шагом с помощью PowerShell. Затем можно настроить командные блоки PowerShell для самостоятельного развертывания других виртуальных машин в Azure.

#### <a name="step-1-create-dc1"></a>Этап 1. Создание DC1

На этом этапе создается виртуальная сеть Azure и добавляется виртуальная машина DC1, которая является контроллером домена AD DS.

Сначала запустите командную строку Windows PowerShell на локальном компьютере.
  
> [!NOTE]
> Для приведенных ниже последовательностей команд используется последняя версия Azure PowerShell. См. статью [Общие сведения об Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). 
  
Войдите в свою учетную запись Azure с помощью указанной ниже команды.
  
```powershell
Connect-AzAccount
```

Получите имя подписки с помощью следующей команды.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Укажите свою подписку Azure. Замените текст в кавычках, в том числе символы < и >, правильным именем.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Затем создайте группу ресурсов для лаборатории тестирования "имитация предприятия". Чтобы определить уникальное имя группы ресурсов, используйте указанную ниже команду для вывода списка имеющихся групп ресурсов.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Создайте группу ресурсов с помощью приведенных ниже команд. Замените все символы в кавычках (в том числе символы < и >) правильными именами.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

После этого создайте виртуальную сеть TestLab, в которой будет размещаться подсеть Corpnet моделируемой среды предприятия, и защитите ее с помощью группы сетевой безопасности. Укажите имя своей группы ресурсов и выполните эти команды в командной строке PowerShell на локальном компьютере.
  
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

Затем создайте виртуальную машину DC1 и настройте ее как контроллер домена для **testlab.**\<ваш публичный домен > домен AD DS и DNS-сервер для виртуальных машин виртуальной сети TestLab. Например, если ваше имя публичного домена — **<span>contoso</span>.com**, виртуальная машина DC1 будет контроллером домена **<span>testlab</span>.contoso.com**.
  
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

Вам будет предложено ввести имя пользователя и пароль учетной записи локального администратора на DC1. Задайте надежный пароль и запишите его вместе с именем пользователя в безопасном месте.
  
После этого подключитесь к виртуальной машине DC1.
  
1. На [портале Azure](https://portal.azure.com) выберите **Группы ресурсов >** [имя новой группы ресурсов] **> DC1 > Подключить**.
    
2. В открытой области выберите элемент **Скачать RDP-файл**. Откройте скачанный файл DC1.rdp и нажмите **Подключить**.
    
3. Укажите имя учетной записи локального администратора DC1:
    
   - Для Windows 7:
    
     В диалоговом окне **Безопасность Windows** выберите элемент **Использовать другую учетную запись**. В поле **Имя пользователя** введите **DC1\\**[имя локальной учетной записи администратора].
    
   - Для Windows 8 и Windows 10:
    
     В диалоговом окне **Безопасность Windows** нажмите **Больше вариантов**, а затем — **Использовать другую учетную запись**. В поле **Имя пользователя** введите **DC1\\**[имя учетной записи локального администратора].
    
4. В поле **Пароль** укажите пароль к учетной записи локального администратора, а затем нажмите кнопку **ОК**.
    
5. Когда появится соответствующий запрос, нажмите кнопку **Да**.
    
После этого добавьте еще один диск с данными в качестве нового тома с буквой диска "F:", используя приведенные ниже команды в командной строке Windows PowerShell на уровне администратора в DC1.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Затем настройте DC1 в качестве контроллера домена и DNS-сервера для домена **testlab.**\<ваш публичный домен>. Укажите имя своего публичного домена, удалите символы \< и >, а затем выполните эти команды в командной строке Windows PowerShell от имени администратора на DC1.
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
Потребуется указать пароль администратора для безопасного режима. Храните этот пароль в надежном месте.
  
Обратите внимание, что на выполнение этих команд может потребоваться несколько минут.
  
После перезапуска виртуальной машины DC1 снова подключитесь к ней.
  
1. На [портале Azure](https://portal.azure.com) выберите элементы **Группы ресурсов >** [имя вашей группы ресурсов] ** DC1 > Подключить**.
    
2. Запустите скачанный файл DC1.rdp, а затем нажмите **Подключить**.
    
3. В разделе **Безопасность Windows** нажмите **Использовать другую учетную запись**. В поле **Имя пользователя** введите **TESTLAB\\**[имя учетной записи локального администратора].
    
4. В поле **Пароль** укажите пароль к учетной записи локального администратора, а затем нажмите кнопку **ОК**.
    
5. Когда появится соответствующий запрос, нажмите кнопку **Да**.
    
Затем создайте учетную запись пользователя в Active Directory, которая будет использоваться при входе в систему на компьютерах, входящих в домен TESTLAB. От имени администратора выполните указанную ниже команду в командной строке Windows PowerShell.
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

Обратите внимание на то, что при выполнении этой команды вам будет предложено ввести пароль учетной записи User1. Так как эта учетная запись будет использоваться для подключения к удаленному рабочему столу для всех компьютеров, входящих в домен TESTLAB, используйте надежный пароль. Запишите пароль к учетной записи User1 и храните его в безопасном месте.
  
Затем сделайте новую учетную запись User1 учетной записью администратора домена, предприятия и схемы. От имени администратора выполните приведенную ниже команду в командной строке Windows PowerShell.
  
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
  
![Шаг 1 базовой конфигурации "имитация предприятия"](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
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
  
Чтобы проверить разрешение имен и сетевое подключение между APP1 и DC1, выполните команду **ping dc1.testlab.**\<имя вашего публичного домена> и убедитесь, что поступило четыре ответа.
  
Затем присоедините виртуальную машину APP1 к домену TESTLAB, выполнив приведенные ниже команды в командной строке Windows PowerShell.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
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
  
![Этап 2 базовой конфигурации "имитация предприятия"](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a>Этап 3: настройка CLIENT1.

На этом этапе создается и настраивается виртуальная машина CLIENT1, которая выступает в качестве типичного ноутбука, планшета или настольного компьютера в интрасети.

> [!NOTE]  
> Приведенный ниже набор команд создает виртуальную машину CLIENT1 под управлением Windows Server 2016 Datacenter. Это возможно благодаря подпискам на Azure любых типов. Если у вас есть подписка на Azure с Visual Studio, то вы можете создать виртуальную машину CLIENT1 под управлением Windows 10 на [портале Azure](https://portal.azure.com). 
  
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
  
Чтобы проверить разрешение имен и сетевое подключение между CLIENT1 и DC1, выполните команду **ping dc1.testlab.**\<имя вашего публичного домена> в командной строке Windows PowerShell и убедитесь, что поступило четыре ответа.
  
Затем присоедините виртуальную машину CLIENT1 к домену TESTLAB, выполнив приведенные ниже команды в командной строке Windows PowerShell.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

Обратите внимание, что после выполнения команды **Add-Computer** вам потребуется указать данные учетной записи домена TESTLAB\\User1.
  
После перезапуска виртуальной машины CLIENT1 подключитесь к ней, используя учетную запись TESTLAB\\User1, а затем откройте командную строку Windows PowerShell от имени администратора.
  
Затем проверьте доступ к веб-ресурсам и общим файловым ресурсам на APP1 с CLIENT1.
  
1. В области дерева диспетчера серверов выберите **Локальный сервер**.
    
2. В поле **Свойства CLIENT1** выберите значение **Вкл.** для параметра **Конфигурация усиленной безопасности Internet Explorer**.
    
3. В разделе **Конфигурация усиленной безопасности Internet Explorer** для параметров **Администраторы** и **Пользователи** выберите значение **Выкл.** и нажмите кнопку **ОК**.
    
4. На начальном экране выберите **Internet Explorer** и нажмите кнопку **ОК**.
    
5. В адресной строке введите **http<span>://</span>app1.testab.**\<имя вашего публичного домена>**/** и нажмите клавишу ВВОД. Вы увидите веб-страницу служб IIS по умолчанию для APP1.
    
6. Нажмите значок проводника на панели задач рабочего стола.
    
7. В адресной строке браузера введите **\\\\app1\\Files**, а затем нажмите клавишу ВВОД. Откроется окно папки с содержимым общей папки Files.
    
8. В окне общей папки **Files** дважды щелкните файл **Example.txt**. Вы увидите содержимое файла Example.txt.
    
9. Закройте окно **example.txt - Блокнот** и окно общей папки **Files**.
    
Это ваша текущая конфигурация.
  
![Этап 3 базовой конфигурации "имитация предприятия"](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a>Этап 2. Создание подписки Microsoft 365 E5

На этом этапе создается новая подписка Microsoft 365 E5, связанная с новым клиентом Azure AD, независимым от производственной подписки. Это можно сделать двумя способами:

- Использовать пробную подписку Microsoft 365 E5. 

  Пробная подписка на Office 365 E5 действительна в течение 30 дней, и этот срок можно легко продлить до 60 дней. После окончания срока действия пробной подписки, необходимо оформить платную подписку или создать новую пробную подписку. Создание новой пробной подписки означает, что вы потеряете свою конфигурацию, которая может включать сложные сценарии.  

- Использовать отдельную производственную подписку на Microsoft 365 E5 с небольшим количеством лицензий.

  Это дополнительные затраты, но в результате вы получите рабочую тестовую среду для тестирования функций, конфигураций и сценарий, срок действия которой не истечет. Вы можете использовать ту же среду тестирования для доказательства правильности концепций, демонстрации возможностей для коллег и руководства, а также разработки и тестирования приложений. Это рекомендуемый метод.

Чтобы оформить пробную подписку Microsoft 365 E5, потребуется вымышленное название компании и новая учетная запись Майкрософт.
  
1. Рекомендуем использовать в качестве названия компании какую-нибудь вариацию имени Contoso (вымышленной компании, используемой в примерах от Майкрософт), но это необязательно. Запишите здесь название своей вымышленной компании: ![](./media/Common-Images/TableLine.png)
    
2. Чтобы зарегистрировать новую учетную запись Майкрософт, перейдите на сайт [https://outlook.com](https://outlook.com) и создайте учетную запись, используя новый адрес электронной почты. Эта учетная запись будет использоваться для регистрации в Office 365.
    
  - Запишите имя и фамилию новой учетной записи здесь: ![](./media/Common-Images/TableLine.png)
    
  - Запишите здесь адрес электронной почты новой учетной записи: ![](./media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Оформление пробной подписки на Office 365 E5

Мы начнем с пробной подписки на Office 365 E5, а затем добавим к ней подписку Microsoft 365 E5.

1. Для среды разработки и тестирования Office 365, имитирующей предприятие, подключитесь к виртуальной машине CLIENT1 на портале Azure, используя учетную запись CORP\User1.  На начальном экране запустите Microsoft Edge и перейдите по адресу [https://aka.ms/e5trial](https://aka.ms/e5trial).
    
2. На странице **приветствия** укажите:
    
  - ваше физическое местонахождение;
    
  - имя и фамилию новой учетной записи Майкрософт;
    
  - новый адрес электронной почты;
    
  - рабочий телефон;
    
  - вымышленное название компании;
    
  - размер организации (250–999 человек).
    
3. Нажмите **Еще одно действие**.
    
4. На странице **создание идентификатора пользователя** введите имя пользователя на основе нового адреса электронной почты, название вымышленной компании после знака @ (удалите все пробелы в названии) и пароль (дважды) для новой учетной записи Office 365. 
    
    Запишите пароль в надежном месте.
    
    Запишите вымышленное название компании (**название организации**) здесь: ![](./media/Common-Images/TableLine.png)
    
5. Нажмите **Создать мою учетную запись**.
    
6. На странице **Докажите. Что. Вы. Не. Робот.** введите номер телефона, поддерживающего текстовые сообщения, а затем нажмите **Отправить мне SMS**.
    
7. Введите код подтверждения из полученного SMS и нажмите **Далее**.
    
8. Запишите здесь URL-адрес страницы входа (выделите и скопируйте): ![](./media/Common-Images/TableLine.png)
    
9. Запишите здесь идентификатор пользователя (выделите и скопируйте): ![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
    Это значение будет называться **именем глобального администратора Office 365**.
    
10. Когда появится надпись **Все готово к работе**, нажмите ее.
    
11. На следующей странице дождитесь завершения настройки Office 365 и появления всех плиток.
    
Появится главная страница портала Office 365, с которой можно получить доступ к службам Office и Центру администрирования Microsoft 365.
  
Вы создали пробную подписку на Office 365, поэтому среда разработки и тестирования имеет собственный клиент Azure AD, отличный от использующихся для любых доступных платных подписок. Это разделение означает, что вы можете добавлять и удалять пользователей и группы в тестовом клиенте, никак не влияя на рабочие подписки.
    
### <a name="configure-your-office-365-e5-trial-subscription"></a>Настройка пробной подписки на Office 365 E5

После этого нужно настроить подписку на Office 365 E5 с дополнительными пользователями, этим пользователям назначаются лицензии Office 365 E5.
  
Следуйте указаниям в статье [Подключение к Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module), чтобы подключить подписку на Office 365 с модулем PowerShell Azure Active Directory для Graph к виртуальной машине CLIENT1.
    
В диалоговом окне "Запрос учетных данных Windows PowerShell" введите имя глобального администратора Office 365 (например, jdoe@contosotoycompany.onmicrosoft.com) и пароль.
  
Введите название организации (например, contosotoycompany), двузначный код страны и пароль обычной учетной записи, а затем выполните следующие команды в командной строке PowerShell:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> Общий пароль используется для автоматизации и упрощения конфигурации среды разработки и тестирования. Очевидно, что это не рекомендуется в производственных подписках. 

#### <a name="record-key-information-for-future-reference"></a>Запишите важнейшую информацию для использования в будущем.

Можно напечатать эту статью, чтобы записать информацию, которая понадобится вам для этой среды в течение 30 дней пробной подписки на Office 365. Пробную подписку можно легко продлить еще на 30 дней. Чтобы создать постоянную среду тестирования и разработки, создайте новую платную подписку с отдельным клиентом Azure AD и с небольшим количеством лицензий.

Запишите эти значения:
  
- Имя глобального администратора Office 365: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (с шага 9 этапа 2)
    
    Кроме того, запишите пароль этой учетной записи в надежном месте.
    
- Название организации с пробной подпиской: ![](./media/Common-Images/TableLine.png) (с шага 4 этапа 2)
    
- Чтобы увидеть список учетных записей пользователей User 2, User 3, User 4 и User 5, выполните следующую команду в командной строке модуля Windows Azure Active Directory для Windows PowerShell:
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    Запишите здесь имена учетных записей:
    
  - Имя учетной записи пользователя User 2: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Имя учетной записи пользователя User 3: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Имя учетной записи пользователя User 4: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Имя учетной записи пользователя User 5: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
    Кроме того, запишите в надежном месте общий пароль.
   

#### <a name="using-an-office-365-e5-devtest-environment"></a>Использование среды разработки и тестирования Office 365 E5

Если вам требуется только среда разработки и тестирования Office 365, то на этом можно остановиться. 

См. [Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md) для получения дополнительных руководств по лаборатории тестирования, применимых одновременно к Office 365 и Microsoft 365.
  
### <a name="add-a-microsoft-365-e5-trial-subscription"></a>Добавление пробной подписки Microsoft 365 E5.

Теперь нужно оформить пробную подписку Microsoft 365 E5 и добавить ее к той же организации, для которой создана пробная подписка на Office 365 E5.
  
Сначала добавьте пробную подписку Microsoft 365 E5 и назначьте лицензию Microsoft 365 для учетной записи глобального администратора.
  
1. С помощью закрытого экземпляра интернет-браузера войдите в Центр администрирования Microsoft 365 [https://admin.microsoft.com](https://admin.microsoft.com), используя данные учетной записи глобального администратора.
    
2. На странице **Центра администрирования Microsoft 365**, в области навигации слева, нажмите **Выставление счетов > Приобретение служб**.
    
3. На странице **Приобретение служб** найдите пункт **Microsoft 365 E5**. Наведите на него указатель мыши и выберите **Начать бесплатный пробный период**.

4. На странице **Пробная версия Microsoft 365 E5** выберите текстовое сообщение или звонок, введите свой номер телефона, затем нажмите кнопку **Отправить сообщение** или **Позвонить мне**.

5. На странице **Подтверждение заказа** нажмите кнопку **Попробовать**.

6. На странице **Получение заказа** нажмите кнопку **Продолжить**.

7. В центре администрирования Microsoft 365 щелкните **Активные пользователи**, а учетную запись администратора.

8. Нажмите **Изменить****лицензии продукта**.

9. Отключите лицензию для Office 365 корпоративный E5 и включите лицензию для Microsoft 365 E5.

10. Нажмите **Сохранить и закрыть**.

Затем повторите действия с 8 по 11 из предыдущей процедуры для всех остальных учетных записей (User 2, User 3, User 4 и User 5).
  
> [!NOTE]
> Период действия пробной подписки Microsoft 365 E5 равен 30 дням. Для среды постоянного тестирования переведите пробную подписку в платную подписку с небольшим количеством лицензий. 
  
### <a name="results"></a>Результаты

Теперь ваша тестовая среда содержит:
  
- Пробную подписку Microsoft 365 E5.
- Все подходящие учетные записи пользователей, готовые к использованию Microsoft 365 E5.
- Смоделированную и упрощенную интрасеть.
    
Это ваша окончательная конфигурация.
  
![Этап 2 базовой конфигурации "имитация предприятия"](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
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
