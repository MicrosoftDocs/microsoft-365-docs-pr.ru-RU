---
title: Управление покупками самообслуживки (администраторы)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Администраторы могут узнать, как управлять покупками самообслуживаем, сделанными пользователями в их организации.
ms.openlocfilehash: 2ce12b7dba4e765745a94fa10f4ba15e7013e3c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920184"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="09215-103">Управление самостоятельно приобретенными лицензиями (администратор)</span><span class="sxs-lookup"><span data-stu-id="09215-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="09215-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="09215-104">The admin center is changing.</span></span> <span data-ttu-id="09215-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="09215-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="09215-106">В качестве администратора вы можете видеть покупки самообслуживки, сделанные людьми в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="09215-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="09215-107">Вы видите имя продукта, имя покупателей, приобретенные подписки, дату истечения срока действия, цену покупки и назначенного пользователя для каждой покупки самостоятельной службы.</span><span class="sxs-lookup"><span data-stu-id="09215-107">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="09215-108">Если это требуется вашей организации, вы можете отключить покупку самостоятельной службы на основе каждого продукта с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09215-108">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="09215-109">У вас одинаковые политики управления данными и доступа к продуктам, купленным с помощью самостоятельной покупки или централизованно.</span><span class="sxs-lookup"><span data-stu-id="09215-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="09215-110">Вы также можете контролировать, могут ли пользователи в вашей организации делать покупки с самообслуживаем.</span><span class="sxs-lookup"><span data-stu-id="09215-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="09215-111">Дополнительные сведения см. [в обзоре Использование AllowSelfServicePurchase для модуля MSCommerce PowerShell.](allowselfservicepurchase-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="09215-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="09215-112">Просмотр подписки на самообслужива</span><span class="sxs-lookup"><span data-stu-id="09215-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="09215-113">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="09215-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="09215-114">На **вкладке Продукты** выберите значок фильтра, а затем выберите **самообслуживку.**</span><span class="sxs-lookup"><span data-stu-id="09215-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="09215-115">Чтобы просмотреть дополнительные сведения о подписке, выберите один из списка.</span><span class="sxs-lookup"><span data-stu-id="09215-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="09215-116">Просмотр лицензий на подписку на покупку самообслужи</span><span class="sxs-lookup"><span data-stu-id="09215-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="09215-117">В центре администрирования перейдите на страницу **Биллинг**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии.</a></span><span class="sxs-lookup"><span data-stu-id="09215-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="09215-118">Выберите значок фильтра, а затем **выберите самообслуживку.**</span><span class="sxs-lookup"><span data-stu-id="09215-118">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="09215-119">Выберите продукт, чтобы увидеть лицензии, присвоенные людям.</span><span class="sxs-lookup"><span data-stu-id="09215-119">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="09215-120">Если есть несколько покупок для продукта, этот продукт указан  только один раз, и столбец Доступное количество отображает общее количество всех подписок, купленных для этого продукта.</span><span class="sxs-lookup"><span data-stu-id="09215-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="09215-121">Список **Пользователей** сгруппировали по именам людей, которые сделали покупки самообслуживки.</span><span class="sxs-lookup"><span data-stu-id="09215-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="09215-122">Чтобы экспортировать список пользователей с лицензиями на эти подписки, выберите подписки, которые вы хотите экспортировать, а затем **экспортировать пользователей**.</span><span class="sxs-lookup"><span data-stu-id="09215-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="09215-123">Отключить или включить покупки самообслужива</span><span class="sxs-lookup"><span data-stu-id="09215-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="09215-124">Вы можете отключить или включить покупки с помощью самообслужива для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="09215-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="09215-125">Модуль **MSCommerce** PowerShell включает значение параметра **PolicyID** для **AllowSelfServicePurchase,** которое позволяет контролировать, могут ли пользователи в организации делать покупки с помощью самообслужива и какие продукты.</span><span class="sxs-lookup"><span data-stu-id="09215-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="09215-126">Модуль **MSCommerce** PowerShell можно использовать для:</span><span class="sxs-lookup"><span data-stu-id="09215-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="09215-127">Просмотр состояния параметра **AllowSelfServicePurchase** по умолчанию, включенного или отключенного продуктом.</span><span class="sxs-lookup"><span data-stu-id="09215-127">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="09215-128">Просмотр списка применимых продуктов и включена ли покупка самообслуживки или отключена</span><span class="sxs-lookup"><span data-stu-id="09215-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="09215-129">Просмотр или изменение текущего параметра для определенного продукта, чтобы включить или отключить его</span><span class="sxs-lookup"><span data-stu-id="09215-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="09215-130">Дополнительные сведения см. [в обзоре Использование AllowSelfServicePurchase для модуля MSCommerce PowerShell.](allowselfservicepurchase-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="09215-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="09215-131">Централизация лицензий по единой подписке</span><span class="sxs-lookup"><span data-stu-id="09215-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="09215-132">Вы можете назначить существующие лицензии или приобрести дополнительные подписки с помощью существующих соглашений для пользователей, назначаемого для покупок самообслужива.</span><span class="sxs-lookup"><span data-stu-id="09215-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="09215-133">После назначения этих централизованно приобретенных лицензий можно попросить покупателей отменить существующие подписки.</span><span class="sxs-lookup"><span data-stu-id="09215-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="09215-134">В центре администрирования перейдите на страницу **Службы** покупки \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">биллинга.</a></span><span class="sxs-lookup"><span data-stu-id="09215-134">In the admin center go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="09215-135">Найдите и выберите продукт, который вы хотите купить, а затем выберите **Купить**.</span><span class="sxs-lookup"><span data-stu-id="09215-135">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="09215-136">Выполните оставшиеся действия для завершения покупки.</span><span class="sxs-lookup"><span data-stu-id="09215-136">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="09215-137">Выполните действия в [Представлении,](#view-who-has-licenses-for-a-self-service-purchase-subscription) у которого есть лицензии для приобретенной подписки на самообслуживку, чтобы экспортировать список пользователей, на которые можно ссылаться на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="09215-137">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="09215-138">Назначьте лицензии всем, у кого есть лицензия в другой подписке.</span><span class="sxs-lookup"><span data-stu-id="09215-138">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="09215-139">Полный список действий см. [в тексте Назначение лицензий пользователям.](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="09215-139">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="09215-140">Свяжитесь с человеком, который купил подписку на покупку самообслуживки, и попросите [его отменить ее.](manage-self-service-purchases-users.md#cancel-a-subscription)</span><span class="sxs-lookup"><span data-stu-id="09215-140">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="09215-141">Take over a self-service purchase subscription</span><span class="sxs-lookup"><span data-stu-id="09215-141">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="09215-142">Вы можете взять на себя подписку на покупку самообслуживки, выполненную пользователем в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="09215-142">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="09215-143">При приобретении подписки на самообслуживку у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="09215-143">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="09215-144">Перемещение пользователей в другую подписку и отмена исходной подписки.</span><span class="sxs-lookup"><span data-stu-id="09215-144">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="09215-145">Отмена подписки на покупку самообслужива и удаление лицензий у назначенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="09215-145">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="09215-146">Перевод пользователей на другую подписку</span><span class="sxs-lookup"><span data-stu-id="09215-146">Move users to a different subscription</span></span>

<span data-ttu-id="09215-147">При переходе пользователей на другую подписку старая подписка автоматически отменяется.</span><span class="sxs-lookup"><span data-stu-id="09215-147">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="09215-148">Пользователь, который первоначально купил подписку на покупку самообслуживки, получает сообщение электронной почты, в которое говорится, что подписка была отменена.</span><span class="sxs-lookup"><span data-stu-id="09215-148">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="09215-149">Вы должны иметь доступную лицензию для каждого пользователя, на который перемещается подписка.</span><span class="sxs-lookup"><span data-stu-id="09215-149">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

1. <span data-ttu-id="09215-150">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="09215-150">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="09215-151">На **вкладке Продукты** выберите значок фильтра, а затем выберите **самообслуживку.**</span><span class="sxs-lookup"><span data-stu-id="09215-151">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="09215-152">Выберите подписку, которую необходимо взять на себя.</span><span class="sxs-lookup"><span data-stu-id="09215-152">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="09215-153">На странице подробные сведения о подписке в разделе Подписки и **параметры** выберите **Управление этой подпиской.**</span><span class="sxs-lookup"><span data-stu-id="09215-153">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="09215-154">В правой области выберите **Перемещение пользователей.**</span><span class="sxs-lookup"><span data-stu-id="09215-154">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="09215-155">Выберите продукт, в который нужно переместить пользователей, а затем выберите **Move users.**</span><span class="sxs-lookup"><span data-stu-id="09215-155">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="09215-156">В поле **Перемещение пользователей** выберите **Перемещение пользователей.**</span><span class="sxs-lookup"><span data-stu-id="09215-156">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="09215-157">Процесс перемещения может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="09215-157">The move process might take several minutes.</span></span> <span data-ttu-id="09215-158">Не закрывай браузер во время процесса.</span><span class="sxs-lookup"><span data-stu-id="09215-158">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="09215-159">По завершению процесса перемещения закроем завершенную области **Move.**</span><span class="sxs-lookup"><span data-stu-id="09215-159">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="09215-160">На странице подробные  сведения о подписке состояние подписки для приобретаемой подписки самообслуживной показывается как **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="09215-160">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="09215-161">Отмена подписки на покупку самообслужи</span><span class="sxs-lookup"><span data-stu-id="09215-161">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="09215-162">При отмене подписки на покупку самостоятельной службы пользователи с лицензиями теряют доступ к продукту.</span><span class="sxs-lookup"><span data-stu-id="09215-162">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="09215-163">Пользователь, который первоначально купил подписку на покупку самообслуживки, получает сообщение электронной почты, в которое говорится, что подписка была отменена.</span><span class="sxs-lookup"><span data-stu-id="09215-163">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

1. <span data-ttu-id="09215-164">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="09215-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="09215-165">На **вкладке Продукты** выберите значок фильтра, а затем выберите **самообслуживку.**</span><span class="sxs-lookup"><span data-stu-id="09215-165">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="09215-166">Выберите подписку, которую необходимо отменить.</span><span class="sxs-lookup"><span data-stu-id="09215-166">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="09215-167">На странице подробные сведения о подписке в разделе Подписки и **параметры** выберите **Управление этой подпиской.**</span><span class="sxs-lookup"><span data-stu-id="09215-167">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="09215-168">В правой области выберите Отмена **подписки.**</span><span class="sxs-lookup"><span data-stu-id="09215-168">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="09215-169">Выберите причину отмены из выпадаемого списка, а затем выберите **подписку Отмена.**</span><span class="sxs-lookup"><span data-stu-id="09215-169">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="09215-170">В поле **Вы уверены, что хотите отменить?** выберите **отмену подписки.**</span><span class="sxs-lookup"><span data-stu-id="09215-170">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="09215-171">Закрой правую области.</span><span class="sxs-lookup"><span data-stu-id="09215-171">Close the right pane.</span></span>
9. <span data-ttu-id="09215-172">На странице сведения о подписке состояние **подписки** показывается как **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="09215-172">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="09215-173">Нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="09215-173">Need help?</span></span> <span data-ttu-id="09215-174">Свяжитесь с нами.</span><span class="sxs-lookup"><span data-stu-id="09215-174">Contact us.</span></span>

<span data-ttu-id="09215-175">Общие вопросы о покупках с самообслуживаем см. в [faq.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="09215-175">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="09215-176">Если у вас есть вопросы или вам нужна помощь с покупками самообслуживки, [обратитесь в службу поддержки.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="09215-176">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>