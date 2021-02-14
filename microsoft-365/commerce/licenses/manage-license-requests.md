---
title: Управление запросами лицензий
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
description: Узнайте, как просмотреть и утвердить или запретить запросы лицензий от пользователей для подписки на Microsoft 365 для бизнеса.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597662"
---
# <a name="manage-license-requests"></a><span data-ttu-id="9d5cf-103">Управление запросами лицензий</span><span class="sxs-lookup"><span data-stu-id="9d5cf-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="9d5cf-104">Сведения в этой статье применимы только к самостоятельно приобретенным продуктам.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="9d5cf-105">Чтобы узнать больше, [см. самостоятельное приобретение задаваемой информации.](../subscriptions/self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="9d5cf-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="9d5cf-106">Если вы отключите самостоятельные покупки в организации, вы можете использовать запросы лицензий для управления процессом запроса лицензии для пользователей.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="9d5cf-107">Когда пользователь пытается самостоятельно приобрести заблокированный продукт, он может отправить запрос на лицензию вам, администратору. При запросе они могут добавлять имена других пользователей, которым также требуются лицензии для продукта.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="9d5cf-108">Если вы блокируете самостоятельное приобретение пользователями, корпорация Майкрософт не отправляет им маркетинговые сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="9d5cf-109">Кроме того, если они используют пробную версию продукта, они не видят запросы на ее покупку.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="9d5cf-110">Дополнительные см. в [подразглавии "Управление самостоятельными покупками (администрирование)".](../subscriptions/manage-self-service-purchases-admins.md)</span><span class="sxs-lookup"><span data-stu-id="9d5cf-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="9d5cf-111">Чтобы увидеть запросы лицензий и  управлять ими, администратор использует вкладку "Запросы" на **странице "Лицензирование".**</span><span class="sxs-lookup"><span data-stu-id="9d5cf-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="9d5cf-112">В списке показано имя запрашиваемого продукта, имя человека, запрашивающий лицензию, дата запроса и состояние запроса.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="9d5cf-113">Администраторы могут отфильтровать список, чтобы показать ожидающих или завершенных запросов.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="9d5cf-114">Запросы удерживаются в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9d5cf-115">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="9d5cf-115">Before you begin</span></span>

<span data-ttu-id="9d5cf-116">Для выполнения задач, выполняемых в этой статье, необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="9d5cf-117">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9d5cf-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="9d5cf-118">Использование собственного процесса запроса</span><span class="sxs-lookup"><span data-stu-id="9d5cf-118">Use your own request process</span></span>

<span data-ttu-id="9d5cf-119">Если у вашей организации есть собственный процесс запроса, вы можете использовать его.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="9d5cf-120">Вы создаете сообщение, которое отображается для пользователей при запросе лицензии.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d5cf-121">Если вы используете собственный процесс запроса, запросы не отображаются на вкладке **"Запросы".** Существующие запросы до того, как вы добавили сообщение, будут отображаться до тех пор, пока вы не утвердите или не отклоите их.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="9d5cf-122">В Центре администрирования перейдите на страницу **"Лицензии** на выставление счета" и выберите  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> вкладку **"Запросы".**</span><span class="sxs-lookup"><span data-stu-id="9d5cf-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="9d5cf-123">Выберите **"Использовать существующий процесс запроса".**</span><span class="sxs-lookup"><span data-stu-id="9d5cf-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="9d5cf-124">В правой области в  поле "Сообщение" введите сообщение, которое пользователи должны видеть при запросе лицензии.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="9d5cf-125">Если вы хотите также включить ссылку на политику организации или другую документацию, введите URL-адрес в текстовом поле "Ссылка на документацию" **(необязательно).**</span><span class="sxs-lookup"><span data-stu-id="9d5cf-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="9d5cf-126">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-126">Select **Save**.</span></span>

<span data-ttu-id="9d5cf-127">When you return to the **Requests** list, you see the message **You're using your own license request process.**</span><span class="sxs-lookup"><span data-stu-id="9d5cf-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="9d5cf-128">Чтобы внести изменения в сообщение, отправленное пользователям, выберите **"Использовать существующий процесс запроса".**</span><span class="sxs-lookup"><span data-stu-id="9d5cf-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="9d5cf-129">Прекратить использование собственного процесса запроса</span><span class="sxs-lookup"><span data-stu-id="9d5cf-129">Stop using your own request process</span></span>

1. <span data-ttu-id="9d5cf-130">В Центре администрирования перейдите на страницу **"Лицензии** на выставление счета" и выберите  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> вкладку **"Запросы".**</span><span class="sxs-lookup"><span data-stu-id="9d5cf-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="9d5cf-131">Выберите **"Использовать существующий процесс запроса".**</span><span class="sxs-lookup"><span data-stu-id="9d5cf-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="9d5cf-132">В правой области с  помощью этого справа обнулите окно запроса организации.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="9d5cf-133">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="9d5cf-134">Утверждение или отказ в запросе лицензии</span><span class="sxs-lookup"><span data-stu-id="9d5cf-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="9d5cf-135">В Центре администрирования перейдите на страницу **"Лицензии** на выставление счета" и выберите  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> вкладку **"Запросы".**</span><span class="sxs-lookup"><span data-stu-id="9d5cf-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="9d5cf-136">Выберите строку, содержаную запрос, который необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="9d5cf-137">На правой области показаны сведения о том, какие пользователи хотят получить лицензии на продукт.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="9d5cf-138">Чтобы отопросить весь запрос, **выберите**"Не утверждать" и в диалоговом окне выберите **"Не утверждать".**</span><span class="sxs-lookup"><span data-stu-id="9d5cf-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="9d5cf-139">Чтобы отопросить запрос у одних пользователей, но утвердить других, выберите X по имени пользователей, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="9d5cf-140">Их имена перемещаются в **списке "Не назначать этим пользователям".**</span><span class="sxs-lookup"><span data-stu-id="9d5cf-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="9d5cf-141">Если у вас несколько продуктов, в области "Выбор продукта" выберите **тот,** для который вы хотите назначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="9d5cf-142">Чтобы запретить пользователям доступ к определенным приложениям и службам, разверните "Включить и отключить" приложения и службы, а затем снять флажки для тех, которые нужно исключить.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="9d5cf-143">В нижней части области введите необязательное сообщение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="9d5cf-144">По завершению выберите **"Утвердить".**</span><span class="sxs-lookup"><span data-stu-id="9d5cf-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="9d5cf-145">На правой области показаны сведения о запросе.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="9d5cf-146">Закроем правую области.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-146">Close the right pane.</span></span>
    <span data-ttu-id="9d5cf-147">Пользователи получают по электронной почте сообщение об одобрении или отклонении запроса.</span><span class="sxs-lookup"><span data-stu-id="9d5cf-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="9d5cf-148">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="9d5cf-148">Related content</span></span>

<span data-ttu-id="9d5cf-149">[Назначение лицензий пользователям](../../admin/manage/assign-licenses-to-users.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="9d5cf-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="9d5cf-150">[Перемещение пользователей в другую подписку](../subscriptions/move-users-different-subscription.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="9d5cf-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="9d5cf-151">[Покупка и удаление лицензий на подписку](buy-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="9d5cf-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>