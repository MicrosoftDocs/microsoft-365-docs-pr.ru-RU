---
title: Настройка настраиваемого списка заблокированных URL-адресов с помощью безопасных ссылок Office 365 ATP
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
description: Узнайте, как настроить список заблокированных URL-адресов для Организации с помощью Office 365 Advanced Threat protection. Заблокированные URL-адреса будут применяться к сообщениям электронной почты и документам Office в соответствии с политиками безопасных ссылок ATP.
ms.openlocfilehash: 5205fbd5ccc873513eed4e367119084516e92bf2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088097"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="6f28c-104">Настройка настраиваемого списка заблокированных URL-адресов с помощью безопасных ссылок Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="6f28c-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f28c-105">Эта статья предназначена для бизнес-клиентов, у которых есть [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="6f28c-105">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="6f28c-106">Если вы являетесь домашним пользователем, который ищет сведения о безопасных ссылках в Outlook, ознакомьтесь со статьей [Advanced Outlook.com Security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="6f28c-106">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="6f28c-107">В [Office 365 Advanced Threat protection](office-365-atp.md) (ATP) в Организации может быть настроен список блокируемых адресов веб-сайтов (URL-адресов).</span><span class="sxs-lookup"><span data-stu-id="6f28c-107">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="6f28c-108">Если URL-адрес заблокирован, пользователи, которые щелкают ссылки на заблокированный URL-адрес, отправляются на [страницу предупреждения](atp-safe-links-warning-pages.md) , напоминающую следующему изображению:</span><span class="sxs-lookup"><span data-stu-id="6f28c-108">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![Этот сайт заблокирован](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="6f28c-110">Список заблокированных URL-адресов определяется группой безопасности Office 365 в Организации, и этот список применяется ко всем пользователям в Организации, на которые распространяется политика безопасных ссылок Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="6f28c-110">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="6f28c-111">В этой статье рассказывается, как настроить настраиваемый список заблокированных URL-адресов вашей организации для [безопасных ссылок ATP в Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="6f28c-111">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="6f28c-112">Просмотр или изменение настраиваемого списка заблокированных URL-адресов</span><span class="sxs-lookup"><span data-stu-id="6f28c-112">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="6f28c-113">[Для безопасных ссылок ATP в Office 365](atp-safe-links.md) используется несколько списков, в том числе настраиваемый список заблокированных URL-адресов вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6f28c-113">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="6f28c-114">Если у вас есть необходимые разрешения, вы можете настроить настраиваемый список в Организации.</span><span class="sxs-lookup"><span data-stu-id="6f28c-114">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="6f28c-115">Для этого необходимо изменить политику безопасных ссылок по умолчанию в Организации.</span><span class="sxs-lookup"><span data-stu-id="6f28c-115">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="6f28c-116">Чтобы изменить (или определить) политики ATP, необходимо назначить одну из ролей, описанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6f28c-116">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="6f28c-117">Роль</span><span class="sxs-lookup"><span data-stu-id="6f28c-117">Role</span></span>  |<span data-ttu-id="6f28c-118">Где/как назначено</span><span class="sxs-lookup"><span data-stu-id="6f28c-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="6f28c-119">Глобальный администратор Office 365</span><span class="sxs-lookup"><span data-stu-id="6f28c-119">Office 365 Global Administrator</span></span> |<span data-ttu-id="6f28c-120">Пользователь, который подписывается на приобретение Office 365, по умолчанию является глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="6f28c-120">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="6f28c-121">(Чтобы узнать больше, ознакомьтесь со статьей [о ролях администратора Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .)</span><span class="sxs-lookup"><span data-stu-id="6f28c-121">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="6f28c-122">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="6f28c-122">Security Administrator</span></span> |<span data-ttu-id="6f28c-123">Центр администрирования Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="6f28c-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="6f28c-124">Управление организациями в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6f28c-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="6f28c-125">Центр администрирования Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="6f28c-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="6f28c-126">или</span><span class="sxs-lookup"><span data-stu-id="6f28c-126">or</span></span> <br>  <span data-ttu-id="6f28c-127">Командлеты PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="6f28c-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span> |

> [!TIP]
> <span data-ttu-id="6f28c-128">Дополнительные сведения о ролях и разрешениях приведены [в разделе разрешения в центре безопасности &amp; и соответствия требованиям Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6f28c-128">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="6f28c-129">Просмотр или изменение настраиваемого списка заблокированных URL-адресов</span><span class="sxs-lookup"><span data-stu-id="6f28c-129">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="6f28c-130">Перейдите к [https://protection.office.com](https://protection.office.com) рабочей или учебной учетной записи и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="6f28c-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="6f28c-131">В панели навигации слева в разделе **Управление угрозами**выберите **пункт** \> **безопасные ссылки**.</span><span class="sxs-lookup"><span data-stu-id="6f28c-131">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="6f28c-132">В разделе **политики, которые применяются ко всей Организации** , выберите **значение по умолчанию**, а затем нажмите кнопку **изменить** (кнопка Изменить напоминает карандаш).</span><span class="sxs-lookup"><span data-stu-id="6f28c-132">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="6f28c-133">![Нажмите кнопку изменить, чтобы изменить политику по умолчанию для защиты безопасных ссылок](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="6f28c-133">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="6f28c-134">Это позволяет просматривать список заблокированных URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="6f28c-134">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="6f28c-135">В первую очередь могут не быть указаны URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="6f28c-135">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="6f28c-136">![Список заблокированных URL-адресов в политике безопасных ссылок по умолчанию](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="6f28c-136">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="6f28c-137">Выберите поле **Введите допустимый URL** -адрес, введите URL-адрес, а затем выберите знак плюса (**+**).</span><span class="sxs-lookup"><span data-stu-id="6f28c-137">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="6f28c-138">Завершив добавление URL-адресов, в правом нижнем углу экрана нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6f28c-138">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="6f28c-139">Следует учитывать несколько моментов.</span><span class="sxs-lookup"><span data-stu-id="6f28c-139">A few things to keep in mind</span></span>

<span data-ttu-id="6f28c-140">При добавлении URL-адресов в список учитывайте следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="6f28c-140">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="6f28c-141">Не включайте косую черту ( **/**) в конце URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="6f28c-141">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="6f28c-142">Например, вместо ввода `https://www.contoso.com/`введите. `https://www.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="6f28c-142">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>
    
- <span data-ttu-id="6f28c-143">Можно указать URL-адрес только для домена (например `contoso.com` , `tailspintoys.com`или).</span><span class="sxs-lookup"><span data-stu-id="6f28c-143">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="6f28c-144">При этом будут заблокированы нажатия на любой URL-адрес, содержащий домен.</span><span class="sxs-lookup"><span data-stu-id="6f28c-144">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="6f28c-145">Можно указать поддомен (например `toys.contoso.com*`,), не блокируя полный домен (например `contoso.com`,).</span><span class="sxs-lookup"><span data-stu-id="6f28c-145">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="6f28c-146">При этом будет выполняться переход по любому URL-адресу, который содержит поддомен, но не будет блокировать переходы по URL-адресу, содержащему полный домен.</span><span class="sxs-lookup"><span data-stu-id="6f28c-146">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="6f28c-147">В URL-адрес можно добавить до трех подстановочных\*знаков ().</span><span class="sxs-lookup"><span data-stu-id="6f28c-147">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="6f28c-148">В следующей таблице приведено несколько примеров того, что можно ввести и какие действия имеют эти записи.</span><span class="sxs-lookup"><span data-stu-id="6f28c-148">The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="6f28c-149">**Пример записи**</span><span class="sxs-lookup"><span data-stu-id="6f28c-149">**Example Entry**</span></span>|<span data-ttu-id="6f28c-150">**Что он делает**</span><span class="sxs-lookup"><span data-stu-id="6f28c-150">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6f28c-151">`contoso.com` или `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="6f28c-151">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="6f28c-152">Блокирует домен, дочерние домены и пути, например `https://www.contoso.com`, и `https://sub.contoso.com``https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="6f28c-152">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>  <br/> |
|`https://contoso.com/a`  <br/> |<span data-ttu-id="6f28c-153">Блокирует сайт `https://contoso.com/a` , но не дополнительные подпути, такие как`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="6f28c-153">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>  <br/> |
|`https://contoso.com/a*`  <br/> |<span data-ttu-id="6f28c-154">Блокирует сайт `https://contoso.com/a` и дополнительные подпути, такие как`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="6f28c-154">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>  <br/> |
|`https://toys.contoso.com*`  <br/> |<span data-ttu-id="6f28c-155">Блокирует поддомен (в данном случае — "Toys"), но разрешить переход на другие URL-адреса доменов `https://contoso.com` ( `https://home.contoso.com`например, или).</span><span class="sxs-lookup"><span data-stu-id="6f28c-155">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="6f28c-156">Определение исключений для определенных пользователей в Организации</span><span class="sxs-lookup"><span data-stu-id="6f28c-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="6f28c-157">Если требуется, чтобы определенные группы могли просматривать URL-адреса, которые могут быть заблокированы для других, можно указать политику безопасных ссылок ATP, которая применяется к определенным получателям.</span><span class="sxs-lookup"><span data-stu-id="6f28c-157">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="6f28c-158">Узнайте [, как настроить настраиваемый список URL-адресов "не переопределять" с помощью ссылок ATP Safe](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="6f28c-158">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

