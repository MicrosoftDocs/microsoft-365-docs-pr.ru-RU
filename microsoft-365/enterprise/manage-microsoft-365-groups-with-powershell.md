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
description: В этой статье узнайте, как выполнять общие задачи управления для групп Microsoft 365 в PowerShell.
ms.openlocfilehash: adf796ad2f2ee7a304c578cd42c700f2b44e7a5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911054"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Управление группами Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

В этой статье данная статья содержит шаги для выполнения общих задач управления для групп в Microsoft PowerShell. В нем также перечислены cmdlets PowerShell для групп. Сведения об управлении сайтами SharePoint см. в раздел Управление сайтами [SharePoint Online с помощью PowerShell.](/sharepoint/manage-team-and-communication-sites-in-powershell)

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Ссылка на рекомендации по использованию Microsoft 365 Groups
<a name="BK_LinkToGuideLines"> </a>

Когда пользователи [создают или редактирует группу в Outlook,](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)вы можете показать им ссылку на рекомендации по использованию организации. Например, если требуется добавить в имя группы определенный префикс или суффикс.

Чтобы указать пользователям рекомендации по использованию для групп Microsoft 365, используйте PowerShell Azure Active Directory (Azure AD). Ознакомьтесь с [cmdlets Azure Active Directory](/azure/active-directory/enterprise-users/groups-settings-cmdlets) для настройки параметров группы и выполните действия в параметрах **Create** на уровне каталога, чтобы определить гиперссылку руководства по использованию. После запуска комлета AAD пользователь увидит ссылку на рекомендации при создании или редактировании группы в Outlook.

![Создание новой группы со ссылкой на рекомендации по использованию](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Щелкните руководство по использованию группы, чтобы увидеть рекомендации по группам Office 365 в организациях](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Разрешить пользователям отправлять в группу Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Если вы хотите включить группы Microsoft 365 в "Отправка as", для настройки этого необходимо использовать кодлеты [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) и [Get-RecipientPermission.](/powershell/module/exchange/get-recipientpermission) После этого пользователи группы Microsoft 365 могут использовать Outlook или Outlook в Интернете для отправки и ответа на электронную почту в качестве группы Microsoft 365. Пользователи могут перейти в группу, создать новую электронную почту и изменить поле "Отправить as" на адрес электронной почты группы.

([Вы также можете сделать это в Центре администрирования Exchange.)](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)

Используйте следующий сценарий, заменив псевдонимом группы, которую необходимо обновить, и псевдонимом пользователя, которому необходимо предоставить *\<GroupAlias\>* *\<UserAlias\>* разрешения. [Подключись к Exchange Online PowerShell,](/powershell/exchange/connect-to-exchange-online-powershell) чтобы запустить этот скрипт.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

После выполнения cmdlet пользователи могут перейти в Outlook или Outlook в Интернете для отправки в качестве группы, добавив адрес групповой электронной почты в **поле From.**

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Создание классификаций для групп Microsoft 365 в организации

Можно создать метки конфиденциальности, которые пользователи в организации могут установить при создании группы Microsoft 365. Чтобы классифицировать группы, рекомендуется использовать метки чувствительности вместо предыдущей функции классификации групп. Сведения об использовании меток конфиденциальности см. в раздел Использование меток конфиденциальности для защиты контента на сайтах [Microsoft Teams, Microsoft 365 и SharePoint.](../compliance/sensitivity-labels-teams-groups-sites.md)

> [!IMPORTANT]
> Если в настоящее время вы используете метки классификации, они больше не будут доступны пользователям, создав группы после включения меток конфиденциальности.

Вы по-прежнему можете использовать предыдущую функцию классификации групп. Можно создавать классификации, которые пользователи в организации могут устанавливать при создании группы Microsoft 365. Например, вы можете разрешить пользователям устанавливать "Standard", "Secret" и "Top Secret" по группам, которые они создают. Классификации групп не задают по умолчанию, и их необходимо создать для того, чтобы пользователи могли их задать. Используйте Azure Active Directory PowerShell, чтобы указать пользователям рекомендации по использованию для Microsoft 365 Groups.

Ознакомьтесь с [cmdlets Azure Active Directory](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) для настройки параметров групп и выполните действия в параметрах **Create** на уровне каталога, чтобы определить классификацию для групп Microsoft 365.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Чтобы связать описание с каждой классификацией, можно использовать параметры  *атрибута ClassificationDescriptions* для определения.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

где классификация соответствует строкам в Списке классификации.

Пример.

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

После запуска вышеуказанного cmdlet Azure Active Directory для набора классификации запустите группу [Set-UnifiedGroup,](/powershell/module/exchange/Set-UnifiedGroup) если требуется установить классификацию для определенной группы.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

Или создайте новую группу с классификацией.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Сведения об использовании Exchange Online PowerShell см. в статьях [Использование PowerShell с Exchange Online](/powershell/exchange/exchange-online-powershell) и [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

После включения этих параметров владелец группы сможет выбрать классификацию из выпадаемой меню в Outlook в Интернете и Outlook и сохранить ее со страницы **Изменить** группу.

![Выберите классификацию группы Microsoft 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Скрыть Группы Microsoft 365 из глобального списка адресов.
<a name="BKMK_CreateClassification"> </a>

Вы можете указать, отображается ли группа Microsoft 365 в глобальном списке адресов (GAL) и других списках в вашей организации. Например, если у вас есть группа юридических отделов, которую вы не хотите отображать в списке адресов, вы можете остановить ее от появления в GAL. Запустите Set-Unified группы, чтобы скрыть группу из списка адресов так:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Разрешить только внутренним пользователям отправлять сообщения в Группы Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Если вы не хотите, чтобы пользователи из других организаций отсылали электронные письма в группу Microsoft 365, можно изменить параметры для этой группы. Это позволит только внутренним пользователям отправлять сообщения электронной почты в вашу группу. Если внешний пользователь попытается отправить сообщение в эту группу, оно будет отклонено.

Запустите Set-UnifiedGroup, чтобы обновить этот параметр, например:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Добавление MailTips в группы Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Всякий раз, когда отправитель пытается отправить сообщение в группу Microsoft 365, им может быть показано mailTip.

Запустите Set-Unified группы, чтобы добавить mailTip в группу:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Наряду с MailTip можно также установить MailTipTranslations, который указывает дополнительные языки для MailTip. Предположим, что необходимо иметь испанский перевод, а затем выполнить следующую команду:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Изменение имени отображения группы Microsoft 365

Имя отображения указывает имя группы Microsoft 365. Это имя можно увидеть в центре администрирования exchange или центре администрирования Microsoft 365. Вы можете изменить имя отображения группы или назначить имя отображения существующей группе Microsoft 365, Set-UnifiedGroup команду:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Изменение параметра по умолчанию групп Microsoft 365 для Outlook на общедоступные или частные
<a name="BKMK_CreateClassification"> </a>

Группы Microsoft 365 в Outlook создаются как частные по умолчанию. Если ваша организация хочет, чтобы группы Microsoft 365 были созданы в качестве общедоступных по умолчанию (или вернулись в private), используйте этот синтаксис cmdlet PowerShell:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

Чтобы установить в частном порядке:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

Чтобы проверить параметр:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Дополнительные дополнительные дополнительные информации см. [в set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) и [Get-OrganizationConfig.](/powershell/module/exchange/get-organizationconfig)

## <a name="microsoft-365-groups-cmdlets"></a>Cmdlets Microsoft 365 Groups

Следующие cmdlets можно использовать с Группами Microsoft 365.

|**Имя командлета**|**Описание**|
|:-----|:-----|
|[Get-UnifiedGroup](/powershell/module/exchange/get-unifiedgroup) <br/> |С помощью этого комлета можно просмотреть существующие группы Microsoft 365 и просмотреть свойства объекта группы  <br/> |
|[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) <br/> |Обновление свойств определенной группы Microsoft 365  <br/> |
|[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) <br/> |Создайте новую группу Microsoft 365. Этот комлет содержит минимальный набор параметров. Чтобы установить значения для расширенных свойств, Set-UnifiedGroup после создания новой группы  <br/> |
|[Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) <br/> |Удаление существующей группы Microsoft 365  <br/> |
|[Get-UnifiedGroupLinks](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |Извлечение сведений о членстве и владельце для группы Microsoft 365  <br/> |
|[Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |Добавление членов, владельцев и подписчиков в существующую группу Microsoft 365 <br/> |
|[Remove-UnifiedGroupLinks](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |Удаление владельцев и членов из существующей группы Microsoft 365  <br/> |
|[Get-UserPhoto](/powershell/module/exchange/get-userphoto) <br/> |Используется для просмотра сведений о фотографии пользователя, связанной с учетной записью. Фотографии пользователей хранятся в Active Directory  <br/> |
|[Set-UserPhoto](/powershell/module/exchange/set-userphoto) <br/> |Используется для связывать фотографию пользователя с учетной записью. Фотографии пользователей хранятся в Active Directory  <br/> |
|[Remove-UserPhoto](/powershell/module/exchange/remove-userphoto) <br/> |Удаление фотографии для группы Microsoft 365  <br/> |

## <a name="related-topics"></a>Родственные темы

[Обновление списков рассылки до Microsoft 365 Groups](/office365/admin/manage/upgrade-distribution-lists)

[Управление разрешениями пользователей на создание групп Microsoft 365](/office365/admin/create-groups/manage-creation-of-groups)

[Управление гостевых доступом к группам Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Изменение статического членства в группе на динамическое в](/azure/active-directory/users-groups-roles/groups-change-type)