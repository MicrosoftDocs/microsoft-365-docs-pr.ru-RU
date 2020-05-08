---
title: Управление покупками самостоятельных служб (Администраторы)
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
- commerce
search.appverid:
- MET150
description: Администраторы могут узнать, как управлять самостоятельными покупками пользователей в Организации.
ms.openlocfilehash: 991dc87c40f41a6cbd2f1c08d4bc72bbb34d28f1
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141154"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="410f3-103">Управление самостоятельно приобретенными лицензиями (администратор)</span><span class="sxs-lookup"><span data-stu-id="410f3-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="410f3-104">Изменяется центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="410f3-104">The admin center is changing.</span></span> <span data-ttu-id="410f3-105">Если ваш интерфейс не отвечает указанным здесь сведениям, ознакомьтесь [со статьей о новом центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="410f3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="410f3-106">Как администратор вы можете просматривать самостоятельные покупки сотрудников Организации.</span><span class="sxs-lookup"><span data-stu-id="410f3-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="410f3-107">Вы можете видеть продукт, название покупателя, подписки на покупку, дату истечения срока действия, покупную цену и пользователей, назначенных для каждой самообслуживания.</span><span class="sxs-lookup"><span data-stu-id="410f3-107">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="410f3-108">Если это необходимо для Организации, вы можете отключать самостоятельные покупки для каждого продукта с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="410f3-108">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="410f3-109">У вас есть те же политики управления данными и доступа к продуктам, приобретаемым с помощью самостоятельной покупки или централизованного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="410f3-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="410f3-110">Вы также можете контролировать, могут ли пользователи в вашей организации совершать собственные покупки.</span><span class="sxs-lookup"><span data-stu-id="410f3-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="410f3-111">Для получения дополнительных сведений обратитесь к разделу [use алловселфсервицепурчасе для модуля PowerShell мскоммерце](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="410f3-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="410f3-112">Просмотр подписок на самостоятельную обслуживание</span><span class="sxs-lookup"><span data-stu-id="410f3-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="410f3-113">В центре администрирования перейдите на страницу **выставление счетов** > по<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">продуктам</a> .</span><span class="sxs-lookup"><span data-stu-id="410f3-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="410f3-114">Рядом с **уточнением результатов**в раскрывающемся списке **тип учетной записи** выберите пункт **самостоятельная служба**.</span><span class="sxs-lookup"><span data-stu-id="410f3-114">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="410f3-115">Чтобы просмотреть дополнительные сведения о подписке, выберите ее в списке.</span><span class="sxs-lookup"><span data-stu-id="410f3-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="410f3-116">Просмотр лицензий на самостоятельную подписку на покупку</span><span class="sxs-lookup"><span data-stu-id="410f3-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="410f3-117">В центре администрирования перейдите на страницу<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">лицензии</a> **выставления счетов** > .</span><span class="sxs-lookup"><span data-stu-id="410f3-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="410f3-118">Нажмите значок фильтра, а затем выберите пункт **самообслуживание**.</span><span class="sxs-lookup"><span data-stu-id="410f3-118">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="410f3-119">Выберите продукт, чтобы просмотреть лицензии, назначенные пользователям.</span><span class="sxs-lookup"><span data-stu-id="410f3-119">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="410f3-120">Если для продукта существует несколько покупок, этот продукт указывается только один раз, а в столбце **доступный объем** отображается общее количество всех подписок, приобретенных для этого продукта.</span><span class="sxs-lookup"><span data-stu-id="410f3-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="410f3-121">Список **пользователей** сгруппирован по именам пользователей, которые внесли самостоятельные покупки.</span><span class="sxs-lookup"><span data-stu-id="410f3-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="410f3-122">Чтобы экспортировать список пользователей с лицензиями для этих подписок, выберите подписки, которые нужно экспортировать, и нажмите кнопку **Экспорт пользователей**.</span><span class="sxs-lookup"><span data-stu-id="410f3-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="410f3-123">Включение и отключение самостоятельных покупок</span><span class="sxs-lookup"><span data-stu-id="410f3-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="410f3-124">Вы можете включать и отключать самостоятельные покупки для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="410f3-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="410f3-125">Модуль PowerShell **мскоммерце** включает значение параметра **полициид** для **алловселфсервицепурчасе** , которое позволяет контролировать, могут ли пользователи в вашей организации совершать покупки самостоятельно, а также для каких продуктов.</span><span class="sxs-lookup"><span data-stu-id="410f3-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="410f3-126">С помощью модуля PowerShell **мскоммерце** можно выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="410f3-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="410f3-127">Просмотр состояния значения &mdash; параметра **алловселфсервицепурчасе** по умолчанию независимо от того, включено или отключено по продукту</span><span class="sxs-lookup"><span data-stu-id="410f3-127">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="410f3-128">Просмотр списка доступных продуктов и включение или отключение самостоятельной покупки</span><span class="sxs-lookup"><span data-stu-id="410f3-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="410f3-129">Просмотр или изменение текущего значения для конкретного продукта, чтобы включить или отключить его</span><span class="sxs-lookup"><span data-stu-id="410f3-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="410f3-130">Для получения дополнительных сведений обратитесь к разделу [use алловселфсервицепурчасе для модуля PowerShell мскоммерце](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="410f3-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="410f3-131">Централизация лицензий в одной подписке</span><span class="sxs-lookup"><span data-stu-id="410f3-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="410f3-132">Вы можете назначить существующие лицензии или приобрести дополнительные подписки с помощью существующих соглашений для пользователей, которым назначена самостоятельная покупка.</span><span class="sxs-lookup"><span data-stu-id="410f3-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="410f3-133">После назначения этих централизованно приобретенных лицензий вы можете запросить отказаться от их текущих подписок.</span><span class="sxs-lookup"><span data-stu-id="410f3-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="410f3-134">Войдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">центр администрирования</a> с помощью учетной записи глобального администратора или администратора выставления счетов.</span><span class="sxs-lookup"><span data-stu-id="410f3-134">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="410f3-135">Перейдите на страницу Услуги по **выставлению счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">покупки</a> .</span><span class="sxs-lookup"><span data-stu-id="410f3-135">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="410f3-136">Найдите и выберите продукт, который вы хотите купить, и нажмите кнопку **купить**.</span><span class="sxs-lookup"><span data-stu-id="410f3-136">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="410f3-137">Выполните оставшиеся действия, чтобы завершить покупку.</span><span class="sxs-lookup"><span data-stu-id="410f3-137">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="410f3-138">Выполните действия, описанные в разделе Просмотр пользователей с [лицензиями на самостоятельную подписку на самостоятельную подписку](#view-who-has-licenses-for-a-self-service-purchase-subscription) , чтобы экспортировать список пользователей, на который необходимо ссылаться на шаге 6.</span><span class="sxs-lookup"><span data-stu-id="410f3-138">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="410f3-139">Назначьте лицензии всем, у которых есть лицензия в другой подписке.</span><span class="sxs-lookup"><span data-stu-id="410f3-139">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="410f3-140">Полные действия приведены в разделе [Назначение лицензий пользователям](../../admin/manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="410f3-140">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

7. <span data-ttu-id="410f3-141">Обратитесь к сотруднику, который приобрел подписку на самостоятельную покупку и попросите его отменить.</span><span class="sxs-lookup"><span data-stu-id="410f3-141">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="410f3-142">Нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="410f3-142">Need help?</span></span> <span data-ttu-id="410f3-143">Свяжитесь с нами.</span><span class="sxs-lookup"><span data-stu-id="410f3-143">Contact us.</span></span>

<span data-ttu-id="410f3-144">Часто задаваемые вопросы об самостоятельных покупках можно найти в разделе [вопросы и ответы по самостоятельному](self-service-purchase-faq.md)обслуживанию.</span><span class="sxs-lookup"><span data-stu-id="410f3-144">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="410f3-145">Если у вас возникнут вопросы или вам нужна помощь по самостоятельным покупкам, [обратитесь в службу поддержки](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="410f3-145">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>
