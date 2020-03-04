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
ms.openlocfilehash: ab0e98963e1274925fcf678307907a93eafc9663
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409634"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="42bca-103">Управление самостоятельно приобретенными лицензиями (администратор)</span><span class="sxs-lookup"><span data-stu-id="42bca-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="42bca-104">Как администратор вы можете просматривать самостоятельные покупки сотрудников Организации.</span><span class="sxs-lookup"><span data-stu-id="42bca-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="42bca-105">Вы можете видеть продукт, название покупателя, подписки на покупку, дату истечения срока действия, покупную цену и пользователей, назначенных для каждой самообслуживания.</span><span class="sxs-lookup"><span data-stu-id="42bca-105">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="42bca-106">Если это необходимо для Организации, вы можете отключать самостоятельные покупки для каждого продукта с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42bca-106">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="42bca-107">У вас есть те же политики управления данными и доступа к продуктам, приобретаемым с помощью самостоятельной покупки или централизованного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="42bca-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="42bca-108">Вы также можете контролировать, могут ли пользователи в вашей организации совершать собственные покупки.</span><span class="sxs-lookup"><span data-stu-id="42bca-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="42bca-109">Для получения дополнительных сведений обратитесь к разделу [use алловселфсервицепурчасе для модуля PowerShell мскоммерце](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="42bca-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="42bca-110">Просмотр подписок на самостоятельную обслуживание</span><span class="sxs-lookup"><span data-stu-id="42bca-110">View self-service subscriptions</span></span>

1. <span data-ttu-id="42bca-111">В центре администрирования откройте страницу "Услуги по **выставлению счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">& услуг</a> ".</span><span class="sxs-lookup"><span data-stu-id="42bca-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="42bca-112">Рядом с **уточнением результатов**в раскрывающемся списке **тип учетной записи** выберите пункт **самостоятельная служба**.</span><span class="sxs-lookup"><span data-stu-id="42bca-112">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="42bca-113">Чтобы просмотреть дополнительные сведения о подписке, выберите ее в списке.</span><span class="sxs-lookup"><span data-stu-id="42bca-113">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="42bca-114">Просмотр лицензий на самостоятельную подписку на покупку</span><span class="sxs-lookup"><span data-stu-id="42bca-114">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="42bca-115">В центре администрирования перейдите на страницу<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">лицензии</a> **выставления счетов** > .</span><span class="sxs-lookup"><span data-stu-id="42bca-115">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="42bca-116">Нажмите значок фильтра, а затем выберите пункт **самообслуживание**.</span><span class="sxs-lookup"><span data-stu-id="42bca-116">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="42bca-117">Выберите продукт, чтобы просмотреть лицензии, назначенные пользователям.</span><span class="sxs-lookup"><span data-stu-id="42bca-117">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="42bca-118">Если для продукта существует несколько покупок, этот продукт указывается только один раз, а в столбце **доступный объем** отображается общее количество всех подписок, приобретенных для этого продукта.</span><span class="sxs-lookup"><span data-stu-id="42bca-118">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="42bca-119">Список **пользователей** сгруппирован по именам пользователей, которые внесли самостоятельные покупки.</span><span class="sxs-lookup"><span data-stu-id="42bca-119">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="42bca-120">Чтобы экспортировать список пользователей с лицензиями для этих подписок, выберите подписки, которые нужно экспортировать, и нажмите кнопку **Экспорт пользователей**.</span><span class="sxs-lookup"><span data-stu-id="42bca-120">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="42bca-121">Включение и отключение самостоятельных покупок</span><span class="sxs-lookup"><span data-stu-id="42bca-121">Disable or enable self-service purchases</span></span>

<span data-ttu-id="42bca-122">Вы можете включать и отключать самостоятельные покупки для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="42bca-122">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="42bca-123">Модуль PowerShell **мскоммерце** включает значение параметра **полициид** для **алловселфсервицепурчасе** , которое позволяет контролировать, могут ли пользователи в вашей организации совершать покупки самостоятельно, а также для каких продуктов.</span><span class="sxs-lookup"><span data-stu-id="42bca-123">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="42bca-124">С помощью модуля PowerShell **мскоммерце** можно выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="42bca-124">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="42bca-125">Просмотр состояния значения &mdash; параметра **алловселфсервицепурчасе** по умолчанию независимо от того, включено или отключено по продукту</span><span class="sxs-lookup"><span data-stu-id="42bca-125">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="42bca-126">Просмотр списка доступных продуктов и включение или отключение самостоятельной покупки</span><span class="sxs-lookup"><span data-stu-id="42bca-126">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="42bca-127">Просмотр или изменение текущего значения для конкретного продукта, чтобы включить или отключить его</span><span class="sxs-lookup"><span data-stu-id="42bca-127">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="42bca-128">Для получения дополнительных сведений обратитесь к разделу [use алловселфсервицепурчасе для модуля PowerShell мскоммерце](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="42bca-128">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="42bca-129">Централизация лицензий в одной подписке</span><span class="sxs-lookup"><span data-stu-id="42bca-129">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="42bca-130">Вы можете назначить существующие лицензии или приобрести дополнительные подписки с помощью существующих соглашений для пользователей, которым назначена самостоятельная покупка.</span><span class="sxs-lookup"><span data-stu-id="42bca-130">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="42bca-131">После назначения этих централизованно приобретенных лицензий вы можете запросить отказаться от их текущих подписок.</span><span class="sxs-lookup"><span data-stu-id="42bca-131">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="42bca-132">Войдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">центр администрирования</a> с помощью учетной записи глобального администратора или администратора выставления счетов.</span><span class="sxs-lookup"><span data-stu-id="42bca-132">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="42bca-133">Перейдите на страницу Услуги по **выставлению счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">покупки</a> .</span><span class="sxs-lookup"><span data-stu-id="42bca-133">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="42bca-134">Найдите и выберите продукт, который вы хотите купить, и нажмите кнопку **купить**.</span><span class="sxs-lookup"><span data-stu-id="42bca-134">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="42bca-135">Выполните оставшиеся действия, чтобы завершить покупку.</span><span class="sxs-lookup"><span data-stu-id="42bca-135">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="42bca-136">Выполните действия, описанные в разделе Просмотр пользователей с [лицензиями на самостоятельную подписку на самостоятельную подписку](#view-who-has-licenses-for-a-self-service-purchase-subscription) , чтобы экспортировать список пользователей, на который необходимо ссылаться на шаге 6.</span><span class="sxs-lookup"><span data-stu-id="42bca-136">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="42bca-137">Назначьте лицензии всем, у которых есть лицензия в другой подписке.</span><span class="sxs-lookup"><span data-stu-id="42bca-137">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="42bca-138">Полные действия приведены в разделе [Назначение лицензий пользователям](../../admin/manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="42bca-138">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

7. <span data-ttu-id="42bca-139">Обратитесь к сотруднику, который приобрел подписку на самостоятельную покупку и попросите его отменить.</span><span class="sxs-lookup"><span data-stu-id="42bca-139">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="42bca-140">Нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="42bca-140">Need help?</span></span> <span data-ttu-id="42bca-141">Свяжитесь с нами.</span><span class="sxs-lookup"><span data-stu-id="42bca-141">Contact us.</span></span>

<span data-ttu-id="42bca-142">Часто задаваемые вопросы об самостоятельных покупках можно найти в разделе [вопросы и ответы по самостоятельному](self-service-purchase-faq.md)обслуживанию.</span><span class="sxs-lookup"><span data-stu-id="42bca-142">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="42bca-143">Если у вас возникнут вопросы или вам нужна помощь по самостоятельным покупкам, [обратитесь в службу поддержки](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="42bca-143">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>
