---
title: Управление Microsoft 365 группами с помощью PowerShell
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
description: В этой статье узнайте, как выполнять общие задачи управления для Microsoft 365 групп в PowerShell.
ms.openlocfilehash: 22bf4d1f3187746483d8d904378e675562a62142
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730562"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="c385b-103">Управление Microsoft 365 группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c385b-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="c385b-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="c385b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c385b-105">В этой статье данная статья содержит шаги для выполнения общих задач управления для групп в Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c385b-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="c385b-106">В нем также перечислены cmdlets PowerShell для групп.</span><span class="sxs-lookup"><span data-stu-id="c385b-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="c385b-107">Сведения об управлении SharePoint сайтами см. в [SharePoint-сайтах с помощью PowerShell.](/sharepoint/manage-team-and-communication-sites-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="c385b-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="c385b-108">Ссылка на рекомендации по Microsoft 365 групп</span><span class="sxs-lookup"><span data-stu-id="c385b-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="c385b-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="c385b-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="c385b-110">Когда пользователи создают или редактирует группу в [Outlook,](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)вы можете показать им ссылку на рекомендации по использованию организации.</span><span class="sxs-lookup"><span data-stu-id="c385b-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="c385b-111">Например, если требуется добавить в имя группы определенный префикс или суффикс.</span><span class="sxs-lookup"><span data-stu-id="c385b-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="c385b-112">Используйте Azure Active Directory (Azure AD) PowerShell, чтобы указать пользователям рекомендации по использованию вашей организации для Microsoft 365 групп.</span><span class="sxs-lookup"><span data-stu-id="c385b-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="c385b-113">Ознакомьтесь [Azure Active Directory](/azure/active-directory/enterprise-users/groups-settings-cmdlets) для настройки параметров группы и выполните действия в параметрах **Create** на уровне каталога, чтобы определить гиперссылки руководства по использованию.</span><span class="sxs-lookup"><span data-stu-id="c385b-113">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/enterprise-users/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="c385b-114">После запуска комлета AAD пользователи увидят ссылку на рекомендации при создании или редактировании группы в Outlook.</span><span class="sxs-lookup"><span data-stu-id="c385b-114">Once you run the AAD cmdlet, users will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![Создание новой группы со ссылкой на рекомендации по использованию](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Щелкните руководство по использованию группы, чтобы увидеть рекомендации Office 365 групп](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="c385b-117">Разрешить пользователям отправлять как группу Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c385b-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="c385b-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="c385b-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="c385b-119">Если вы хотите включить Microsoft 365 группы в "Отправить as", для настройки этого используйте смеделя [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) и [Get-RecipientPermission.](/powershell/module/exchange/get-recipientpermission)</span><span class="sxs-lookup"><span data-stu-id="c385b-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="c385b-120">После этого параметра пользователи Microsoft 365 группы могут использовать Outlook или Outlook в Интернете для отправки и ответа на электронную почту в качестве Microsoft 365 группы.</span><span class="sxs-lookup"><span data-stu-id="c385b-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="c385b-121">Пользователи могут перейти в группу, создать новую электронную почту и изменить поле "Отправить as" на адрес электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="c385b-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="c385b-122">([Вы также можете сделать это в центре администрирования Exchange.)](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)</span><span class="sxs-lookup"><span data-stu-id="c385b-122">([You can also do this in the Exchange Admin Center](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="c385b-123">Используйте следующий сценарий, заменив псевдонимом группы, которую необходимо обновить, и псевдонимом пользователя, которому необходимо предоставить *\<GroupAlias\>* *\<UserAlias\>* разрешения.</span><span class="sxs-lookup"><span data-stu-id="c385b-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="c385b-124">[Подключение Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) для запуска этого сценария.</span><span class="sxs-lookup"><span data-stu-id="c385b-124">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="c385b-125">После выполнения cmdlet пользователи могут перейти в Outlook или Outlook в Интернете для отправки в качестве группы, добавив адрес групповой электронной почты в **поле From.**</span><span class="sxs-lookup"><span data-stu-id="c385b-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="c385b-126">Создание классификаций для Microsoft 365 групп в организации</span><span class="sxs-lookup"><span data-stu-id="c385b-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="c385b-127">Можно создать метки конфиденциальности, которые пользователи в организации могут установить при создании Microsoft 365 Group.</span><span class="sxs-lookup"><span data-stu-id="c385b-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="c385b-128">Чтобы классифицировать группы, рекомендуется использовать метки чувствительности вместо предыдущей функции классификации групп.</span><span class="sxs-lookup"><span data-stu-id="c385b-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="c385b-129">Сведения об использовании меток конфиденциальности см. в материалах [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 группах](../compliance/sensitivity-labels-teams-groups-sites.md)и SharePoint сайтах.</span><span class="sxs-lookup"><span data-stu-id="c385b-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c385b-130">Если в настоящее время вы используете метки классификации, они больше не будут доступны пользователям, создав группы после включения меток конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="c385b-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="c385b-131">Вы по-прежнему можете использовать предыдущую функцию классификации групп.</span><span class="sxs-lookup"><span data-stu-id="c385b-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="c385b-132">Можно создать классификации, которые пользователи в организации могут задать при создании Microsoft 365 Group.</span><span class="sxs-lookup"><span data-stu-id="c385b-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="c385b-133">Например, вы можете разрешить пользователям устанавливать "Standard", "Secret" и "Top Secret" по группам, которые они создают.</span><span class="sxs-lookup"><span data-stu-id="c385b-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="c385b-134">Классификации групп не задают по умолчанию, и их необходимо создать для того, чтобы пользователи могли их задать.</span><span class="sxs-lookup"><span data-stu-id="c385b-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="c385b-135">Используйте Azure Active Directory PowerShell, чтобы указать пользователям рекомендации по использованию для Microsoft 365 групп.</span><span class="sxs-lookup"><span data-stu-id="c385b-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="c385b-136">Ознакомьтесь [Azure Active Directory](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) для настройки параметров группы и выполните действия в параметрах **Create** на уровне каталога, чтобы определить классификацию для Microsoft 365 групп.</span><span class="sxs-lookup"><span data-stu-id="c385b-136">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="c385b-137">Чтобы связать описание с каждой классификацией, можно использовать параметры  *атрибута ClassificationDescriptions* для определения.</span><span class="sxs-lookup"><span data-stu-id="c385b-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="c385b-138">где классификация соответствует строкам в Списке классификации.</span><span class="sxs-lookup"><span data-stu-id="c385b-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="c385b-139">Пример.</span><span class="sxs-lookup"><span data-stu-id="c385b-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="c385b-140">После запуска вышеуказанного Azure Active Directory, чтобы установить классификацию, запустите группу [Set-UnifiedGroup,](/powershell/module/exchange/Set-UnifiedGroup) если вы хотите установить классификацию для определенной группы.</span><span class="sxs-lookup"><span data-stu-id="c385b-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="c385b-141">Или создайте новую группу с классификацией.</span><span class="sxs-lookup"><span data-stu-id="c385b-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="c385b-142">Сведения об использовании Exchange Online PowerShell см. в статьях [Использование PowerShell с Exchange Online](/powershell/exchange/exchange-online-powershell) и [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c385b-142">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="c385b-143">После включения этих параметров владелец группы сможет выбрать классификацию из выпадаемой меню Outlook в Интернете и Outlook и сохранить ее со страницы **Группы редактирования.**</span><span class="sxs-lookup"><span data-stu-id="c385b-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![Выбор классификации Microsoft 365 группы](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="c385b-145">Скрыть Microsoft 365 группы из глобального списка адресов.</span><span class="sxs-lookup"><span data-stu-id="c385b-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="c385b-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="c385b-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="c385b-147">Вы можете указать, отображается ли Microsoft 365 в глобальном списке адресов (GAL) и других списках в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c385b-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="c385b-148">Например, если у вас есть группа юридических отделов, которую вы не хотите отображать в списке адресов, вы можете остановить ее от появления в GAL.</span><span class="sxs-lookup"><span data-stu-id="c385b-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="c385b-149">Запустите Set-Unified группы, чтобы скрыть группу из списка адресов так:</span><span class="sxs-lookup"><span data-stu-id="c385b-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="c385b-150">Разрешить отправку сообщения только внутренним пользователям в Microsoft 365 Группы</span><span class="sxs-lookup"><span data-stu-id="c385b-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="c385b-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="c385b-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="c385b-152">Если вы не хотите, чтобы пользователи из других организаций отсылали электронные письма в группу Microsoft 365, вы можете изменить параметры для этой группы.</span><span class="sxs-lookup"><span data-stu-id="c385b-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="c385b-153">Это позволит только внутренним пользователям отправлять сообщения электронной почты в вашу группу.</span><span class="sxs-lookup"><span data-stu-id="c385b-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="c385b-154">Если внешний пользователь попытается отправить сообщение в эту группу, оно будет отклонено.</span><span class="sxs-lookup"><span data-stu-id="c385b-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="c385b-155">Запустите Set-UnifiedGroup, чтобы обновить этот параметр, например:</span><span class="sxs-lookup"><span data-stu-id="c385b-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="c385b-156">Добавление MailTips в Microsoft 365 группы</span><span class="sxs-lookup"><span data-stu-id="c385b-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="c385b-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="c385b-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="c385b-158">Всякий раз, когда отправитель пытается отправить электронное письмо в группу Microsoft 365, ему может быть показано mailTip.</span><span class="sxs-lookup"><span data-stu-id="c385b-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="c385b-159">Запустите Set-Unified группы, чтобы добавить mailTip в группу:</span><span class="sxs-lookup"><span data-stu-id="c385b-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="c385b-160">Наряду с MailTip можно также установить MailTipTranslations, который указывает дополнительные языки для MailTip.</span><span class="sxs-lookup"><span data-stu-id="c385b-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="c385b-161">Предположим, что необходимо иметь испанский перевод, а затем выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c385b-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="c385b-162">Изменение имени отображения группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c385b-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="c385b-163">Имя отображения указывает имя группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c385b-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="c385b-164">Это имя можно увидеть в центре администрирования exchange или Microsoft 365 центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="c385b-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="c385b-165">Вы можете изменить имя отображения группы или назначить имя отображения существующей Microsoft 365, задав команду Set-UnifiedGroup:</span><span class="sxs-lookup"><span data-stu-id="c385b-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="c385b-166">Изменение параметра по умолчанию групп Microsoft 365 для Outlook на общедоступные или частные</span><span class="sxs-lookup"><span data-stu-id="c385b-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="c385b-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="c385b-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="c385b-168">Microsoft 365 Группы в Outlook создаются как частные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c385b-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="c385b-169">Если организация хочет, чтобы Microsoft 365 группы были созданы в качестве общедоступных по умолчанию (или обратно в private), используйте этот синтаксис групп PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c385b-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="c385b-170">Чтобы установить в частном порядке:</span><span class="sxs-lookup"><span data-stu-id="c385b-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="c385b-171">Чтобы проверить параметр:</span><span class="sxs-lookup"><span data-stu-id="c385b-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="c385b-172">Дополнительные дополнительные дополнительные информации см. [в set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) и [Get-OrganizationConfig.](/powershell/module/exchange/get-organizationconfig)</span><span class="sxs-lookup"><span data-stu-id="c385b-172">To learn more, see [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="c385b-173">Microsoft 365 Групповая группа</span><span class="sxs-lookup"><span data-stu-id="c385b-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="c385b-174">Следующие cmdlets можно использовать с Microsoft 365 группами.</span><span class="sxs-lookup"><span data-stu-id="c385b-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="c385b-175">**Имя командлета**</span><span class="sxs-lookup"><span data-stu-id="c385b-175">**Cmdlet name**</span></span>|<span data-ttu-id="c385b-176">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c385b-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c385b-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="c385b-177">Get-UnifiedGroup</span></span>](/powershell/module/exchange/get-unifiedgroup) <br/> |<span data-ttu-id="c385b-178">С помощью этого комлета можно просмотреть существующие Microsoft 365 группы и просмотреть свойства объекта группы</span><span class="sxs-lookup"><span data-stu-id="c385b-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="c385b-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="c385b-179">Set-UnifiedGroup</span></span>](/powershell/module/exchange/set-unifiedgroup) <br/> |<span data-ttu-id="c385b-180">Обновление свойств определенной Microsoft 365 Group</span><span class="sxs-lookup"><span data-stu-id="c385b-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="c385b-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="c385b-181">New-UnifiedGroup</span></span>](/powershell/module/exchange/new-unifiedgroup) <br/> |<span data-ttu-id="c385b-182">Создайте новую группу Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c385b-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="c385b-183">Этот комлет содержит минимальный набор параметров.</span><span class="sxs-lookup"><span data-stu-id="c385b-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="c385b-184">Чтобы установить значения для расширенных свойств, Set-UnifiedGroup после создания новой группы</span><span class="sxs-lookup"><span data-stu-id="c385b-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="c385b-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="c385b-185">Remove-UnifiedGroup</span></span>](/powershell/module/exchange/remove-unifiedgroup) <br/> |<span data-ttu-id="c385b-186">Удаление существующей Microsoft 365 группы</span><span class="sxs-lookup"><span data-stu-id="c385b-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="c385b-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="c385b-187">Get-UnifiedGroupLinks</span></span>](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |<span data-ttu-id="c385b-188">Извлечение сведений о членстве и владельце для Microsoft 365 Group</span><span class="sxs-lookup"><span data-stu-id="c385b-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="c385b-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="c385b-189">Add-UnifiedGroupLinks</span></span>](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |<span data-ttu-id="c385b-190">Добавление членов, владельцев и подписчиков в существующую группу Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c385b-190">Add members, owners, and subscribers to an existing Microsoft 365 Group</span></span> <br/> |
|[<span data-ttu-id="c385b-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="c385b-191">Remove-UnifiedGroupLinks</span></span>](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |<span data-ttu-id="c385b-192">Удаление владельцев и членов из существующей Microsoft 365 Group</span><span class="sxs-lookup"><span data-stu-id="c385b-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="c385b-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="c385b-193">Get-UserPhoto</span></span>](/powershell/module/exchange/get-userphoto) <br/> |<span data-ttu-id="c385b-194">Используется для просмотра сведений о фотографии пользователя, связанной с учетной записью.</span><span class="sxs-lookup"><span data-stu-id="c385b-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="c385b-195">Фотографии пользователей хранятся в Active Directory</span><span class="sxs-lookup"><span data-stu-id="c385b-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="c385b-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="c385b-196">Set-UserPhoto</span></span>](/powershell/module/exchange/set-userphoto) <br/> |<span data-ttu-id="c385b-197">Используется для связывать фотографию пользователя с учетной записью.</span><span class="sxs-lookup"><span data-stu-id="c385b-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="c385b-198">Фотографии пользователей хранятся в Active Directory</span><span class="sxs-lookup"><span data-stu-id="c385b-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="c385b-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="c385b-199">Remove-UserPhoto</span></span>](/powershell/module/exchange/remove-userphoto) <br/> |<span data-ttu-id="c385b-200">Удаление фотографии для группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c385b-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="c385b-201">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c385b-201">Related topics</span></span>

[<span data-ttu-id="c385b-202">Обновление списков рассылки для Microsoft 365 групп</span><span class="sxs-lookup"><span data-stu-id="c385b-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="c385b-203">Управление разрешениями пользователей на создание групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c385b-203">Manage who can create Microsoft 365 Groups</span></span>](/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="c385b-204">Управление гостевых доступом к Microsoft 365 группам</span><span class="sxs-lookup"><span data-stu-id="c385b-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="c385b-205">Изменение статического членства в группе на динамическое в</span><span class="sxs-lookup"><span data-stu-id="c385b-205">Change static group membership to dynamic in</span></span>](/azure/active-directory/users-groups-roles/groups-change-type)
