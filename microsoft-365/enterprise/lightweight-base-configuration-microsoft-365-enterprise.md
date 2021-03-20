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
description: Используйте это руководство по тестовой лаборатории для создания легкой тестовой среды для тестирования Microsoft 365 для предприятия.
ms.openlocfilehash: 2de0760cef7339f62229575b1e0a54b3c67a4e9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909710"
---
# <a name="the-lightweight-base-configuration"></a>Простая базовая конфигурация

*Это руководство по тестовой лаборатории можно использовать для microsoft 365 для корпоративных и корпоративных тестовых сред Office 365.*

В этой статье описывается создание упрощенной среды с подпиской на Microsoft 365 E5 и компьютером под управлением Windows 10 Enterprise.

![Простая среда тестирования Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Создание легкой тестовой среды включает пять этапов:
- [Этап 1. Создание подписки на Microsoft 365 E5](#phase-1-create-your-microsoft-365-e5-subscription)
- [Этап 2. Настройка пробной подписки на Office 365](#phase-2-configure-your-office-365-trial-subscription)
- [Этап 3. Добавление пробной подписки Microsoft 365 E5](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [Этап 4. Создание компьютера с ОС Windows 10 Корпоративная](#phase-4-create-a-windows-10-enterprise-computer)
- [Этап 5. Присоединение компьютера с Windows 10 к Azure AD](#phase-5-join-your-windows-10-computer-to-azure-ad)

Используйте среду для тестирования функций и функций [Microsoft 365 для предприятия.](https://www.microsoft.com/microsoft-365/enterprise)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Визуальную карту для всех статей в стеке Microsoft 365 для корпоративной лаборатории тестирования см. в статье [Microsoft 365 для](../downloads/Microsoft365EnterpriseTLGStack.pdf)корпоративного руководства по тестовой лаборатории.

>[!NOTE]
>Можно напечатать эту статью, чтобы записать информацию, которая понадобится вам для этой среды в течение 30 дней пробной подписки на Office 365. Пробную подписку можно легко продлить еще на 30 дней. Чтобы создать постоянную среду тестирования, создайте новую платную подписку с отдельным клиентом Azure AD и с небольшим количеством лицензий.

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>Этап 1. Создание подписки на Microsoft 365 E5

Мы начинаем с пробной подписки Microsoft 365 E5, а затем добавляем к ней подписку Microsoft 365 E5.

>[!NOTE]
>Рекомендуется создать пробную подписку на Office 365, чтобы в тестовой среде был отдельный клиент Azure AD от всех платных подписок, которые у вас есть в настоящее время. Это разделение означает, что вы можете добавлять и удалять пользователей и группы в тестовом клиенте, не затрагивая производственные подписки.

Чтобы оформить пробную подписку Microsoft 365 E5, потребуется вымышленное название компании и новая учетная запись Майкрософт.
  
1. Рекомендуем использовать в качестве названия компании какую-нибудь вариацию имени Contoso (вымышленной компании, используемой в примерах от Майкрософт), но это необязательно. Запишите здесь название своей вымышленной компании: ![Линия](../media/Common-Images/TableLine.png)
    
2. Чтобы зарегистрировать новую учетную запись Майкрософт, перейдите на сайт [https://outlook.com](https://outlook.com) и создайте учетную запись, используя новый адрес электронной почты. Эта учетная запись будет использоваться для регистрации в Office 365.
    
    - Запишите здесь имя и фамилию для новой учетной записи: ![Линия](../media/Common-Images/TableLine.png)
    
    - Запишите здесь адрес электронной почты новой учетной записи: ![Линия](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Оформление пробной подписки на Office 365 E5

1. В браузере перейдите к [https://aka.ms/e5trial](https://aka.ms/e5trial) .
    
2. На шаге 1 из "Спасибо" за выбор страницы **Office 365 E5** введите новый адрес учетной записи электронной почты.
3. На шаге 2 процесса подписки на маршрут введите запрашиваемую информацию и выполните проверку.
4. На шаге 3 введите имя организации, а затем имя учетной записи, которое будет глобальным администратором для подписки.
5. Запишите сведения страницы входа (выделите и скопируйте) с шага 4 здесь: ![Линия](../media/Common-Images/TableLine.png)
6. Запишите здесь идентификатор пользователя: ![Линия](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Запись пароля, который вы ввели в безопасном расположении.
   Это значение будет называться **именем глобального администратора**.
7. Выберите **Перейти к настройке**.
8. В Office 365 E5 Setup выберите Продолжить использование организации **.onmicrosoft.com** для электронной почты и регистрации, а затем выберите **Exit и продолжить позже.**

Должен открыться Центр администрирования Microsoft 365.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Этап 2. Настройка пробной подписки на Office 365

На этом этапе настраивается подписка с дополнительными пользователями, этим пользователям назначаются лицензии Office 365 E5.
  
Чтобы подключиться к подписке с помощью модуля Azure Active Directory PowerShell для Graph с компьютера, используйте инструкции в [Connect to Microsoft 365 с PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
    
В **диалоговом окне Windows PowerShell запроса** учетных данных введите имя глобального администратора (например, *jdoe@contosotoycompany.onmicrosoft.com)* и пароль.
  
Заполните имя организации (например, *contosotoycompany),* код страны с двумя символами для вашего расположения, общий пароль учетной записи, а затем запустите следующие команды из запроса PowerShell:

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

Если вы еще не записали эти значения, зафиксировать их сейчас:
  
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

Если вам нужна только тестовая среда Office 365, вам не нужно читать остальную часть этой статьи.

Дополнительные руководства по тестовой лаборатории, применимые как к Office 365, так и к [Microsoft 365,](m365-enterprise-test-lab-guides.md)см. в справочниках Microsoft 365 для корпоративной лаборатории тестирования.
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Этап 3. Добавление пробной подписки Microsoft 365 E5

На этом этапе можно оформить пробную подписку Microsoft 365 E5 и добавить ее к той же организации, для которой создана пробная подписка на Office 365 E5.
  
Сначала добавьте пробную подписку Microsoft 365 E5 и назначьте новую лицензию Microsoft 365 для учетной записи глобального администратора.
  
1. В частном окне интернет-браузера используйте учетные данные глобальной учетной записи администратора, чтобы войти в центр администрирования Microsoft 365 в [https://admin.microsoft.com](https://admin.microsoft.com) .
    
2. На странице Центра администрирования **Microsoft 365** в левой навигации выберите службы > **покупки.**
    
3. На странице **Службы покупки** выберите **Microsoft 365 E5** и выберите **бесплатную пробную пробную версия.**

4. На странице Пробная версия **Microsoft 365 E5** решите получить текстовое сообщение или телефонный звонок, введите номер телефона, а затем выберите **Text me** или Call **me**. Выполните проверку.

5. На странице **Подтвердите свой заказ,** выберите **Попробуйте сейчас**.

6. На странице **получения заказа** выберите **Продолжить**.

7. В центре администрирования Microsoft 365 выберите Пользователи > **активных пользователей.**

8. В **active users** выберите учетную запись администратора.

9. Выберите **лицензии и приложения.**

10. Отключите лицензию для Office 365 корпоративный E5 и включите лицензию для Microsoft 365 E5.

11. Выберите **сохранить изменения,** а затем закроем области сведений о учетной записи пользователя.

Затем повторите действия с 8 по 11 из предыдущей процедуры для всех остальных учетных записей (User 2, User 3, User 4 и User 5).
  
> [!NOTE]
> Продолжительность пробной подписки Microsoft 365 E5 составляет 30 дней. Чтобы создать постоянную среду тестирования, переведите пробную подписку в платную подписку с небольшим количеством лицензий.
  
Теперь ваша тестовая среда содержит:
  
- Пробную подписку Microsoft 365 E5.
- Все подходящие учетные записи пользователей (либо только глобального администратора или всех пяти пользователей), поддерживающие Microsoft 365 E5.
    
Итоговая конфигурация, которая добавляет Microsoft 365 E5, выглядит так:
  
![Этап 3 разработки тестовой среды, включающей Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Этап 4. Создание компьютера с ОС Windows 10 Корпоративная

На этом этапе мы создадим изолированный компьютер с Windows 10 Корпоративная в виде физического компьютера либо виртуальной машины (обычной или в Azure).
  
### <a name="physical-computer"></a>Физический компьютер

На персональном компьютере установите Windows 10 Enterprise. Вы можете скачать пробную версии Windows 10 Enterprise [здесь](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine"></a>Виртуальная машина

Используйте гипервизор по вашему выбору, чтобы создать виртуальную машину, а затем установить на нее Windows 10 Enterprise. Вы можете скачать пробную версии Windows 10 Enterprise [здесь](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine-in-azure"></a>Виртуальная машина в Azure

Для создания виртуальной машины с Windows 10 в Microsoft Azure ***необходима подписка на основе Visual Studio*** с доступом к образу Windows 10 Корпоративная. В других типах подписок Azure, например пробной или платной, подобный доступ отсутствует. Последние сведения по этой теме см. в статье [Использование клиента Windows в Azure для сценариев разработки и тестирования](/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> Для указанных ниже последовательностей команд используется последняя версия Azure PowerShell. См. [в рублях Начало работы с помощью cmdlets Azure PowerShell.](/powershell/azureps-cmdlets-docs/) Эти наборы команд создают виртуальную машину под управлением Windows 10 Корпоративная с именем WIN10, а также всю необходимую инфраструктуру, включая группу ресурсов, учетную запись хранения и виртуальную сеть. Если вы уже знакомы со службами инфраструктуры Azure, адаптируем эти инструкции в соответствии с развернутой инфраструктурой.
  
Для начала запустите командную строку Microsoft PowerShell.
  
Войдите в свою учетную запись Azure с помощью указанной ниже команды.
  
```powershell
Connect-AzAccount
```

Получите имя подписки с помощью этой команды.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Укажите свою подписку Azure. Замените все в кавычках, включая \< and > символы, правильным именем.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Затем создайте группу ресурсов. Чтобы выбрать уникальное имя для группы ресурсов, с помощью этой команды отобразите имеющиеся группы ресурсов.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Создайте группу ресурсов с помощью следующих команд. Замените все в кавычках, включая \< and > символы, правильными именами.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Далее создайте новую виртуальную сеть и виртуальную машину WIN10 с этими командами. При появлении запроса укажите имя и пароль учетной записи локального администратора WIN10 и сохраните их в надежном месте.
  
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
> Для виртуальной машины в Azure используйте  [эти инструкции](/azure/virtual-machines/windows/connect-logon) для подключения к ней.
  
Затем присоедините компьютер WIN10 к клиенту Azure AD, отвечающему за вашу подписку на Microsoft 365 E5.
  
1. На рабочем столе компьютера WIN10 выберите **Параметры >** параметров > учетных записей > access или > Connect .
    
2. В **диалоговом окне Настройка** работы или учебной учетной записи выберите Присоединитесь к этому устройству **в Azure Active Directory.**
    
3. В **work или учебной учетной** записи введите имя глобальной учетной записи администратора подписки Microsoft 365 E5 и выберите **Далее**.
    
4. В **введите пароль,** введите пароль для глобальной учетной записи администратора, а затем выберите **Вход** в .
    
5. Если вам будет предложено убедиться, что это ваша организация, выберите **Присоединиться,** а затем выберите **Готово.**
    
6. Закройте окно параметров.
    
Далее установите приложения Microsoft 365 для предприятия на компьютере WIN10:
  
1. Откройте браузер Microsoft Edge и вопишитесь в центр администрирования [Microsoft 365](https://admin.microsoft.com) с учетными данными глобальной учетной записи администратора.
    
2. На **вкладке Microsoft Office Главная** выберите **Установите Office**.
    
3. При запросе, что делать, выберите **Выполнить,** а затем выберите **Да** для **управления учетной записью пользователя**.
    
4. Подождите, пока Office завершит установку. Когда вы **видите, что вы все установлено!**, выберите **Закрыть дважды.**
    
Итоговая среда выглядит так:

![Этап 5 разработки тестовой среды, включающей Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Эта среда включает компьютер с Windows 10, который:

- присоединен к клиенту Azure AD, отвечающему за подписку Microsoft 365 E5;
- зарегистрирован в Microsoft Intune (EMS) в качестве устройства Azure AD;
- Установленные приложения Microsoft 365 для предприятия.
  
Теперь вы готовы поэкспериментировать с дополнительными [функциями Microsoft 365 для предприятия.](https://www.microsoft.com/microsoft-365/enterprise)
  
## <a name="next-steps"></a>Дальнейшие действия

Ознакомьтесь с этими дополнительными комплектами руководств по лаборатории тестирования:
  
- [Идентификация](m365-enterprise-test-lab-guides.md#identity)
- [Управление мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Защита информации](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Документация по Microsoft 365 для предприятий](/microsoft-365-enterprise/)