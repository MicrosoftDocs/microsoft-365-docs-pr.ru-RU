---
title: Изменение планов Office 365 для бизнеса вручную
f1.keywords:
- NOCSH
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
- commerce
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: Вручную изменяйте подписки, приобретая новую подписку и убедившись, что обе подписки указаны и активны.
ms.openlocfilehash: 0042e0fd2fa5ac10be512246c252bc1d0f679709
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245987"
---
# <a name="change-plans-manually"></a><span data-ttu-id="a402b-103">Изменение планов вручную</span><span class="sxs-lookup"><span data-stu-id="a402b-103">Change plans manually</span></span>

> [!NOTE]
> <span data-ttu-id="a402b-104">Эта статья относится к новому центру администрирования.</span><span class="sxs-lookup"><span data-stu-id="a402b-104">This article applies to the new admin center.</span></span> <span data-ttu-id="a402b-105">Новый центр администрирования доступен всем администраторам Microsoft 365, и вы можете принять участие в этой группе, выбрав пункт **попробовать новый переключатель центра администрирования** в верхней части домашней страницы.</span><span class="sxs-lookup"><span data-stu-id="a402b-105">The new admin center is available to all Microsoft 365 admins, and you can opt in by selecting **Try the new admin center** toggle located at the top of the Home page.</span></span> <span data-ttu-id="a402b-106">Дополнительные сведения см. в статье [О новом Центре администрирования Microsoft 365](../../admin/microsoft-365-admin-center-preview.md).</span><span class="sxs-lookup"><span data-stu-id="a402b-106">For more information, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md).</span></span> <span data-ttu-id="a402b-107">Чтобы просмотреть статью о старом центре администрирования, ознакомьтесь со статьей [Переключение планов Office 365 для бизнеса вручную](switch-plans-manually.md).</span><span class="sxs-lookup"><span data-stu-id="a402b-107">To view the article about the old admin center, see [Switch Office 365 for business plans manually](switch-plans-manually.md).</span></span>

## <a name="step-1-decide-how-to-change-plans"></a><span data-ttu-id="a402b-108">Шаг 1: выбор способа изменения планов</span><span class="sxs-lookup"><span data-stu-id="a402b-108">Step 1: Decide how to change plans</span></span>

<span data-ttu-id="a402b-109">Лучший способ изменения всех пользователей с одного плана на другой — [использовать вкладку Обновление](upgrade-to-different-plan.md). Иногда это невозможно.</span><span class="sxs-lookup"><span data-stu-id="a402b-109">The best way to change all your users from one plan to another is to [use the Upgrade tab](upgrade-to-different-plan.md). Sometimes this isn't possible.</span></span> <span data-ttu-id="a402b-110">Изменение планов вручную:</span><span class="sxs-lookup"><span data-stu-id="a402b-110">Change plans manually instead:</span></span>

- <span data-ttu-id="a402b-111">Если вкладка **Обновление** указывает, что обновить текущий план невозможно.</span><span class="sxs-lookup"><span data-stu-id="a402b-111">If the **Upgrade** tab indicates you can't upgrade the current plan.</span></span>

- <span data-ttu-id="a402b-112">Если при выборе вкладки **Обновление** необходимый план отсутствует в списке.</span><span class="sxs-lookup"><span data-stu-id="a402b-112">If, when you select the **Upgrade** tab, the plan you want isn't listed.</span></span>

- <span data-ttu-id="a402b-113">Если вы не хотите выполнять обновление всех пользователей одинаковым образом.</span><span class="sxs-lookup"><span data-stu-id="a402b-113">If you don't want to upgrade all your users in the same way.</span></span> <span data-ttu-id="a402b-114">Некоторым организациям необходимо, чтобы разные пользователи были подписаны на разные планы.</span><span class="sxs-lookup"><span data-stu-id="a402b-114">Some businesses need different users subscribed to different plans.</span></span> <span data-ttu-id="a402b-115">Для этого используйте ручное изменение.</span><span class="sxs-lookup"><span data-stu-id="a402b-115">Use a manual change for this.</span></span>

<span data-ttu-id="a402b-116">Чтобы продолжить изменение вручную, прочтите [Шаг 2: купить новую подписку](#step-2-buy-a-new-subscription) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="a402b-116">To continue with a manual change, read [Step 2: Buy a new subscription](#step-2-buy-a-new-subscription) in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a402b-117">Если вы изменяете план с меньшим количеством служб, связанных с данными, чем текущий план (понижение уровня), необходимо вручную выполнить резервное копирование всех данных, которые необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="a402b-117">If you are changing to a plan with fewer data-related services than your current plan (downgrading), you need to manually back up any data you wish to keep.</span></span> <span data-ttu-id="a402b-118">Дополнительные сведения см. в статье [резервное копирование данных перед переключением O365 для бизнес-планов](back-up-data-before-switching-plans.md).</span><span class="sxs-lookup"><span data-stu-id="a402b-118">For more information, see [Back up data before switching O365 for business plans](back-up-data-before-switching-plans.md).</span></span>

## <a name="step-2-buy-a-new-subscription"></a><span data-ttu-id="a402b-119">Шаг 2: приобретение новой подписки</span><span class="sxs-lookup"><span data-stu-id="a402b-119">Step 2: Buy a new subscription</span></span>

<span data-ttu-id="a402b-120">**Уже приобрели?**</span><span class="sxs-lookup"><span data-stu-id="a402b-120">**Already purchased?**</span></span> <span data-ttu-id="a402b-121">Если у вас уже есть подписка, в которую вы хотите переместить пользователей, пропустите этот шаг и перейдите к [шагу 3: проверьте новую подписку и лицензии,](#step-3-check-your-new-subscription-and-licenses) приведенные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="a402b-121">If you already have a subscription you want to move users to, skip this step and go to [Step 3: Check your new subscription and licenses](#step-3-check-your-new-subscription-and-licenses) in this topic.</span></span>

<span data-ttu-id="a402b-122">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="a402b-122">OR</span></span>

<span data-ttu-id="a402b-123">**Приобретение новой подписки и лицензий.** Чтобы купить новую подписку, выполните инструкции в статье [Приобретение другой подписки на Office 365 для бизнеса](../buy-another-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="a402b-123">**Purchase a new subscription and licenses:** Follow the steps in [Buy another Office 365 for business subscription](../buy-another-subscription.md) to buy a new subscription.</span></span>

<span data-ttu-id="a402b-124">Убедитесь в том, что покупаете подписку для той же организации, в которой сейчас находятся пользователи.</span><span class="sxs-lookup"><span data-stu-id="a402b-124">Make sure you purchase a subscription for the same organization that the users are in now.</span></span> <span data-ttu-id="a402b-125">Например, проверьте адреса электронной почты пользователей Office 365, которых хотите переместить.</span><span class="sxs-lookup"><span data-stu-id="a402b-125">For example, check the email addresses for the Office 365 users you want to move.</span></span> <span data-ttu-id="a402b-126">Если их адреса электронной почты \@входят в Contoso.com, необходимо приобрести новую подписку на contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a402b-126">If their email addresses include \@contoso.com, you must purchase a new subscription for contoso.com.</span></span>
<span data-ttu-id="a402b-127">Добавьте лицензию для каждого пользователя, которого хотите переместить.</span><span class="sxs-lookup"><span data-stu-id="a402b-127">Include a license for each user that you want to move.</span></span>

## <a name="step-3-check-your-new-subscription-and-licenses"></a><span data-ttu-id="a402b-128">Шаг 3: Проверка новой подписки и лицензий</span><span class="sxs-lookup"><span data-stu-id="a402b-128">Step 3: Check your new subscription and licenses</span></span>

1. <span data-ttu-id="a402b-129">В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Продукты и службы</a>.</span><span class="sxs-lookup"><span data-stu-id="a402b-129">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="a402b-130">**Проверка того, что обе подписки указаны и активны** Подписка, из которой вы перемещаете пользователей, и подписка, в которую вы перемещаете пользователей, должны быть указаны вместе.</span><span class="sxs-lookup"><span data-stu-id="a402b-130">**Verify that both subscriptions are listed and active** The subscription that you're moving users from and the subscription that you're moving users to must be listed together.</span></span> <span data-ttu-id="a402b-131">Если при первой проверке новой подписки нет, попробуйте еще раз позже.</span><span class="sxs-lookup"><span data-stu-id="a402b-131">If the new subscription isn't there when you first check, try again later.</span></span> <span data-ttu-id="a402b-132">Убедитесь, что обе подписки активны.</span><span class="sxs-lookup"><span data-stu-id="a402b-132">Check that both subscriptions are active.</span></span> <span data-ttu-id="a402b-133">[Новая подписка не указана или неактивна](#the-new-subscription-isnt-listed-or-isnt-active).</span><span class="sxs-lookup"><span data-stu-id="a402b-133">[The new subscription isn't listed, or isn't active](#the-new-subscription-isnt-listed-or-isnt-active).</span></span>

3. <span data-ttu-id="a402b-134">**Убедитесь, что у вас достаточно лицензий для каждого пользователя** . Каждому пользователю необходима лицензия, соответствующая своей подписке.</span><span class="sxs-lookup"><span data-stu-id="a402b-134">**Check that you have enough licenses for each user** Each user needs a license that matches their subscription.</span></span> <span data-ttu-id="a402b-135">Так, если вы хотите переместить десять пользователей в Office 365 корпоративный E5, у вас должно быть десять доступных лицензий.</span><span class="sxs-lookup"><span data-stu-id="a402b-135">So if you want to move ten users to Office 365 Enterprise E5, you'll need to make sure ten licenses are available.</span></span>

4. <span data-ttu-id="a402b-136">**Нужно больше лицензий для новой подписки?**</span><span class="sxs-lookup"><span data-stu-id="a402b-136">**Need more licenses for the new subscription?**</span></span>
   <span data-ttu-id="a402b-137">Перейдите на страницу **продукты & услуг** и [приобретите дополнительные лицензии](../licenses/buy-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="a402b-137">Go to the **Products & services** page and [buy more licenses](../licenses/buy-licenses.md).</span></span>

> [<span data-ttu-id="a402b-138">Что насчет старых лицензий?</span><span class="sxs-lookup"><span data-stu-id="a402b-138">What about the old licenses?</span></span>](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a><span data-ttu-id="a402b-139">Новая подписка не указана или неактивна</span><span class="sxs-lookup"><span data-stu-id="a402b-139">The new subscription isn't listed, or isn't active</span></span>

- <span data-ttu-id="a402b-140">**Если вы приобрели две подписки, и они обе не указаны**, возможно, они были приобретены для разных организаций (разных доменов).</span><span class="sxs-lookup"><span data-stu-id="a402b-140">**If you purchased two subscriptions and they are not both listed here**, they may have been purchased for different organizations (for different domains).</span></span> <span data-ttu-id="a402b-141">Подписки не распространяются за пределы организаций.</span><span class="sxs-lookup"><span data-stu-id="a402b-141">Subscriptions can't cross organization boundaries.</span></span>

- <span data-ttu-id="a402b-142">**Если вы знаете, что у вас есть дополнительная подписка**, она не указана или неактивна, [обратитесь в службу поддержки Майкрософт](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="a402b-142">**If you know you have an additional subscription**, and it's not listed here, or is not active, [call Microsoft support](../../admin/contact-support-for-business-products.md).</span></span>

### <a name="what-about-the-old-licenses"></a><span data-ttu-id="a402b-143">Что насчет старых лицензий?</span><span class="sxs-lookup"><span data-stu-id="a402b-143">What about the old licenses?</span></span>

<span data-ttu-id="a402b-144">Лицензии для текущей подписки будут удалены позже. С этого момента вы будете платить только за новые пользовательские лицензии.</span><span class="sxs-lookup"><span data-stu-id="a402b-144">The licenses for the current subscription will be removed later; you'll only pay for the new user licenses from then on.</span></span>

## <a name="step-4-reassign-licenses"></a><span data-ttu-id="a402b-145">Шаг 4: переназначение лицензий</span><span class="sxs-lookup"><span data-stu-id="a402b-145">Step 4: Reassign licenses</span></span>

### <a name="reassign-a-license-for-one-user"></a><span data-ttu-id="a402b-146">Переназначение лицензии для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="a402b-146">Reassign a license for one user</span></span>

1. <span data-ttu-id="a402b-147">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="a402b-147">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="a402b-148">На странице **Активные пользователи** выберите пользователя, которому вы хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="a402b-148">On the **Active users** page, select the user to whom you want to assign a license.</span></span>

3. <span data-ttu-id="a402b-149">На вкладке " **лицензии и приложения** Te" разверните узел **лицензии**, выберите поля для лицензий, которые необходимо назначить, а затем нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="a402b-149">On te **Licenses and Apps** tab, expand **Licenses**, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

### <a name="reassign-licenses-for-multiple-users-at-once"></a><span data-ttu-id="a402b-150">Переназначение лицензий сразу для нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="a402b-150">Reassign licenses for multiple users at once</span></span>

1. <span data-ttu-id="a402b-151">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="a402b-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="a402b-152">Выберите кружки рядом с именами пользователей, для которых требуется заменить существующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="a402b-152">Select the circles next to the names of the users for whom you want to replace existing licenses.</span></span>

3. <span data-ttu-id="a402b-153">В верхней части нажмите кнопку **Дополнительные параметры** (**...**), а затем выберите пункт **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="a402b-153">At the top, select **More options** (**...**), and then choose **Manage product licenses**.</span></span>

4. <span data-ttu-id="a402b-154">Select **Replace existing product license assignments** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="a402b-154">Select **Replace existing product license assignments** \> **Next**.</span></span>

5. <span data-ttu-id="a402b-155">Установите выключатель для продукта, лицензию на который вы хотите назначить, в положение **Вкл.**</span><span class="sxs-lookup"><span data-stu-id="a402b-155">Switch the toggle to the **On** position for the products you want to assign to these users.</span></span>

    > [!TIP]
    > - <span data-ttu-id="a402b-156">Чтобы ограничить доступ пользователей к службам, переключитесь в режим **отключения** для служб, которые нужно удалить для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="a402b-156">To limit which services are available to the user, switch to toggles to the **Off** position for the services that you want to remove for that user.</span></span> <span data-ttu-id="a402b-157">Например, чтобы пользователь имел доступ ко всем имеющимся службам, кроме Skype для бизнеса online, установите выключатель для службы Skype для бизнеса online в положение **Выкл.**</span><span class="sxs-lookup"><span data-stu-id="a402b-157">For example, if you want the user to have access to all available services except Skype for Business Online, you can switch the toggle for the Skype for Business Online service to the **Off** position.</span></span>
    > - <span data-ttu-id="a402b-158">Все предыдущие назначения лицензий для выбранных пользователей будут удалены.</span><span class="sxs-lookup"><span data-stu-id="a402b-158">Any previous license assignments for the selected users will be removed.</span></span>

6. <span data-ttu-id="a402b-159">В нижней части области **Заменить имеющиеся продукты** нажмите **Заменить** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a402b-159">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a><span data-ttu-id="a402b-160">Шаг 5: Отмена подписки или удаление лицензий, которые больше не нужны (необязательно)</span><span class="sxs-lookup"><span data-stu-id="a402b-160">Step 5: Cancel subscriptions or remove licenses that you no longer need (Optional)</span></span>

<span data-ttu-id="a402b-161">Если вы переместили всех пользователей с одной подписки на другую и вам больше не нужна исходная подписка, вы можете [отменить ее](cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="a402b-161">If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).</span></span>

<span data-ttu-id="a402b-162">Если вы переместили в другую подписку только часть пользователей, [удалите лицензии](../licenses/remove-licenses-from-subscription.md), которые вам больше не нужны.</span><span class="sxs-lookup"><span data-stu-id="a402b-162">If you moved only some users to a different subscription, [remove licenses](../licenses/remove-licenses-from-subscription.md) that you no longer need.</span></span>

## <a name="call-support-to-help-you-change-plans"></a><span data-ttu-id="a402b-163">Обращение в службу поддержки для помощи в изменении планов</span><span class="sxs-lookup"><span data-stu-id="a402b-163">Call support to help you change plans</span></span>
[<span data-ttu-id="a402b-164">Позвонить в службу поддержки Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a402b-164">Call Microsoft support</span></span>](../../admin/contact-support-for-business-products.md)