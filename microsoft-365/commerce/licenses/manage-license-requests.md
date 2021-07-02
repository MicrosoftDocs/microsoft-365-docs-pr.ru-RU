---
title: Управление запросами лицензий
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: Узнайте, как просмотреть и утвердить или запретить запросы лицензий от пользователей для Microsoft 365 подписки для бизнеса.
ms.date: 06/07/2021
ms.openlocfilehash: 23258d21ebb413c56323aa4dab25cee60baf2be0
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256811"
---
# <a name="manage-license-requests"></a><span data-ttu-id="712bb-103">Управление запросами лицензий</span><span class="sxs-lookup"><span data-stu-id="712bb-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="712bb-104">Сведения в этой статье применимы только к приобретаемой самообслуживаемой продукции.</span><span class="sxs-lookup"><span data-stu-id="712bb-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="712bb-105">Дополнительные дополнительные информации см. в [faq самообслуживной покупки.](../subscriptions/self-service-purchase-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="712bb-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.yml).</span></span>

<span data-ttu-id="712bb-106">Если вы отключите покупки самообслужива в организации, вы можете использовать запросы лицензий для управления процессом запроса лицензии для пользователей.</span><span class="sxs-lookup"><span data-stu-id="712bb-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="712bb-107">Если пользователь пытается сделать самообслуживаемую покупку заблокированного продукта, он может отправить запрос на лицензию вам, администратору. Когда они делают запрос, они могут добавлять имена других пользователей, которым также нужны лицензии для продукта.</span><span class="sxs-lookup"><span data-stu-id="712bb-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="712bb-108">Если вы не позволяете пользователям делать покупки с самообслуживаем, Корпорация Майкрософт не отправляет им маркетинговые сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="712bb-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="712bb-109">Кроме того, если они используют пробную версию продукта, они не видят подсказки для его покупки.</span><span class="sxs-lookup"><span data-stu-id="712bb-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="712bb-110">Дополнительные новости см. в [см. в руб. Управление покупками самообслуживки (Admin).](../subscriptions/manage-self-service-purchases-admins.md)</span><span class="sxs-lookup"><span data-stu-id="712bb-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="712bb-111">Чтобы увидеть и управлять запросами лицензий, администратор использует вкладку **Запросы** на **странице Лицензирование.**</span><span class="sxs-lookup"><span data-stu-id="712bb-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="712bb-112">В списке показаны имя запрашиваемого продукта, имя запрашиваемого лица, запрашивающий лицензию, запрашиваемая дата и состояние запроса.</span><span class="sxs-lookup"><span data-stu-id="712bb-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="712bb-113">Администраторы могут фильтровать список, чтобы показывать ожидающих или завершенных запросов.</span><span class="sxs-lookup"><span data-stu-id="712bb-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="712bb-114">Запросы проводятся в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="712bb-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="712bb-115">Подготовка</span><span class="sxs-lookup"><span data-stu-id="712bb-115">Before you begin</span></span>

<span data-ttu-id="712bb-116">Вы должны быть глобальным администратором для выполнения задач в этой статье.</span><span class="sxs-lookup"><span data-stu-id="712bb-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="712bb-117">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="712bb-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="712bb-118">Использование собственного процесса запроса</span><span class="sxs-lookup"><span data-stu-id="712bb-118">Use your own request process</span></span>

<span data-ttu-id="712bb-119">Если в организации есть собственный процесс запроса, вы можете использовать его вместо этого.</span><span class="sxs-lookup"><span data-stu-id="712bb-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="712bb-120">Создается сообщение, отображаемая пользователям при запросе лицензии.</span><span class="sxs-lookup"><span data-stu-id="712bb-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="712bb-121">Если вы используете собственный процесс запроса, на вкладке **Запросы** не отображаются запросы. Существующие запросы перед добавленным сообщением продолжают отображаться до утверждения или отклонки.</span><span class="sxs-lookup"><span data-stu-id="712bb-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="712bb-122">В центре администрирования перейдите на страницу **Биллинг**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии,</a> а затем выберите вкладку **Запросы.**</span><span class="sxs-lookup"><span data-stu-id="712bb-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="712bb-123">Выберите **Вместо этого используйте существующий процесс запроса.**</span><span class="sxs-lookup"><span data-stu-id="712bb-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="712bb-124">В правой области в поле **Сообщение** введите сообщение, которое пользователи должны видеть при запросе лицензии.</span><span class="sxs-lookup"><span data-stu-id="712bb-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="712bb-125">Если вы хотите также включить ссылку на политику организации или другую документацию, введите URL-адрес в текстовом окне Ссылка на документацию **(необязательный).**</span><span class="sxs-lookup"><span data-stu-id="712bb-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="712bb-126">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="712bb-126">Select **Save**.</span></span>

<span data-ttu-id="712bb-127">Когда вы возвращаетесь в список **Запросов,** вы видите сообщение, которое вы используете свой собственный процесс **запроса лицензии.**</span><span class="sxs-lookup"><span data-stu-id="712bb-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="712bb-128">Чтобы внести изменения в сообщение, отправленное пользователям, выберите Вместо этого используйте **существующий процесс запроса.**</span><span class="sxs-lookup"><span data-stu-id="712bb-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="712bb-129">Прекратить использование собственного процесса запроса</span><span class="sxs-lookup"><span data-stu-id="712bb-129">Stop using your own request process</span></span>

1. <span data-ttu-id="712bb-130">В центре администрирования перейдите на страницу **Биллинг**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии,</a> а затем выберите вкладку **Запросы.**</span><span class="sxs-lookup"><span data-stu-id="712bb-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="712bb-131">Выберите **Вместо этого используйте существующий процесс запроса.**</span><span class="sxs-lookup"><span data-stu-id="712bb-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="712bb-132">В правой области зачистим контрольный ящик **Use my organization's request process.**</span><span class="sxs-lookup"><span data-stu-id="712bb-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="712bb-133">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="712bb-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="712bb-134">Утверждение или отказ в запросе лицензии</span><span class="sxs-lookup"><span data-stu-id="712bb-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="712bb-135">В центре администрирования перейдите на страницу **Биллинг**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии,</a> а затем выберите вкладку **Запросы.**</span><span class="sxs-lookup"><span data-stu-id="712bb-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="712bb-136">Выберите строку, которая содержит запрос, который необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="712bb-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="712bb-137">На правой области показаны сведения о том, какие пользователи хотят получить лицензии на продукт.</span><span class="sxs-lookup"><span data-stu-id="712bb-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="712bb-138">Чтобы запретить весь запрос, выберите **Не** одобряйте, а в диалоговом окне выберите **Не одобряйте**.</span><span class="sxs-lookup"><span data-stu-id="712bb-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="712bb-139">Чтобы отказать некоторым пользователям в запросе, но утвердить других, выберите X по имени пользователей, которые вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="712bb-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="712bb-140">Их имена перемещаются под **Не назначать этим пользователям**.</span><span class="sxs-lookup"><span data-stu-id="712bb-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="712bb-141">Если у вас несколько продуктов, в статье **Выберите** продукт, выберите тот, для чего необходимо назначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="712bb-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="712bb-142">Чтобы запретить пользователям доступ к определенным приложениям и службам, разверните приложения и службы включите или отключите, а затем очистите флажки для тех, которые необходимо исключить.</span><span class="sxs-lookup"><span data-stu-id="712bb-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="712bb-143">В нижней части области введите дополнительное сообщение в текстовом окне.</span><span class="sxs-lookup"><span data-stu-id="712bb-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="712bb-144">По завершению выберите **Утверждение**.</span><span class="sxs-lookup"><span data-stu-id="712bb-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="712bb-145">На правой области показаны сведения о запросе.</span><span class="sxs-lookup"><span data-stu-id="712bb-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="712bb-146">Закрой правую области.</span><span class="sxs-lookup"><span data-stu-id="712bb-146">Close the right pane.</span></span>
    <span data-ttu-id="712bb-147">Пользователи получают сообщение электронной почты, в которое сообщается, что их запрос был утвержден или отклонен.</span><span class="sxs-lookup"><span data-stu-id="712bb-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="712bb-148">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="712bb-148">Related content</span></span>

<span data-ttu-id="712bb-149">[Назначение лицензий пользователям](../../admin/manage/assign-licenses-to-users.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="712bb-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="712bb-150">[Перемещение пользователей в другую подписку](../subscriptions/move-users-different-subscription.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="712bb-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="712bb-151">[Покупка или удаление лицензий подписки](buy-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="712bb-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>
