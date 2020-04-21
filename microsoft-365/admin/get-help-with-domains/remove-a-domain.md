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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Узнайте, как удалить старый домен из Microsoft 365 и переместить пользователей и группы в другой домен.
ms.openlocfilehash: 21b2b17e5cab022f67c71c0d3858f8a03b45899b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628438"
---
# <a name="remove-a-domain"></a><span data-ttu-id="98249-103">Удаление домена</span><span class="sxs-lookup"><span data-stu-id="98249-103">Remove a domain</span></span>

<span data-ttu-id="98249-104">Авторы: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span><span class="sxs-lookup"><span data-stu-id="98249-104">Contributors: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span></span>
  
 <span data-ttu-id="98249-105">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="98249-105">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="98249-106">Вы удаляете домен, так как хотите добавить его в другой план подписки Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="98249-106">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="98249-107">Или вам нужно просто отменить свою подписку?</span><span class="sxs-lookup"><span data-stu-id="98249-107">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="98249-108">Вы можете [сменить план или подписку](../../commerce/subscriptions/switch-to-a-different-plan.md) либо [отменить подписку](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="98249-108">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="98249-109">Шаг 1: перемещение пользователей в другой домен</span><span class="sxs-lookup"><span data-stu-id="98249-109">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="98249-110">Перемещение пользователей</span><span class="sxs-lookup"><span data-stu-id="98249-110">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="98249-111">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="98249-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="98249-112">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="98249-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="98249-113">Выберите пункт **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="98249-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="98249-114">Установите флажки рядом с именами всех пользователей, которых требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="98249-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="98249-115">В верхней части страницы нажмите кнопку **Дополнительные параметры** (**...**), а затем выберите команду **изменить домены**.</span><span class="sxs-lookup"><span data-stu-id="98249-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="98249-116">В области **изменить домены** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="98249-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="98249-p102">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="98249-p102">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="98249-119">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="98249-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="98249-120">Выберите пункт **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="98249-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="98249-121">Установите флажки рядом с именами всех пользователей, которых требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="98249-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="98249-122">В верхней части страницы выберите **Дополнительные** > **домены редактирования**.</span><span class="sxs-lookup"><span data-stu-id="98249-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="98249-123">В области **изменить домены** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="98249-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="98249-p103">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="98249-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="98249-126">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="98249-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="98249-127">Выберите пункт **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="98249-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="98249-128">Установите флажки рядом с именами всех пользователей, которых требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="98249-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="98249-129">В верхней части страницы выберите **Дополнительные** > **домены редактирования**.</span><span class="sxs-lookup"><span data-stu-id="98249-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="98249-130">В области **изменить домены** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="98249-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="98249-p104">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="98249-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="98249-133">Самостоятельное перемещение</span><span class="sxs-lookup"><span data-stu-id="98249-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="98249-134">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="98249-134">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="98249-135">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="98249-135">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="98249-136">Перейдите к разделу **Активные пользователи** **пользователей** \> и выберите свою учетную запись из списка.</span><span class="sxs-lookup"><span data-stu-id="98249-136">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="98249-137">На вкладке **учетная запись** выберите пункт **Управление именем пользователя**, а затем выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="98249-137">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="98249-138">В верхней части выберите имя учетной записи, а затем нажмите **выйти**.</span><span class="sxs-lookup"><span data-stu-id="98249-138">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="98249-139">Выполните вход с новым доменом и тем же паролем.</span><span class="sxs-lookup"><span data-stu-id="98249-139">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="98249-140">Вы также можете использовать PowerShell для перемещения пользователей в другой домен.</span><span class="sxs-lookup"><span data-stu-id="98249-140">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="98249-141">Для получения дополнительных сведений см. [Set – мсолусерпринЦипалнаме](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) .</span><span class="sxs-lookup"><span data-stu-id="98249-141">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="98249-142">Чтобы задать домен по умолчанию, используйте [Set – мсолдомаин](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="98249-142">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="98249-143">Перейдите к разделу **Активные пользователи** **пользователей** \> и выберите свое имя в списке.</span><span class="sxs-lookup"><span data-stu-id="98249-143">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="98249-144">В разделе **имя пользователя и электронная почта** нажмите кнопку **изменить**, а затем выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="98249-144">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="98249-145">Выберите **задать в качестве основного** > **сохранения** > **закрытия**.</span><span class="sxs-lookup"><span data-stu-id="98249-145">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="98249-146">В верхней части выберите имя учетной записи, а затем нажмите **выйти**.</span><span class="sxs-lookup"><span data-stu-id="98249-146">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="98249-147">Выполните вход с новым доменом и тем же паролем.</span><span class="sxs-lookup"><span data-stu-id="98249-147">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="98249-148">Вы также можете использовать PowerShell для перемещения пользователей в другой домен.</span><span class="sxs-lookup"><span data-stu-id="98249-148">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="98249-149">Для получения дополнительных сведений см. [Set – мсолусерпринЦипалнаме](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) .</span><span class="sxs-lookup"><span data-stu-id="98249-149">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="98249-150">Чтобы задать домен по умолчанию, используйте [Set – мсолдомаин](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="98249-150">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="98249-151">Перейдите к разделу **Активные пользователи** **пользователей** \> и выберите свое имя в списке.</span><span class="sxs-lookup"><span data-stu-id="98249-151">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="98249-152">В разделе **имя пользователя и электронная почта** нажмите кнопку **изменить**, а затем выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="98249-152">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="98249-153">Выберите **задать в качестве основного** > **сохранения** > **закрытия**.</span><span class="sxs-lookup"><span data-stu-id="98249-153">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="98249-154">В верхней части выберите имя учетной записи, а затем нажмите **выйти**.</span><span class="sxs-lookup"><span data-stu-id="98249-154">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="98249-155">Выполните вход с новым доменом и тем же паролем.</span><span class="sxs-lookup"><span data-stu-id="98249-155">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="98249-156">Вы также можете использовать PowerShell для перемещения пользователей в другой домен.</span><span class="sxs-lookup"><span data-stu-id="98249-156">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="98249-157">Для получения дополнительных сведений см. [Set – мсолусерпринЦипалнаме](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) .</span><span class="sxs-lookup"><span data-stu-id="98249-157">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="98249-158">Чтобы задать домен по умолчанию, используйте [Set – мсолдомаин](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="98249-158">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="98249-159">Шаг 2: перемещение групп в другой домен</span><span class="sxs-lookup"><span data-stu-id="98249-159">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="98249-160">В центре администрирования перейдите на страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> **группы** \> .</span><span class="sxs-lookup"><span data-stu-id="98249-160">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="98249-161">Выберите имя группы, а затем на вкладке **Общие** в разделе **адрес электронной почты, основной**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="98249-161">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="98249-162">Используйте раскрывающийся список для выбора другого домена.</span><span class="sxs-lookup"><span data-stu-id="98249-162">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="98249-163">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="98249-163">Select **Save**, then **Close**.</span></span> <span data-ttu-id="98249-164">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="98249-164">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="98249-165">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центре администрирования</a>перейдите на страницу **группы** **группы** > .</span><span class="sxs-lookup"><span data-stu-id="98249-165">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="98249-166">Выберите имя группы, а затем нажмите кнопку **изменить** рядом с **именем**.</span><span class="sxs-lookup"><span data-stu-id="98249-166">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="98249-167">Используйте раскрывающийся список для выбора другого домена.</span><span class="sxs-lookup"><span data-stu-id="98249-167">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="98249-168">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="98249-168">Select **Save**, then **Close**.</span></span> <span data-ttu-id="98249-169">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="98249-169">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="98249-170">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центре администрирования</a>перейдите на страницу **группы** **группы** > .</span><span class="sxs-lookup"><span data-stu-id="98249-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="98249-171">Выберите имя группы, а затем нажмите кнопку **изменить** рядом с **именем**.</span><span class="sxs-lookup"><span data-stu-id="98249-171">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="98249-172">Используйте раскрывающийся список для выбора другого домена.</span><span class="sxs-lookup"><span data-stu-id="98249-172">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="98249-173">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="98249-173">Select **Save**, then **Close**.</span></span> <span data-ttu-id="98249-174">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="98249-174">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="98249-175">Шаг 3: удаление старого домена</span><span class="sxs-lookup"><span data-stu-id="98249-175">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="98249-176">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="98249-176">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="98249-177">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">домены</a> **установки** \> ".</span><span class="sxs-lookup"><span data-stu-id="98249-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="98249-178">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">домены</a> **установки** \> ".</span><span class="sxs-lookup"><span data-stu-id="98249-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="98249-179">На странице **Domains (домены** ) выберите домен, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="98249-179">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="98249-180">В правой области нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="98249-180">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="98249-181">Следуйте дополнительным приглашениям, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="98249-181">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="98249-182">Время, необходимое для удаления домена</span><span class="sxs-lookup"><span data-stu-id="98249-182">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="98249-183">365 для удаления домена в случае отсутствия ссылок на группы безопасности, списки рассылки, пользователей и группы Майкрософт 365 может потребоваться до 5 минут.</span><span class="sxs-lookup"><span data-stu-id="98249-183">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="98249-184">Если же домен используется очень широко, на его удаление может потребоваться несколько часов или один день.</span><span class="sxs-lookup"><span data-stu-id="98249-184">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="98249-p112">Если у вас сотни или тысячи пользователей, используйте PowerShell, чтобы отправить им всем запрос, а затем перенести их в другой домен. В противном случае может оказаться, что нескольких пользователей нет в интерфейсе. В результате вы не сможете удалить домен и не сумеете определить причину. Дополнительные сведения см. в статье о командлете [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Чтобы задать домен по умолчанию, используйте командлет [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="98249-p112">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="98249-189">Остались вопросы?</span><span class="sxs-lookup"><span data-stu-id="98249-189">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="98249-190">Не удается удалить домен [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) из вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="98249-190">You can't remove the [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) domain from your account.</span></span>
  
<span data-ttu-id="98249-p113">Не получилось? Возможно, ваш домен необходимо удалить вручную. [Позвоните нем](../contact-support-for-business-products.md), и мы поможем вам это сделать.</span><span class="sxs-lookup"><span data-stu-id="98249-p113">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="98249-194">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="98249-194">Related articles</span></span>

[<span data-ttu-id="98249-195">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="98249-195">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="98249-196">Получение справки по доменам Office 365</span><span class="sxs-lookup"><span data-stu-id="98249-196">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="98249-197">Переключение на другой план Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="98249-197">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="98249-198">Отмена подписки</span><span class="sxs-lookup"><span data-stu-id="98249-198">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
