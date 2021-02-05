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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Узнайте, как удалить старый домен из Microsoft 365 и переместить пользователей и группы в другой домен.
ms.openlocfilehash: 39f8d97abb3a424251d6847da02f0dcc58baff31
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114013"
---
# <a name="remove-a-domain"></a><span data-ttu-id="e3414-103">Удаление домена</span><span class="sxs-lookup"><span data-stu-id="e3414-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e3414-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="e3414-104">The admin center is changing.</span></span> <span data-ttu-id="e3414-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="e3414-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end
  
 <span data-ttu-id="e3414-106">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="e3414-106">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e3414-107">Вы удаляете домен, потому что хотите добавить его в другой план подписки На Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e3414-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="e3414-108">Или вам нужно просто отменить свою подписку?</span><span class="sxs-lookup"><span data-stu-id="e3414-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="e3414-109">Вы можете [сменить план или подписку](../../commerce/subscriptions/switch-to-a-different-plan.md) либо [отменить подписку](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="e3414-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="e3414-110">Шаг 1. Перемещение пользователей в другой домен</span><span class="sxs-lookup"><span data-stu-id="e3414-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="e3414-111">Перемещение пользователей</span><span class="sxs-lookup"><span data-stu-id="e3414-111">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e3414-112">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="e3414-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="e3414-113">Выберите **"Пользователи** > **активные пользователи"**.</span><span class="sxs-lookup"><span data-stu-id="e3414-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e3414-114">Выберите поля рядом с именами всех пользователей, которых нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="e3414-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e3414-115">Выберите **дополнительные параметры** **(...**) в верхней части страницы и выберите **"Изменить домены".**</span><span class="sxs-lookup"><span data-stu-id="e3414-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="e3414-116">В области **"Изменение доменов"** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="e3414-p103">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e3414-119">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="e3414-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="e3414-120">Выберите **"Пользователи** > **активные пользователи"**.</span><span class="sxs-lookup"><span data-stu-id="e3414-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e3414-121">Выберите поля рядом с именами всех пользователей, которых нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="e3414-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e3414-122">В верхней части страницы выберите  > **"Дополнительные домены редактирования".**</span><span class="sxs-lookup"><span data-stu-id="e3414-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="e3414-123">В области **"Изменение доменов"** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="e3414-p104">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e3414-126">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="e3414-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="e3414-127">Выберите **"Пользователи** > **активные пользователи"**.</span><span class="sxs-lookup"><span data-stu-id="e3414-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e3414-128">Выберите поля рядом с именами всех пользователей, которых нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="e3414-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e3414-129">В верхней части страницы выберите  > **"Дополнительные домены редактирования".**</span><span class="sxs-lookup"><span data-stu-id="e3414-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="e3414-130">В области **"Изменение доменов"** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="e3414-p105">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="e3414-133">Перемещение себя</span><span class="sxs-lookup"><span data-stu-id="e3414-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e3414-134">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="e3414-134">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="e3414-135">Перейдите **к** \> **"Активные пользователи"** и выберите свою учетную запись в списке.</span><span class="sxs-lookup"><span data-stu-id="e3414-135">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="e3414-136">На **вкладке "Учетная** запись" **выберите "Управление именю пользователя",** а затем выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-136">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="e3414-137">В верхней части выберите имя своей учетной записи, а затем **выберите "Выйти".**</span><span class="sxs-lookup"><span data-stu-id="e3414-137">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e3414-138">Во sign in with the new domain and your same password.</span><span class="sxs-lookup"><span data-stu-id="e3414-138">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e3414-139">Вы также можете использовать PowerShell для перемещения пользователей в другой домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-139">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e3414-140">Дополнительные сведения см. в перенастройке [Set-MsolUserPrincipalName.](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="e3414-140">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e3414-141">Чтобы установить домен по умолчанию, используйте [Set-MsolDomain.](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="e3414-141">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e3414-142">Перейдите **к** \> **"Активные пользователи"** и выберите свое имя в списке.</span><span class="sxs-lookup"><span data-stu-id="e3414-142">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="e3414-143">В разделе **"Имя пользователя / Электронная почта"** выберите "Изменить", а затем выберите другой домен. </span><span class="sxs-lookup"><span data-stu-id="e3414-143">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="e3414-144">Select **Set as primary** > **Save** > **Close**.</span><span class="sxs-lookup"><span data-stu-id="e3414-144">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="e3414-145">В верхней части выберите имя своей учетной записи, а затем **выберите "Выйти".**</span><span class="sxs-lookup"><span data-stu-id="e3414-145">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e3414-146">Во sign in with the new domain and your same password.</span><span class="sxs-lookup"><span data-stu-id="e3414-146">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e3414-147">Вы также можете использовать PowerShell для перемещения пользователей в другой домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-147">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e3414-148">Дополнительные сведения см. в перенастройке [Set-MsolUserPrincipalName.](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="e3414-148">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e3414-149">Чтобы установить домен по умолчанию, используйте [Set-MsolDomain.](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="e3414-149">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e3414-150">Перейдите **к** \> **"Активные пользователи"** и выберите свое имя в списке.</span><span class="sxs-lookup"><span data-stu-id="e3414-150">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="e3414-151">В разделе **"Имя пользователя / Электронная почта"** выберите "Изменить", а затем выберите другой домен. </span><span class="sxs-lookup"><span data-stu-id="e3414-151">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="e3414-152">Select **Set as primary** > **Save** > **Close**.</span><span class="sxs-lookup"><span data-stu-id="e3414-152">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="e3414-153">В верхней части выберите имя своей учетной записи, а затем **выберите "Выйти".**</span><span class="sxs-lookup"><span data-stu-id="e3414-153">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e3414-154">Во sign in with the new domain and your same password.</span><span class="sxs-lookup"><span data-stu-id="e3414-154">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e3414-155">Вы также можете использовать PowerShell для перемещения пользователей в другой домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-155">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e3414-156">Дополнительные сведения см. в перенастройке [Set-MsolUserPrincipalName.](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="e3414-156">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e3414-157">Чтобы установить домен по умолчанию, используйте [Set-MsolDomain.](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="e3414-157">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="e3414-158">Шаг 2. Перемещение групп в другой домен</span><span class="sxs-lookup"><span data-stu-id="e3414-158">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e3414-159">В Центре администрирования перейдите на **страницу** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">"Группы групп".</a></span><span class="sxs-lookup"><span data-stu-id="e3414-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="e3414-160">Выберите имя группы, а затем на вкладке **"Общие"** в области **"Адрес электронной почты", "Основной"** выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="e3414-160">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="e3414-161">В выпадаемом списке выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-161">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e3414-162">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e3414-162">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e3414-163">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="e3414-163">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e3414-164">В Центре <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">администрирования перейдите</a>на **страницу** > **"Группы групп".**</span><span class="sxs-lookup"><span data-stu-id="e3414-164">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="e3414-165">Выберите имя группы, а затем выберите **"Изменить** рядом с **именем".**</span><span class="sxs-lookup"><span data-stu-id="e3414-165">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="e3414-166">В выпадаемом списке выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-166">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e3414-167">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e3414-167">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e3414-168">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="e3414-168">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e3414-169">В Центре <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">администрирования перейдите</a>на **страницу** > **"Группы групп".**</span><span class="sxs-lookup"><span data-stu-id="e3414-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="e3414-170">Выберите имя группы, а затем выберите **"Изменить** рядом с **именем".**</span><span class="sxs-lookup"><span data-stu-id="e3414-170">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="e3414-171">В выпадаемом списке выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="e3414-171">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e3414-172">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e3414-172">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e3414-173">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="e3414-173">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="e3414-174">Шаг 3. Удаление старого домена</span><span class="sxs-lookup"><span data-stu-id="e3414-174">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e3414-175">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="e3414-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e3414-176">В Центре администрирования перейдите на страницу **"Домены** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">установки".</a></span><span class="sxs-lookup"><span data-stu-id="e3414-176">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e3414-177">В Центре администрирования перейдите на страницу **"Домены** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">установки".</a></span><span class="sxs-lookup"><span data-stu-id="e3414-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="e3414-178">На странице **"Домены"** выберите домен, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="e3414-178">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="e3414-179">В правой области выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="e3414-179">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="e3414-180">Следуйте дополнительным запросам и выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="e3414-180">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="e3414-181">Время, необходимое для удаления домена</span><span class="sxs-lookup"><span data-stu-id="e3414-181">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="e3414-182">Удаление домена в Microsoft 365 может занять всего 5 минут, если на него не ссылается множество групп безопасности, списков рассылки, пользователей и групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3414-182">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="e3414-183">Если же домен используется очень широко, на его удаление может потребоваться несколько часов или один день.</span><span class="sxs-lookup"><span data-stu-id="e3414-183">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="e3414-p113">Если у вас сотни или тысячи пользователей, используйте PowerShell, чтобы отправить им всем запрос, а затем перенести их в другой домен. В противном случае может оказаться, что нескольких пользователей нет в интерфейсе. В результате вы не сможете удалить домен и не сумеете определить причину. Дополнительные сведения см. в статье о командлете [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Чтобы задать домен по умолчанию, используйте командлет [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="e3414-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="e3414-188">Требуется дополнительная помощь?</span><span class="sxs-lookup"><span data-stu-id="e3414-188">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e3414-189">Не удается удалить домен [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) из вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e3414-189">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span> <span data-ttu-id="e3414-190">После удаления домена учетные записи пользователей будут возвращаться к адресу .onmicrosoft.com в качестве основного SMTP/UserprincipalName.</span><span class="sxs-lookup"><span data-stu-id="e3414-190">When you remove a domain, user accounts will revert back to the ".onmicrosoft.com" address as the Primary SMTP/UserprincipalName.</span></span>
  
<span data-ttu-id="e3414-191">Не получилось?</span><span class="sxs-lookup"><span data-stu-id="e3414-191">Still not working?</span></span> <span data-ttu-id="e3414-192">Возможно, ваш домен необходимо удалить вручную.</span><span class="sxs-lookup"><span data-stu-id="e3414-192">Your domain might need to be manually removed.</span></span> <span data-ttu-id="e3414-193">[Позвоните нем](../contact-support-for-business-products.md), и мы поможем вам это сделать.</span><span class="sxs-lookup"><span data-stu-id="e3414-193">[Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="e3414-194">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e3414-194">Related articles</span></span>

[<span data-ttu-id="e3414-195">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="e3414-195">Domains FAQ</span></span>](../setup/domains-faq.yml)

[<span data-ttu-id="e3414-196">Переход на другой план Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e3414-196">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="e3414-197">Отмена подписки</span><span class="sxs-lookup"><span data-stu-id="e3414-197">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
