---
title: Управление запросами на лицензии
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: Сведения о том, как просматривать и утверждать или отклонять запросы лицензий от пользователей для подписки на Microsoft 365 для бизнеса.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597662"
---
# <a name="manage-license-requests"></a><span data-ttu-id="24211-103">Управление запросами на лицензии</span><span class="sxs-lookup"><span data-stu-id="24211-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="24211-104">Сведения, приведенные в этой статье, применимы только к самостоятельно приобретенным продуктам.</span><span class="sxs-lookup"><span data-stu-id="24211-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="24211-105">Чтобы узнать больше, ознакомьтесь со статьей " [самостоятельная Покупка вопросов](../subscriptions/self-service-purchase-faq.md)".</span><span class="sxs-lookup"><span data-stu-id="24211-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="24211-106">Если вы отключите самостоятельную покупку в Организации, вы можете использовать запросы с лицензиями для управления процессом запроса лицензии для пользователей.</span><span class="sxs-lookup"><span data-stu-id="24211-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="24211-107">Когда пользователь пытается выполнить самостоятельную покупку для продукта, который вы заблокированы, он может отправить запрос на получение лицензии администратору. При выполнении запроса они могут добавлять имена других пользователей, которым также необходимы лицензии на продукт.</span><span class="sxs-lookup"><span data-stu-id="24211-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="24211-108">Если вы блокируете самостоятельную покупку, корпорация Майкрософт не отправляет маркетинговые сообщения по маркетингу.</span><span class="sxs-lookup"><span data-stu-id="24211-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="24211-109">Кроме того, если используется пробная версия продукта, они не видят приглашения для его приобретения.</span><span class="sxs-lookup"><span data-stu-id="24211-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="24211-110">Чтобы узнать больше, ознакомьтесь со статьей [Управление самостоятельными покупками (администратором)](../subscriptions/manage-self-service-purchases-admins.md).</span><span class="sxs-lookup"><span data-stu-id="24211-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="24211-111">Для просмотра и управления запросами лицензии администратор использует вкладку **запросы** на странице **Лицензирование** .</span><span class="sxs-lookup"><span data-stu-id="24211-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="24211-112">В списке отображается имя запрашиваемого продукта, имя пользователя, запросившего лицензию, дату запроса и состояние запроса.</span><span class="sxs-lookup"><span data-stu-id="24211-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="24211-113">Администраторы могут отфильтровать список для отображения ожидающих или завершенных запросов.</span><span class="sxs-lookup"><span data-stu-id="24211-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="24211-114">Запросы удерживаются в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="24211-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="24211-115">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="24211-115">Before you begin</span></span>

<span data-ttu-id="24211-116">Для выполнения задач, описанных в этой статье, необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="24211-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="24211-117">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="24211-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="24211-118">Использование собственного процесса запроса</span><span class="sxs-lookup"><span data-stu-id="24211-118">Use your own request process</span></span>

<span data-ttu-id="24211-119">Если в Организации есть собственный процесс запроса, его можно использовать вместо этого.</span><span class="sxs-lookup"><span data-stu-id="24211-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="24211-120">Вы создаете сообщение, которое будет отображаться для пользователей при запросе лицензии.</span><span class="sxs-lookup"><span data-stu-id="24211-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24211-121">Если вы используете свой собственный процесс запроса, на вкладке **запросы** не будут отображаться никакие запросы. существующие запросы из до добавления сообщения продолжают отображаться до утверждения или отклонения.</span><span class="sxs-lookup"><span data-stu-id="24211-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="24211-122">В центре администрирования перейдите на страницу лицензии **выставления счетов**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> , а затем выберите вкладку **запросы** .</span><span class="sxs-lookup"><span data-stu-id="24211-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="24211-123">Выберите **использовать существующий процесс запроса**.</span><span class="sxs-lookup"><span data-stu-id="24211-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="24211-124">В правой области в окне **сообщения** введите сообщение, которое будут видеть пользователи при запросе лицензии.</span><span class="sxs-lookup"><span data-stu-id="24211-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="24211-125">Если вы хотите также добавить ссылку на политику Организации или другую документацию, введите URL-адрес в текстовое поле **ссылка на документацию (необязательно)** .</span><span class="sxs-lookup"><span data-stu-id="24211-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="24211-126">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="24211-126">Select **Save**.</span></span>

<span data-ttu-id="24211-127">Когда вы вернетесь в список **запросы** , вы увидите сообщение, в котором вы используете **собственный процесс запроса лицензии**.</span><span class="sxs-lookup"><span data-stu-id="24211-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="24211-128">Чтобы внести изменения в сообщение, которое отправляется пользователям, установите флажок **использовать существующий процесс запроса**.</span><span class="sxs-lookup"><span data-stu-id="24211-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="24211-129">Прекращение использования собственного процесса запроса</span><span class="sxs-lookup"><span data-stu-id="24211-129">Stop using your own request process</span></span>

1. <span data-ttu-id="24211-130">В центре администрирования перейдите на страницу лицензии **выставления счетов**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> , а затем выберите вкладку **запросы** .</span><span class="sxs-lookup"><span data-stu-id="24211-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="24211-131">Выберите **использовать существующий процесс запроса**.</span><span class="sxs-lookup"><span data-stu-id="24211-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="24211-132">В правой области снимите флажок **использовать процесс запроса в Организации** .</span><span class="sxs-lookup"><span data-stu-id="24211-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="24211-133">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="24211-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="24211-134">Утверждение или отклонение запроса лицензии</span><span class="sxs-lookup"><span data-stu-id="24211-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="24211-135">В центре администрирования перейдите на страницу лицензии **выставления счетов**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> , а затем выберите вкладку **запросы** .</span><span class="sxs-lookup"><span data-stu-id="24211-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="24211-136">Выберите строку, содержащую запрос, который необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="24211-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="24211-137">В правой области отображаются сведения о том, какие пользователи хотят получить лицензии на продукт.</span><span class="sxs-lookup"><span data-stu-id="24211-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="24211-138">Чтобы отклонить весь запрос, выберите параметр **не утверждать**и в диалоговом окне выберите **не утверждать**.</span><span class="sxs-lookup"><span data-stu-id="24211-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="24211-139">Чтобы запретить некоторым пользователям запрос, но одобрить других, выберите X по имени пользователя, которого нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="24211-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="24211-140">Их имена перемещаются в раздел "не **назначать этим пользователям**".</span><span class="sxs-lookup"><span data-stu-id="24211-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="24211-141">Если имеется несколько продуктов, в разделе **Выбор продукта**выберите один, который будет использоваться для назначения лицензий.</span><span class="sxs-lookup"><span data-stu-id="24211-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="24211-142">Чтобы запретить пользователям доступ к определенным приложениям и службам, разверните узел **Включение и отключение приложений и служб**, снимите флажки для тех, которые требуется исключить.</span><span class="sxs-lookup"><span data-stu-id="24211-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="24211-143">В нижней части области введите необязательное сообщение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="24211-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="24211-144">По завершении нажмите кнопку **утвердить**.</span><span class="sxs-lookup"><span data-stu-id="24211-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="24211-145">В правой области отображаются сведения о запросе.</span><span class="sxs-lookup"><span data-stu-id="24211-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="24211-146">Закройте область справа.</span><span class="sxs-lookup"><span data-stu-id="24211-146">Close the right pane.</span></span>
    <span data-ttu-id="24211-147">Пользователи получают электронное письмо с сообщением о том, что их запрос утвержден или отклонен.</span><span class="sxs-lookup"><span data-stu-id="24211-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="24211-148">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="24211-148">Related content</span></span>

<span data-ttu-id="24211-149">[Назначение лицензий пользователям](../../admin/manage/assign-licenses-to-users.md) (статья) </span><span class="sxs-lookup"><span data-stu-id="24211-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="24211-150">[Перемещение пользователей в другую подписку](../subscriptions/move-users-different-subscription.md) (статья) </span><span class="sxs-lookup"><span data-stu-id="24211-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="24211-151">[Приобретение и удаление лицензий на подписку](buy-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="24211-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>