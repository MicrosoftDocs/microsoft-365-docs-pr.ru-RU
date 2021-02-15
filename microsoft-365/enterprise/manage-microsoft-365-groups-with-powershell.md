---
title: Управление группами Microsoft 365 с помощью PowerShell
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: В этой статье вы узнаете, как выполнять общие задачи управления для групп Microsoft 365 в PowerShell.
ms.openlocfilehash: 1cad2aa39a6b106cbb4dbfbafa995899b2442ed1
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830619"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Управление группами Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

В этой статье данная статья содержит действия для выполнения общих задач управления для групп в Microsoft PowerShell. Здесь также перечислены cmdlets PowerShell для групп. Сведения об управлении сайтами SharePoint см. в теме "Управление сайтами [SharePoint Online с помощью PowerShell".](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell)

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Ссылка на рекомендации по использованию групп Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Когда пользователи [создают или редактют группу в Outlook,](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)вы можете показать им ссылку на рекомендации по использованию вашей организации. Например, если требуется добавить к имени группы определенный префикс или суффикс.

Используйте Azure Active Directory (Azure AD) PowerShell, чтобы указать пользователям рекомендации по использованию групп Microsoft 365 в вашей организации. Ознакомьтесь [с cmdlets Azure Active Directory](https://go.microsoft.com/fwlink/?LinkID=827484) для настройки параметров группы и следуйте инструкциям в области "Создание параметров" на уровне каталога, чтобы определить гиперссылки руководства по использованию.  После запуска cmdlet AAD пользователь увидит ссылку на ваши рекомендации при создании или редактировании группы в Outlook.

![Создание группы со ссылкой на рекомендации по использованию](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Щелкните руководство по использованию групп, чтобы увидеть рекомендации по группам Office 365 в организациях](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Разрешить пользователям отправлять в качестве группы Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Если вы хотите, чтобы группы Microsoft 365 могли отправлять сообщения "Отправить как", настройте эту возможность с помощью дополнительных средств [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) и [Get-RecipientPermission.](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) После этого пользователи группы Microsoft 365 смогут отправлять сообщения электронной почты и отвечать на них в качестве группы Microsoft 365 с помощью Outlook или Outlook в Интернете. Пользователи могут перейти в группу, создать новое сообщение электронной почты и изменить поле "Отправить как" на адрес электронной почты группы.

([Это также можно сделать в Центре администрирования Exchange.)](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)

Используйте следующий сценарий, заменив псевдоним группы, которую необходимо обновить, и псевдонимом пользователя, которому вы хотите предоставить *\<GroupAlias\>* *\<UserAlias\>* разрешения. [Подключите Exchange Online PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) чтобы запустить этот сценарий.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

После выполнения этого cmdlet пользователи могут перейти в Outlook или Outlook в Интернете для отправки  в качестве группы, добавив адрес электронной почты группы в поле "От".

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Создание классификаций для групп Microsoft 365 в организации

Вы можете создавать метки конфиденциальности, которые пользователи в вашей организации могут устанавливать при создании группы Microsoft 365. Если вы хотите классифицировать группы, рекомендуем использовать метки конфиденциальности вместо предыдущей функции классификации групп. Сведения об использовании меток конфиденциальности см. в под названием "Использование меток конфиденциальности для защиты контента в Microsoft Teams, группах [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)и на сайтах SharePoint".

> [!IMPORTANT]
> Если вы в настоящее время используете метки классификации, они больше не будут доступны пользователям, которые создают группы после включения меток конфиденциальности.

Вы по-прежнему можете использовать предыдущую функцию классификации групп. Вы можете создавать классификации, которые пользователи в организации могут устанавливать при создании группы Microsoft 365. Например, можно разрешить пользователям устанавливать "Стандартный", "Секретный" и "Главный секрет" для групп, которые они создают. Классификации групп не задаются по умолчанию, и их необходимо создать, чтобы пользователи могли их настроить. Используйте Azure Active Directory PowerShell, чтобы указать пользователям рекомендации по использованию групп Microsoft 365 в вашей организации.

Ознакомьтесь [с cmdlets Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) для настройки параметров группы и следуйте шагам в области "Создание параметров" на уровне каталога, чтобы определить классификацию для групп Microsoft 365. 

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Чтобы связать описание с каждой классификацией, можно использовать атрибут  *classificationDescriptions* параметров для определения.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

где классификация соответствует строкам в ClassificationList.

Пример.

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

После запуска вышеуказанного cmdlet Azure Active Directory, чтобы настроить классификацию, запустите [его,](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) если вы хотите настроить классификацию для определенной группы.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

Или создайте группу с классификацией.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Сведения об использовании Exchange Online PowerShell см. в статьях [Использование PowerShell с Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) и [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

После включения этих параметров владелец группы сможет выбрать классификацию в выпадаемом меню Outlook в Интернете  и Outlook и сохранить ее на странице редактирования группы.

![Выбор классификации группы Microsoft 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Скрытие групп Microsoft 365 из глобального списка адресов.
<a name="BKMK_CreateClassification"> </a>

Вы можете указать, отображается ли группа Microsoft 365 в глобальном списке адресов (GAL) и других списках в организации. Например, если у вас есть группа юридических отделов, которую не нужно отображать в списке адресов, вы можете остановить ее, чтобы она не появлялась в списке адресов. Запустите Set-Unified group, чтобы скрыть группу из списка адресов, как по этому:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Разрешить отправку сообщений в группы Microsoft 365 только внутренним пользователям
<a name="BKMK_CreateClassification"> </a>

Если вы не хотите, чтобы пользователи из других организаций могли отправлять сообщения электронной почты в группу Microsoft 365, вы можете изменить параметры этой группы. Это позволит отправлять сообщения электронной почты в группу только внутренним пользователям. Если внешний пользователь попытается отправить сообщение этой группе, оно будет отклонено.

Запустите Set-UnifiedGroup для обновления этого параметра, например:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Добавление сообщений в группы Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Каждый раз, когда отправитель пытается отправить сообщение электронной почты в группу Microsoft 365, ему может быть выказано сообщение с сообщением.

Запустите Set-Unified группы для добавления в группу электронной почты:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Наряду с mailTip можно также настроить mailTipTranslations, который указывает дополнительные языки для этой mailTip. Предположим, что вы хотите получить испанский перевод, а затем запустите следующую команду:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Изменение отображаемого имени группы Microsoft 365

Отображаемого имени указывает имя группы Microsoft 365. Это имя можно увидеть в Центре администрирования Exchange или Центре администрирования Microsoft 365. Вы можете изменить отображаемого имени группы или назначить отображаемого имени существующей группе Microsoft 365, выдав Set-UnifiedGroup команды:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Изменение параметра по умолчанию для групп Microsoft 365 для Outlook на общедоступный или частный
<a name="BKMK_CreateClassification"> </a>

Группы Microsoft 365 в Outlook по умолчанию создаются как частные. Если ваша организация хочет, чтобы группы Microsoft 365 по умолчанию создавались как общедоступные (или закрытые), используйте синтаксис этого синтаксиса для powerShell:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

Чтобы установить частное:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

Чтобы проверить параметр:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Дополнительные узнать [см. в настройках Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) и [Get-OrganizationConfig.](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig)

## <a name="microsoft-365-groups-cmdlets"></a>Microsoft 365 Groups cmdlets

С группами Microsoft 365 можно использовать следующие cmdlets.

|**Имя командлета**|**Описание**|
|:-----|:-----|
|[Get-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |Используйте этот cmdlet для просмотра существующих групп Microsoft 365 и просмотра свойств объекта группы  <br/> |
|[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |Обновление свойств определенной группы Microsoft 365  <br/> |
|[New-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |Создайте группу Microsoft 365. Этот cmdlet предоставляет минимальный набор параметров. Чтобы установить значения для расширенных свойств, используйте Set-UnifiedGroup после создания новой группы  <br/> |
|[Remove-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |Удаление существующей группы Microsoft 365  <br/> |
|[Get-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |Извлечение сведений о членстве и владельце для группы Microsoft 365  <br/> |
|[Add-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |Добавление участников, владельцев и подписчиков в существующую группу Microsoft 365 <br/> |
|[Remove-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |Удаление владельцев и участников из существующей группы Microsoft 365  <br/> |
|[Get-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |Используется для просмотра сведений о фотографии пользователя, связанной с учетной записью. Фотографии пользователей хранятся в Active Directory  <br/> |
|[Set-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |Используется для связываия фотографии пользователя с учетной записью. Фотографии пользователей хранятся в Active Directory  <br/> |
|[Remove-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |Удаление фотографии для группы Microsoft 365  <br/> |

## <a name="related-topics"></a>Связанные статьи

[Обновление списков рассылки до групп Microsoft 365](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[Управление тем, кто может создавать группы Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[Управление гостевим доступом к группам Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Изменение статического членства в группах на динамическое](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
