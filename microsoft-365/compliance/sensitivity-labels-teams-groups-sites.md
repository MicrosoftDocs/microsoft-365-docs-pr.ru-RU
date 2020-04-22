---
title: Использование меток конфиденциальности на сайтах Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint (общедоступная предварительная версия)
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Чтобы защитить контент на сайтах SharePoint и Microsoft Teams, а также в группах Microsoft 365, используйте метки конфиденциальности.
ms.openlocfilehash: b9ca945ac90ab27d3bc25f1022070eff4737bc10
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631306"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites-public-preview"></a>Использование меток конфиденциальности для защиты контента на сайтах Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint (общедоступная предварительная версия)

>*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*

Создав метки конфиденциальности в [Центре соответствия требованиям Microsoft 365](https://protection.office.com/), вы можете применять их к следующим контейнерам: сайты Microsoft Teams, группы Microsoft 365 и сайты SharePoint. Используйте следующие параметры метки, чтобы защитить содержимое этих контейнеров:

- Конфиденциальность сайтов групп (общедоступных или закрытых), подключенных к группам Microsoft 365
- Доступ внешних пользователей
- Доступ с неуправляемых устройств 

Когда вы применяете эту метку к поддерживаемому контейнеру, метка автоматически применяет настроенные параметры к подключенному сайту или группе. 

Однако содержимое таких контейнеров не наследует метки для таких параметров, как имя метки, наглядная маркировка или шифрование. Чтобы пользователи могли маркировать свои документы на сайтах SharePoint или групповых сайтах, [включите метки чувствительности для файлов Office в SharePoint и OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="about-the-public-preview-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a>Сведения об общедоступной предварительной версии для сайтов Microsoft Teams, групп Microsoft 365 и сайтов SharePoint

Метки конфиденциальности для сайтов Microsoft Teams, групп Microsoft 365 и сайтов SharePoint постепенно развертываются среди клиентов и могут измениться до окончательного выпуска. Эта общедоступная предварительная версия не работает в сетях доставки содержимого Office 365 (CDN).

До включения этой предварительной версии и настройки новых параметров меток конфиденциальности пользователи могут просматривать и применять метки конфиденциальности в своих приложениях. Например, в Word:

![Метка конфиденциальности, отображаемая в классическом приложении Word](../media/sensitivity-label-word.png)

После включения и настройки этой предварительной версии пользователи смогут дополнительно просматривать и применять метки конфиденциальности к сайтам Microsoft Teams, группам Microsoft 365 и сайтам SharePoint. Например, при создании нового сайта группы в SharePoint:

![Метка конфиденциальности при создании сайта группы в SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a>Включение этой предварительной версии и синхронизация меток

1. Так как эта функция использует функциональные возможности Azure AD, то для включения предварительной версии следуйте инструкциям из документации Azure AD: [Назначение меток конфиденциальности группам Microsoft 365 в Azure Active Directory (предварительная версия)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).

2. Теперь [подключитесь к PowerShell Центра безопасности и соответствия требованиям Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
    
    Например, в сеансе PowerShell, который вы запускаете как администратор, войдите в систему с помощью учетной записи глобального администратора.
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

3. Выполните следующие команды для синхронизации ваших меток конфиденциальности с Azure AD, чтобы их можно было использовать с группами Microsoft 365:
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>Настройка параметров сайта и группы при создании или изменении меток конфиденциальности

Теперь вы можете создавать или изменять метки конфиденциальности, которые должны быть доступны для сайтов и групп. При включении предварительной версии в мастере присвоения меток конфиденциальности появится новая страница: **Параметры сайта и группы**.

Если вам нужна помощь по созданию или изменению метки конфиденциальности, см. инструкции в статье [Создание и настройка меток конфиденциальности](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).

На этой новой странице **Параметры сайта и группы** настройте параметры:

- **Конфиденциальность сайтов групп, подключенных к группам Microsoft 365**: Установка по умолчанию **Никто – позволить пользователю выбрать, кто имеет доступ к сайту** в настоящее время развертывается для клиентов. Оставьте этот параметр по умолчанию, если вы хотите защитить содержимое в контейнере с помощью метки чувствительности, но при этом разрешите пользователям самим настраивать параметры конфиденциальности.
    
    Выберите **Публичный** или **Приватный**, чтобы установить и заблокировать настройку конфиденциальности при применении этого ярлыка к контейнеру. Выберите **Публичный**, если вы хотите, чтобы кто-либо в вашей организации имел доступ к сайту группы или группе, к которой применяется этот ярлык, или **Приватный**, если вы хотите, чтобы доступ был ограничен только утвержденными участниками в вашей организации. 
    
    Параметр **Общий** или **Частный** заменяет любой предыдущий параметр конфиденциальности, который может быть настроен для группы или группы, и блокирует значение конфиденциальности, чтобы его можно было изменить, только сначала удалив метку чувствительности из контейнера. После удаления метки чувствительности настройки конфиденциальности из метки остаются, и пользователи теперь могут изменить их снова.

- **Доступ внешних пользователей**. Определяет, может ли владелец группы [добавлять гостей в группу](/office365/admin/create-groups/manage-guest-access-in-groups).

- **Неуправляемые устройства**. Для [неуправляемых устройств](/sharepoint/control-access-from-unmanaged-devices) можно разрешить полный доступ, доступ только через Интернет или полностью заблокировать доступ. 

![Вкладка "Параметры сайта и группы"](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> Когда вы применяете метку к команде, группе или сайту, в силу вступают только эти параметры сайта и группы. Другие параметры метки, например шифрование и маркировка контента, не применяются к содержимому в команде, группе или на сайте.
> 
> Постепенное развертывание для арендаторов: только ярлыки с настройками сайта и группы будут доступны для выбора при создании пользователями групп, групп и сайтов. Если в настоящее время вы можете применить метку к контейнеру, когда для метки не включены настройки сайта и группы, к контейнеру применяется только имя метки.

Если метка конфиденциальности еще не опубликована, опубликуйте ее, [добавив в политику меток конфиденциальности](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy). Пользователи, которым назначена политика меток конфиденциальности, включающая эту метку, смогут выбирать ее для сайтов и групп.

Из политики меток только параметр политики **Применить эту метку по умолчанию к документам**, и электронная почта применима при применении этой метки к контейнерам. Другие параметры политики не применяются, включая обязательную маркировку, требующую обоснования пользователя и ссылку на пользовательскую страницу справки.

## <a name="sensitivity-label-management"></a>Управление метками конфиденциальности

> [!WARNING]
> Создание, изменение и удаление меток конфиденциальности, используемых для сайтов Microsoft Teams, групп Microsoft 365 и сайтов SharePoint, требует тщательного соотнесения с политикой публикации меток для пользователей. 

Чтобы избежать создания ошибок для сайтов и групп, которые могут повлиять на всех пользователей, воспользуйтесь следующим руководством.

**Создание и публикация меток**

После создания и публикации метки может потребоваться до 24 часов, чтобы она стала видимой для пользователей команд, групп и сайтов. Чтобы опубликовать метку для всех пользователей в клиенте, используйте следующие действия:

1. Создайте метку конфиденциальности и опубликуйте ее лишь для нескольких учетных записей пользователей в клиенте.

2. Подождите 24 часа.

3. После 24-часового ожидания используйте одну из учетных записей пользователей, указанных в действии 1, чтобы создать команду, группу Microsoft 365 или сайт SharePoint с меткой, созданной в действии 1.

4. Если в действии 3 операции создания не возникают ошибки, опубликуйте метку для всех пользователей в клиенте. При возникновении ошибок обратитесь в [службу поддержки Майкрософт](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

**Изменение и удаление опубликованных меток**

Если вы измените или удалите метку чувствительности с включенными настройками сайта и группы, и эта метка будет включена в одну или несколько политик меток, эти действия могут привести к сбоям при создании для всех команд, групп и сайтов. Чтобы избежать этой ситуации, используйте следующее руководство:

1. Удалите метку конфиденциальности из всех политик меток, содержащих ее.

2. Подождите 48 часов.

3. После 48-часового ожидания попробуйте создать команду, группу или сайт и убедитесь, что метка больше не отображается.

4. Если метка конфиденциальности не отображается, вы можете безопасно изменить или удалить ее. Если метка по-прежнему отображается, обратитесь в [службу поддержки Майкрософт](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

## <a name="assign-sensitivity-labels-to-microsoft-365-groups"></a>Назначение меток конфиденциальности группам Microsoft 365

Теперь вы можете применить метки или метку конфиденциальности к группам Microsoft 365. Инструкции см. в документации Azure AD:

- [Назначение метки новой группе на портале Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [Назначение метки существующей группе на портале Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  [Удаление метки из существующей группы на портале Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>Применение метки конфиденциальности к новой команде

Пользователи могут выбирать метки конфиденциальности при создании новых команд в Microsoft Teams. При выборе метки в раскрывающемся списке **Чувствительность** параметр конфиденциальности может измениться, чтобы отразить конфигурацию метки. В зависимости от параметра доступа внешних пользователей, выбранного для метки, пользователи могут или не могут добавлять в команду людей из-за пределов организации.

[Дополнительные сведения о метках конфиденциальности для Teams](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![Параметр конфиденциальности при создании новой команды](../media/privacy-setting-new-team.png)

После создания команды метка конфиденциальности отображается в правом верхнем углу всех каналов.

![Отображение метки конфиденциальности в команде](../media/privacy-setting-teams.png)

Служба автоматически применяет такую же метку конфиденциальности к группе Microsoft 365 и подключенному сайту команды SharePoint.

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a>Применение метки конфиденциальности к новой группе в Outlook в Интернете

В Outlook в Интернете при создании группы можно выбрать или изменить параметр **Конфиденциальность** для опубликованных меток:

![Создание группы и выбор параметра в разделе "Конфиденциальность"](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>Применение метки конфиденциальности к новому сайту

Администраторы и конечные пользователи могут выбирать метки чувствительности [при создании современных сайтов групп и сайтов связи](/sharepoint/create-site-collection) и расширять **дополнительные параметры**:

![Создание сайта и выбор параметра в разделе "Конфиденциальность"](../media/sensitivity-label-new-communication-site.png)

В раскрывающемся списке отображаются имена меток для выбора, а значок справки отображает все имена меток с их подсказкой, которая может помочь пользователям определить правильную метку для применения.

Когда метка применяется, и пользователи переходят на сайт, они видят название метки и применяемые политики. Например, этот сайт был помечен как **конфиденциальный**, а для параметра конфиденциальности установлено значение **Личное**:

![Сайт с примененной меткой конфиденциальности](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a>Просмотр меток конфиденциальности в Центре администрирования SharePoint

Чтобы просмотреть примененные метки конфиденциальности, используйте страницу **Активные сайты** в новом Центре администрирования SharePoint. Возможно, сначала потребуется добавить столбец **Конфиденциальность**:

![Столбец "Конфиденциальность" на странице "Активные сайты"](../media/manage-site-sensitivity-labels.png)

[Дополнительные сведения об управлении сайтами в новом Центре администрирования SharePoint](/sharepoint/manage-sites-in-new-admin-center).

## <a name="change-site-and-group-settings-for-a-label"></a>Изменение параметров сайта и группы для метки

Когда осуществляется изменение параметров сайта и группы для метки, требуется выполнить следующие команды PowerShell, чтобы ваши команды, сайты и группы могли использовать новые параметры. Рекомендуется не изменять параметры сайта и группы для метки после применения метки конфиденциальности к нескольким командам, группам или сайтам.

1. Сначала [подключитесь к PowerShell Центра безопасности и соответствия требованиям Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
    
    Например, в сеансе PowerShell, который вы запускаете как администратор, войдите в систему с помощью учетной записи глобального администратора.
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. Получите список меток конфиденциальности с их GUID с помощью командлета [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps).
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. Запишите GUID для измененных меток.

4. Теперь [подключитесь к PowerShell Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
    Например,
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```
    
5. запустите командлет [Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps), указав GUID вашей метки вместо GUID примера "e48058ea-98e8-4940-8db0-ba1310fd955e": 
    
    ```powershell
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

6. Для каждой группы повторно примените метку конфиденциальности, указав GUID метки вместо GUID примера "e48058ea-98e8-4940-8db0-ba1310fd955e":
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a>Поддержка меток конфиденциальности

Вы можете использовать метки конфиденциальности, настроенные для параметров сайта и группы, в следующих приложениях и службах:

- SharePoint Online
- Teams
- Outlook в Интернете
- Центр администрирования SharePoint
- Центр администрирования Azure AD

Другие приложения и службы, в которых пока нельзя использовать метки конфиденциальности, настроенные для параметров сайта и группы, включают:

- Outlook для Mac
- Outlook Mobile
- Классическая версия Outlook для Windows
- Forms
- Dynamics 365
- Yammer
- Stream
- Планировщик
- Project
- PowerBI
- Центр администрирования Teams
- Центр администрирования Microsoft 365
- Центр администрирования Exchange


## <a name="classic-azure-ad-group-classification"></a>Классическая классификация групп Azure AD

Если вы включите эту предварительную версию, Microsoft 365 больше не будет поддерживать старые классификации для новых групп Office 365 и сайтов SharePoint. Однако существующие группы и сайты по-прежнему будут отображать старые значения классификации, если их не преобразовать для использования меток конфиденциальности.

В качестве примера использования старой классификации групп для SharePoint см. статью [Классификация "современных" сайтов SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).

Эти классификации были настроены с помощью Azure AD PowerShell или основной библиотеки PnP и определяют значения параметра `ClassificationList`. Если в вашем клиенте определены значения классификации, они отображаются при выполнении следующей команды из [модуля AzureADPreview PowerShell](https://www.powershellgallery.com/packages/AzureADPreview):

```powershell
   ($setting["ClassificationList"])
```

Чтобы преобразовать старые классификации для использования меток конфиденциальности, выполните одно из следующих действий:

- Используйте существующие метки. Укажите нужные параметры меток для сайтов и групп, изменив опубликованные метки конфиденциальности.

- Создайте новые метки. Укажите нужные параметры меток для сайтов и групп, создав и опубликовав новые метки конфиденциальности с такими же именами, как в существующих классификациях.

Затем: 

1. Используйте PowerShell, чтобы применить метки конфиденциальности к существующим группам Microsoft 365 и сайтам SharePoint с помощью сопоставления имен. Соответствующие инструкции см. в следующем разделе.

2. Удалите старые классификации из существующих групп и сайтов.

Хотя вы не можете запретить пользователям создавать группы в приложениях и службах, которые пока не поддерживают метки конфиденциальности, вы можете запустить повторяющийся скрипт PowerShell для поиска новых групп, созданных пользователями со старыми классификациями, и их преобразования для использования меток конфиденциальности. 

#### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a>Преобразование классификаций для групп Microsoft 365 в метки конфиденциальности с помощью PowerShell

1. Сначала [подключитесь к PowerShell Центра безопасности и соответствия требованиям Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
    
    Например, в сеансе PowerShell, который вы запускаете как администратор, войдите в систему с помощью учетной записи глобального администратора.
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. Получите список меток конфиденциальности с их GUID с помощью командлета [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps).
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. Запишите GUID для меток конфиденциальности, которые нужно применить к группам Office 365.

4. Теперь [подключитесь к PowerShell Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
    Пример:
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```

6. Запишите GUID для меток конфиденциальности, которые нужно применить к группам Microsoft 365.

7. Используйте следующую команду в качестве примера, чтобы получить список групп, использующих в настоящее время классификацию General (Общее).

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. Для каждой группы добавьте GUID новой метки конфиденциальности. Например,

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. Повторите действия 5 и 6 для остальных категорий групп.

## <a name="auditing-sensitivity-label-activities"></a>Аудит действий с метками конфиденциальности

Если пользователь отправляет документ на сайт, защищенный с помощью метки конфиденциальности, и метка конфиденциальности документа имеет [более высокий приоритет](sensitivity-labels.md#label-priority-order-matters), чем метка конфиденциальности, примененная к сайту, это действие не блокируется. Например, вы применили метку **Общее** к сайту SharePoint, а другой пользователь отправляет на этот сайт документ с меткой **Конфиденциально**. Так как метка конфиденциальности с более высоким приоритетом определяет более конфиденциальное содержимое, чем содержимое с меткой меньшего приоритета, эта ситуация может являться проблемой безопасности.

Хотя действие не блокируется, оно подвергается аудиту, чтобы вы могли определить документы с таким несоответствием приоритетов меток и принять необходимые меры. Например, удалить или переместить отправленный документ с сайта. 

Проблема безопасности не возникает, если метка конфиденциальности документа имеет более низкий приоритет, чем метка конфиденциальности, примененная к сайту. Например, документ с меткой **Общее** отправляется на сайт с меткой **Конфиденциально**. В этом сценарии событие аудита не создается.

Чтобы найти это событие в журнале аудита, выполните поиск по запросу **Обнаружено несоответствие конфиденциальности документа** в категории **Действия с файлами и страницами**. 

Когда кто-нибудь добавляет или удаляет метку конфиденциальности на сайте или в группе, такие действия также подвергаются аудиту. Эти события можно найти в категории [Действия с метками конфиденциальности](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities). 

Инструкции по поиску в журнале аудита см. в статье [Поиск по журналу аудита в Центре безопасности и соответствия требованиям](search-the-audit-log-in-security-and-compliance.md).

## <a name="troubleshoot-sensitivity-label-deployment"></a>Устранение неполадок при развертывании меток конфиденциальности

Возникают проблемы с метками конфиденциальности для сайтов Microsoft Teams, групп Microsoft 365 и сайтов SharePoint? Проверьте следующее:

### <a name="labels-not-visible-after-publishing"></a>Метки не отображаются после публикации
Если у вас возникают проблемы при создании сайта или группы Microsoft 365 после включения этих параметров или изменения имени или всплывающей подсказки метки конфиденциальности, подождите несколько часов после сохранения изменений метки, а затем попробуйте снова создать команду или группу. Сведения см. в разделе [Планирование развертывания после создания или изменения метки конфиденциальности](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).

Если вы все еще не видите новую метку чувствительности в SharePoint Online, обратитесь в [службу поддержки Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

### <a name="team-group-or-sharepoint-site-creation-errors"></a>Ошибки при создании команды, группы или сайта SharePoint
Если в режиме общедоступного предварительного просмотра возникают ошибки создания, вы можете отключить метки конфиденциальности для сайтов Microsoft Teams, групп Microsoft 365 и сайтов SharePoint, используя те же инструкции из раздела [Включить поддержку меток конфиденциальности в PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell). Но чтобы отключить предварительную версию на шаге 5, отключите функцию с помощью `$setting["EnableMIPLabels"] = "False"`.

## <a name="additional-resources"></a>Дополнительные ресурсы

Просмотрите запись вебинара и ответы на вопросы об [использовании меток конфиденциальности в Microsoft Teams, группах Office 365 и сайтах SharePoint Online](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).

