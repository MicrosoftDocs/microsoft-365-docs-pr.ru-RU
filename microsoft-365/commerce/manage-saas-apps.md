---
title: Управление приложениями с помощью программного обеспечения и службы для Организации
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
search.appverid: MET150
description: Сведения о том, как активировать сторонние приложения и управлять ими в центре администрирования Microsoft 365.
ms.openlocfilehash: 3e6d77eec71ca1137e0aaf44b62d198d9c87b0c5
ms.sourcegitcommit: cf7c410268175e2633e9f0d65dc859c5034658e5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232749"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="91cf8-103">Управление подписками сторонних приложений для Организации</span><span class="sxs-lookup"><span data-stu-id="91cf8-103">Manage third-party app subscriptions for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="91cf8-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="91cf8-104">The admin center is changing.</span></span> <span data-ttu-id="91cf8-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="91cf8-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="91cf8-106">Вы можете управлять лицензиями и выставлением счетов для сторонних приложений в центре администрирования Microsoft 365 с включенным режимом предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="91cf8-106">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="91cf8-107">Обновленные функции включают расширенные возможности управления подписками, Улучшенный доступ к сведениям о выставлении счетов и улучшенную гибкость для управления ведомостью.</span><span class="sxs-lookup"><span data-stu-id="91cf8-107">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="91cf8-108">Управление подписками основано на обновленной бизнес-платформе Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="91cf8-108">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="91cf8-109">Это относится к приложениям программного обеспечения, которые клиенты приобрели напрямую или от стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="91cf8-109">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="91cf8-110">Как получить приложения с программным обеспечением от имени службы</span><span class="sxs-lookup"><span data-stu-id="91cf8-110">How to get software-as-a-service apps</span></span>

<span data-ttu-id="91cf8-111">Существует несколько способов приобретения сторонних приложений.</span><span class="sxs-lookup"><span data-stu-id="91cf8-111">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="91cf8-112">**Прямая Покупка** — клиенты могут напрямую приобрести подписки на [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)или [AppSource](https://www.appsource.com/).</span><span class="sxs-lookup"><span data-stu-id="91cf8-112">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="91cf8-113">**Покупка партнеров** — работа с партнером через центр партнеров для приобретения подписки.</span><span class="sxs-lookup"><span data-stu-id="91cf8-113">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="91cf8-114">**Предложение корпорации Майкрософт** — ответ на предложение от продаж Майкрософт, включающее сторонние приложения.</span><span class="sxs-lookup"><span data-stu-id="91cf8-114">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="91cf8-115">Когда клиенты приобретают приложения и принимают соглашение с клиентами корпорации Майкрософт, они могут управлять ими в центре администрирования Microsoft 365 или Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="91cf8-115">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="91cf8-116">Поставщики приложений продают свои приложения с помощью простой ставки или приобретения лицензий для пользователей.</span><span class="sxs-lookup"><span data-stu-id="91cf8-116">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="91cf8-117">**Flat rate** (также называемые ценообразованием на основе сайта) приложения продают цену за ежемесячную или годовую цену.</span><span class="sxs-lookup"><span data-stu-id="91cf8-117">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="91cf8-118">На странице приложение количество лицензий в списке не ограничено.</span><span class="sxs-lookup"><span data-stu-id="91cf8-118">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="91cf8-119">**Licenses** — цены приложений продаются по лицензии.</span><span class="sxs-lookup"><span data-stu-id="91cf8-119">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="91cf8-120">Клиенты назначают лицензии каждому пользователю в Организации</span><span class="sxs-lookup"><span data-stu-id="91cf8-120">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="91cf8-121">Поддерживаемые регионы</span><span class="sxs-lookup"><span data-stu-id="91cf8-121">Supported regions</span></span>

<span data-ttu-id="91cf8-122">В этих регионах доступна поддержка сторонних приложений:</span><span class="sxs-lookup"><span data-stu-id="91cf8-122">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="91cf8-123">Аргентина</span><span class="sxs-lookup"><span data-stu-id="91cf8-123">Argentina</span></span>
- <span data-ttu-id="91cf8-124">Австралия</span><span class="sxs-lookup"><span data-stu-id="91cf8-124">Australia</span></span>
- <span data-ttu-id="91cf8-125">Канада</span><span class="sxs-lookup"><span data-stu-id="91cf8-125">Canada</span></span>
- <span data-ttu-id="91cf8-126">Чили</span><span class="sxs-lookup"><span data-stu-id="91cf8-126">Chile</span></span>
- <span data-ttu-id="91cf8-127">Франция</span><span class="sxs-lookup"><span data-stu-id="91cf8-127">France</span></span>
- <span data-ttu-id="91cf8-128">Германия</span><span class="sxs-lookup"><span data-stu-id="91cf8-128">Germany</span></span>
- <span data-ttu-id="91cf8-129">Греция</span><span class="sxs-lookup"><span data-stu-id="91cf8-129">Greece</span></span>
- <span data-ttu-id="91cf8-130">Пуэрто-Рико</span><span class="sxs-lookup"><span data-stu-id="91cf8-130">Puerto Rico</span></span>
- <span data-ttu-id="91cf8-131">Южная Африка</span><span class="sxs-lookup"><span data-stu-id="91cf8-131">South Africa</span></span>
- <span data-ttu-id="91cf8-132">Соединенное Королевство</span><span class="sxs-lookup"><span data-stu-id="91cf8-132">United Kingdom</span></span>
- <span data-ttu-id="91cf8-133">Соединенные Штаты</span><span class="sxs-lookup"><span data-stu-id="91cf8-133">United States</span></span>
- <span data-ttu-id="91cf8-134">Западная Европа</span><span class="sxs-lookup"><span data-stu-id="91cf8-134">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="91cf8-135">Активация сторонних приложений</span><span class="sxs-lookup"><span data-stu-id="91cf8-135">Activate third-party apps</span></span>

<span data-ttu-id="91cf8-136">Администраторы должны активировать сторонние приложения, прежде чем назначать их пользователям.</span><span class="sxs-lookup"><span data-stu-id="91cf8-136">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="91cf8-137">Эти приложения активируются на портале стороннего издателя.</span><span class="sxs-lookup"><span data-stu-id="91cf8-137">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="91cf8-138">В центре администрирования перейдите на страницу " **выставление счетов**для  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">приложений</a> продуктов".</span><span class="sxs-lookup"><span data-stu-id="91cf8-138">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91cf8-139">Найдите и выберите приложение, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="91cf8-139">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91cf8-140">В разделе **параметры & действия**выберите элемент **Управление в портале издателя**.</span><span class="sxs-lookup"><span data-stu-id="91cf8-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="91cf8-141">Вы будете направлены на сайт издателя приложения, на котором можно активировать приложение.</span><span class="sxs-lookup"><span data-stu-id="91cf8-141">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="91cf8-142">Управление сторонними приложениями</span><span class="sxs-lookup"><span data-stu-id="91cf8-142">Manage third-party apps</span></span>

<span data-ttu-id="91cf8-143">Администраторы управляют сторонними приложениями в двух расположениях: центр администрирования Microsoft 365 и портал стороннего поставщика приложений.</span><span class="sxs-lookup"><span data-stu-id="91cf8-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="91cf8-144">Вот что можно делать на каждом портале.</span><span class="sxs-lookup"><span data-stu-id="91cf8-144">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="91cf8-145">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="91cf8-145">Microsoft 365 admin center</span></span> | <span data-ttu-id="91cf8-146">Портал издателя приложения</span><span class="sxs-lookup"><span data-stu-id="91cf8-146">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="91cf8-147">Изменение количества лицензий</span><span class="sxs-lookup"><span data-stu-id="91cf8-147">Change license quantity</span></span> <br> <span data-ttu-id="91cf8-148">Управление тем, как вы оплачиваете счет</span><span class="sxs-lookup"><span data-stu-id="91cf8-148">Manage how you pay your bill</span></span> <br> <span data-ttu-id="91cf8-149">Управление тем, как вы оплачиваете счет</span><span class="sxs-lookup"><span data-stu-id="91cf8-149">Manage how you pay your bill</span></span> <br> <span data-ttu-id="91cf8-150">Изменение способа оплаты (кредитная карта)</span><span class="sxs-lookup"><span data-stu-id="91cf8-150">Change payment method (credit card)</span></span> <br> <span data-ttu-id="91cf8-151">Просмотр счета</span><span class="sxs-lookup"><span data-stu-id="91cf8-151">View invoice</span></span> <br> <span data-ttu-id="91cf8-152">Отмена подписки на приложение</span><span class="sxs-lookup"><span data-stu-id="91cf8-152">Cancel app subscription</span></span> | <span data-ttu-id="91cf8-153">Настройка приложения (один раз для каждого приложения)</span><span class="sxs-lookup"><span data-stu-id="91cf8-153">Set up app (once for each app)</span></span> <br> <span data-ttu-id="91cf8-154">Назначение лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="91cf8-154">Assign licenses to users</span></span> <br> <span data-ttu-id="91cf8-155">Техническая поддержка</span><span class="sxs-lookup"><span data-stu-id="91cf8-155">Technical support</span></span> |

<span data-ttu-id="91cf8-156">После активации приложения оно остается активным, пока оно не будет отменено, истечет срок его действия или если оплата не остается текущей.</span><span class="sxs-lookup"><span data-stu-id="91cf8-156">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="91cf8-157">Эти события меняют состояние приложения на Disabled (отключено).</span><span class="sxs-lookup"><span data-stu-id="91cf8-157">These events change the app status to disabled.</span></span> <span data-ttu-id="91cf8-158">После отключения приложение не может быть повторно активировано.</span><span class="sxs-lookup"><span data-stu-id="91cf8-158">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="91cf8-159">Чтобы продолжить работу с приложением, купите еще одну копию этого приложения.</span><span class="sxs-lookup"><span data-stu-id="91cf8-159">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="91cf8-160">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="91cf8-160">Assign licenses</span></span>

<span data-ttu-id="91cf8-161">Администраторам необходимо активировать сторонние приложения, прежде чем назначать их пользователям.</span><span class="sxs-lookup"><span data-stu-id="91cf8-161">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="91cf8-162">Они активируются на портале стороннего издателя.</span><span class="sxs-lookup"><span data-stu-id="91cf8-162">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="91cf8-163">На странице приложения в разделе **параметры & действиях**выберите ссылку для назначения лицензий.</span><span class="sxs-lookup"><span data-stu-id="91cf8-163">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="91cf8-164">В центре администрирования перейдите на страницу " **выставление счетов**для  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">приложений</a> продуктов".</span><span class="sxs-lookup"><span data-stu-id="91cf8-164">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91cf8-165">Найдите и выберите приложение, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="91cf8-165">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91cf8-166">В разделе **параметры & действий**выберите ссылку для **управления на портале издателя**.</span><span class="sxs-lookup"><span data-stu-id="91cf8-166">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="91cf8-167">Изменение количества лицензий</span><span class="sxs-lookup"><span data-stu-id="91cf8-167">Change license quantity</span></span>

<span data-ttu-id="91cf8-168">Администраторы могут изменять число лицензий, принадлежащих Организации.</span><span class="sxs-lookup"><span data-stu-id="91cf8-168">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="91cf8-169">Это относится только к приложениям, приобретенным с ценообразованием на уровне места.</span><span class="sxs-lookup"><span data-stu-id="91cf8-169">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="91cf8-170">В центре администрирования перейдите на страницу " **выставление счетов**для  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">приложений</a> продуктов".</span><span class="sxs-lookup"><span data-stu-id="91cf8-170">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91cf8-171">Найдите и выберите приложение, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="91cf8-171">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91cf8-172">Выберите **изменить количество лицензий**.</span><span class="sxs-lookup"><span data-stu-id="91cf8-172">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="91cf8-173">Управление методами оплаты</span><span class="sxs-lookup"><span data-stu-id="91cf8-173">Manage payment methods</span></span>

<span data-ttu-id="91cf8-174">Для приложений типа "от" и "Service" каждому назначен профиль выставления счетов.</span><span class="sxs-lookup"><span data-stu-id="91cf8-174">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="91cf8-175">Профили выставления счетов позволяют настроить продукты, включаемые в счет, и способ оплаты счетов.</span><span class="sxs-lookup"><span data-stu-id="91cf8-175">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="91cf8-176">В частности, это:</span><span class="sxs-lookup"><span data-stu-id="91cf8-176">They include:</span></span>

- <span data-ttu-id="91cf8-177">**Способы оплаты** — кредитные карты или передача с проверкой/проводкой</span><span class="sxs-lookup"><span data-stu-id="91cf8-177">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="91cf8-178">**Контактная информация** : адрес для выставления счетов и имя контакта</span><span class="sxs-lookup"><span data-stu-id="91cf8-178">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="91cf8-179">**Roles** — роли, позволяющие изменить профиль выставления счетов, счета оплаты или использовать метод оплаты в профиле выставления счетов, чтобы сделать покупку.</span><span class="sxs-lookup"><span data-stu-id="91cf8-179">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="91cf8-180">Дополнительные сведения о профилях выставления счетов приведены в статье Общие сведения о [профилях выставления счетов](https://docs.microsoft.com/microsoft-store/billing-profile).</span><span class="sxs-lookup"><span data-stu-id="91cf8-180">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="91cf8-181">Изменение профиля выставления счетов в подписке приложения программного обеспечения и обслуживания</span><span class="sxs-lookup"><span data-stu-id="91cf8-181">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="91cf8-182">В центре администрирования перейдите на страницу " **выставление счетов**для  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">приложений</a> продуктов".</span><span class="sxs-lookup"><span data-stu-id="91cf8-182">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91cf8-183">Найдите и выберите приложение, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="91cf8-183">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91cf8-184">Рядом с пунктом **профиль выставления счетов**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="91cf8-184">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="91cf8-185">Дополнительные сведения о счетах накладных приведены в разделе [сведения](billing-and-payments/understand-your-invoice.md)о счете.</span><span class="sxs-lookup"><span data-stu-id="91cf8-185">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="91cf8-186">Отмена подписки на приложение программного обеспечения от имени службы</span><span class="sxs-lookup"><span data-stu-id="91cf8-186">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="91cf8-187">Вы можете отменить программное обеспечение как приложение-службу на странице приложения.</span><span class="sxs-lookup"><span data-stu-id="91cf8-187">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="91cf8-188">В центре администрирования перейдите на страницу " **выставление счетов**для  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">приложений</a> продуктов".</span><span class="sxs-lookup"><span data-stu-id="91cf8-188">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91cf8-189">Найдите и выберите приложение, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="91cf8-189">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91cf8-190">В разделе **параметры & действия**выберите **Отменить подписку**.</span><span class="sxs-lookup"><span data-stu-id="91cf8-190">Under **Settings & actions**, select **Cancel subscription**.</span></span>
