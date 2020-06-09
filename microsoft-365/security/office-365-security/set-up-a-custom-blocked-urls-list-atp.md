---
title: Настройка настраиваемого списка заблокированных URL-адресов с помощью безопасных ссылок ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как настроить список заблокированных URL-адресов для Организации с помощью Office 365 Advanced Threat protection.
ms.openlocfilehash: 5c5253aabf5d5235e31f24624fd9e1b3f4adb184
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617268"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="c0841-103">Настройка настраиваемого списка заблокированных URL-адресов с помощью безопасных ссылок ATP</span><span class="sxs-lookup"><span data-stu-id="c0841-103">Set up a custom blocked URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0841-104">Эта статья предназначена для бизнес-клиентов, у которых есть [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="c0841-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="c0841-105">Если вы являетесь домашним пользователем, который ищет сведения о безопасных ссылках в Outlook, ознакомьтесь со статьей [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="c0841-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="c0841-106">В [Office 365 Advanced Threat protection](office-365-atp.md) (ATP) в Организации может быть настроен список блокируемых адресов веб-сайтов (URL-адресов).</span><span class="sxs-lookup"><span data-stu-id="c0841-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="c0841-107">Если URL-адрес заблокирован, пользователи, которые щелкают ссылки на заблокированный URL-адрес, отправляются на [страницу предупреждения](atp-safe-links-warning-pages.md) , напоминающую следующему изображению:</span><span class="sxs-lookup"><span data-stu-id="c0841-107">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span>

![Этот сайт заблокирован](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="c0841-109">Список заблокированных URL-адресов определяется группой безопасности Microsoft 365 для бизнеса, и этот список применяется ко всем пользователям в Организации, на которые распространяется политика безопасных ссылок Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="c0841-109">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span>

<span data-ttu-id="c0841-110">В этой статье рассказывается, как настроить настраиваемый список заблокированных URL-адресов вашей организации для [безопасных ссылок ATP в Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="c0841-110">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="c0841-111">Просмотр или изменение настраиваемого списка заблокированных URL-адресов</span><span class="sxs-lookup"><span data-stu-id="c0841-111">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="c0841-112">[Для безопасных ссылок ATP в Office 365](atp-safe-links.md) используется несколько списков, в том числе настраиваемый список заблокированных URL-адресов вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c0841-112">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="c0841-113">Если у вас есть необходимые разрешения, вы можете настроить настраиваемый список в Организации.</span><span class="sxs-lookup"><span data-stu-id="c0841-113">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="c0841-114">Для этого необходимо изменить политику безопасных ссылок по умолчанию в Организации.</span><span class="sxs-lookup"><span data-stu-id="c0841-114">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="c0841-115">Чтобы изменить (или определить) политики ATP, необходимо назначить одну из ролей, описанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c0841-115">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="c0841-116">Role</span><span class="sxs-lookup"><span data-stu-id="c0841-116">Role</span></span>|<span data-ttu-id="c0841-117">Где/как назначено</span><span class="sxs-lookup"><span data-stu-id="c0841-117">Where/how assigned</span></span>|
|---------|---------|
|<span data-ttu-id="c0841-118">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="c0841-118">global administrator</span></span>|<span data-ttu-id="c0841-119">Сотрудник, который подписывается на приобретение Microsoft 365, по умолчанию является глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="c0841-119">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="c0841-120">(Чтобы узнать больше, ознакомьтесь со статьей [о ролях администратора майкрософт 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)</span><span class="sxs-lookup"><span data-stu-id="c0841-120">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="c0841-121">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="c0841-121">Security Administrator</span></span>|<span data-ttu-id="c0841-122">Центр администрирования Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="c0841-122">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="c0841-123">Управление организациями в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c0841-123">Exchange Online Organization Management</span></span>|<span data-ttu-id="c0841-124">Центр администрирования Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="c0841-124">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="c0841-125">или</span><span class="sxs-lookup"><span data-stu-id="c0841-125">or</span></span> <br>  <span data-ttu-id="c0841-126">Командлеты PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="c0841-126">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|

> [!TIP]
> <span data-ttu-id="c0841-127">Дополнительные сведения о ролях и разрешениях приведены [в разделе разрешения в центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c0841-127">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="c0841-128">Просмотр или изменение настраиваемого списка заблокированных URL-адресов</span><span class="sxs-lookup"><span data-stu-id="c0841-128">To view or edit a custom blocked URLs list</span></span>

1. <span data-ttu-id="c0841-129">Перейдите к [https://protection.office.com](https://protection.office.com) рабочей или учебной учетной записи и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="c0841-129">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="c0841-130">В панели навигации слева в разделе **Управление угрозами**выберите **пункт** \> **безопасные ссылки**.</span><span class="sxs-lookup"><span data-stu-id="c0841-130">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="c0841-131">В разделе **политики, которые применяются ко всей Организации** , выберите **значение по умолчанию**, а затем нажмите кнопку **изменить** (кнопка Изменить напоминает карандаш).</span><span class="sxs-lookup"><span data-stu-id="c0841-131">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="c0841-132">![Нажмите кнопку изменить, чтобы изменить политику по умолчанию для защиты безопасных ссылок](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="c0841-132">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="c0841-133">Это позволяет просматривать список заблокированных URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="c0841-133">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="c0841-134">В первую очередь могут не быть указаны URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="c0841-134">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="c0841-135">![Список заблокированных URL-адресов в политике безопасных ссылок по умолчанию](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="c0841-135">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>

4. <span data-ttu-id="c0841-136">Выберите поле **Введите допустимый URL** -адрес, введите URL-адрес, а затем выберите знак плюса ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="c0841-136">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span>

5. <span data-ttu-id="c0841-137">Завершив добавление URL-адресов, в правом нижнем углу экрана нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c0841-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="c0841-138">Следует учитывать несколько моментов.</span><span class="sxs-lookup"><span data-stu-id="c0841-138">A few things to keep in mind</span></span>

<span data-ttu-id="c0841-139">При добавлении URL-адресов в список учитывайте следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="c0841-139">While you add URLs to your list, keep the following points in mind:</span></span>

- <span data-ttu-id="c0841-140">Не включайте косую черту ( **/** ) в конце URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="c0841-140">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="c0841-141">Например, вместо ввода `https://www.contoso.com/` введите `https://www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="c0841-141">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>

- <span data-ttu-id="c0841-142">Можно указать URL-адрес только для домена (например `contoso.com` , или `tailspintoys.com` ).</span><span class="sxs-lookup"><span data-stu-id="c0841-142">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="c0841-143">При этом будут заблокированы нажатия на любой URL-адрес, содержащий домен.</span><span class="sxs-lookup"><span data-stu-id="c0841-143">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="c0841-144">Можно указать поддомен (например,), `toys.contoso.com*` не блокируя полный домен (например, `contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="c0841-144">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="c0841-145">При этом будет выполняться переход по любому URL-адресу, который содержит поддомен, но не будет блокировать переходы по URL-адресу, содержащему полный домен.</span><span class="sxs-lookup"><span data-stu-id="c0841-145">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>

- <span data-ttu-id="c0841-146">В URL-адрес можно добавить до трех подстановочных знаков ( \* ).</span><span class="sxs-lookup"><span data-stu-id="c0841-146">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="c0841-147">В следующей таблице приведено несколько примеров того, что можно ввести и какие действия имеют эти записи.</span><span class="sxs-lookup"><span data-stu-id="c0841-147">The following table lists some examples of what you can enter and what effect those entries have.</span></span>

|<span data-ttu-id="c0841-148">Пример записи</span><span class="sxs-lookup"><span data-stu-id="c0841-148">Example Entry</span></span>|<span data-ttu-id="c0841-149">Что он делает</span><span class="sxs-lookup"><span data-stu-id="c0841-149">What It Does</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0841-150">`contoso.com` или `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="c0841-150">`contoso.com` or `*contoso.com*`</span></span>|<span data-ttu-id="c0841-151">Блокирует домен, дочерние домены и пути, например `https://www.contoso.com` , `https://sub.contoso.com` и`https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="c0841-151">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="c0841-152">Блокирует сайт, `https://contoso.com/a` но не дополнительные подпути, такие как`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="c0841-152">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="c0841-153">Блокирует сайт `https://contoso.com/a` и дополнительные подпути, такие как`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="c0841-153">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="c0841-154">Блокирует поддомен (в данном случае — "Toys"), но разрешить переход на другие URL-адреса доменов (например `https://contoso.com` , или `https://home.contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="c0841-154">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="c0841-155">Определение исключений для определенных пользователей в Организации</span><span class="sxs-lookup"><span data-stu-id="c0841-155">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="c0841-156">Если требуется, чтобы определенные группы могли просматривать URL-адреса, которые могут быть заблокированы для других, можно указать политику безопасных ссылок ATP, которая применяется к определенным получателям.</span><span class="sxs-lookup"><span data-stu-id="c0841-156">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="c0841-157">Узнайте [, как настроить настраиваемый список URL-адресов "не переопределять" с помощью ссылок ATP Safe](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="c0841-157">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
