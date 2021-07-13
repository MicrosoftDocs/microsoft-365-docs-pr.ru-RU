---
title: Удаление домена
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Узнайте, как удалить старый домен из Microsoft 365 и переместить пользователей и группы в другой домен или отменить подписку.
ms.openlocfilehash: 227ca3e58a4c6278278048deeffcf68c1d659546
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393875"
---
# <a name="remove-a-domain"></a><span data-ttu-id="d1034-103">Удаление домена</span><span class="sxs-lookup"><span data-stu-id="d1034-103">Remove a domain</span></span>

 <span data-ttu-id="d1034-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="d1034-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="d1034-105">Вы удаляете домен, так как хотите добавить его в другой Microsoft 365 подписки?</span><span class="sxs-lookup"><span data-stu-id="d1034-105">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="d1034-106">Или вам нужно просто отменить свою подписку?</span><span class="sxs-lookup"><span data-stu-id="d1034-106">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="d1034-107">Вы можете [сменить план или подписку](../../commerce/subscriptions/switch-to-a-different-plan.md) либо [отменить подписку](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="d1034-107">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>

### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="d1034-108">Шаг 1. Перемещение пользователей в другой домен</span><span class="sxs-lookup"><span data-stu-id="d1034-108">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="d1034-109">Перемещение пользователей</span><span class="sxs-lookup"><span data-stu-id="d1034-109">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d1034-110">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="d1034-110">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d1034-111">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="d1034-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d1034-112">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="d1034-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

::: moniker-end

2. <span data-ttu-id="d1034-113">Выбор **пользователей**  >  **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d1034-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="d1034-114">Выберите поля рядом с именами всех пользователей, которых вы хотите переместить.</span><span class="sxs-lookup"><span data-stu-id="d1034-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="d1034-115">В верхней части страницы выберите **домены Change**.</span><span class="sxs-lookup"><span data-stu-id="d1034-115">At the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="d1034-116">В области **Изменить домены** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="d1034-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="d1034-p102">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="d1034-p102">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

#### <a name="move-yourself"></a><span data-ttu-id="d1034-119">Перемещение самостоятельно</span><span class="sxs-lookup"><span data-stu-id="d1034-119">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d1034-120">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="d1034-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d1034-121">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="d1034-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d1034-122">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="d1034-122">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

::: moniker-end

2. <span data-ttu-id="d1034-123">Перейдите **к активным** \> **пользователям** и выберите учетную запись из списка.</span><span class="sxs-lookup"><span data-stu-id="d1034-123">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="d1034-124">На **вкладке Учетная** запись **выберите Управление иным** доменом.</span><span class="sxs-lookup"><span data-stu-id="d1034-124">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>

4. <span data-ttu-id="d1034-125">В верхней части выберите имя учетной записи, а затем **выберите Sign Out**.</span><span class="sxs-lookup"><span data-stu-id="d1034-125">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="d1034-126">Вход с новым доменом и тем же паролем.</span><span class="sxs-lookup"><span data-stu-id="d1034-126">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="d1034-p103">Переместить пользователей в другой домен можно также с помощью PowerShell. Дополнительные сведения см. в статье о командлете [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname). Чтобы задать домен по умолчанию, используйте командлет [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).</span><span class="sxs-lookup"><span data-stu-id="d1034-p103">You can also use PowerShell to move users to another domain. See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) for more information. To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).</span></span>

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="d1034-130">Шаг 2. Перемещение групп в другой домен</span><span class="sxs-lookup"><span data-stu-id="d1034-130">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d1034-131">В центре администрирования перейдите на страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">групп.</a></span><span class="sxs-lookup"><span data-stu-id="d1034-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="d1034-132">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">администрирования</a>перейдите на страницу **Группы** > **групп.**</span><span class="sxs-lookup"><span data-stu-id="d1034-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d1034-133">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">администрирования</a>перейдите на страницу **Группы** > **групп.**</span><span class="sxs-lookup"><span data-stu-id="d1034-133">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

::: moniker-end

2. <span data-ttu-id="d1034-134">Выберите имя группы, а затем на вкладке **General** в соответствии с адресом **электронной почты, Primary**, выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d1034-134">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="d1034-135">Используйте выпадаемый список, чтобы выбрать другой домен.</span><span class="sxs-lookup"><span data-stu-id="d1034-135">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="d1034-136">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="d1034-136">Select **Save**, then **Close**.</span></span> <span data-ttu-id="d1034-137">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="d1034-137">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="d1034-138">Шаг 3. Удаление старого домена</span><span class="sxs-lookup"><span data-stu-id="d1034-138">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d1034-139">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="d1034-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d1034-140">В центре администрирования перейдите на страницу **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains.</a></span><span class="sxs-lookup"><span data-stu-id="d1034-140">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d1034-141">В центре администрирования перейдите на страницу **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains.</a></span><span class="sxs-lookup"><span data-stu-id="d1034-141">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="d1034-142">На странице **Домены** выберите домен, который необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="d1034-142">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="d1034-143">В правой области выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d1034-143">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="d1034-144">Выполните дополнительные запросы и выберите **Close**.</span><span class="sxs-lookup"><span data-stu-id="d1034-144">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="d1034-145">Время, необходимое для удаления домена</span><span class="sxs-lookup"><span data-stu-id="d1034-145">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="d1034-146">Удаление домена может занять всего 5 минут Microsoft 365 если он не указан во многих местах, таких как группы безопасности, списки рассылки, пользователи и Microsoft 365 группы.</span><span class="sxs-lookup"><span data-stu-id="d1034-146">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="d1034-147">Если же домен используется очень широко, на его удаление может потребоваться несколько часов или один день.</span><span class="sxs-lookup"><span data-stu-id="d1034-147">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>

<span data-ttu-id="d1034-p106">Если у вас сотни или тысячи пользователей, используйте PowerShell, чтобы отправить им всем запрос, а затем перенести их в другой домен. В противном случае может оказаться, что нескольких пользователей нет в интерфейсе. В результате вы не сможете удалить домен и не сумеете определить причину. Дополнительные сведения см. в статье о командлете [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname). Чтобы задать домен по умолчанию, используйте командлет [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).</span><span class="sxs-lookup"><span data-stu-id="d1034-p106">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) for more information. To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).</span></span>

## <a name="still-need-help"></a><span data-ttu-id="d1034-152">Требуется дополнительная помощь?</span><span class="sxs-lookup"><span data-stu-id="d1034-152">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="d1034-153">Не удается удалить домен [".onmicrosoft.com"](../setup/domains-faq.yml) из вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d1034-153">You can't remove the [".onmicrosoft.com"](../setup/domains-faq.yml) domain from your account.</span></span> <span data-ttu-id="d1034-154">После удаления домена учетные записи пользователей будут возвращаться к адресу ".onmicrosoft.com" в качестве основного SMTP/UserprincipalName.</span><span class="sxs-lookup"><span data-stu-id="d1034-154">When you remove a domain, user accounts will revert back to the ".onmicrosoft.com" address as the Primary SMTP/UserprincipalName.</span></span>

<span data-ttu-id="d1034-p108">Не получилось? Возможно, ваш домен необходимо удалить вручную. [Позвоните нем](../../business-video/get-help-support.md), и мы поможем вам это сделать.</span><span class="sxs-lookup"><span data-stu-id="d1034-p108">Still not working? Your domain might need to be manually removed. [Give us a call](../../business-video/get-help-support.md) and we'll help you take care of it!</span></span>

::: moniker-end

::: moniker range="o365-germany"

> [!NOTE]
> <span data-ttu-id="d1034-158">Вы не можете удалить [домен ".onmicrosoft.de"](../setup/domains-faq.yml) из учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d1034-158">You can't remove the [".onmicrosoft.de"](../setup/domains-faq.yml) domain from your account.</span></span> <span data-ttu-id="d1034-159">После удаления домена учетные записи пользователей будут возвращаться к адресу ".onmicrosoft.de" в качестве основного SMTP/UserprincipalName.</span><span class="sxs-lookup"><span data-stu-id="d1034-159">When you remove a domain, user accounts will revert back to the ".onmicrosoft.de" address as the Primary SMTP/UserprincipalName.</span></span>

<span data-ttu-id="d1034-p110">Не получилось? Возможно, ваш домен необходимо удалить вручную. [Позвоните нем](../../business-video/get-help-support.md?view=o365-germany&preserve-view=true), и мы поможем вам это сделать.</span><span class="sxs-lookup"><span data-stu-id="d1034-p110">Still not working? Your domain might need to be manually removed. [Give us a call](../../business-video/get-help-support.md?view=o365-germany&preserve-view=true) and we'll help you take care of it!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d1034-163">Вы не можете удалить [домен ".partner.onmschina.cn"](../setup/domains-faq.yml) из учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d1034-163">You can't remove the [".partner.onmschina.cn"](../setup/domains-faq.yml) domain from your account.</span></span> <span data-ttu-id="d1034-164">После удаления домена учетные записи пользователей будут возвращаться к адресу ".partner.onmschina.cn" в качестве основного SMTP/UserprincipalName.</span><span class="sxs-lookup"><span data-stu-id="d1034-164">When you remove a domain, user accounts will revert back to the ".partner.onmschina.cn" address as the Primary SMTP/UserprincipalName.</span></span>

<span data-ttu-id="d1034-p112">Не получилось? Возможно, ваш домен необходимо удалить вручную. [Позвоните нем](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true), и мы поможем вам это сделать.</span><span class="sxs-lookup"><span data-stu-id="d1034-p112">Still not working? Your domain might need to be manually removed. [Give us a call](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true) and we'll help you take care of it!</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="d1034-168">См. также:</span><span class="sxs-lookup"><span data-stu-id="d1034-168">Related content</span></span>

<span data-ttu-id="d1034-169">[Вопросы и ответы о доменах](../setup/domains-faq.yml) (статья)</span><span class="sxs-lookup"><span data-stu-id="d1034-169">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>

<span data-ttu-id="d1034-170">[Переключиться на другой Microsoft 365 бизнес-плана](../../commerce/subscriptions/switch-to-a-different-plan.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="d1034-170">[Switch to a different Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md) (article)</span></span>

<span data-ttu-id="d1034-171">[Отмена подписки](../../commerce/subscriptions/cancel-your-subscription.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="d1034-171">[Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md) (article)</span></span>
