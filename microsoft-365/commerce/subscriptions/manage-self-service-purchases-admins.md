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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce
search.appverid:
- MET150
description: Администраторы могут узнать, как управлять покупками самообслуживаем, сделанными пользователями в их организации.
ms.openlocfilehash: 59d64c047ddf4f33c2ef3277f3139f1b7692b891
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244996"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="11d7b-103">Управление самостоятельно приобретенными лицензиями (администратор)</span><span class="sxs-lookup"><span data-stu-id="11d7b-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="11d7b-104">В качестве администратора вы можете видеть покупки самообслуживки, сделанные людьми в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="11d7b-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="11d7b-105">Вы видите имя продукта, имя покупателей, приобретенные подписки, дату истечения срока действия, цену покупки и назначенного пользователя для каждой покупки самостоятельной службы.</span><span class="sxs-lookup"><span data-stu-id="11d7b-105">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="11d7b-106">Если это требуется вашей организации, вы можете отключить покупку самостоятельной службы на основе каждого продукта с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11d7b-106">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="11d7b-107">У вас одинаковые политики управления данными и доступа к продуктам, купленным с помощью самостоятельной покупки или централизованно.</span><span class="sxs-lookup"><span data-stu-id="11d7b-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="11d7b-108">Вы также можете контролировать, могут ли пользователи в вашей организации делать покупки с самообслуживаем.</span><span class="sxs-lookup"><span data-stu-id="11d7b-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="11d7b-109">Дополнительные сведения см. [в обзоре Использование AllowSelfServicePurchase для модуля MSCommerce PowerShell.](allowselfservicepurchase-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="11d7b-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="11d7b-110">Просмотр подписки на самообслужива</span><span class="sxs-lookup"><span data-stu-id="11d7b-110">View self-service subscriptions</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="11d7b-111">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="11d7b-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="11d7b-112">В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="11d7b-112">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="11d7b-113">В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="11d7b-113">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end

2. <span data-ttu-id="11d7b-114">На **вкладке Продукты** выберите значок фильтра, а затем выберите **самообслуживку.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="11d7b-115">Чтобы просмотреть дополнительные сведения о подписке, выберите один из списка.</span><span class="sxs-lookup"><span data-stu-id="11d7b-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="11d7b-116">Просмотр лицензий на подписку на покупку самообслужи</span><span class="sxs-lookup"><span data-stu-id="11d7b-116">View who has licenses for a self-service purchase subscription</span></span>

> [!NOTE]
> <span data-ttu-id="11d7b-117">В качестве администратора вы не можете назначить лицензии или отменить их назначение для подписок, самостоятельно приобретенных пользователем в организации.</span><span class="sxs-lookup"><span data-stu-id="11d7b-117">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="11d7b-118">Вы можете [получить контроль над самостоятельно приобретенной подпиской](#take-over-a-self-service-purchase-subscription), а затем назначить лицензии или отменить их назначение.</span><span class="sxs-lookup"><span data-stu-id="11d7b-118">You can [take over a self-service purchase subscription](#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="11d7b-119">В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="11d7b-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="11d7b-120">В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="11d7b-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="11d7b-121">В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="11d7b-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="11d7b-122">Выберите значок фильтра, а затем **выберите самообслуживку.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-122">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="11d7b-123">Выберите продукт, чтобы увидеть лицензии, присвоенные людям.</span><span class="sxs-lookup"><span data-stu-id="11d7b-123">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="11d7b-124">Если есть несколько покупок для продукта, этот продукт указан  только один раз, и столбец Доступное количество отображает общее количество всех подписок, купленных для этого продукта.</span><span class="sxs-lookup"><span data-stu-id="11d7b-124">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="11d7b-125">Список **Пользователей** сгруппировали по именам людей, которые сделали покупки самообслуживки.</span><span class="sxs-lookup"><span data-stu-id="11d7b-125">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="11d7b-126">Чтобы экспортировать список пользователей с лицензиями на эти подписки, выберите подписки, которые вы хотите экспортировать, а затем **экспортировать пользователей**.</span><span class="sxs-lookup"><span data-stu-id="11d7b-126">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="11d7b-127">Отключить или включить покупки самообслужива</span><span class="sxs-lookup"><span data-stu-id="11d7b-127">Disable or enable self-service purchases</span></span>

<span data-ttu-id="11d7b-128">Вы можете отключить или включить покупки с помощью самообслужива для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="11d7b-128">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="11d7b-129">Модуль **MSCommerce** PowerShell включает значение параметра **PolicyID** для **AllowSelfServicePurchase,** которое позволяет контролировать, могут ли пользователи в организации делать покупки с помощью самообслужива и какие продукты.</span><span class="sxs-lookup"><span data-stu-id="11d7b-129">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="11d7b-130">Модуль **MSCommerce** PowerShell можно использовать для:</span><span class="sxs-lookup"><span data-stu-id="11d7b-130">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="11d7b-131">Просмотр состояния параметра **AllowSelfServicePurchase** по умолчанию, включенного или отключенного продуктом.</span><span class="sxs-lookup"><span data-stu-id="11d7b-131">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="11d7b-132">Просмотр списка применимых продуктов и включена ли покупка самообслуживки или отключена</span><span class="sxs-lookup"><span data-stu-id="11d7b-132">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="11d7b-133">Просмотр или изменение текущего параметра для определенного продукта, чтобы включить или отключить его</span><span class="sxs-lookup"><span data-stu-id="11d7b-133">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="11d7b-134">Дополнительные сведения см. [в обзоре Использование AllowSelfServicePurchase для модуля MSCommerce PowerShell.](allowselfservicepurchase-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="11d7b-134">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="11d7b-135">Централизация лицензий по единой подписке</span><span class="sxs-lookup"><span data-stu-id="11d7b-135">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="11d7b-136">Вы можете назначить существующие лицензии или приобрести дополнительные подписки с помощью существующих соглашений для пользователей, назначаемого для покупок самообслужива.</span><span class="sxs-lookup"><span data-stu-id="11d7b-136">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="11d7b-137">После назначения этих централизованно приобретенных лицензий можно попросить покупателей отменить существующие подписки.</span><span class="sxs-lookup"><span data-stu-id="11d7b-137">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="11d7b-138">В центре администрирования перейдите на страницу **Службы** покупки > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">биллинга.</a></span><span class="sxs-lookup"><span data-stu-id="11d7b-138">In the admin center go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="11d7b-139">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">администрирования</a>перейдите на страницу **Службы** покупки > **биллинга.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-139">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="11d7b-140">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">администрирования</a>перейдите на страницу **Службы** покупки > **биллинга.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-140">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

2. <span data-ttu-id="11d7b-141">Найдите и выберите продукт, который вы хотите купить, а затем выберите **Купить**.</span><span class="sxs-lookup"><span data-stu-id="11d7b-141">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="11d7b-142">Выполните оставшиеся действия для завершения покупки.</span><span class="sxs-lookup"><span data-stu-id="11d7b-142">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="11d7b-143">Выполните действия в [Представлении,](#view-who-has-licenses-for-a-self-service-purchase-subscription) у которого есть лицензии для приобретенной подписки на самообслуживку, чтобы экспортировать список пользователей, на которые можно ссылаться на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="11d7b-143">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="11d7b-144">Назначьте лицензии всем, у кого есть лицензия в другой подписке.</span><span class="sxs-lookup"><span data-stu-id="11d7b-144">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="11d7b-145">Полный список действий см. [в тексте Назначение лицензий пользователям.](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="11d7b-145">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="11d7b-146">Свяжитесь с человеком, который купил подписку на покупку самообслуживки, и попросите [его отменить ее.](manage-self-service-purchases-users.md#cancel-a-subscription)</span><span class="sxs-lookup"><span data-stu-id="11d7b-146">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="11d7b-147">Take over a self-service purchase subscription</span><span class="sxs-lookup"><span data-stu-id="11d7b-147">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="11d7b-148">Вы можете взять на себя подписку на покупку самообслуживки, выполненную пользователем в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="11d7b-148">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="11d7b-149">При приобретении подписки на самообслуживку у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="11d7b-149">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="11d7b-150">Перемещение пользователей в другую подписку и отмена исходной подписки.</span><span class="sxs-lookup"><span data-stu-id="11d7b-150">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="11d7b-151">Отмена подписки на покупку самообслужива и удаление лицензий у назначенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="11d7b-151">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="11d7b-152">Перевод пользователей на другую подписку</span><span class="sxs-lookup"><span data-stu-id="11d7b-152">Move users to a different subscription</span></span>

<span data-ttu-id="11d7b-153">При переходе пользователей на другую подписку старая подписка автоматически отменяется.</span><span class="sxs-lookup"><span data-stu-id="11d7b-153">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="11d7b-154">Пользователь, который первоначально купил подписку на покупку самообслуживки, получает сообщение электронной почты, в которое говорится, что подписка была отменена.</span><span class="sxs-lookup"><span data-stu-id="11d7b-154">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="11d7b-155">Вы должны иметь доступную лицензию для каждого пользователя, на который перемещается подписка.</span><span class="sxs-lookup"><span data-stu-id="11d7b-155">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="11d7b-156">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="11d7b-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="11d7b-157">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">администрирования</a>перейдите на страницу **Выставление** купюру > **продуктов.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-157">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="11d7b-158">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">администрирования</a>перейдите на страницу **Выставление** купюру > **продуктов.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-158">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="11d7b-159">На **вкладке Продукты** выберите значок фильтра, а затем выберите **самообслуживку.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-159">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="11d7b-160">Выберите подписку, которую необходимо взять на себя.</span><span class="sxs-lookup"><span data-stu-id="11d7b-160">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="11d7b-161">На странице подробные сведения о подписке в разделе Подписки и **параметры** выберите **Управление этой подпиской.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-161">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="11d7b-162">В правой области выберите **Перемещение пользователей.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-162">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="11d7b-163">Выберите продукт, в который нужно переместить пользователей, а затем выберите **Move users.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-163">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="11d7b-164">В поле **Перемещение пользователей** выберите **Перемещение пользователей.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-164">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="11d7b-165">Процесс перемещения может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="11d7b-165">The move process might take several minutes.</span></span> <span data-ttu-id="11d7b-166">Не закрывай браузер во время процесса.</span><span class="sxs-lookup"><span data-stu-id="11d7b-166">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="11d7b-167">По завершению процесса перемещения закроем завершенную области **Move.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-167">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="11d7b-168">На странице подробные  сведения о подписке состояние подписки для приобретаемой подписки самообслуживной показывается как **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="11d7b-168">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="11d7b-169">Отмена подписки на покупку самообслужи</span><span class="sxs-lookup"><span data-stu-id="11d7b-169">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="11d7b-170">При отмене подписки на покупку самостоятельной службы пользователи с лицензиями теряют доступ к продукту.</span><span class="sxs-lookup"><span data-stu-id="11d7b-170">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="11d7b-171">Пользователь, который первоначально купил подписку на покупку самообслуживки, получает сообщение электронной почты, в которое говорится, что подписка была отменена.</span><span class="sxs-lookup"><span data-stu-id="11d7b-171">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="11d7b-172">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="11d7b-172">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="11d7b-173">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">администрирования</a>перейдите на страницу **Выставление** купюру > **продуктов.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-173">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="11d7b-174">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">администрирования</a>перейдите на страницу **Выставление** купюру > **продуктов.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-174">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="11d7b-175">На **вкладке Продукты** выберите значок фильтра, а затем выберите **самообслуживку.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-175">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="11d7b-176">Выберите подписку, которую хотите отменить.</span><span class="sxs-lookup"><span data-stu-id="11d7b-176">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="11d7b-177">На странице подробные сведения о подписке в разделе Подписки и **параметры** выберите **Управление этой подпиской.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-177">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="11d7b-178">В правой области выберите Отмена **подписки.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-178">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="11d7b-179">Выберите причину отмены из выпадаемого списка, а затем выберите **подписку Отмена.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-179">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="11d7b-180">В поле **Вы уверены, что хотите отменить?** выберите **отмену подписки.**</span><span class="sxs-lookup"><span data-stu-id="11d7b-180">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="11d7b-181">Закрой правую области.</span><span class="sxs-lookup"><span data-stu-id="11d7b-181">Close the right pane.</span></span>
9. <span data-ttu-id="11d7b-182">На странице сведения о подписке состояние **подписки** показывается как **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="11d7b-182">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="11d7b-183">Нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="11d7b-183">Need help?</span></span> <span data-ttu-id="11d7b-184">Свяжитесь с нами.</span><span class="sxs-lookup"><span data-stu-id="11d7b-184">Contact us.</span></span>

<span data-ttu-id="11d7b-185">Общие вопросы о покупках с самообслуживаем см. в [faq.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="11d7b-185">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="11d7b-186">Если у вас есть вопросы или вам нужна помощь с покупками самообслуживки, [обратитесь в службу поддержки.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="11d7b-186">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>