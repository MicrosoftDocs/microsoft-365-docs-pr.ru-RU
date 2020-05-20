---
title: Управление методами оплаты
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Узнайте, как управлять способами оплаты в центре администрирования Microsoft 365.
ms.openlocfilehash: d31da19c10eb61719ba813d271dbdcf573a5aff3
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322163"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="30e7d-103">Управление методами оплаты</span><span class="sxs-lookup"><span data-stu-id="30e7d-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="30e7d-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="30e7d-104">The admin center is changing.</span></span> <span data-ttu-id="30e7d-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="30e7d-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>
::: moniker-end

<span data-ttu-id="30e7d-106">При покупке бизнес-продуктов или услуг корпорации Майкрософт вы можете использовать существующий метод оплаты или добавить новый.</span><span class="sxs-lookup"><span data-stu-id="30e7d-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="30e7d-107">Вы можете использовать кредитную или дебетовую карту или банковский счет для оплаты приобретенных вами вещей.</span><span class="sxs-lookup"><span data-stu-id="30e7d-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="30e7d-108">Если у вашей организации есть профиль выставления счетов, а вы являетесь владельцем профиля выставления счетов или сотрудником профиля выставления счетов, вы можете использовать профиль выставления счетов, который подписывается по кредитной карте или платежу по счетам, чтобы делать счета покупки или оплаты.</span><span class="sxs-lookup"><span data-stu-id="30e7d-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="30e7d-109">Если вы являетесь менеджером счетов для выставления счетов, вы можете использовать профиль выставления счетов только для оплаты векселей.</span><span class="sxs-lookup"><span data-stu-id="30e7d-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="30e7d-110">Чтобы узнать больше о профилях выставления счетов и ролях, ознакомьтесь со статьей [Управление профилями выставления счетов](manage-billing-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="30e7d-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="30e7d-111">Если ваша учетная запись организации не имеет профиля выставления счетов, любой глобальный администратор или администратор выставления счетов может управлять и использовать любой банковский счет, который добавляется к бизнес-счету.</span><span class="sxs-lookup"><span data-stu-id="30e7d-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="30e7d-112">Тем не менее, вы можете управлять и использовать только кредитные карты, которые вы добавляете.</span><span class="sxs-lookup"><span data-stu-id="30e7d-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="30e7d-113">Возможность оплаты с помощью банковского счета недоступна в некоторых странах или регионах.</span><span class="sxs-lookup"><span data-stu-id="30e7d-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="30e7d-114">Необходимо использовать метод оплаты, выданный из той же страны, что и клиент.</span><span class="sxs-lookup"><span data-stu-id="30e7d-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="30e7d-115">Добавление способа оплаты</span><span class="sxs-lookup"><span data-stu-id="30e7d-115">Add a payment method</span></span>

<span data-ttu-id="30e7d-116">Добавление метода оплаты не связывает с ним какие бы то ни было подписки.</span><span class="sxs-lookup"><span data-stu-id="30e7d-116">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="30e7d-117">Чтобы назначить одну подписку методу оплаты, ознакомьтесь со статьей [изменение способа оплаты для одной подписки](#change-a-payment-method-for-a-single-subscription).</span><span class="sxs-lookup"><span data-stu-id="30e7d-117">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="30e7d-118">Чтобы заменить все подписки, использующие другой способ оплаты, на новый, ознакомьтесь со статьей [Замена метода оплаты](#replace-a-payment-method).</span><span class="sxs-lookup"><span data-stu-id="30e7d-118">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="30e7d-119">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="30e7d-119">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="30e7d-120">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="30e7d-120">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="30e7d-121">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="30e7d-121">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="30e7d-122">Выберите элемент **Добавление метода оплаты**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-122">Select **Add a payment method**.</span></span>

3. <span data-ttu-id="30e7d-123">На странице **Методы оплаты** выберите метод оплаты в раскрывающемся меню.</span><span class="sxs-lookup"><span data-stu-id="30e7d-123">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>

4. <span data-ttu-id="30e7d-124">Введите сведения о новой карточке или банковском счете, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-124">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="30e7d-125">Обновление сведений о методе оплаты</span><span class="sxs-lookup"><span data-stu-id="30e7d-125">Update payment method details</span></span>

<span data-ttu-id="30e7d-126">Вы можете изменить имя для кредитной или дебетовой карты, адреса выставления счетов или даты истечения срока действия для существующего метода оплаты.</span><span class="sxs-lookup"><span data-stu-id="30e7d-126">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="30e7d-127">Однако вы не можете изменить карточку или номер учетной записи.</span><span class="sxs-lookup"><span data-stu-id="30e7d-127">However, you can't change the card or account number.</span></span> <span data-ttu-id="30e7d-128">Если номер учетной записи изменился, [замените его на другой способ оплаты](#replace-a-payment-method), а затем [удалите старый](#delete-a-payment-method).</span><span class="sxs-lookup"><span data-stu-id="30e7d-128">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="30e7d-129">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="30e7d-129">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="30e7d-130">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="30e7d-130">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="30e7d-131">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="30e7d-131">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="30e7d-132">Выберите строку метода оплаты, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="30e7d-132">Select the row of the payment method to update.</span></span> <span data-ttu-id="30e7d-133">В правой области нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-133">In the right pane, select **Edit**.</span></span>

3. <span data-ttu-id="30e7d-134">Обновите сведения о методе оплаты, включая имя для кредитной или дебетовой карты, адрес для выставления счетов или дату окончания срока действия, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-134">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="30e7d-135">Замена способа оплаты</span><span class="sxs-lookup"><span data-stu-id="30e7d-135">Replace a payment method</span></span>

<span data-ttu-id="30e7d-136">При замене способа оплаты вы заменили его для всех подписок и профилей выставления счетов, использующих один и тот же способ оплаты.</span><span class="sxs-lookup"><span data-stu-id="30e7d-136">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="30e7d-137">При замене метода платежа существующий метод оплаты не удаляется.</span><span class="sxs-lookup"><span data-stu-id="30e7d-137">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="30e7d-138">Он по-прежнему доступен для выбора и использования для других подписок и профилей выставления счетов.</span><span class="sxs-lookup"><span data-stu-id="30e7d-138">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="30e7d-139">Чтобы изменить способ оплаты для одной подписки, ознакомьтесь со статьей [изменение способа оплаты для одной подписки](#change-a-payment-method-for-a-single-subscription).</span><span class="sxs-lookup"><span data-stu-id="30e7d-139">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="30e7d-140">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="30e7d-140">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="30e7d-141">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="30e7d-141">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="30e7d-142">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="30e7d-142">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="30e7d-143">Выберите строку метода оплаты для замены.</span><span class="sxs-lookup"><span data-stu-id="30e7d-143">Select the row of the payment method to replace.</span></span> <span data-ttu-id="30e7d-144">В области справа перечислены все профили выставления счетов и отдельные подписки, использующие выбранный способ оплаты.</span><span class="sxs-lookup"><span data-stu-id="30e7d-144">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>

3. <span data-ttu-id="30e7d-145">В области справа выберите **заменить метод оплаты для всех элементов**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-145">In the right pane, select **Replace payment method for all items**.</span></span>

4. <span data-ttu-id="30e7d-146">Чтобы использовать существующий метод оплаты, выберите его в раскрывающемся списке, а затем нажмите **заменить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-146">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="30e7d-147">Если у вас есть подписки, связанные с профилем выставления счетов, вы можете оплатить их только с помощью кредитных или дебетовых карт.</span><span class="sxs-lookup"><span data-stu-id="30e7d-147">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="30e7d-148">Если у вас есть банковские счета, указанные на странице **способы оплаты** , они недоступны для выбора в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="30e7d-148">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>

5. <span data-ttu-id="30e7d-149">Чтобы добавить новый метод оплаты, нажмите кнопку **Добавить метод оплаты**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-149">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="30e7d-150">В области **метод добавления оплаты** введите сведения об учетной записи, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-150">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="30e7d-151">Необходимо использовать метод оплаты из той же страны, что и клиент.</span><span class="sxs-lookup"><span data-stu-id="30e7d-151">You must use a payment method from the same country as your tenant.</span></span>

7. <span data-ttu-id="30e7d-152">Новый метод оплаты уже выбран в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="30e7d-152">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="30e7d-153">Нажмите кнопку **Replace** (Заменить).</span><span class="sxs-lookup"><span data-stu-id="30e7d-153">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="30e7d-154">Изменение способа оплаты для одной подписки</span><span class="sxs-lookup"><span data-stu-id="30e7d-154">Change a payment method for a single subscription</span></span>

<span data-ttu-id="30e7d-155">Вы можете изменить способ оплаты, используемый для оплаты одной подписки.</span><span class="sxs-lookup"><span data-stu-id="30e7d-155">You can change the payment method used to pay for a single subscription.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="30e7d-156">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="30e7d-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="30e7d-157">В Центре администрирования перейдите на страницу **Выставление счетов** > **Ваши продукты**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-157">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="30e7d-158">В Центре администрирования перейдите на страницу **Выставление счетов** > **Ваши продукты**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-158">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

2. <span data-ttu-id="30e7d-159">На вкладке **подписки** выберите подписку, с которой вы хотите платить, с помощью альтернативного метода оплаты.</span><span class="sxs-lookup"><span data-stu-id="30e7d-159">On the **Subscriptions** tab, select the subscription that you want to pay for with the alternate payment method.</span></span>

3. <span data-ttu-id="30e7d-160">В разделе **выставление счетов**рядом с пунктом метод оплаты нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-160">Under **Billing**, next to the payment method, select **Edit**.</span></span>

4. <span data-ttu-id="30e7d-161">Рядом с существующим методом оплаты нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-161">Next to your existing payment method, select **Change**.</span></span>

5. <span data-ttu-id="30e7d-162">В раскрывающемся списке выберите альтернативный способ оплаты или нажмите, чтобы добавить метод оплаты.</span><span class="sxs-lookup"><span data-stu-id="30e7d-162">From the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>

6. <span data-ttu-id="30e7d-163">Если вы добавляете метод оплаты, введите сведения об карточке или учетной записи, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-163">If you add a payment method, enter the card or account details, then select **Save**.</span></span>

7. <span data-ttu-id="30e7d-164">Убедитесь, что выбранный метод оплаты задан правильно, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-164">Verify that the selected payment method is correct, then select **Save**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="30e7d-165">Удаление метода оплаты</span><span class="sxs-lookup"><span data-stu-id="30e7d-165">Delete a payment method</span></span>

<span data-ttu-id="30e7d-166">Можно удалить только метод оплаты, не присоединенный к подписке или профилю выставления счетов.</span><span class="sxs-lookup"><span data-stu-id="30e7d-166">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="30e7d-167">Это относится ко всем подпискам, независимо от их состояния.</span><span class="sxs-lookup"><span data-stu-id="30e7d-167">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="30e7d-168">Удаление метода оплаты без подсоединенных подписок или профилей выставления счетов</span><span class="sxs-lookup"><span data-stu-id="30e7d-168">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="30e7d-169">Если способ оплаты не связан с подписками или профилями выставления счетов, можно сразу удалить его.</span><span class="sxs-lookup"><span data-stu-id="30e7d-169">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="30e7d-170">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="30e7d-170">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="30e7d-171">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="30e7d-171">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="30e7d-172">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="30e7d-172">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="30e7d-173">Найдите метод оплаты, который необходимо удалить, выберите три точки, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-173">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>

3. <span data-ttu-id="30e7d-174">В нижней части правой области нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-174">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="30e7d-175">Удаление метода оплаты с присоединенными подписками или профилями выставления счетов</span><span class="sxs-lookup"><span data-stu-id="30e7d-175">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="30e7d-176">Если метод оплаты присоединен к любой подписку или к профилям выставления счетов, сначала замените его на существующий метод оплаты или добавьте новый, а затем удалите старый метод оплаты.</span><span class="sxs-lookup"><span data-stu-id="30e7d-176">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="30e7d-177">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="30e7d-177">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="30e7d-178">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="30e7d-178">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="30e7d-179">В центре администрирования перейдите на **Billing** > страницу платежных **ведомостей &** оплаты оплаты оплате оплате > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="30e7d-179">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="30e7d-180">Выберите строку для удаляемого метода оплаты.</span><span class="sxs-lookup"><span data-stu-id="30e7d-180">Select the row for the payment method to delete.</span></span> <span data-ttu-id="30e7d-181">В правой области перечислены существующие подписки, которые используют этот способ оплаты.</span><span class="sxs-lookup"><span data-stu-id="30e7d-181">The right pane lists existing subscriptions that use that payment method.</span></span>

3. <span data-ttu-id="30e7d-182">В правой области нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-182">In the right pane, select **Delete**.</span></span>

4. <span data-ttu-id="30e7d-183">Чтобы использовать существующий метод оплаты, выберите его в раскрывающемся списке, нажмите кнопку **Далее**, а затем выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-183">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="30e7d-184">Если у вас есть подписки, связанные с профилем выставления счетов, вы можете оплатить их только с помощью кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="30e7d-184">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="30e7d-185">Если у вас есть банковские счета, указанные на странице **способы оплаты** , они недоступны для выбора в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="30e7d-185">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>

5. <span data-ttu-id="30e7d-186">Чтобы добавить новый метод оплаты, нажмите кнопку **Добавить метод оплаты**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-186">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="30e7d-187">Выберите тип способа оплаты, который требуется добавить, введите сведения об учетной записи, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-187">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>

7. <span data-ttu-id="30e7d-188">Новый метод оплаты уже выбран в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="30e7d-188">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="30e7d-189">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-189">Select **Next**.</span></span>

8. <span data-ttu-id="30e7d-190">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="30e7d-190">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="30e7d-191">Устранение неполадок, связанных со способом оплаты</span><span class="sxs-lookup"><span data-stu-id="30e7d-191">Troubleshoot payment methods</span></span>

|<span data-ttu-id="30e7d-192">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="30e7d-192">**Issue**</span></span>|<span data-ttu-id="30e7d-193">**Инструкции по устранению**</span><span class="sxs-lookup"><span data-stu-id="30e7d-193">**Troubleshooting steps**</span></span>|
|:----------|:-----|
|<span data-ttu-id="30e7d-194">**Получено сообщение об ошибке "браузер блокирует файлы cookie".**</span><span class="sxs-lookup"><span data-stu-id="30e7d-194">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="30e7d-195">Разрешите в настройках своего браузера прием файлов cookie от сторонних сайтов и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="30e7d-195">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="30e7d-196">**Кредитная или дебетовая карта отклонена.**</span><span class="sxs-lookup"><span data-stu-id="30e7d-196">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="30e7d-197">При оплате кредитной или дебетовой картой, если ваша карта отклонена, вы получите сообщение электронной почты с сообщением о том, что корпорации Майкрософт не удалось обработать платеж.</span><span class="sxs-lookup"><span data-stu-id="30e7d-197">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="30e7d-198">Дважды убедитесь, что &mdash; номер карточки, Дата окончания срока действия, имя карточки и адрес, включая город, область и почтовый индекс, отображаются точно так же, &mdash; как в карточке и в операторе.</span><span class="sxs-lookup"><span data-stu-id="30e7d-198">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="30e7d-199">Вы можете обновить сведения о карточке и сразу отправите платеж с помощью ссылки **сопоставление сальдо** в разделе **выставление счетов** на странице сведения о подписке.</span><span class="sxs-lookup"><span data-stu-id="30e7d-199">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="30e7d-200">Дополнительные сведения: [что делать, если кредитная карта отклонена и просрочена Дата платежа?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span><span class="sxs-lookup"><span data-stu-id="30e7d-200">For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span></span>  <br/><br/>  <span data-ttu-id="30e7d-201">Если кредитная карта все равно отклоняется, обратитесь в банк.</span><span class="sxs-lookup"><span data-stu-id="30e7d-201">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="30e7d-202">Возможно, ваша карта неактивна.</span><span class="sxs-lookup"><span data-stu-id="30e7d-202">It's possible that your card isn't active.</span></span> <span data-ttu-id="30e7d-203">Если вы недавно получали открытую в почте карточку с обновленным сроком действия, убедитесь, что она активирована.</span><span class="sxs-lookup"><span data-stu-id="30e7d-203">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="30e7d-204">В вашем банке можно также указать, является ли ваша карта неутвержденной для интерактивных, международных и повторяющихся транзакций.</span><span class="sxs-lookup"><span data-stu-id="30e7d-204">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="30e7d-205">**Я хочу обновить номер карты или банковского счета.**</span><span class="sxs-lookup"><span data-stu-id="30e7d-205">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="30e7d-206">Вы не можете изменить карточку или номер учетной записи для существующего метода оплаты.</span><span class="sxs-lookup"><span data-stu-id="30e7d-206">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="30e7d-207">Если номер карты или учетной записи изменился, [замените его на другой способ оплаты](#replace-a-payment-method), который перемещает все активные подписки со способа оплаты на новый, а затем [удаляет старый метод оплаты](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span><span class="sxs-lookup"><span data-stu-id="30e7d-207">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="30e7d-208">**В моей учетной записи есть только одна карточка или банковский счет, и их нужно удалить.**</span><span class="sxs-lookup"><span data-stu-id="30e7d-208">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="30e7d-209">Если у вас есть только один метод оплаты, необходимо [заменить его на новый метод оплаты](#replace-a-payment-method) , прежде чем его можно будет удалить.</span><span class="sxs-lookup"><span data-stu-id="30e7d-209">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="30e7d-210">**Не удается добавить карточку или банковский счет.**</span><span class="sxs-lookup"><span data-stu-id="30e7d-210">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="30e7d-211">Необходимо использовать метод оплаты, выданный из той же страны, что и клиент.</span><span class="sxs-lookup"><span data-stu-id="30e7d-211">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="30e7d-212">Если у вас возникли проблемы с вводом сведений о карте или банковском счете, [обратитесь в службу поддержки](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="30e7d-212">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-articles"></a><span data-ttu-id="30e7d-213">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="30e7d-213">Related articles</span></span>

[<span data-ttu-id="30e7d-214">Оплата вашей бизнес-подписки</span><span class="sxs-lookup"><span data-stu-id="30e7d-214">Pay for your business subscription</span></span>](pay-for-your-subscription.md)

[<span data-ttu-id="30e7d-215">Управление профилями выставления счетов</span><span class="sxs-lookup"><span data-stu-id="30e7d-215">Manage billing profiles</span></span>](manage-billing-profiles.md)

[<span data-ttu-id="30e7d-216">Изменение частоты оплаты</span><span class="sxs-lookup"><span data-stu-id="30e7d-216">Change your payment frequency</span></span>](change-payment-frequency.md)