---
title: Управление уведомлениями о выставлении счетов и вложениями счетов-фактур
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: prkalid, guyb
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
search.appverid:
- MET150
description: Узнайте, как управлять тем, кто получает сообщения уведомлений о выставлении счетов и вложения счетов.
ms.date: 03/17/2021
ms.openlocfilehash: 75c75175930434619a01886b1096757bf04111c5
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888365"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="2ae5f-103">Управление уведомлениями о выставлении счетов и вложениями счетов-фактур</span><span class="sxs-lookup"><span data-stu-id="2ae5f-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="2ae5f-104">Страница **уведомлений о выставлении счета** позволяет управлять тем, кто получает электронные уведомления о выставлении счета для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="2ae5f-105">На странице также предоставляется возможность получения счетов-фактур организации [в виде вложений электронной почты.](#receive-your-organizations-invoices-as-email-attachments)</span><span class="sxs-lookup"><span data-stu-id="2ae5f-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2ae5f-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="2ae5f-106">Before you begin</span></span>

<span data-ttu-id="2ae5f-107">Вы должны быть глобальным администратором для действий, описанных в этой статье.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="2ae5f-108">Администраторы биллинга могут внести некоторые из этих изменений, как отмечено в разделах ниже.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="2ae5f-109">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2ae5f-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="2ae5f-110">Изменение языка, на который вы получаете электронную почту</span><span class="sxs-lookup"><span data-stu-id="2ae5f-110">Change the language you receive email in</span></span>

> [!NOTE]
> <span data-ttu-id="2ae5f-111">Администраторы биллинга также могут делать шаги в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-111">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="2ae5f-112">Сообщения уведомлений о выставлении счета отправляются на предпочтительном языке организации.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-112">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="2ae5f-113">Чтобы изменить предпочитаемый язык, используйте следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-113">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="2ae5f-114">В центре Microsoft 365 администрирования перейдите на **страницу** уведомлений о выставлении  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">биллинга.</a></span><span class="sxs-lookup"><span data-stu-id="2ae5f-114">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="2ae5f-115">В разделе **Параметры уведомлений** о выставлении счета выберите **параметры редактирования уведомлений.**</span><span class="sxs-lookup"><span data-stu-id="2ae5f-115">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="2ae5f-116">В области **параметров** уведомлений о выставлении счета в **языке Preferred выберите** язык, который вы хотите использовать, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-116">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="2ae5f-117">Изменение получения уведомлений о выставлении счета</span><span class="sxs-lookup"><span data-stu-id="2ae5f-117">Change who receives billing notifications</span></span>

<span data-ttu-id="2ae5f-118">Уведомления о выставлении счета организации отправляются на основной и альтернативный адрес электронной почты каждого администратора Global и Billing. Чтобы изменить роль администратора Global или Billing, используйте следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-118">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="2ae5f-119">Назначение ролей администратора с помощью страницы уведомлений о выставлении счета</span><span class="sxs-lookup"><span data-stu-id="2ae5f-119">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="2ae5f-120">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Уведомления о выставлении счетов</a>.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="2ae5f-121">В разделе **Администраторы, получающие уведомления** о  выставлении счета, выберите ссылку администратора биллинга или **глобального** администратора в тексте описания.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-121">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="2ae5f-122">В правой области на вкладке **Назначены администраторы** выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-122">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="2ae5f-123">В области **Добавить администраторов** введите имя или имя пользователя, а затем выберите пользователя из списка предложений.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-123">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="2ae5f-124">Добавьте несколько пользователей, пока не будет сделано.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-124">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="2ae5f-125">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-125">Select **Save**.</span></span> <span data-ttu-id="2ae5f-126">Пользователь добавляется в список назначенных администраторов.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-126">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="2ae5f-127">Удаление ролей администратора с помощью страницы уведомлений о выставлении счета</span><span class="sxs-lookup"><span data-stu-id="2ae5f-127">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="2ae5f-128">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Уведомления о выставлении счетов</a>.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="2ae5f-129">В разделе **Администраторы, получающие уведомления** о  выставлении счета, выберите ссылку администратора биллинга или **глобального** администратора в тексте описания.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-129">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="2ae5f-130">В правой области на вкладке **Назначены** администраторы выберите пользователей, чтобы удалить из роли, а затем **выберите Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-130">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="2ae5f-131">В поле подтверждения выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-131">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="2ae5f-132">Пользователь удаляется из списка назначенного администратора.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-132">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="2ae5f-133">Изменение адресов электронной почты для администраторов</span><span class="sxs-lookup"><span data-stu-id="2ae5f-133">Change the email addresses for admins</span></span>

<span data-ttu-id="2ae5f-134">Чтобы изменить основной и альтернативный адрес электронной почты других администраторов в организации, используйте следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-134">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="2ae5f-135">Администраторы биллинга могут изменять собственные основные и альтернативные адреса электронной почты, но не для других администраторов.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-135">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="2ae5f-136">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Уведомления о выставлении счетов</a>.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-136">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="2ae5f-137">В разделе **Администраторы, получающие уведомления о выставлении счета,** выберите имя.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-137">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="2ae5f-138">В правой области добавьте или обновите основной и альтернативный адрес электронной почты по мере необходимости, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-138">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="2ae5f-139">Изменение контактной электронной почты организации</span><span class="sxs-lookup"><span data-stu-id="2ae5f-139">Change your organization's contact email</span></span>

<span data-ttu-id="2ae5f-140">Помимо администраторов global и Billing мы отправляем уведомления о выставлении счета на контактный адрес электронной почты организации.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-140">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="2ae5f-141">Чтобы изменить адрес электронной почты, используйте следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-141">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="2ae5f-142">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Уведомления о выставлении счетов</a>.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-142">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="2ae5f-143">В **соответствии с контактом Организации, получающие уведомления о** выставлении счета, выберите контакт организации.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-143">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="2ae5f-144">В правой области введите адрес электронной почты, который необходимо использовать, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-144">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="2ae5f-145">Получение счетов-фактур организации в виде вложений электронной почты</span><span class="sxs-lookup"><span data-stu-id="2ae5f-145">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="2ae5f-146">Администраторы биллинга также могут делать шаги в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-146">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="2ae5f-147">Вы можете иметь копию счета-фактуры организации, присоединенную в виде PDF-файла, к электронным письмам уведомлений о выставлении счетов, когда будет готов новый счет.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-147">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="2ae5f-148">Используйте следующие действия для получения счетов-фактур в качестве вложений.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-148">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="2ae5f-149">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Уведомления о выставлении счетов</a>.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-149">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="2ae5f-150">В **настройках уведомлений о выставлении счета** выберите **параметры редактирования уведомлений.**</span><span class="sxs-lookup"><span data-stu-id="2ae5f-150">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="2ae5f-151">В области **параметров** уведомлений о выставлении счетов в статье **Прикрепите PDF** к электронной почте-фактуре, проверьте почтовый ящик, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-151">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="2ae5f-152">Чтобы в любое время перестать получать вложение накладной, выполните действия, которые были выше, и на шаге 3 выполните очистку pdf-адреса к почтовому ящику электронной почты накладных. </span><span class="sxs-lookup"><span data-stu-id="2ae5f-152">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="2ae5f-153">Что делать, если у меня есть профиль вы выставления счета?</span><span class="sxs-lookup"><span data-stu-id="2ae5f-153">What if I have a billing profile?</span></span>

<span data-ttu-id="2ae5f-154">Если у вас есть профиль биллинга, некоторые действия, описанные в этой статье, могут немного отличаться для некоторых подписок.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-154">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="2ae5f-155">В этом разделе описаны эти различия.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-155">This section describes those differences.</span></span> [<span data-ttu-id="2ae5f-156">Как узнать, есть ли у меня профиль вы выставления счета?</span><span class="sxs-lookup"><span data-stu-id="2ae5f-156">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="2ae5f-157">Кто получает уведомления о выставлении счета?</span><span class="sxs-lookup"><span data-stu-id="2ae5f-157">Who receives Billing notifications?</span></span>

<span data-ttu-id="2ae5f-158">Сообщения уведомлений о выставлении счета отправляются на основные и альтернативные адреса электронной почты для пользователей, которым назначена одна из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="2ae5f-158">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="2ae5f-159">Владелец профилей биллинга</span><span class="sxs-lookup"><span data-stu-id="2ae5f-159">Billing profile owner</span></span>
- <span data-ttu-id="2ae5f-160">Вкладчик профилей биллинга</span><span class="sxs-lookup"><span data-stu-id="2ae5f-160">Billing profile contributor</span></span>
- <span data-ttu-id="2ae5f-161">Менеджер по счетам</span><span class="sxs-lookup"><span data-stu-id="2ae5f-161">Invoice manager</span></span>

<span data-ttu-id="2ae5f-162">Дополнительные данные о выставлении ролей профилей и управлении ими см. в странице [Understand Microsoft Customer Agreement administrative roles in Azure.](/azure/cost-management-billing/manage/understand-mca-roles)</span><span class="sxs-lookup"><span data-stu-id="2ae5f-162">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="2ae5f-163">Чтобы изменить тех, кто получает уведомления о выставлении счета вашей организации, используйте следующие действия, чтобы изменить роли, замещенные пользователями.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-163">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="2ae5f-164">В центре администрирования перейдите на **страницу** Счетов &  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">платежей.</a></span><span class="sxs-lookup"><span data-stu-id="2ae5f-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="2ae5f-165">На **вкладке профилей биллинга** выберите профиль биллинга.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-165">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="2ae5f-166">В разделе **Роли профилей** биллинга назначьте или удалите роли для владельца профилей биллинга, вкладчика профилей биллинга **или** **диспетчера счетов.**</span><span class="sxs-lookup"><span data-stu-id="2ae5f-166">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="2ae5f-167">Получение счетов в виде вложений электронной почты</span><span class="sxs-lookup"><span data-stu-id="2ae5f-167">Receive invoices as email attachments</span></span>

<span data-ttu-id="2ae5f-168">Чтобы получать счета в виде вложений в уведомления о выставлении счетов, используйте следующие действия, чтобы включить этот параметр для определенного профиля выставления счетов.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-168">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="2ae5f-169">В центре администрирования перейдите на **страницу** Счетов &  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">платежей.</a></span><span class="sxs-lookup"><span data-stu-id="2ae5f-169">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="2ae5f-170">Выберите **вкладку Профилей Биллинга,** а затем выберите профиль выкладки из списка.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-170">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="2ae5f-171">На странице сведения о профиле выставления счетов в статье **Get invoices in email attachments** switch the toggle to **On**.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-171">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="2ae5f-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="2ae5f-172">Related content</span></span>

<span data-ttu-id="2ae5f-173">[Просмотр счета](view-your-bill-or-invoice.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="2ae5f-173">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="2ae5f-174">[Сведения о выставлении Microsoft 365 для бизнеса в Мексике](/microsoft-365/commerce/billing-and-payments/mexico-billing-info) (статья) </span><span class="sxs-lookup"><span data-stu-id="2ae5f-174">[Billing information for Microsoft 365 for business in Mexico](/microsoft-365/commerce/billing-and-payments/mexico-billing-info) (article) </span></span>\
<span data-ttu-id="2ae5f-175">[Понимание счета или](understand-your-invoice2.md) счета Microsoft 365 для бизнеса (статья)</span><span class="sxs-lookup"><span data-stu-id="2ae5f-175">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="2ae5f-176">[Добавление пользователей и назначение лицензий](../../admin/add-users/add-users.md) одновременно (статья)</span><span class="sxs-lookup"><span data-stu-id="2ae5f-176">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>
