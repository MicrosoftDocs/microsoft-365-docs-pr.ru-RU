---
title: Настройка настраиваемого списка "не переписывать" URL-адресов с помощью безопасных ссылок ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как настроить пользовательские Заблокированные URL-адреса для пользователей и не переписывать список URL-адресов для группы пользователей в политиках безопасных ссылок на Office 365 ATP.
ms.openlocfilehash: ff2ce18897d7bd1d3890335a237e32bffd1a77e6
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202355"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a><span data-ttu-id="ac3bd-103">Настройка настраиваемого списка "не переписывать" URL-адресов с помощью безопасных ссылок ATP</span><span class="sxs-lookup"><span data-stu-id="ac3bd-103">Set up a custom do-not-rewrite URLs list using ATP Safe Links</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="ac3bd-104">Эта статья предназначена для бизнес-клиентов, у которых есть [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="ac3bd-105">Если вы являетесь домашним пользователем, который ищет сведения о безопасных ссылках в Outlook, ознакомьтесь со статьей [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="ac3bd-106">В [Office 365 Advanced Threat protection](office-365-atp.md) (ATP) в организации могут быть [Настраиваемые Заблокированные URL-адреса](set-up-a-custom-blocked-urls-list-atp.md), например, если пользователи щелкают веб-адреса (URL-адреса) в сообщениях электронной почты или определенных документах Office, они не смогут переходить к этим URL-адресам.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs.</span></span> <span data-ttu-id="ac3bd-107">В организации также могут быть настроены списки "не переопределять" для определенных групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-107">Your organization can also have custom "do not rewrite" lists for specific groups in your organization.</span></span> <span data-ttu-id="ac3bd-108">Список "не переопределять" позволяет некоторым пользователям посещать URL-адреса, которые в противном случае блокируются [безопасными ссылками ATP в Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-108">A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="ac3bd-109">В этой статье описывается, как указать список URL-адресов, исключаемых из проверки безопасных ссылок ATP, и некоторые важные моменты, которые следует учитывать.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

> [!NOTE]
> <span data-ttu-id="ac3bd-110">Если ваша организация использует политики безопасных ссылок, список "не переопределять" является единственным поддерживаемым методом для сторонних антифишинговых проверок.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-110">If your organization use Safe Links policies, the "do not rewrite" list is the only supported method for third party phishing tests.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="ac3bd-111">Настройка списка "не переопределять"</span><span class="sxs-lookup"><span data-stu-id="ac3bd-111">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="ac3bd-112">Защита безопасных ссылок ATP использует несколько списков, в том числе список заблокированных URL-адресов вашей организации, а также списки "не переопределять" для исключений.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-112">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions.</span></span> <span data-ttu-id="ac3bd-113">Если у вас есть необходимые разрешения, вы можете настроить настраиваемые списки "не переопределять".</span><span class="sxs-lookup"><span data-stu-id="ac3bd-113">If you have the necessary permissions, you can set up your custom "do not rewrite" lists.</span></span> <span data-ttu-id="ac3bd-114">Это делается при добавлении или изменении политик безопасных ссылок, которые применяются к определенным получателям в Организации.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-114">You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span>

<span data-ttu-id="ac3bd-115">Чтобы изменить (или определить) политики ATP, необходимо назначить соответствующую роль.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-115">To edit (or define) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="ac3bd-116">В следующей таблице приводятся некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-116">The following table includes some examples.</span></span> <span data-ttu-id="ac3bd-117">Дополнительные сведения см. [в разделе разрешения в центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-117">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

|<span data-ttu-id="ac3bd-118">Роль</span><span class="sxs-lookup"><span data-stu-id="ac3bd-118">Role</span></span>|<span data-ttu-id="ac3bd-119">Где/как назначено</span><span class="sxs-lookup"><span data-stu-id="ac3bd-119">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="ac3bd-120">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="ac3bd-120">global administrator</span></span>|<span data-ttu-id="ac3bd-121">Сотрудник, который подписывается на приобретение Microsoft 365, по умолчанию является глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-121">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="ac3bd-122">(Чтобы узнать больше, ознакомьтесь со статьей [о ролях администратора майкрософт 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)</span><span class="sxs-lookup"><span data-stu-id="ac3bd-122">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="ac3bd-123">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="ac3bd-123">Security Administrator</span></span>|<span data-ttu-id="ac3bd-124">Центр администрирования Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="ac3bd-124">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="ac3bd-125">Управление организациями в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ac3bd-125">Exchange Online Organization Management</span></span>|<span data-ttu-id="ac3bd-126">Центр администрирования Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="ac3bd-126">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="ac3bd-127">или</span><span class="sxs-lookup"><span data-stu-id="ac3bd-127">or</span></span> <br>  <span data-ttu-id="ac3bd-128">Командлеты PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="ac3bd-128">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="ac3bd-129">Дополнительные сведения о ролях и разрешениях приведены [в разделе разрешения в центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-129">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="ac3bd-130">Просмотр и редактирование настраиваемого списка URL-адресов "не переопределять"</span><span class="sxs-lookup"><span data-stu-id="ac3bd-130">To view or edit a custom "do not rewrite" URLs list</span></span>

1. <span data-ttu-id="ac3bd-131">Перейдите к [https://protection.office.com](https://protection.office.com) рабочей или учебной учетной записи и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-131">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="ac3bd-132">На левой панели навигации в разделе **Threat management** \> **Policy** \> **безопасные ссылки**политики управления угрозой.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-132">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="ac3bd-133">В разделе **политики, которые применяются к определенным получателям** нажмите кнопку **создать** (Новая кнопка напоминает знак плюса ( **+** )), чтобы создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-133">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy.</span></span> <span data-ttu-id="ac3bd-134">(Кроме того, вы можете изменить существующую политику.)</span><span class="sxs-lookup"><span data-stu-id="ac3bd-134">(Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="ac3bd-135">![Нажмите кнопку Создать, чтобы добавить политику безопасных ссылок для определенных получателей электронной почты.](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="ac3bd-135">![Choose New to add a Safe Links policy for specific email recipients](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>

4. <span data-ttu-id="ac3bd-136">Укажите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-136">Specify a name and description for your policy.</span></span>

5. <span data-ttu-id="ac3bd-137">Включение **URL** -адресов будет перезаписано и проверено на список известных вредоносных ссылок, когда пользователь щелкает ссылку.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-137">Turn **ON** URLs will be rewritten and checked against a list of known malicious links when user clicks on the link.</span></span>

6. <span data-ttu-id="ac3bd-138">В разделе **не переопределять следующие URL-адреса** установите флажок **Введите действительный URL-** адрес, введите URL-адрес, а затем выберите знак плюс (+).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-138">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, enter a URL, and then choose the plus sign (+).</span></span>

7. <span data-ttu-id="ac3bd-139">В разделе **применено** выберите **получатель**, а затем выберите группу (группы), которую нужно включить в политику.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-139">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="ac3bd-140">Нажмите кнопку **Добавить**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-140">Choose **Add**, and then choose **OK**.</span></span>

8. <span data-ttu-id="ac3bd-141">Завершив добавление URL-адресов, в правом нижнем углу экрана нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-141">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ac3bd-142">Обязательно изучите свой список заблокированных URL-адресов в Организации.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-142">Make sure to review your organization's custom list of blocked URLs.</span></span> <span data-ttu-id="ac3bd-143">[В разделе Настройка настраиваемого списка заблокированных URL-адресов с помощью ссылок ATP Safe](set-up-a-custom-blocked-urls-list-atp.md).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-143">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>

## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="ac3bd-144">Важные моменты, которые следует учитывать</span><span class="sxs-lookup"><span data-stu-id="ac3bd-144">Important points to keep in mind</span></span>

- <span data-ttu-id="ac3bd-145">Все URL-адреса, указанные в списке "не перезаписывать", будут исключены из проверки безопасных ссылок ATP для указанных получателей.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-145">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>

- <span data-ttu-id="ac3bd-146">Рассмотрите возможность добавления часто используемых внутренних URL-адресов в список "не переопределять" для усовершенствования взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-146">Consider adding commonly used internal URLs to the "do not rewrite" list to improve the user experience.</span></span> <span data-ttu-id="ac3bd-147">Например, если у вас есть локальные службы, такие как Skype для бизнеса или SharePoint, вы можете добавить их URL-адреса в список, чтобы исключить их из проверки.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-147">For example, if you have on-premises services, such as Skype for Business or Sharepoint, you can add their URLs to the list to exclude them from scanning.</span></span>

- <span data-ttu-id="ac3bd-148">Если у вас уже есть список URL-адресов в списке "не переопределять", обязательно просмотрите список и добавьте подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-148">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate.</span></span> <span data-ttu-id="ac3bd-149">Например, если у имеющегося списка есть запись, `https://contoso.com/a` а вы хотите включить подпути, такие как `https://contoso.com/a/b` в вашей политике, добавьте к записи подстановочный знак, чтобы он выглядел так `https://contoso.com/a/*` :</span><span class="sxs-lookup"><span data-stu-id="ac3bd-149">For example, if your existing list has an entry like `https://contoso.com/a` and you want to include subpaths like `https://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="ac3bd-150">При указании списка "не переопределять" для политики безопасных ссылок ATP можно добавить до трех подстановочных знаков ( \* ).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-150">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcards (\*).</span></span> <span data-ttu-id="ac3bd-151">В явном виде используются префиксы или поддомены.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-151">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="ac3bd-152">Например, запись `contoso.com` не совпадает с `*.contoso.com/*` , так как `*.contoso.com/*` позволяет людям посещать поддомены и пути в указанном домене.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-152">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

<span data-ttu-id="ac3bd-153">В следующей таблице приведены примеры того, что можно ввести и какие действия имеют эти записи.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-153">The following table lists examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="ac3bd-154">Пример записи</span><span class="sxs-lookup"><span data-stu-id="ac3bd-154">Example Entry</span></span>|<span data-ttu-id="ac3bd-155">Что он делает</span><span class="sxs-lookup"><span data-stu-id="ac3bd-155">What It Does</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="ac3bd-156">Позволяет получателям посещать сайт, как, например, `https://contoso.com` без поддоменов или путей.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-156">Allows recipients to visit a site like `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="ac3bd-157">Позволяет получателям посещать домен, дочерние домены и пути, например `https://www.contoso.com` ,, `https://www.contoso.com` , `https://maps.contoso.com` или `https://www.contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ac3bd-157">Allows recipients to visit a domain, subdomains, and paths, such as `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`.</span></span> <br/><br/> <span data-ttu-id="ac3bd-158">Эта запись по сути лучше `*contoso.com*` , так как она не включает потенциально мошеннические сайты, например `https://www.falsecontoso.com` или `https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="ac3bd-158">This entry is inherently better than `*contoso.com*`, because it doesn't include potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="ac3bd-159">Позволяет конкретным получателям посетить сайт, например `https://contoso.com/a` , недопустимые подпути, такие как `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="ac3bd-159">Allows specific recipients to visit a site like `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="ac3bd-160">Позволяет конкретным получателям посещать подобные `https://contoso.com/a` и вложенные пути, такие как `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="ac3bd-160">Allows specific recipients to visit a site like `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|
