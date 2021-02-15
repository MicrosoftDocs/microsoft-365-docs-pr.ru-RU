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
# <a name="the-simulated-enterprise-base-configuration"></a>Базовая конфигурация "имитация предприятия"

*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 для предприятий и Office 365 корпоративный.*

В этой статье описано, как создать упрощенную среду для Microsoft 365 для предприятий, которая включает:

- Пробная или платная подписка Microsoft 365 E5
- Упрощенная интрасеть организации, подключенная к Интернету и состоящая из трех виртуальных машин в виртуальной сети Azure (DC1, APP1 и CLIENT1).
 
![Базовая конфигурация "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

Создание упрощенной тестовой среды состоит из двух этапов:
- [Этап 1. Создание имитированной интрасети](#phase-1-create-a-simulated-intranet)
- [Этап 2. Создание подписки Microsoft 365 E5](#phase-2-create-your-microsoft-365-e5-subscription)

Вы можете использовать итоговую среду для тестирования функций и функций [](m365-enterprise-test-lab-guides.md) [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise) для предприятий с помощью дополнительных руководств по лаборатории тестирования или самостоятельно.

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Чтобы получить визуальную карту всех статей в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-create-a-simulated-intranet"></a>Этап 1. Создание имитированной интрасети

На этом этапе создайте имитированную интрасеть в службах инфраструктуры Azure, которая включает контроллер домена доменных служб Active Directory (AD DS), сервер приложений и клиентский компьютер.

Вы будете использовать эти компьютеры в дополнительных руководствах по лаборатории тестирования [Microsoft 365](m365-enterprise-test-lab-guides.md) для предприятий для настройки и демонстрации гибридных удостоверений и других возможностей.

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a>Способ 1. Создание имитированной интрасети с помощью шаблона Azure Resource Manager

В этом методе используется шаблон Azure Resource Manager для создания имитированной интрасети. Шаблоны Azure Resource Manager содержат все инструкции по созданию сетевой инфраструктуры Azure, виртуальных машин и их конфигурации.

Перед развертыванием шаблона прочитайте страницу [ШАБЛОНА README](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) и подготовьтесь к следующим сведениям:

- Имя публичного домена DNS тестовой среды (testlab). \<*your public domain*> Это имя будет вводиться в поле **"Доменное имя"** страницы **настраиваемого** развертывания.
- Префикс метки DNS для URL-адресов общедоступных IP-адресов виртуальных машин. Вам понадобится ввести эту метку в поле **Префикс метки DNS** на странице **Настраиваемое развертывание**.

После того как вы прочтете инструкции, выберите "Развернуть в **Azure"** на странице [README шаблона,](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) чтобы начать работу.

>[!Note]
>Для имитации интрасети, построенной по шаблону Azure Resource Manager, требуется платная подписка azure.

После завершения работы шаблона конфигурация выглядит так:

![Имитированная интрасеть в службах инфраструктуры Azure](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a>Способ 2. Создание имитированной интрасети с помощью Azure PowerShell

Этот способ предполагает использование Windows PowerShell и модуля Azure PowerShell для создания сетевой инфраструктуры, виртуальных машин и их конфигурации.

Используйте этот способ, если вы хотите получить возможность создания элементов инфраструктуры Azure шаг за шагом с помощью PowerShell. Затем можно настроить командные блоки PowerShell для самостоятельного развертывания других виртуальных машин в Azure.

#### <a name="step-1-create-dc1"></a>Этап 1. Создание DC1

На этом этапе создается виртуальная сеть Azure и добавляется виртуальная машина DC1, которая является контроллером домена для домена AD DS.

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

Укажите свою подписку Azure. Замените все в кавычках, включая угловые скобки ("<" и ">"), правильным именем.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Затем создайте группу ресурсов для лаборатории тестирования "имитация предприятия". Чтобы определить уникальное имя группы ресурсов, используйте указанную ниже команду для вывода списка имеющихся групп ресурсов.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Создайте группу ресурсов с помощью следующих команд. Замените все кавычек, включая угловые скобки, правильными именами.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Затем создайте виртуальную сеть TestLab, в которой будет работать подсеть корпоративной сети имитированной корпоративной среды, и защитите ее с помощью группы безопасности сети. Уполноможите имя группы ресурсов и запустите эти команды в командной командной области PowerShell на локальном компьютере.
  
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

Вам будет предложено ввести имя пользователя и пароль учетной записи локального администратора на DC1. Задайте надежный пароль и запишите его вместе с именем пользователя в безопасном месте.
  
Затем подключите виртуальную машину DC1:
  
1. На [портале Azure](https://portal.azure.com)выберите группы **ресурсов** > <***имя*** новой группы ресурсов> > **DC1**  >  **Connect.**
    
2. На открытой области выберите **"Загрузить RDP-файл".** Откройте скачаный файл DC1.rdp и выберите **"Подключиться".**
    
3. Укажите имя учетной записи локального администратора DC1:
    
   - Для Windows 7:
    
     В **диалоговом окне "Безопасность Windows"** выберите **"Использовать другую учетную запись".** Введите **имя учетной** **записи локального \\** администратора DC1 <  в>.
    
   - Для Windows 8 и Windows 10:
    
     В **диалоговом окне "Безопасность Windows"** выберите "Дополнительные **варианты"** и выберите **"Использовать другую учетную запись".** Введите **имя учетной** **записи локального \\** администратора DC1 <  в>.
    
4. Введите **пароль** учетной записи локального администратора и выберите **"ОК".**
    
5. При запросе выберите **"Да".**
    
После этого добавьте еще один диск с данными в качестве нового тома с буквой диска "F:", используя приведенные ниже команды в командной строке Windows PowerShell на уровне администратора в DC1.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Затем настройте DC1 как контроллер домена и DNS-сервер для домена **testlab.**\<*your public domain*> . Укажите свое имя публичного домена, удалите угловые скобки и затем запустите эти команды в командной Windows PowerShell на DC1.
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
Потребуется указать пароль администратора для безопасного режима. Храните этот пароль в надежном месте.
  
Обратите внимание, что на выполнение этих команд может потребоваться несколько минут.
  
После перезапуска виртуальной машины DC1 снова подключитесь к ней.
  
1. На [портале Azure выберите](https://portal.azure.com) **группы** ресурсов > <*имя* группы ресурсов> > **DC1**  >  **Connect.**
    
2. Запустите скачаный файл DC1.rdp и выберите **"Подключиться".**
    
3. В **Windows Security** выберите **"Использовать другую учетную запись".** Введите **имя учетной** **записи локального \\** администратора TESTLAB <  в>.
    
4. В поле **"Пароль"** введите пароль учетной записи локального администратора и выберите **"ОК".**
    
5. При запросе выберите **"Да".**
    
Затем создайте учетную запись пользователя в Active Directory, которая будет использоваться при входе на рядовые компьютеры домена TESTLAB. От имени администратора выполните указанную ниже команду в командной строке Windows PowerShell.
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

Обратите внимание на то, что при выполнении этой команды вам будет предложено ввести пароль учетной записи User1. Эта учетная запись будет использоваться для подключений к удаленному рабочему столу для всех компьютеров- членов домена TESTLAB, поэтому выберите надежный пароль. Запишите пароль к учетной записи User1 и храните его в безопасном месте.
  
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

Текущая конфигурация выглядит так:
  
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
  
Чтобы проверить разрешение имен и сетевое взаимодействие между APP1 и DC1, выполните команду **ping dc1.testlab.**\<*your public domain name*> и убедитесь что получено четыре ответа.
  
Затем присоедините виртуальную машину APP1 к домену TESTLAB, выполнив приведенные ниже команды в командной строке Windows PowerShell.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Обратите внимание, что после запуска команды **Add-Computer** необходимо предоставить учетные данные учетной записи домена TESTLAB \\ User1.
  
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

Текущая конфигурация выглядит так:
  
![Этап 2 базовой конфигурации "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a>Этап 3: настройка CLIENT1.

На этом этапе создается и настраивается виртуальная машина CLIENT1, которая выступает в качестве типичного ноутбука, планшета или настольного компьютера в интрасети.

> [!NOTE]  
> Приведенный ниже набор команд создает виртуальную машину CLIENT1 под управлением Windows Server 2016 Datacenter. Это возможно благодаря подпискам на Azure любых типов. Если у вас есть подписка на Azure с Visual Studio, вы можете создать виртуальную машину CLIENT1 под управлением Windows 10 на [портале Azure](https://portal.azure.com).
  
Чтобы создать виртуальную машину Azure для CLIENT1, в заполните имя группы ресурсов и запустите эти команды в командной командной области на локальном компьютере.
  
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
  
Чтобы проверить разрешение имен и сетевое взаимодействие между CLIENT1 и DC1, выполните команду **ping dc1.testlab.**\<*your public domain name*> в командной строке Windows PowerShell и убедитесь, что получено четыре ответа.
  
Затем присоедините виртуальную машину CLIENT1 к домену TESTLAB, выполнив приведенные ниже команды в командной строке Windows PowerShell.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Обратите внимание, что после выполнения команды **Add-Computer** вам потребуется указать данные учетной записи домена TESTLAB\\User1.
  
После перезапуска виртуальной машины CLIENT1 подключитесь к ней, используя учетную запись TESTLAB\\User1, а затем откройте командную строку Windows PowerShell от имени администратора.
  
Затем проверьте доступ к веб-ресурсам и общим файловым ресурсам на APP1 с CLIENT1.
  
1. В диспетчере серверов в области дерева выберите **локальный сервер.**
    
2. In **Properties for CLIENT1**, select **On** next to **IE Enhanced Security Configuration**.
    
3. В **конфигурации усиленной безопасности Internet Explorer** выберите  "Выключите" для администраторов и **пользователей,** а затем выберите  "ОК". 
    
4. На экране "Начните" выберите **Internet Explorer** и выберите **"ОК".**
    
5. В адресной панели введите **http <span>://</span>app1.testab.** \<*your public domain name*> **/** и нажмите ввод .  Вы увидите страницу служб IIS по умолчанию для APP1.
    
6. На панели задач рабочего стола выберите значок проводника.
    
7. В адресной панели введите **\\ \\ app1 \\ Files** и нажмите **ввод**. Вы увидите окно папки с содержимым общей папки Files.
    
8. В окне общей папки **Files** дважды щелкните файл **Example.txt**. Вы увидите содержимое файла Example.txt.
    
9. Закройте окно **example.txt - Блокнот** и окно общей папки **Files**.
    
Текущая конфигурация выглядит так:
  
![Этап 3 базовой конфигурации "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a>Этап 2. Создание подписки Microsoft 365 E5

На этом этапе создается новая подписка Microsoft 365 E5, связанная с новым клиентом Azure AD, независимым от производственной подписки. Это можно сделать двумя способами:

- Использовать пробную подписку Microsoft 365 E5.

  Пробная подписка на Office 365 E5 действительна в течение 30 дней, и этот срок можно легко продлить до 60 дней. После окончания срока действия пробной подписки, необходимо оформить платную подписку или создать новую пробную подписку. Создание новой пробной подписки означает, что вы потеряете свою конфигурацию, которая может включать сложные сценарии.  

- Использовать отдельную производственную подписку на Microsoft 365 E5 с небольшим количеством лицензий.

  Это дополнительные затраты, но гарантирует, что у вас есть рабочая тестовая среда, срок действия которой не истек; в нем можно попробовать функции, конфигурации и сценарии. Вы можете использовать в долгосрочной перспективе ту же тестовую среду для подтверждения концепции, демонстрации для коллег и управления, а также для разработки и тестирования приложений. Это рекомендуемый метод.

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Оформление пробной подписки на Office 365 E5

На портале Azure подключите клиент CLIENT1 с помощью учетной записи CORP\User1.

Чтобы создать пробную подписку на Office 365 E5, выполните инструкции из [этапа 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) руководства по лаборатории тестирования простой базовой конфигурации.

Чтобы настроить новую пробную подписку на Office 365 E5, выполните инструкции из [этапа 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) руководства по лаборатории тестирования простой базовой конфигурации.

#### <a name="using-an-office-365-e5-test-environment"></a>Использование среды тестирования Office 365 E5

Если вам нужна только тестовая среда Office 365, прочитать оставшуюся часть этой статьи не нужно.

Дополнительные руководства по лаборатории тестирования, применимые к Microsoft 365 и Office 365, см. в руководстве по лаборатории тестирования [Microsoft 365 для предприятий.](m365-enterprise-test-lab-guides.md)

### <a name="add-a-microsoft-365-e5-trial-subscription"></a>Добавление пробной подписки Microsoft 365 E5.

Чтобы добавить пробную подписку microsoft 365 E5 и настроить учетные записи пользователей с лицензиями, выполните инструкции на этапе [3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) руководства по лаборатории тестирования для облегченной базовой конфигурации.

  
## <a name="results"></a>Результаты

Теперь ваша тестовая среда содержит:
  
- Пробную подписку Microsoft 365 E5.
- Все подходящие учетные записи пользователей, готовые к использованию Microsoft 365 E5.
- Смоделированную и упрощенную интрасеть.
    
Окончательная конфигурация выглядит так:
  
![Этап 2 базовой конфигурации "имитация предприятия"](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
Теперь вы готовы поэкспериментировать с дополнительными функциями [Microsoft 365 для предприятий.](https://www.microsoft.com/microsoft-365/enterprise)
  
## <a name="next-steps"></a>Дальнейшие действия

Ознакомьтесь с этими дополнительными комплектами руководств по лаборатории тестирования:
  
- [Идентификация](m365-enterprise-test-lab-guides.md#identity)
- [Управление мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Защита информации](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Документация по Microsoft 365 для предприятий](https://docs.microsoft.com/microsoft-365-enterprise/)
