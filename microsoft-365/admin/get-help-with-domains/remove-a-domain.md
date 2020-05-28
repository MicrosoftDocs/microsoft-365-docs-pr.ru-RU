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
ms.openlocfilehash: c5e629f0d683c6dc3e18b1278027ac3a88cc834b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399900"
---
# <a name="remove-a-domain"></a><span data-ttu-id="be556-103">Удаление домена</span><span class="sxs-lookup"><span data-stu-id="be556-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="be556-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="be556-104">The admin center is changing.</span></span> <span data-ttu-id="be556-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="be556-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="be556-106">Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="be556-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="be556-107">Вы удаляете домен, так как хотите добавить его в другой план подписки Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="be556-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="be556-108">Или вам нужно просто отменить свою подписку?</span><span class="sxs-lookup"><span data-stu-id="be556-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="be556-109">Вы можете [сменить план или подписку](../../commerce/subscriptions/switch-to-a-different-plan.md) либо [отменить подписку](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="be556-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="be556-110">Шаг 1: перемещение пользователей в другой домен</span><span class="sxs-lookup"><span data-stu-id="be556-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="be556-111">Перемещение пользователей</span><span class="sxs-lookup"><span data-stu-id="be556-111">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="be556-112">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="be556-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="be556-113">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="be556-113">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="be556-114">Выберите пункт **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="be556-114">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="be556-115">Установите флажки рядом с именами всех пользователей, которых требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="be556-115">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="be556-116">В верхней части страницы нажмите кнопку **Дополнительные параметры** (**...**), а затем выберите команду **изменить домены**.</span><span class="sxs-lookup"><span data-stu-id="be556-116">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="be556-117">В области **изменить домены** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="be556-117">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="be556-p103">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="be556-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="be556-120">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="be556-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="be556-121">Выберите пункт **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="be556-121">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="be556-122">Установите флажки рядом с именами всех пользователей, которых требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="be556-122">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="be556-123">В верхней части страницы выберите **Дополнительные** > **домены редактирования**.</span><span class="sxs-lookup"><span data-stu-id="be556-123">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="be556-124">В области **изменить домены** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="be556-124">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="be556-p104">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="be556-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="be556-127">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="be556-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="be556-128">Выберите пункт **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="be556-128">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="be556-129">Установите флажки рядом с именами всех пользователей, которых требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="be556-129">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="be556-130">В верхней части страницы выберите **Дополнительные** > **домены редактирования**.</span><span class="sxs-lookup"><span data-stu-id="be556-130">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="be556-131">В области **изменить домены** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="be556-131">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="be556-p105">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="be556-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="be556-134">Самостоятельное перемещение</span><span class="sxs-lookup"><span data-stu-id="be556-134">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="be556-135">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="be556-135">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="be556-136">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="be556-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="be556-137">Перейдите к **Users** разделу \> **Активные пользователи**пользователей и выберите свою учетную запись из списка.</span><span class="sxs-lookup"><span data-stu-id="be556-137">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="be556-138">На вкладке **учетная запись** выберите пункт **Управление именем пользователя**, а затем выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="be556-138">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="be556-139">В верхней части выберите имя учетной записи, а затем нажмите **выйти**.</span><span class="sxs-lookup"><span data-stu-id="be556-139">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="be556-140">Выполните вход с новым доменом и тем же паролем.</span><span class="sxs-lookup"><span data-stu-id="be556-140">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="be556-141">Вы также можете использовать PowerShell для перемещения пользователей в другой домен.</span><span class="sxs-lookup"><span data-stu-id="be556-141">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="be556-142">Для получения дополнительных сведений см. [Set – мсолусерпринЦипалнаме](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) .</span><span class="sxs-lookup"><span data-stu-id="be556-142">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="be556-143">Чтобы задать домен по умолчанию, используйте [Set – мсолдомаин](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="be556-143">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="be556-144">Перейдите к **Users** разделу \> **Активные пользователи**пользователей и выберите свое имя в списке.</span><span class="sxs-lookup"><span data-stu-id="be556-144">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="be556-145">В разделе **имя пользователя и электронная почта** нажмите кнопку **изменить**, а затем выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="be556-145">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="be556-146">Выберите **задать в качестве основного** > **сохранения** > **закрытия**.</span><span class="sxs-lookup"><span data-stu-id="be556-146">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="be556-147">В верхней части выберите имя учетной записи, а затем нажмите **выйти**.</span><span class="sxs-lookup"><span data-stu-id="be556-147">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="be556-148">Выполните вход с новым доменом и тем же паролем.</span><span class="sxs-lookup"><span data-stu-id="be556-148">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="be556-149">Вы также можете использовать PowerShell для перемещения пользователей в другой домен.</span><span class="sxs-lookup"><span data-stu-id="be556-149">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="be556-150">Для получения дополнительных сведений см. [Set – мсолусерпринЦипалнаме](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) .</span><span class="sxs-lookup"><span data-stu-id="be556-150">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="be556-151">Чтобы задать домен по умолчанию, используйте [Set – мсолдомаин](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="be556-151">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="be556-152">Перейдите к **Users** разделу \> **Активные пользователи**пользователей и выберите свое имя в списке.</span><span class="sxs-lookup"><span data-stu-id="be556-152">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="be556-153">В разделе **имя пользователя и электронная почта** нажмите кнопку **изменить**, а затем выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="be556-153">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="be556-154">Выберите **задать в качестве основного** > **сохранения** > **закрытия**.</span><span class="sxs-lookup"><span data-stu-id="be556-154">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="be556-155">В верхней части выберите имя учетной записи, а затем нажмите **выйти**.</span><span class="sxs-lookup"><span data-stu-id="be556-155">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="be556-156">Выполните вход с новым доменом и тем же паролем.</span><span class="sxs-lookup"><span data-stu-id="be556-156">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="be556-157">Вы также можете использовать PowerShell для перемещения пользователей в другой домен.</span><span class="sxs-lookup"><span data-stu-id="be556-157">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="be556-158">Для получения дополнительных сведений см. [Set – мсолусерпринЦипалнаме](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) .</span><span class="sxs-lookup"><span data-stu-id="be556-158">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="be556-159">Чтобы задать домен по умолчанию, используйте [Set – мсолдомаин](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="be556-159">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="be556-160">Шаг 2: перемещение групп в другой домен</span><span class="sxs-lookup"><span data-stu-id="be556-160">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="be556-161">В центре администрирования перейдите на **Groups** \> страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> группы.</span><span class="sxs-lookup"><span data-stu-id="be556-161">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="be556-162">Выберите имя группы, а затем на вкладке **Общие** в разделе **адрес электронной почты, основной**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="be556-162">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="be556-163">Используйте раскрывающийся список для выбора другого домена.</span><span class="sxs-lookup"><span data-stu-id="be556-163">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="be556-164">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="be556-164">Select **Save**, then **Close**.</span></span> <span data-ttu-id="be556-165">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="be556-165">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="be556-166">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центре администрирования</a>перейдите на **Groups** > страницу **группы** группы.</span><span class="sxs-lookup"><span data-stu-id="be556-166">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="be556-167">Выберите имя группы, а затем нажмите кнопку **изменить** рядом с **именем**.</span><span class="sxs-lookup"><span data-stu-id="be556-167">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="be556-168">Используйте раскрывающийся список для выбора другого домена.</span><span class="sxs-lookup"><span data-stu-id="be556-168">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="be556-169">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="be556-169">Select **Save**, then **Close**.</span></span> <span data-ttu-id="be556-170">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="be556-170">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="be556-171">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центре администрирования</a>перейдите на **Groups** > страницу **группы** группы.</span><span class="sxs-lookup"><span data-stu-id="be556-171">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="be556-172">Выберите имя группы, а затем нажмите кнопку **изменить** рядом с **именем**.</span><span class="sxs-lookup"><span data-stu-id="be556-172">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="be556-173">Используйте раскрывающийся список для выбора другого домена.</span><span class="sxs-lookup"><span data-stu-id="be556-173">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="be556-174">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="be556-174">Select **Save**, then **Close**.</span></span> <span data-ttu-id="be556-175">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="be556-175">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="be556-176">Шаг 3: удаление старого домена</span><span class="sxs-lookup"><span data-stu-id="be556-176">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="be556-177">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="be556-177">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="be556-178">В центре администрирования перейдите на страницу " **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">домены</a> установки".</span><span class="sxs-lookup"><span data-stu-id="be556-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="be556-179">В центре администрирования перейдите на страницу " **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">домены</a> установки".</span><span class="sxs-lookup"><span data-stu-id="be556-179">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="be556-180">На странице **Domains (домены** ) выберите домен, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="be556-180">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="be556-181">В правой области нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="be556-181">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="be556-182">Следуйте дополнительным приглашениям, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="be556-182">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="be556-183">Время, необходимое для удаления домена</span><span class="sxs-lookup"><span data-stu-id="be556-183">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="be556-184">365 для удаления домена в случае отсутствия ссылок на группы безопасности, списки рассылки, пользователей и группы Майкрософт 365 может потребоваться до 5 минут.</span><span class="sxs-lookup"><span data-stu-id="be556-184">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="be556-185">Если же домен используется очень широко, на его удаление может потребоваться несколько часов или один день.</span><span class="sxs-lookup"><span data-stu-id="be556-185">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="be556-p113">Если у вас сотни или тысячи пользователей, используйте PowerShell, чтобы отправить им всем запрос, а затем перенести их в другой домен. В противном случае может оказаться, что нескольких пользователей нет в интерфейсе. В результате вы не сможете удалить домен и не сумеете определить причину. Дополнительные сведения см. в статье о командлете [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Чтобы задать домен по умолчанию, используйте командлет [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="be556-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="be556-190">Остались вопросы?</span><span class="sxs-lookup"><span data-stu-id="be556-190">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="be556-191">Не удается удалить домен [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) из вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="be556-191">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="be556-p114">Не получилось? Возможно, ваш домен необходимо удалить вручную. [Позвоните нем](../contact-support-for-business-products.md), и мы поможем вам это сделать.</span><span class="sxs-lookup"><span data-stu-id="be556-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="be556-195">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="be556-195">Related articles</span></span>

[<span data-ttu-id="be556-196">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="be556-196">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="be556-197">Получение справки по доменам Office 365</span><span class="sxs-lookup"><span data-stu-id="be556-197">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="be556-198">Переход на другой план Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="be556-198">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="be556-199">Отмена подписки</span><span class="sxs-lookup"><span data-stu-id="be556-199">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
