---
title: Удаление домена
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
ms.openlocfilehash: 6f5e36a897316c8cdc057a725957c54e7eb53edc
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079765"
---
# <a name="remove-a-domain"></a><span data-ttu-id="fb3ac-103">Удаление домена</span><span class="sxs-lookup"><span data-stu-id="fb3ac-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="fb3ac-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-104">The admin center is changing.</span></span> <span data-ttu-id="fb3ac-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="fb3ac-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="fb3ac-106">Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fb3ac-107">Вы удаляете домен, так как хотите добавить его в другой план подписки Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="fb3ac-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="fb3ac-108">Или вам нужно просто отменить свою подписку?</span><span class="sxs-lookup"><span data-stu-id="fb3ac-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="fb3ac-109">Вы можете [сменить план или подписку](../../commerce/subscriptions/switch-to-a-different-plan.md) либо [отменить подписку](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="fb3ac-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="fb3ac-110">Шаг 1: перемещение пользователей в другой домен</span><span class="sxs-lookup"><span data-stu-id="fb3ac-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="fb3ac-111">Перемещение пользователей</span><span class="sxs-lookup"><span data-stu-id="fb3ac-111">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fb3ac-112">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="fb3ac-113">Выберите пункт **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="fb3ac-114">Установите флажки рядом с именами всех пользователей, которых требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="fb3ac-115">В верхней части страницы нажмите кнопку **Дополнительные параметры** (**...**), а затем выберите команду **изменить домены**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="fb3ac-116">В области **изменить домены** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="fb3ac-117">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-117">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span></span> <span data-ttu-id="fb3ac-118">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-118">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fb3ac-119">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="fb3ac-120">Выберите пункт **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="fb3ac-121">Установите флажки рядом с именами всех пользователей, которых требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="fb3ac-122">В верхней части страницы выберите **Дополнительные** > **домены редактирования**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="fb3ac-123">В области **изменить домены** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="fb3ac-124">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-124">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span></span> <span data-ttu-id="fb3ac-125">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-125">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fb3ac-126">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="fb3ac-127">Выберите пункт **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="fb3ac-128">Установите флажки рядом с именами всех пользователей, которых требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="fb3ac-129">В верхней части страницы выберите **Дополнительные** > **домены редактирования**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="fb3ac-130">В области **изменить домены** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="fb3ac-131">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-131">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span></span> <span data-ttu-id="fb3ac-132">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-132">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="fb3ac-133">Самостоятельное перемещение</span><span class="sxs-lookup"><span data-stu-id="fb3ac-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fb3ac-134">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-134">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="fb3ac-135">Перейдите к **Users** разделу \> **Активные пользователи**пользователей и выберите свою учетную запись из списка.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-135">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="fb3ac-136">На вкладке **учетная запись** выберите пункт **Управление именем пользователя**, а затем выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-136">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="fb3ac-137">В верхней части выберите имя учетной записи, а затем нажмите **выйти**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-137">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="fb3ac-138">Выполните вход с новым доменом и тем же паролем.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-138">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="fb3ac-139">Вы также можете использовать PowerShell для перемещения пользователей в другой домен.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-139">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="fb3ac-140">Для получения дополнительных сведений см. [Set – мсолусерпринЦипалнаме](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) .</span><span class="sxs-lookup"><span data-stu-id="fb3ac-140">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="fb3ac-141">Чтобы задать домен по умолчанию, используйте [Set – мсолдомаин](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="fb3ac-141">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fb3ac-142">Перейдите к **Users** разделу \> **Активные пользователи**пользователей и выберите свое имя в списке.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-142">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="fb3ac-143">В разделе **имя пользователя и электронная почта** нажмите кнопку **изменить**, а затем выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-143">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="fb3ac-144">Выберите **задать в качестве основного** > **сохранения** > **закрытия**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-144">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="fb3ac-145">В верхней части выберите имя учетной записи, а затем нажмите **выйти**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-145">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="fb3ac-146">Выполните вход с новым доменом и тем же паролем.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-146">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="fb3ac-147">Вы также можете использовать PowerShell для перемещения пользователей в другой домен.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-147">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="fb3ac-148">Для получения дополнительных сведений см. [Set – мсолусерпринЦипалнаме](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) .</span><span class="sxs-lookup"><span data-stu-id="fb3ac-148">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="fb3ac-149">Чтобы задать домен по умолчанию, используйте [Set – мсолдомаин](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="fb3ac-149">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fb3ac-150">Перейдите к **Users** разделу \> **Активные пользователи**пользователей и выберите свое имя в списке.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-150">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="fb3ac-151">В разделе **имя пользователя и электронная почта** нажмите кнопку **изменить**, а затем выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-151">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="fb3ac-152">Выберите **задать в качестве основного** > **сохранения** > **закрытия**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-152">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="fb3ac-153">В верхней части выберите имя учетной записи, а затем нажмите **выйти**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-153">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="fb3ac-154">Выполните вход с новым доменом и тем же паролем.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-154">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="fb3ac-155">Вы также можете использовать PowerShell для перемещения пользователей в другой домен.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-155">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="fb3ac-156">Для получения дополнительных сведений см. [Set – мсолусерпринЦипалнаме](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) .</span><span class="sxs-lookup"><span data-stu-id="fb3ac-156">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="fb3ac-157">Чтобы задать домен по умолчанию, используйте [Set – мсолдомаин](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="fb3ac-157">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="fb3ac-158">Шаг 2: перемещение групп в другой домен</span><span class="sxs-lookup"><span data-stu-id="fb3ac-158">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fb3ac-159">В центре администрирования перейдите на **Groups** \> страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> группы.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="fb3ac-160">Выберите имя группы, а затем на вкладке **Общие** в разделе **адрес электронной почты, основной**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-160">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="fb3ac-161">Используйте раскрывающийся список для выбора другого домена.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-161">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="fb3ac-162">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-162">Select **Save**, then **Close**.</span></span> <span data-ttu-id="fb3ac-163">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-163">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fb3ac-164">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центре администрирования</a>перейдите на **Groups** > страницу **группы** группы.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-164">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="fb3ac-165">Выберите имя группы, а затем нажмите кнопку **изменить** рядом с **именем**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-165">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="fb3ac-166">Используйте раскрывающийся список для выбора другого домена.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-166">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="fb3ac-167">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-167">Select **Save**, then **Close**.</span></span> <span data-ttu-id="fb3ac-168">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-168">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fb3ac-169">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центре администрирования</a>перейдите на **Groups** > страницу **группы** группы.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="fb3ac-170">Выберите имя группы, а затем нажмите кнопку **изменить** рядом с **именем**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-170">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="fb3ac-171">Используйте раскрывающийся список для выбора другого домена.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-171">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="fb3ac-172">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-172">Select **Save**, then **Close**.</span></span> <span data-ttu-id="fb3ac-173">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-173">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="fb3ac-174">Шаг 3: удаление старого домена</span><span class="sxs-lookup"><span data-stu-id="fb3ac-174">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fb3ac-175">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="fb3ac-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fb3ac-176">В центре администрирования перейдите на страницу " **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">домены</a> установки".</span><span class="sxs-lookup"><span data-stu-id="fb3ac-176">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fb3ac-177">В центре администрирования перейдите на страницу " **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">домены</a> установки".</span><span class="sxs-lookup"><span data-stu-id="fb3ac-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="fb3ac-178">На странице **Domains (домены** ) выберите домен, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-178">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="fb3ac-179">В правой области нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-179">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="fb3ac-180">Следуйте дополнительным приглашениям, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-180">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="fb3ac-181">Время, необходимое для удаления домена</span><span class="sxs-lookup"><span data-stu-id="fb3ac-181">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="fb3ac-182">365 для удаления домена в случае отсутствия ссылок на группы безопасности, списки рассылки, пользователей и группы Майкрософт 365 может потребоваться до 5 минут.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-182">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="fb3ac-183">Если же домен используется очень широко, на его удаление может потребоваться несколько часов или один день.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-183">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="fb3ac-184">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-184">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain.</span></span> <span data-ttu-id="fb3ac-185">Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-185">Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why.</span></span> <span data-ttu-id="fb3ac-186">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-186">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="fb3ac-187">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="fb3ac-187">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="fb3ac-188">Требуется дополнительная помощь?</span><span class="sxs-lookup"><span data-stu-id="fb3ac-188">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="fb3ac-189">Не удается удалить домен [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) из вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-189">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="fb3ac-190">Still not working?</span><span class="sxs-lookup"><span data-stu-id="fb3ac-190">Still not working?</span></span> <span data-ttu-id="fb3ac-191">Your domain might need to be manually removed.</span><span class="sxs-lookup"><span data-stu-id="fb3ac-191">Your domain might need to be manually removed.</span></span> <span data-ttu-id="fb3ac-192">[Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span><span class="sxs-lookup"><span data-stu-id="fb3ac-192">[Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="fb3ac-193">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fb3ac-193">Related articles</span></span>

[<span data-ttu-id="fb3ac-194">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="fb3ac-194">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="fb3ac-195">Получение справки по доменам Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fb3ac-195">Get help with Microsoft 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="fb3ac-196">Переход на другой план Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="fb3ac-196">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="fb3ac-197">Отмена подписки</span><span class="sxs-lookup"><span data-stu-id="fb3ac-197">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
