---
title: Федеративная идентификация для среды тестирования Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: Сводка. Сведения о настройке федеративной аутентификации для среды тестирования Microsoft 365.
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487688"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>Федеративная идентификация для среды тестирования Microsoft 365

*Это руководство по тестовой лаборатории можно использовать как для Microsoft 365, так и для Office 365 корпоративный среды тестирования.*

Microsoft 365 поддерживает федеративную идентификацию. Это означает, что Microsoft 365 не проверяет непосредственно учетные данные, а направляет подключающегося пользователя на сервер федеративной проверки подлинности, которому доверяет Microsoft 365. Если учетные данные пользователя правильны, сервер федеративной проверки подлинности выдает маркер безопасности, который клиент затем отправляет в Microsoft 365 как подтверждение проверки подлинности. Федеративная идентификация позволяет разгрузить и масштабировать проверку подлинности для подписки Microsoft 365, а также реализовать расширенные сценарии проверки подлинности и безопасности.
  
В этой статье описывается настройка федератированной проверки подлинности для Microsoft 365 тестовой среды, в результате чего ниже дается следующее:

![Федеративная аутентификация для среды тестирования Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
Конфигурация состоит из следующих компонентов:
  
- Пробная Microsoft 365 E5 или производственная подписка.
    
- Упрощенная интрасеть организации, подключенная к Интернету, состоящая из пяти виртуальных машин в подсети виртуальной сети Azure (DC1, APP1, CLIENT1, ADFS1 и PROXY1). Azure AD Подключение app1 для синхронизации списка учетных записей в домене Active Directory Domain Services с Microsoft 365. PROXY1 получает входящие запросы аутентификации. ADFS1 проверяет учетные данные с помощью DC1 и выдает маркеры безопасности.
    
Настройка этой тестовой среды включает пять этапов:
- [Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Этап 2. Создание сервера AD FS](#phase-2-create-the-ad-fs-server)
- [Этап 3. Создание веб-прокси-сервера](#phase-3-create-the-web-proxy-server)
- [Этап 4. Создание самозаверяющего сертификата и настройка ADFS1 и PROXY1](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [Этап 5. Настройка федеративной идентификации для Microsoft 365](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> Эту тестовую среду нельзя настроить подпиской Azure Trial.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365

Следуйте инструкциям в [синхронизации с хашированием паролей для Microsoft 365](password-hash-sync-m365-ent-test-environment.md). В результате конфигурация выглядит так:
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
Конфигурация состоит из следующих компонентов:
  
- Пробная Microsoft 365 E5 или платная подписка.
- Упрощенная интрасеть организации, подключенная к Интернету, состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure. Azure AD Подключение app1 для синхронизации домена TESTLAB Active Directory Domain Services (AD DS) с клиентом Azure AD Microsoft 365 подписки.

## <a name="phase-2-create-the-ad-fs-server"></a>Этап 2. Создание сервера AD FS

Сервер AD FS обеспечивает федеративную аутентификацию между Microsoft 365 и учетными записями в домене corp.contoso.com, размещенном на DC1.
  
Чтобы создать виртуальную машину Azure для ADFS1, укажите имя своей подписки, группы ресурсов и расположение Azure для базовой конфигурации, а затем выполните указанные ниже команды в командной строке Azure PowerShell на локальном компьютере.
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

После этого на [портале Azure](https://portal.azure.com) подключитесь к виртуальной машине ADFS1, используя имя и пароль учетной записи локального администратора ADFS1. Затем откройте командную строку Windows PowerShell.
  
Чтобы проверить разрешение имен и сетевое подключение между ADFS1 и DC1, выполните команду **ping dc1.corp.contoso.com** и убедитесь, что поступило четыре ответа.
  
Далее присоедините виртуальную машину ADFS1 к домену CORP, выполнив указанные ниже команды в командной строке Windows PowerShell на ADFS1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

В результате конфигурация выглядит так:
  
![Сервер AD FS добавлен в DirSync для среды тестирования Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a>Этап 3. Создание веб-прокси-сервера

PROXY1 обеспечивает передачу сообщений аутентификации через прокси-соединения между подключающимися пользователями и ADFS1.
  
Чтобы создать виртуальную машину Azure для PROXY1, укажите имя группы ресурсов, расположение Azure, а затем выполните указанные ниже команды в командной строке Azure PowerShell на локальном компьютере.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> Машине PROXY1 присваивается статический общедоступный IP-адрес, который не должен меняться при перезапуске виртуальной машины PROXY1, так как на него указывает созданная вами общедоступная запись DNS.
  
Далее добавьте правило в группу сетевой безопасности для подсети CorpNet, чтобы разрешить нежелательный входящий трафик из Интернета на частный IP-адрес PROXY1 и порт TCP 443. Выполните эти команды в командной строке Azure PowerShell на локальном компьютере.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

После этого подключитесь к виртуальной машине PROXY1 на [портале Azure](https://portal.azure.com), используя имя и пароль учетной записи локального администратора PROXY1. Затем откройте командную строку Windows PowerShell на PROXY1.
  
Чтобы проверить разрешение имен и сетевое подключение между PROXY1 и DC1, выполните команду **ping dc1.corp.contoso.com** и убедитесь, что поступило четыре ответа.
  
Далее присоедините виртуальную машину PROXY1 к домену CORP, выполнив указанные ниже команды в командной строке Windows PowerShell на PROXY1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Отображайте общедоступный IP-адрес PROXY1 с Azure PowerShell команд на локальном компьютере.
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

После этого обратитесь к своему поставщику общедоступных DNS и создайте запись A для имени **fs.testlab.**\<*your DNS domain name*>, которая разрешается в IP-адрес, отображаемый командой **Write-Host**. Имя **fs.testlab.**\<*your DNS domain name*> далее именуется *FQDN службы федерации*.
  
После этого воспользуйтесь учетными данными CORP\\User1 на [портале Azure](https://portal.azure.com), чтобы подключиться к виртуальной машине DC1, а затем выполните следующие команды в командной строке Windows PowerShell, открытой от имени администратора:
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
Эти команды создают внутреннюю запись DNS A, чтобы виртуальные машины виртуальной сети Azure могли разрешить внутреннюю службу федерации FQDN на закрытый IP-адрес ADFS1.
  
В результате конфигурация выглядит так:
  
![Прокси-сервер веб-приложений добавлен в DirSync для среды тестирования Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>Этап 4. Создание самозаверяющего сертификата и настройка ADFS1 и PROXY1

На этом этапе создается самозаверяющий цифровой сертификат для полного доменного имени службы федерации и настраиваются ADFS1 и PROXY1 как ферма AD FS.
  
Сначала подключитесь к виртуальной машине DC1 на [портале Azure](https://portal.azure.com), используя учетные данные CORP\\User1, а затем откройте командную строку Windows PowerShell от имени администратора. 
  
Далее создайте учетную запись службы AD FS с этой командой в командной Windows PowerShell на DC1:
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
Обратите внимание, что при выполнении этой команды вам будет предложено ввести пароль учетной записи. Выберите надежный пароль и запишите его в безопасном месте. Она понадобится для этого этапа и для фазы 5.
  
Подключитесь к виртуальной машине ADFS1 на [портале Azure](https://portal.azure.com), используя учетные данные CORP\\User1. Откройте командную строку Windows PowerShell на ADFS1 от имени администратора, введите FQDN службы федерации и выполните следующие команды для создания самозаверяющего сертификата:
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

После этого выполните указанные ниже действия, чтобы сохранить новый самозаверяющий сертификат в виде файла.
  
1. Выберите **Начните,** **введитеmmc.exe,** а затем нажмите **кнопку Ввод**.
    
2. Выберите **добавление**  >  **или удаление прикрепление файлов**.
    
3. В **добавлении или прикрепление-инах**  дважды щелкните Сертификаты в списке доступных оснастки, выберите учетную запись Компьютера **и** выберите **Далее**.
    
4. В **Выберите компьютер** выберите **Готово**, а затем выберите **ОК**.
    
5. В области дерева выберите **Сертификаты (локальный компьютер) > Личное > Сертификаты**.
    
6. Выберите и удерживайте (или правой кнопкой мыши) сертификат с FQDN службы федерации, выберите все **задачи,** а затем выберите **Экспорт**.
    
7. На странице **Welcome** выберите **Далее**.
    
8. На странице **Экспорт частный ключ** выберите **Да,** а затем выберите **Далее**.
    
9. На странице **Формат файла экспорта** выберите экспорт всех расширенных **свойств** и выберите **Далее**.
    
10. На странице **Безопасность** выберите **пароль и** введите пароль в **Password** и **Подтверди пароль.**
    
11. На странице **"Файл на экспорт"** выберите **Просмотр**.
    
12. Просмотрите **папку C: \\ Certs,** введите **SSL** в **имени файла** и выберите **Сохранить.**
    
13. На странице **Файл для экспорта** выберите **Далее**.
    
14. На странице **Завершение мастера экспорта сертификатов** выберите **Finish**. При запросе выберите **ОК**.
    
После этого установите службу AD FS, выполнив следующую команду в командной строке Windows PowerShell на ADFS1:
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

Дождитесь завершения установки.
  
После этого выполните указанные ниже действия, чтобы настроить службу AD FS.
  
1. Выберите **Начните,** а затем выберите **значок Server Manager.**
    
2. В области дерева диспетчера серверов выберите **AD FS**.
    
3. В панели инструментов в верхней части выберите оранжевый символ осторожности, а затем выберите Настройка службы **федерации на этом сервере.**
    
4. На странице **Welcome** мастера настройки служб Федерации active Directory выберите **Далее**.
    
5. На странице **Подключение AD DS** выберите **Далее**.
    
6. На странице **Настройка свойств службы**:
    
  - Для **сертификата SSL** выберите стрелку вниз, а затем выберите сертификат с именем службы федерации FQDN.
    
  - В **имя отображения службы Федерации** введите имя вымышленной организации.
    
  - Нажмите кнопку **Далее**.
    
7. На странице **Укажите имя** учетной записи службы **выберите Выберите** **имя учетной записи.**
    
8. В **выберите учетную запись** пользователя или службы введите **ADFS-Service,** выберите **Имена** проверки, а затем выберите **ОК**.
    
9. В **пароль учетной** записи введите пароль для ADFS-Service учетной записи, а затем выберите **Далее**.
    
10. На странице **Указать конфигурацию базы данных** выберите **Далее**.
    
11. На странице **Параметры обзора** выберите **Далее**.
    
12. На странице **Предварительные проверки** выберите **Настройка**.

13. На странице **Результаты** выберите **Закрыть**.
    
14. Выберите **Пуск,** выберите значок питания, **перезапустите,** а затем выберите **Продолжить**.
    
Откройте [портал Azure](https://portal.azure.com) и подключитесь к PROXY1, используя учетные данные CORP\\User1.
  
После этого выполните указанные ниже действия, чтобы установить самозаверяющий сертификат на **PROXY1 и APP1**.
  
1. Выберите **Начните,** **введитеmmc.exe,** а затем нажмите **кнопку Ввод**.
    
2. Выберите **файл > добавить или удалить прикрепление в**.
    
3. В **добавлении или прикрепление-инах**  дважды щелкните Сертификаты в списке доступных оснастки, выберите учетную запись Компьютера **и** выберите **Далее**.
    
4. В **Выберите компьютер** выберите **Готово**, а затем выберите **ОК**.
    
5. В области дерева откройте **сертификаты (локальный компьютер)**  >    >  **Персональные сертификаты**.
    
6. Выберите и удерживайте (или правой кнопкой мыши) **Личное,** выберите **все задачи,** а затем выберите **Импорт**.
    
7. На странице **Welcome** выберите **Далее**.
    
8. На странице **Файл импорт введите** **\\ \\ adfs1 \\ certs \\ ssl.pfx,** а затем выберите **Далее**.
    
9. На странице **Защиты личных ключей** введите пароль сертификата в **Password,** а затем выберите **Далее.**
    
10. На странице **Магазина сертификатов** выберите **Далее.**
    
11. На странице **Завершение выберите** **Finish**.
    
12. На странице **Хранилище сертификатов** выберите **Далее**.
    
13. При запросе выберите **ОК**.
    
14. В области дерева выберите **Сертификаты.**
    
15. Выберите и удерживайте (или правой кнопкой мыши) сертификат, а затем выберите **Copy**.
    
16. В области дерева откройте сертификаты **доверенных** корневых  >  **органов сертификации.**
    
17. Переместите указатель мыши ниже списка установленных сертификатов, выберите и удерживайте (или правой кнопкой мыши), а затем выберите **Вастер**.
    
Откройте командную строку администратора PowerShell и выполните следующую команду:
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

Дождитесь завершения установки.
  
Сделайте так, чтобы прокси-служба веб-приложения использовала ADFS1 в качестве сервера федерации:
  
1. Выберите **Начните,** а затем выберите **диспетчер сервера.**
    
2. В области дерева выберите **удаленный доступ.**
    
3. В панели инструментов в верхней части выберите оранжевый символ осторожности и выберите Мастер прокси-сервера **Веб-приложения**.
    
4. На странице **Welcome** мастера конфигурации прокси-серверов веб-приложения выберите **Далее**.
    
5. На странице **Сервер федерации**:
    
  - В поле **имя службы Федерации** введите FQDN службы федерации.
    
  - В поле **Имя пользователя** введите **CORP \\ User1**.
    
  - В поле **Пароль** введите пароль для учетной записи User1.
    
  - Нажмите кнопку **Далее**.
    
6. На странице **AD FS Proxy Certificate** выберите стрелку вниз, выберите сертификат с помощью службы федерации FQDN и выберите **Далее**.
    
7. На странице **Подтверждение** выберите **Настройка**.
    
8. На странице **Результаты** выберите **Закрыть**.
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>Этап 5. Настройка федеративной идентификации для Microsoft 365

Используйте учетные данные CORP\\User1 на [портале Azure](https://portal.azure.com), чтобы подключиться к виртуальной машине APP1.
  
Выполните следующие действия, чтобы настроить федеративную проверку подлинности для Azure AD Connect и подписки Microsoft 365:
  
1. На рабочем столе дважды щелкните значок **Azure AD Connect**.
    
2. На странице **Welcome to Azure AD** Подключение **настройка**.
    
3. На странице **Дополнительные задачи** выберите **изменить вход** пользователя, а затем выберите **Далее**.
    
4. На странице **Подключение Azure AD введите** имя и пароль учетной записи глобального администратора, а затем выберите **Далее**.
    
5. На странице **Вход пользователя** выберите Федерацию с **AD FS,** а затем выберите **Далее**.
    
6. На странице **фермы AD FS** выберите Использование существующей фермы **AD FS,** введите **ADFS1** в поле **Имя** сервера, а затем выберите **Далее**.
    
7. При запросе учетных данных сервера введите учетные данные учетной записи CORP \\ User1 и выберите **ОК.**
    
8. На странице **учетные данные** администратора домена введите **CORP \\ User1** в поле **Username,** введите пароль учетной записи в поле **Пароль,** а затем выберите **Далее**.
    
9. На странице учетной записи службы **AD FS** введите **CORP \\ ADFS-Service** в поле **Имя** пользователя домена, введите пароль учетной записи в поле **Пароль** пользователя домена и выберите **Далее**.
    
10. На странице **Azure AD Domain** в **Домене** выберите имя домена, который вы ранее создали и добавили в подписку на этапе 1, а затем выберите **Далее**.
    
11. На странице **Готово к настройке** выберите **Настройка**.
    
12. На странице **Полная установка выберите** **Проверить**.
    
    Вы должны видеть сообщения, указывающие, что и интрасеть, и конфигурация Интернета проверены.
    
13. На странице **Полная установка** выберите **Exit**.
    
Действия для демонстрации работы федеративной аутентификации:
  
1. Откройте новый частный экземпляр браузера на локальном компьютере и перейдите по адресу [https://admin.microsoft.com](https://admin.microsoft.com).
    
2. Для учетных данных входа введите **user1@** \<*the domain created in Phase 1*> .
    
    Например, если тестовый домен **testlab.contoso.com,** введите "user1@testlab.contoso.com". Нажмите **клавишу Tab** или Microsoft 365 автоматически перенаправить вас.
    
    Теперь вы должны видеть, **что ваше подключение не является закрытой страницей.** Это происходит из-за установки самозаверяемого сертификата на ADFS1, который настольный компьютер не может проверить. В производственном развертывании федератированной проверки подлинности используется сертификат из доверенного органа сертификации, и пользователи не увидят эту страницу.
    
3. На странице **Подключение не является закрытым,** выберите **Расширенный**, а затем **\<*your federation service FQDN*>** выберите Продолжить . 
    
4. На странице с именем вымышленной организации войдите с помощью следующих учетных данных:
    
  - имя **CORP\\User1**;
    
  - пароль учетной записи User1.
    
    Откроется **Домашняя страница Microsoft Office**.
    
Эта процедура демонстрирует, что между пробной подпиской и доменом AD DS corp.contoso.com, размещенным на DC1, настроена федеративная проверка подлинности. Вот как устроен процесс проверки подлинности:
  
1. Когда вы используете федеративный домен, созданный на этапе 1, в имени учетной записи для входа, Microsoft 365 перенаправляет ваш браузер на полное доменное имя службы федерации и PROXY1.
    
2. PROXY1 направляет локальный компьютер на страницу входа вымышленной организации.
    
3. Когда вы отправляете имя CORP\\User1 и пароль на PROXY1, сервер пересылает эти данные на ADFS1.
    
4. ADFS1 проверяет имя CORP\\User1 и пароль с помощью DC1 и отправляет на локальный компьютер токен безопасности.
    
5. Локальный компьютер отправляет маркер безопасности в Microsoft 365.
    
6. Microsoft 365 проверяет, действительно ли маркер безопасности создан в ADFS1, и разрешает доступ.
    
Теперь для вашей пробной подписки настроена федеративная проверка подлинности. Вы можете использовать эту среду разработки и тестирования для расширенных сценариев проверки подлинности.
  
## <a name="next-step"></a>Следующий шаг

Когда вы готовы развернуть федерационную проверку подлинности с высокой доступностью для Microsoft 365 Azure, см. в статью Развертывание федерарной проверки подлинности с высокой доступностью для Microsoft 365 [в Azure.](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
