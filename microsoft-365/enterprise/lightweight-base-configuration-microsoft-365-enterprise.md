---
title: Простая базовая конфигурация
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
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
description: Используйте это руководство по лаборатории тестирования для создания облегченной тестовой среды для тестирования Microsoft 365 для предприятия.
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487392"
---
# <a name="the-lightweight-base-configuration"></a>Простая базовая конфигурация

*Это руководство по лаборатории тестирования можно использовать как для Microsoft 365 Enterprise, так и для корпоративных тестовых сред Office 365.*

В этой статье описано, как создать упрощенную среду с подпиской на Microsoft 365 и компьютер под управлением Windows 10 Корпоративная.

![Простая среда тестирования Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Создание упрощенной тестовой среды состоит из пяти этапов:
- [Этап 1: Создание подписки на Microsoft 365](#phase-1-create-your-microsoft-365-e5-subscription)
- [Этап 2. Настройка пробной подписки на Office 365](#phase-2-configure-your-office-365-trial-subscription)
- [Этап 3. Добавление пробной подписки Microsoft 365 E5](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [Этап 4. Создание компьютера с ОС Windows 10 Корпоративная](#phase-4-create-a-windows-10-enterprise-computer)
- [Этап 5. Присоединение компьютера с Windows 10 к Azure AD](#phase-5-join-your-windows-10-computer-to-azure-ad)

Используйте полученную среду для тестирования функций и функций [Microsoft 365 для предприятий](https://www.microsoft.com/microsoft-365/enterprise).

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, ознакомьтесь со статьей " [руководство по лаборатории тестирования для microsoft 365 для предприятий](../downloads/Microsoft365EnterpriseTLGStack.pdf)".

>[!NOTE]
>Можно напечатать эту статью, чтобы записать информацию, которая понадобится вам для этой среды в течение 30 дней пробной подписки на Office 365. Пробную подписку можно легко продлить еще на 30 дней. Чтобы создать постоянную среду тестирования, создайте новую платную подписку с отдельным клиентом Azure AD и с небольшим количеством лицензий.

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>Этап 1: Создание подписки на Microsoft 365

Начнем с пробной подписки Microsoft 365 и добавьте к ней подписку на Microsoft 365.

>[!NOTE]
>Рекомендуется создать пробную подписку на Office 365, чтобы у вашей тестовой среды был отдельный клиент Azure AD из любой платной подписки, имеющейся в данный момент. Это разделение означает, что вы можете добавлять и удалять пользователей и группы в тестовом клиенте, не затрагивая рабочие подписки.

Чтобы оформить пробную подписку Microsoft 365 E5, потребуется вымышленное название компании и новая учетная запись Майкрософт.
  
1. Рекомендуем использовать в качестве названия компании какую-нибудь вариацию имени Contoso (вымышленной компании, используемой в примерах от Майкрософт), но это необязательно. Запишите здесь название своей вымышленной компании: ![Линия](../media/Common-Images/TableLine.png)
    
2. Чтобы зарегистрировать новую учетную запись Майкрософт, перейдите на сайт [https://outlook.com](https://outlook.com) и создайте учетную запись, используя новый адрес электронной почты. Эта учетная запись будет использоваться для регистрации в Office 365.
    
    - Запишите здесь имя и фамилию для новой учетной записи: ![Линия](../media/Common-Images/TableLine.png)
    
    - Запишите здесь адрес электронной почты новой учетной записи: ![Линия](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Оформление пробной подписки на Office 365 E5

1. В браузере перейдите по адресу [https://aka.ms/e5trial](https://aka.ms/e5trial) .
    
2. На шаге 1 **Благодарим вас за выбор страницы Office 365** , введите новый адрес учетной записи электронной почты.
3. На шаге 2 процесса подписки введите требуемые сведения, а затем выполните проверку.
4. На шаге 3 Введите название организации, а затем имя учетной записи, которая будет глобальным администратором для подписки.
5. Запишите сведения страницы входа (выделите и скопируйте) с шага 4 здесь: ![Линия](../media/Common-Images/TableLine.png)
6. Запишите здесь идентификатор пользователя: ![Линия](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Запишите пароль, который вы ввели в надежном расположении.
   Это значение будет называться **именем глобального администратора**.
7. Нажмите кнопку **Перейти к программе установки**.
8. В Office 365, выберите **продолжить использование *вашей организации*. onmicrosoft.com для электронной почты и входа**, а затем выберите команду **выйти и продолжить позже**.

Должен открыться Центр администрирования Microsoft 365.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Этап 2. Настройка пробной подписки на Office 365

На этом этапе настраивается подписка с дополнительными пользователями, этим пользователям назначаются лицензии Office 365 E5.
  
Чтобы подключиться к подписке с помощью модуля Azure Active Directory PowerShell для работы с компьютером, выполните инструкции, приведенные в статье [Подключение к Microsoft 365 с помощью PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
    
В диалоговом окне **запрос учетных данных Windows PowerShell** введите имя глобального администратора (например, *jdoe@contosotoycompany.onmicrosoft.com*) и пароль.
  
Введите название организации (например, *контосотойкомпани*), 2-значный код страны для своего расположения, пароль общего учетной записи, а затем выполните следующие команды в командной консоли PowerShell:

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
> Общий пароль используется для автоматизации и упрощения конфигурации среды тестирования. Очевидно, что это не рекомендуется в производственных подписках. 

### <a name="record-key-information-for-future-reference"></a>Запишите важнейшую информацию для использования в будущем.

Если вы еще не записали эти значения, запишите их сейчас:
  
- Имя глобального администратора: ![Линия](../media/Common-Images/TableLine.png).onmicrosoft.com (с шага 6 этапа 1)
    
    Кроме того, запишите пароль этой учетной записи в надежном месте.
    
- Название вашей организации: ![Линия](../media/Common-Images/TableLine.png) (с шага 4 этапа 1)
    
- Чтобы увидеть список учетных записей пользователей User 2, User 3, User 4 и User 5, выполните следующую команду в командной строке модуля Windows Azure Active Directory для Windows PowerShell:
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    Запишите здесь имена учетных записей:
    
  - Имя учетной записи пользователя User 2: user2@![Линия](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Имя учетной записи пользователя User 3: user3@![Линия](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Имя учетной записи пользователя User 4: user4@![Линия](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Имя учетной записи пользователя User 5: user5@![Линия](../media/Common-Images/TableLine.png).onmicrosoft.com
    
    Кроме того, запишите в надежном месте общий пароль.
   
### <a name="using-an-office-365-test-environment"></a>Использование среды тестирования Office 365

Если вам нужна только тестовая среда Office 365, не нужно читать оставшуюся часть этой статьи.

Дополнительные руководства по лаборатории тестирования, которые относятся как к Office 365, так и к Microsoft 365, представлены в [статье Microsoft 365 for Enterprise Lab Lab Guides](m365-enterprise-test-lab-guides.md).
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Этап 3. Добавление пробной подписки Microsoft 365 E5

На этом этапе можно оформить пробную подписку Microsoft 365 E5 и добавить ее к той же организации, для которой создана пробная подписка на Office 365 E5.
  
Сначала добавьте пробную подписку Microsoft 365 E5 и назначьте новую лицензию Microsoft 365 для учетной записи глобального администратора.
  
1. В частном окне браузера Интернета используйте учетные данные глобального администратора, чтобы войти в центр администрирования Microsoft 365 по адресу [https://admin.microsoft.com](https://admin.microsoft.com) .
    
2. На странице **центра администрирования Microsoft 365** в левой области навигации выберите **выставление счетов > приобрести службы**.
    
3. На странице " **Покупка служб** " выберите пункт **Microsoft 365**об/д и выберите **получить бесплатную пробную версию**.

4. На странице **пробная версия Microsoft 365** , выберите Получение текстового сообщения или телефонного звонка, введите свой номер телефона, а затем выберите текстовые или **текстовые письма** или **позвонить мне**. Выполните проверку.

5. На странице **Подтверждение заказа** нажмите кнопку **попробовать сейчас**.

6. На странице **прием заказов** нажмите кнопку **продолжить**.

7. В центре администрирования Microsoft 365 выберите **пользователи > активные пользователи**.

8. В окне **Активные пользователи**выберите учетную запись администратора.

9. Выберите **лицензии и приложения**.

10. Отключите лицензию для Office 365 корпоративный E5 и включите лицензию для Microsoft 365 E5.

11. Нажмите кнопку **сохранить изменения**, а затем закройте область сведений об учетной записи пользователя.

Затем повторите действия с 8 по 11 из предыдущей процедуры для всех остальных учетных записей (User 2, User 3, User 4 и User 5).
  
> [!NOTE]
> Продолжительность пробной подписки Microsoft 365 в течение 30 дней. Чтобы создать постоянную среду тестирования, переведите пробную подписку в платную подписку с небольшим количеством лицензий.
  
Теперь ваша тестовая среда содержит:
  
- Пробную подписку Microsoft 365 E5.
- Все подходящие учетные записи пользователей (либо только глобального администратора или всех пяти пользователей), поддерживающие Microsoft 365 E5.
    
Результирующая конфигурация, в которой добавляется Microsoft 365, выглядит следующим образом:
  
![Этап 3 разработки тестовой среды, включающей Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Этап 4. Создание компьютера с ОС Windows 10 Корпоративная

На этом этапе мы создадим изолированный компьютер с Windows 10 Корпоративная в виде физического компьютера либо виртуальной машины (обычной или в Azure).
  
### <a name="physical-computer"></a>Физический компьютер

На персональном компьютере установите Windows 10 Корпоративная. Пробную версию Windows 10 Корпоративная можно скачать [здесь](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine"></a>Виртуальная машина

Создайте виртуальную машину с помощью низкоуровневой оболочки, а затем установите Windows 10 Корпоративная. Пробную версию Windows 10 Корпоративная можно скачать [здесь](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine-in-azure"></a>Виртуальная машина в Azure

Для создания виртуальной машины с Windows 10 в Microsoft Azure ***необходима подписка на основе Visual Studio*** с доступом к образу Windows 10 Корпоративная. В других типах подписок Azure, например пробной или платной, подобный доступ отсутствует. Последние сведения по этой теме см. в статье [Использование клиента Windows в Azure для сценариев разработки и тестирования](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> Для указанных ниже последовательностей команд используется последняя версия Azure PowerShell. Обратитесь к разделу начало [работы с командлетами Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Эти наборы команд создают виртуальную машину под управлением Windows 10 Корпоративная с именем WIN10, а также всю необходимую инфраструктуру, включая группу ресурсов, учетную запись хранения и виртуальную сеть. Если вы уже знакомы со службами инфраструктуры Azure, разработайте эти инструкции в соответствии с развернутой в настоящее время инфраструктурой.
  
Для начала запустите командную строку Microsoft PowerShell.
  
Войдите в свою учетную запись Azure с помощью указанной ниже команды.
  
```powershell
Connect-AzAccount
```

Получите имя подписки с помощью этой команды.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Укажите свою подписку Azure. Замените все в кавычках, включая \< and > символы, на правильное имя.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Затем создайте группу ресурсов. Чтобы выбрать уникальное имя для группы ресурсов, с помощью этой команды отобразите имеющиеся группы ресурсов.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Создайте группу ресурсов с помощью следующих команд. Замените все в кавычках, включая \< and > символы, на правильные имена.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Затем создайте новую виртуальную сеть и виртуальную машину WIN10 с помощью этих команд. При появлении запроса укажите имя и пароль учетной записи локального администратора WIN10 и сохраните их в надежном месте.
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a>Этап 5. Присоединение компьютера с Windows 10 к Azure AD

После создания физической или виртуальной машины с Windows 10 Корпоративная войдите в систему, используя учетную запись локального администратора.
  
> [!NOTE]
> Чтобы подключиться к виртуальной машине в Azure, выполните  [указанные ниже действия](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) .
  
Затем присоедините компьютер WIN10 к клиенту Azure AD, отвечающему за вашу подписку на Microsoft 365 E5.
  
1. На рабочем столе компьютера WIN10 нажмите кнопку **пуск > параметры > учетные записи > доступ к работе или учебному > Connect**.
    
2. В диалоговом окне **Настройка рабочей или учебной учетной записи** выберите **присоединить это устройство к Azure Active Directory**.
    
3. В поле **Рабочая или учебная учетная запись**введите имя учетной записи глобального администратора для подписки Microsoft 365 и нажмите кнопку **Далее**.
    
4. В поле **Введите пароль**введите пароль для учетной записи глобального администратора, а затем нажмите кнопку **войти**.
    
5. Когда отобразится запрос о том, что это ваша организация, нажмите кнопку **присоединиться**, а затем нажмите кнопку **Готово**.
    
6. Закройте окно параметров.
    
Затем установите Microsoft 365 Apps для предприятий на компьютере с WIN10:
  
1. Откройте браузер Microsoft EDGE и войдите в [центр администрирования microsoft 365](https://admin.microsoft.com) с учетной записью глобального администратора.
    
2. На **главной вкладке Microsoft Office** выберите пункт **Установка Office**.
    
3. При появлении соответствующего запроса нажмите кнопку **выполнить**, а затем выберите **Да** для **контроля учетных записей пользователей**.
    
4. Подождите, пока Office завершит установку. Когда вы увидите **все готово!** нажмите кнопку **Закрыть** дважды.
    
Результирующая среда выглядит следующим образом:

![Этап 5 разработки тестовой среды, включающей Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Эта среда включает компьютер с Windows 10, который:

- присоединен к клиенту Azure AD, отвечающему за подписку Microsoft 365 E5;
- зарегистрирован в Microsoft Intune (EMS) в качестве устройства Azure AD;
- Приложения Microsoft 365 для Enterprise установлены.
  
Теперь вы можете поэкспериментировать с дополнительными возможностями [Microsoft 365 для предприятий](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Дальнейшие действия

Ознакомьтесь с этими дополнительными комплектами руководств по лаборатории тестирования:
  
- [Идентификация](m365-enterprise-test-lab-guides.md#identity)
- [Управление мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Защита информации](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Microsoft 365 для корпоративных документов](https://docs.microsoft.com/microsoft-365-enterprise/)
