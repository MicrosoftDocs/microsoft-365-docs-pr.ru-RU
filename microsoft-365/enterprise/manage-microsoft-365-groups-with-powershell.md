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
description: В этой статье рассказывается, как выполнять стандартные задачи управления для групп Microsoft 365 в PowerShell.
ms.openlocfilehash: c1aa551597644b7f41c3445a791ea27579464f7b
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277479"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Управление группами Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

В этой статье приводятся инструкции по выполнению стандартных задач управления для групп в Microsoft PowerShell. Кроме того, в нем перечислены командлеты PowerShell для групп. Сведения об управлении сайтами SharePoint можно найти [в статье Управление сайтами SharePoint Online с помощью PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Ссылки на рекомендации по использованию групп Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Когда пользователи [создают или редактируют группу в Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), вы можете показывать им ссылку на рекомендации по использованию вашей организации. Например, если требуется добавить в имя группы определенный префикс или суффикс.

Используйте оболочку PowerShell Azure Active Directory (Azure AD), чтобы указать пользователям в Организации рекомендации по использованию для групп Microsoft 365. Изучите [командлеты Azure Active Directory для настройки параметров групп](https://go.microsoft.com/fwlink/?LinkID=827484) и следуйте шагам, описанным в разделе **CREATE Settings на уровне каталога** , чтобы определить гиперссылку на рекомендации по использованию. После запуска командлета AAD пользователь увидит ссылку на свои рекомендации при создании или изменении группы в Outlook.

![Создание ссылки на новую группу с рекомендациями по использованию](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Выберите пункт рекомендации по использованию групп, чтобы просмотреть рекомендации для организаций Office 365 для групп](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Разрешить пользователям отправлять сообщения в качестве группы Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Если вы хотите включить "Отправить как" для групп Microsoft 365, выполните командлеты [Add – RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) и [Get – RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) , чтобы настроить этот параметр. После включения этого параметра пользователи группы Microsoft 365 могут использовать Outlook или Outlook в Интернете для отправки электронной почты и ответа в качестве группы Microsoft 365. Пользователи могут перейти к группе, создать новую электронную почту и изменить поле "Отправить как" на адрес электронной почты группы.

([Это также можно сделать в центре администрирования Exchange](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)

Используйте следующий сценарий, заменив *\<GroupAlias\>* псевдонимом группы, которую требуется обновить, и *\<UserAlias\>* указав псевдоним пользователя, которому необходимо предоставить разрешения. Чтобы запустить этот скрипт, [подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) .

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

После выполнения командлета пользователи могут перейти в Outlook или Outlook в Интернете для отправки в качестве группы, добавив адрес электронной почты группы в поле " **от** ".

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Создание классификаций для групп Microsoft 365 в Организации

Вы можете создавать метки конфиденциальности, которые пользователи в организации могут установить при создании группы Microsoft 365. Если вы хотите классифицировать группы, мы рекомендуем использовать метки чувствительности вместо функции классификации предыдущих групп. Сведения об использовании меток конфиденциальности приведены в разделе [Использование меток конфиденциальности для защиты содержимого в Microsoft Teams, microsoft 365 Groups и сайтов SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!IMPORTANT]
> Если вы используете метки классификации, они больше не будут доступны пользователям, которые создают группы после включения меток конфиденциальности.

Вы по-прежнему можете использовать функцию классификации предыдущих групп. Вы можете создавать классификации, которые пользователи в организации могут установить при создании группы Microsoft 365. Например, вы можете разрешить пользователям устанавливать "стандартные", "секрет" и "самый высокий секрет" при создании групп. Классификации групп не задаются по умолчанию и их необходимо создать, чтобы пользователи могли их настраивать. Используйте PowerShell Azure Active Directory, чтобы указать пользователям в Организации рекомендации по использованию для групп Microsoft 365.

Изучите [командлеты Azure Active Directory для настройки параметров групп](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) и следуйте шагам, описанным в разделе **CREATE Settings на уровне каталога** , чтобы определить классификацию для групп Microsoft 365.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Чтобы связать описание с каждой классификацией, можно использовать атрибут параметров  *классификатиондескриптионс* для определения.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

где классификация соответствует строкам в Классификатионлист.

Пример:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

После выполнения приведенного выше командлета Azure Active Directory для настройки классификации запустите командлет [Set – UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) , если необходимо задать классификацию для определенной группы.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

Или создайте новую группу с классификацией.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Сведения об использовании Exchange Online PowerShell см. в статьях [Использование PowerShell с Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) и [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

После включения этих параметров владелец группы сможет выбрать классификацию из раскрывающегося меню в Outlook в Интернете и Outlook и сохранить его на странице " **изменение** группы".

![Выберите Microsoft 365 Group Classification](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Скрыть группы Microsoft 365 в глобальном списке адресов.
<a name="BKMK_CreateClassification"> </a>

Вы можете указать, будет ли группа Microsoft 365 отображаться в глобальном списке адресов (GAL) и других списках в Организации. Например, если у вас есть юридическое лицо, которое не должно отображаться в списке адресов, можно остановить отображение этой группы в глобальном списке адресов. Выполните командлет Set – Unified Group, чтобы скрыть группу в списке адресов следующим образом:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Разрешить только внутренним пользователям отправлять сообщения в группы Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Если вы не хотите, чтобы пользователи из других организаций отправляли сообщения электронной почты в группу Microsoft 365, можно изменить параметры этой группы. Она позволит только внутренним пользователям отправлять электронную почту в вашу группу. Если внешний пользователь попытается отправить сообщение в эту группу, оно будет отклонено.

Выполните командлет Set – UnifiedGroup, чтобы обновить этот параметр, как показано ниже.

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Добавление подсказок в группы Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Когда отправитель пытается отправить сообщение в группу Microsoft 365, к ним можно будет отобразить подсказка.

Выполните командлет Set – Unified Group, чтобы добавить подсказка в группу:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Кроме того, в подсказка можно задать MailTipTranslations, задающий дополнительные языки для подсказка. Предположим, вы хотите использовать Испанский перевод, а затем выполните следующую команду:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Изменение отображаемого имени группы Microsoft 365

Отображаемое имя указывает имя группы Microsoft 365. Это имя можно увидеть в центре администрирования Exchange или в центре администрирования Microsoft 365. Можно изменить отображаемое имя группы или назначить отображаемое имя существующей группе Microsoft 365, выполнив команду Set – UnifiedGroup:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Изменение параметров по умолчанию для групп Microsoft 365 для Outlook как общедоступных или частных
<a name="BKMK_CreateClassification"> </a>

Группы Microsoft 365 в Outlook по умолчанию создаются как частные. Если организации требуется, чтобы группы Microsoft 365 были созданы как общедоступные по умолчанию (или обратно в личный), используйте следующий синтаксис командлета PowerShell:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

Для настройки в значение Private:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

Чтобы проверить параметр:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Дополнительные сведения см. в статье [Set – OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) и [Get – OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).

## <a name="microsoft-365-groups-cmdlets"></a>Командлеты Microsoft 365 Groups

С группами Microsoft 365 можно использовать следующие командлеты.

|**Имя командлета**|**Описание**|
|:-----|:-----|
|[Get — UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |Используйте этот командлет для поиска существующих групп Microsoft 365 и просмотра свойств объекта Group.  <br/> |
|[Set — UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |Обновление свойств определенной группы Microsoft 365  <br/> |
|[New — UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |Создайте новую группу Microsoft 365. Этот командлет предоставляет минимальный набор параметров. Чтобы задать значения для расширенных свойств, используйте Set – UnifiedGroup после создания новой группы.  <br/> |
|[Remove — UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |Удаление существующей группы Microsoft 365  <br/> |
|[Get — Унифиедграуплинкс](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |Получение сведений о членстве и владельце для группы Microsoft 365  <br/> |
|[Add — Унифиедграуплинкс](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |Добавление сотен или тысяч пользователей или новых владельцев в существующую группу Microsoft 365  <br/> |
|[Remove — Унифиедграуплинкс](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |Удаление владельцев и членов существующей группы Microsoft 365  <br/> |
|[Get — UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |Используется для просмотра сведений о фотографии пользователя, связанной с учетной записью. Фотографии пользователей хранятся в Active Directory  <br/> |
|[Set — UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |Используется для связывания фотографии пользователя с учетной записью. Фотографии пользователей хранятся в Active Directory  <br/> |
|[Remove — UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |Удаление фотографии для группы Microsoft 365  <br/> |

## <a name="related-topics"></a>Статьи по теме

[Обновление списков рассылки до групп Майкрософт 365](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[Управление пользователями, которые могут создавать группы Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[Управление гостевым доступом к группам Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Изменение членства статической группы на Dynamic in](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
