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
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="9de87-103">Управление группами Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9de87-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="9de87-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="9de87-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9de87-105">В этой статье данная статья содержит действия для выполнения общих задач управления для групп в Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9de87-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="9de87-106">Здесь также перечислены cmdlets PowerShell для групп.</span><span class="sxs-lookup"><span data-stu-id="9de87-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="9de87-107">Сведения об управлении сайтами SharePoint см. в теме "Управление сайтами [SharePoint Online с помощью PowerShell".](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="9de87-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="9de87-108">Ссылка на рекомендации по использованию групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="9de87-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="9de87-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="9de87-110">Когда пользователи [создают или редактют группу в Outlook,](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)вы можете показать им ссылку на рекомендации по использованию вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9de87-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="9de87-111">Например, если требуется добавить к имени группы определенный префикс или суффикс.</span><span class="sxs-lookup"><span data-stu-id="9de87-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="9de87-112">Используйте Azure Active Directory (Azure AD) PowerShell, чтобы указать пользователям рекомендации по использованию групп Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9de87-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="9de87-113">Ознакомьтесь [с cmdlets Azure Active Directory](https://go.microsoft.com/fwlink/?LinkID=827484) для настройки параметров группы и следуйте инструкциям в области "Создание параметров" на уровне каталога, чтобы определить гиперссылки руководства по использованию. </span><span class="sxs-lookup"><span data-stu-id="9de87-113">Check out [Azure Active Directory cmdlets for configuring group settings](https://go.microsoft.com/fwlink/?LinkID=827484) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="9de87-114">После запуска cmdlet AAD пользователь увидит ссылку на ваши рекомендации при создании или редактировании группы в Outlook.</span><span class="sxs-lookup"><span data-stu-id="9de87-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![Создание группы со ссылкой на рекомендации по использованию](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Щелкните руководство по использованию групп, чтобы увидеть рекомендации по группам Office 365 в организациях](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="9de87-117">Разрешить пользователям отправлять в качестве группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="9de87-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="9de87-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="9de87-119">Если вы хотите, чтобы группы Microsoft 365 могли отправлять сообщения "Отправить как", настройте эту возможность с помощью дополнительных средств [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) и [Get-RecipientPermission.](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission)</span><span class="sxs-lookup"><span data-stu-id="9de87-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="9de87-120">После этого пользователи группы Microsoft 365 смогут отправлять сообщения электронной почты и отвечать на них в качестве группы Microsoft 365 с помощью Outlook или Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="9de87-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="9de87-121">Пользователи могут перейти в группу, создать новое сообщение электронной почты и изменить поле "Отправить как" на адрес электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="9de87-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="9de87-122">([Это также можно сделать в Центре администрирования Exchange.)](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)</span><span class="sxs-lookup"><span data-stu-id="9de87-122">([You can also do this in the Exchange Admin Center](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="9de87-123">Используйте следующий сценарий, заменив псевдоним группы, которую необходимо обновить, и псевдонимом пользователя, которому вы хотите предоставить *\<GroupAlias\>* *\<UserAlias\>* разрешения.</span><span class="sxs-lookup"><span data-stu-id="9de87-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="9de87-124">[Подключите Exchange Online PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) чтобы запустить этот сценарий.</span><span class="sxs-lookup"><span data-stu-id="9de87-124">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="9de87-125">После выполнения этого cmdlet пользователи могут перейти в Outlook или Outlook в Интернете для отправки  в качестве группы, добавив адрес электронной почты группы в поле "От".</span><span class="sxs-lookup"><span data-stu-id="9de87-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="9de87-126">Создание классификаций для групп Microsoft 365 в организации</span><span class="sxs-lookup"><span data-stu-id="9de87-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="9de87-127">Вы можете создавать метки конфиденциальности, которые пользователи в вашей организации могут устанавливать при создании группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9de87-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="9de87-128">Если вы хотите классифицировать группы, рекомендуем использовать метки конфиденциальности вместо предыдущей функции классификации групп.</span><span class="sxs-lookup"><span data-stu-id="9de87-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="9de87-129">Сведения об использовании меток конфиденциальности см. в под названием "Использование меток конфиденциальности для защиты контента в Microsoft Teams, группах [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)и на сайтах SharePoint".</span><span class="sxs-lookup"><span data-stu-id="9de87-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9de87-130">Если вы в настоящее время используете метки классификации, они больше не будут доступны пользователям, которые создают группы после включения меток конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="9de87-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="9de87-131">Вы по-прежнему можете использовать предыдущую функцию классификации групп.</span><span class="sxs-lookup"><span data-stu-id="9de87-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="9de87-132">Вы можете создавать классификации, которые пользователи в организации могут устанавливать при создании группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9de87-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="9de87-133">Например, можно разрешить пользователям устанавливать "Стандартный", "Секретный" и "Главный секрет" для групп, которые они создают.</span><span class="sxs-lookup"><span data-stu-id="9de87-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="9de87-134">Классификации групп не задаются по умолчанию, и их необходимо создать, чтобы пользователи могли их настроить.</span><span class="sxs-lookup"><span data-stu-id="9de87-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="9de87-135">Используйте Azure Active Directory PowerShell, чтобы указать пользователям рекомендации по использованию групп Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9de87-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="9de87-136">Ознакомьтесь [с cmdlets Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) для настройки параметров группы и следуйте шагам в области "Создание параметров" на уровне каталога, чтобы определить классификацию для групп Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="9de87-136">Check out [Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="9de87-137">Чтобы связать описание с каждой классификацией, можно использовать атрибут  *classificationDescriptions* параметров для определения.</span><span class="sxs-lookup"><span data-stu-id="9de87-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="9de87-138">где классификация соответствует строкам в ClassificationList.</span><span class="sxs-lookup"><span data-stu-id="9de87-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="9de87-139">Пример.</span><span class="sxs-lookup"><span data-stu-id="9de87-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="9de87-140">После запуска вышеуказанного cmdlet Azure Active Directory, чтобы настроить классификацию, запустите [его,](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) если вы хотите настроить классификацию для определенной группы.</span><span class="sxs-lookup"><span data-stu-id="9de87-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="9de87-141">Или создайте группу с классификацией.</span><span class="sxs-lookup"><span data-stu-id="9de87-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="9de87-142">Сведения об использовании Exchange Online PowerShell см. в статьях [Использование PowerShell с Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) и [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9de87-142">Check out [Using PowerShell with Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="9de87-143">После включения этих параметров владелец группы сможет выбрать классификацию в выпадаемом меню Outlook в Интернете  и Outlook и сохранить ее на странице редактирования группы.</span><span class="sxs-lookup"><span data-stu-id="9de87-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![Выбор классификации группы Microsoft 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="9de87-145">Скрытие групп Microsoft 365 из глобального списка адресов.</span><span class="sxs-lookup"><span data-stu-id="9de87-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="9de87-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="9de87-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="9de87-147">Вы можете указать, отображается ли группа Microsoft 365 в глобальном списке адресов (GAL) и других списках в организации.</span><span class="sxs-lookup"><span data-stu-id="9de87-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="9de87-148">Например, если у вас есть группа юридических отделов, которую не нужно отображать в списке адресов, вы можете остановить ее, чтобы она не появлялась в списке адресов.</span><span class="sxs-lookup"><span data-stu-id="9de87-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="9de87-149">Запустите Set-Unified group, чтобы скрыть группу из списка адресов, как по этому:</span><span class="sxs-lookup"><span data-stu-id="9de87-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="9de87-150">Разрешить отправку сообщений в группы Microsoft 365 только внутренним пользователям</span><span class="sxs-lookup"><span data-stu-id="9de87-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="9de87-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="9de87-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="9de87-152">Если вы не хотите, чтобы пользователи из других организаций могли отправлять сообщения электронной почты в группу Microsoft 365, вы можете изменить параметры этой группы.</span><span class="sxs-lookup"><span data-stu-id="9de87-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="9de87-153">Это позволит отправлять сообщения электронной почты в группу только внутренним пользователям.</span><span class="sxs-lookup"><span data-stu-id="9de87-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="9de87-154">Если внешний пользователь попытается отправить сообщение этой группе, оно будет отклонено.</span><span class="sxs-lookup"><span data-stu-id="9de87-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="9de87-155">Запустите Set-UnifiedGroup для обновления этого параметра, например:</span><span class="sxs-lookup"><span data-stu-id="9de87-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="9de87-156">Добавление сообщений в группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="9de87-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="9de87-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="9de87-158">Каждый раз, когда отправитель пытается отправить сообщение электронной почты в группу Microsoft 365, ему может быть выказано сообщение с сообщением.</span><span class="sxs-lookup"><span data-stu-id="9de87-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="9de87-159">Запустите Set-Unified группы для добавления в группу электронной почты:</span><span class="sxs-lookup"><span data-stu-id="9de87-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="9de87-160">Наряду с mailTip можно также настроить mailTipTranslations, который указывает дополнительные языки для этой mailTip.</span><span class="sxs-lookup"><span data-stu-id="9de87-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="9de87-161">Предположим, что вы хотите получить испанский перевод, а затем запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9de87-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="9de87-162">Изменение отображаемого имени группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="9de87-163">Отображаемого имени указывает имя группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9de87-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="9de87-164">Это имя можно увидеть в Центре администрирования Exchange или Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9de87-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="9de87-165">Вы можете изменить отображаемого имени группы или назначить отображаемого имени существующей группе Microsoft 365, выдав Set-UnifiedGroup команды:</span><span class="sxs-lookup"><span data-stu-id="9de87-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="9de87-166">Изменение параметра по умолчанию для групп Microsoft 365 для Outlook на общедоступный или частный</span><span class="sxs-lookup"><span data-stu-id="9de87-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="9de87-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="9de87-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="9de87-168">Группы Microsoft 365 в Outlook по умолчанию создаются как частные.</span><span class="sxs-lookup"><span data-stu-id="9de87-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="9de87-169">Если ваша организация хочет, чтобы группы Microsoft 365 по умолчанию создавались как общедоступные (или закрытые), используйте синтаксис этого синтаксиса для powerShell:</span><span class="sxs-lookup"><span data-stu-id="9de87-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="9de87-170">Чтобы установить частное:</span><span class="sxs-lookup"><span data-stu-id="9de87-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="9de87-171">Чтобы проверить параметр:</span><span class="sxs-lookup"><span data-stu-id="9de87-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="9de87-172">Дополнительные узнать [см. в настройках Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) и [Get-OrganizationConfig.](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig)</span><span class="sxs-lookup"><span data-stu-id="9de87-172">To learn more, see [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="9de87-173">Microsoft 365 Groups cmdlets</span><span class="sxs-lookup"><span data-stu-id="9de87-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="9de87-174">С группами Microsoft 365 можно использовать следующие cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9de87-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="9de87-175">**Имя командлета**</span><span class="sxs-lookup"><span data-stu-id="9de87-175">**Cmdlet name**</span></span>|<span data-ttu-id="9de87-176">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9de87-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="9de87-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="9de87-177">Get-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |<span data-ttu-id="9de87-178">Используйте этот cmdlet для просмотра существующих групп Microsoft 365 и просмотра свойств объекта группы</span><span class="sxs-lookup"><span data-stu-id="9de87-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="9de87-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="9de87-179">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |<span data-ttu-id="9de87-180">Обновление свойств определенной группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="9de87-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="9de87-181">New-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |<span data-ttu-id="9de87-182">Создайте группу Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9de87-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="9de87-183">Этот cmdlet предоставляет минимальный набор параметров.</span><span class="sxs-lookup"><span data-stu-id="9de87-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="9de87-184">Чтобы установить значения для расширенных свойств, используйте Set-UnifiedGroup после создания новой группы</span><span class="sxs-lookup"><span data-stu-id="9de87-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="9de87-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="9de87-185">Remove-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |<span data-ttu-id="9de87-186">Удаление существующей группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="9de87-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="9de87-187">Get-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |<span data-ttu-id="9de87-188">Извлечение сведений о членстве и владельце для группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="9de87-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="9de87-189">Add-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |<span data-ttu-id="9de87-190">Добавление участников, владельцев и подписчиков в существующую группу Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-190">Add members, owners, and subscribers to an existing Microsoft 365 Group</span></span> <br/> |
|[<span data-ttu-id="9de87-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="9de87-191">Remove-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |<span data-ttu-id="9de87-192">Удаление владельцев и участников из существующей группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="9de87-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="9de87-193">Get-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |<span data-ttu-id="9de87-194">Используется для просмотра сведений о фотографии пользователя, связанной с учетной записью.</span><span class="sxs-lookup"><span data-stu-id="9de87-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="9de87-195">Фотографии пользователей хранятся в Active Directory</span><span class="sxs-lookup"><span data-stu-id="9de87-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="9de87-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="9de87-196">Set-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |<span data-ttu-id="9de87-197">Используется для связываия фотографии пользователя с учетной записью.</span><span class="sxs-lookup"><span data-stu-id="9de87-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="9de87-198">Фотографии пользователей хранятся в Active Directory</span><span class="sxs-lookup"><span data-stu-id="9de87-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="9de87-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="9de87-199">Remove-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |<span data-ttu-id="9de87-200">Удаление фотографии для группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="9de87-201">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="9de87-201">Related topics</span></span>

[<span data-ttu-id="9de87-202">Обновление списков рассылки до групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="9de87-203">Управление тем, кто может создавать группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-203">Manage who can create Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="9de87-204">Управление гостевим доступом к группам Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de87-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="9de87-205">Изменение статического членства в группах на динамическое</span><span class="sxs-lookup"><span data-stu-id="9de87-205">Change static group membership to dynamic in</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
