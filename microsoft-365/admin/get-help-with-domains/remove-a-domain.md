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
ms.openlocfilehash: 57e52cc4f44e41d31200b8b5469aed6c36b63d24
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814424"
---
# <a name="remove-a-domain"></a><span data-ttu-id="79627-103">Удаление домена</span><span class="sxs-lookup"><span data-stu-id="79627-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="79627-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="79627-104">The admin center is changing.</span></span> <span data-ttu-id="79627-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="79627-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="79627-106">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="79627-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="79627-107">Хотите удалить домен, чтобы добавить его в другой план подписки на Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="79627-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="79627-108">Или вам нужно просто отменить свою подписку?</span><span class="sxs-lookup"><span data-stu-id="79627-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="79627-109">Вы можете [сменить план или подписку](../../commerce/subscriptions/switch-to-a-different-plan.md) либо [отменить подписку](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="79627-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="79627-110">Шаг 1. Перенос пользователей в другой домен</span><span class="sxs-lookup"><span data-stu-id="79627-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="79627-111">Перемещение пользователей</span><span class="sxs-lookup"><span data-stu-id="79627-111">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79627-112">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="79627-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="79627-113">Выберите **Users** > **активных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="79627-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="79627-114">Установите флажки рядом с именами всех пользователей, которых нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="79627-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="79627-115">Выберите **"Дополнительные** **параметры" ( ...** в верхней части страницы, а затем нажмите кнопку **Изменить домены.**</span><span class="sxs-lookup"><span data-stu-id="79627-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="79627-116">В области **"Изменить домены"** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="79627-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="79627-p103">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="79627-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="79627-119">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="79627-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="79627-120">Выберите **Users** > **активных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="79627-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="79627-121">Установите флажки рядом с именами всех пользователей, которых нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="79627-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="79627-122">At the top of the page, choose **More** > **Edit domains.**</span><span class="sxs-lookup"><span data-stu-id="79627-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="79627-123">На панели **"Изменение доменов"** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="79627-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="79627-p104">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="79627-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="79627-126">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="79627-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="79627-127">Выберите **Users** > **активных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="79627-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="79627-128">Установите флажки рядом с именами всех пользователей, которых нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="79627-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="79627-129">At the top of the page, choose **More** > **Edit domains.**</span><span class="sxs-lookup"><span data-stu-id="79627-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="79627-130">На панели **"Изменение доменов"** выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="79627-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="79627-p105">Это нужно сделать и для вашей учетной записи, если она находится в домене, который вы хотите удалить. Чтобы продолжить работу после изменения домена для своей учетной записи, выйдите из службы и снова войдите в нее, используя новый домен.</span><span class="sxs-lookup"><span data-stu-id="79627-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="79627-133">Перемещение самостоятельно</span><span class="sxs-lookup"><span data-stu-id="79627-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79627-134">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центр администрирования</a>.</span><span class="sxs-lookup"><span data-stu-id="79627-134">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="79627-135">Перейдите в **раздел** \> **"Активные пользователи"** и выберите свою учетную запись из списка.</span><span class="sxs-lookup"><span data-stu-id="79627-135">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="79627-136">На **вкладке Account** (Учетная запись) нажмите **кнопку Manage username**(Управление именем пользователя) и выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="79627-136">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="79627-137">At the top, select your account name, then select **Out.**</span><span class="sxs-lookup"><span data-stu-id="79627-137">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="79627-138">Войдите с новым доменом и вашим же паролем.</span><span class="sxs-lookup"><span data-stu-id="79627-138">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="79627-139">Переместить пользователей в другой домен можно также с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79627-139">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="79627-140">Дополнительные сведения см. в статье [О Set-MsolUserPrincipalName.](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="79627-140">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="79627-141">Чтобы задать домен по умолчанию, [используйте Set-MsolDomain.](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="79627-141">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="79627-142">Перейдите в **раздел** \> **"Активные пользователи"** и выберите свое имя в списке.</span><span class="sxs-lookup"><span data-stu-id="79627-142">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="79627-143">В разделе **"Имя пользователя/ Электронная почта"** выберите **"Изменить",** а затем выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="79627-143">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="79627-144">Выберите **"Задать как основное закрытие** > **функции** > **сохранения".**</span><span class="sxs-lookup"><span data-stu-id="79627-144">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="79627-145">At the top, select your account name, then select **Out.**</span><span class="sxs-lookup"><span data-stu-id="79627-145">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="79627-146">Войдите с новым доменом и вашим же паролем.</span><span class="sxs-lookup"><span data-stu-id="79627-146">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="79627-147">Переместить пользователей в другой домен можно также с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79627-147">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="79627-148">Дополнительные сведения см. в статье [О Set-MsolUserPrincipalName.](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="79627-148">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="79627-149">Чтобы задать домен по умолчанию, [используйте Set-MsolDomain.](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="79627-149">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="79627-150">Перейдите в **раздел** \> **"Активные пользователи"** и выберите свое имя в списке.</span><span class="sxs-lookup"><span data-stu-id="79627-150">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="79627-151">В разделе **"Имя пользователя/ Электронная почта"** выберите **"Изменить",** а затем выберите другой домен.</span><span class="sxs-lookup"><span data-stu-id="79627-151">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="79627-152">Выберите **"Задать как основное закрытие** > **функции** > **сохранения".**</span><span class="sxs-lookup"><span data-stu-id="79627-152">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="79627-153">At the top, select your account name, then select **Out.**</span><span class="sxs-lookup"><span data-stu-id="79627-153">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="79627-154">Войдите с новым доменом и вашим же паролем.</span><span class="sxs-lookup"><span data-stu-id="79627-154">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="79627-155">Переместить пользователей в другой домен можно также с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79627-155">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="79627-156">Дополнительные сведения см. в статье [О Set-MsolUserPrincipalName.](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="79627-156">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="79627-157">Чтобы задать домен по умолчанию, [используйте Set-MsolDomain.](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="79627-157">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="79627-158">Шаг 2. Перемещение групп в другой домен</span><span class="sxs-lookup"><span data-stu-id="79627-158">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79627-159">В Центре администрирования перейдите на страницу **"Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">групп".</a></span><span class="sxs-lookup"><span data-stu-id="79627-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="79627-160">Выберите имя группы, а затем на вкладке **"Общие"** выберите "Общие" **в разделе "Адрес электронной почты" "Основной"** и выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="79627-160">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="79627-161">Используйте раскрывающийся список для выбора другого домена.</span><span class="sxs-lookup"><span data-stu-id="79627-161">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="79627-162">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="79627-162">Select **Save**, then **Close**.</span></span> <span data-ttu-id="79627-163">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="79627-163">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="79627-164">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования перейдите</a>на страницу **"Группы** > **групп".**</span><span class="sxs-lookup"><span data-stu-id="79627-164">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="79627-165">Выберите имя группы, а затем — **"Изменить"** рядом с **именем.**</span><span class="sxs-lookup"><span data-stu-id="79627-165">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="79627-166">Используйте раскрывающийся список для выбора другого домена.</span><span class="sxs-lookup"><span data-stu-id="79627-166">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="79627-167">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="79627-167">Select **Save**, then **Close**.</span></span> <span data-ttu-id="79627-168">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="79627-168">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="79627-169">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования перейдите</a>на страницу **"Группы** > **групп".**</span><span class="sxs-lookup"><span data-stu-id="79627-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="79627-170">Выберите имя группы, а затем — **"Изменить"** рядом с **именем.**</span><span class="sxs-lookup"><span data-stu-id="79627-170">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="79627-171">Используйте раскрывающийся список для выбора другого домена.</span><span class="sxs-lookup"><span data-stu-id="79627-171">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="79627-172">Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="79627-172">Select **Save**, then **Close**.</span></span> <span data-ttu-id="79627-173">Повторите эти шаги для всех групп или списков рассылки, связанных с доменом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="79627-173">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="79627-174">Шаг 3. Удалите старый домен</span><span class="sxs-lookup"><span data-stu-id="79627-174">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79627-175">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="79627-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="79627-176">В Центре администрирования перейдите на страницу **"Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">доменов".</a></span><span class="sxs-lookup"><span data-stu-id="79627-176">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="79627-177">В Центре администрирования перейдите на страницу **"Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">доменов".</a></span><span class="sxs-lookup"><span data-stu-id="79627-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="79627-178">На странице **"Домены"** выберите домен, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="79627-178">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="79627-179">В правой области выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="79627-179">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="79627-180">Следуйте дополнительным инструкциям, а затем нажмите кнопку **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="79627-180">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="79627-181">Время, необходимое для удаления домена</span><span class="sxs-lookup"><span data-stu-id="79627-181">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="79627-182">Удаление домена в Microsoft 365 может занять около 5 минут, если на него ссылается много мест, таких как группы безопасности, списки рассылки, пользователи и группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="79627-182">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="79627-183">Если же домен используется очень широко, на его удаление может потребоваться несколько часов или один день.</span><span class="sxs-lookup"><span data-stu-id="79627-183">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="79627-p113">Если у вас сотни или тысячи пользователей, используйте PowerShell, чтобы отправить им всем запрос, а затем перенести их в другой домен. В противном случае может оказаться, что нескольких пользователей нет в интерфейсе. В результате вы не сможете удалить домен и не сумеете определить причину. Дополнительные сведения см. в статье о командлете [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Чтобы задать домен по умолчанию, используйте командлет [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="79627-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="79627-188">Остались вопросы?</span><span class="sxs-lookup"><span data-stu-id="79627-188">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="79627-189">Не удается удалить домен [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) из вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="79627-189">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="79627-p114">Не получилось? Возможно, ваш домен необходимо удалить вручную. [Позвоните нем](../contact-support-for-business-products.md), и мы поможем вам это сделать.</span><span class="sxs-lookup"><span data-stu-id="79627-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="79627-193">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="79627-193">Related articles</span></span>

[<span data-ttu-id="79627-194">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="79627-194">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="79627-195">Переход на другой план Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="79627-195">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="79627-196">Отмена подписки</span><span class="sxs-lookup"><span data-stu-id="79627-196">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
