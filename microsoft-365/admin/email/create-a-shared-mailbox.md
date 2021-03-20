---
title: Создание общего почтового ящика
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Создайте общий почтовый ящик, чтобы позволить сразу нескольким сотрудникам организации читать электронную почту и отвечать на сообщения, отправленные на один адрес.
ms.openlocfilehash: 004473b329b14be9287f249b1d640c3b0803412a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915882"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="6c277-103">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="6c277-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="6c277-104">Если ваша организация использует гибридную среду Exchange, вам следует использовать локальный Центр администрирования Exchange (EAC) для создания общих почтовых ящиков и управления ими.</span><span class="sxs-lookup"><span data-stu-id="6c277-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="6c277-105">См. статью [Создание общих почтовых ящиков в Центре администрирования Exchange](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span><span class="sxs-lookup"><span data-stu-id="6c277-105">See [Create shared mailboxes in the Exchange admin center](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span></span><br><br>
> <span data-ttu-id="6c277-106">Если вы не знаете, нужен ли вам общий почтовый ящик или группа Microsoft 365 для Outlook, см. инструкции в статье [Сравнение групп](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6c277-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="6c277-107">Обратите внимание, что в настоящее время невозможно перенести общий почтовый ящик в группу Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c277-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="6c277-108">Если вам нужна эта возможность, дайте нам знать, [проголосовав здесь](https://go.microsoft.com/fwlink/?linkid=871518).</span><span class="sxs-lookup"><span data-stu-id="6c277-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="6c277-p103">Общие почтовые ящики позволяют группе пользователей отслеживать и отправлять сообщения с общего адреса, например info@contoso.com. Когда пользователь из группы отвечает на сообщение, отправленное на общий почтовый ящик, оно отображается как отправленное с общего почтового ящика, а не от отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="6c277-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="6c277-111">Общие почтовые ящики включают общий календарь.</span><span class="sxs-lookup"><span data-stu-id="6c277-111">Shared mailboxes include a shared calendar.</span></span> <span data-ttu-id="6c277-112">На многих малых предприятиях сотрудники отмечают в общем календаре свои встречи.</span><span class="sxs-lookup"><span data-stu-id="6c277-112">A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments.</span></span> <span data-ttu-id="6c277-113">Например, если посещение клиентов входит в обязанности трех сотрудников, все они могут отмечать свои встречи в общем календаре.</span><span class="sxs-lookup"><span data-stu-id="6c277-113">For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments.</span></span> <span data-ttu-id="6c277-114">Таким образом все будут знать, кто и где находится.</span><span class="sxs-lookup"><span data-stu-id="6c277-114">This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="6c277-115">Перед созданием общего почтового ящика ознакомьтесь со статьей [Сведения об общих почтовых ящиках](about-shared-mailboxes.md) для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="6c277-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="6c277-116">Создание общего почтового ящика и добавление участников</span><span class="sxs-lookup"><span data-stu-id="6c277-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="6c277-117">Войдите с помощью учетной записи глобального администратора Exchange.</span><span class="sxs-lookup"><span data-stu-id="6c277-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="6c277-118">Если появится сообщение "**Вам не предоставлены разрешения на доступ к этой странице или выполнение этого действия**", у вас нет прав администратора.</span><span class="sxs-lookup"><span data-stu-id="6c277-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="6c277-119">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="6c277-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="6c277-120">В [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=848041) откройте страницу **Группы** \> **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="6c277-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="6c277-121">В [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=850627) откройте страницу **Группы** \> **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="6c277-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="6c277-122">На странице **Общие почтовые ящики** нажмите **+ Добавить почтовый ящик**.</span><span class="sxs-lookup"><span data-stu-id="6c277-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="6c277-123">Введите имя для общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="6c277-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="6c277-124">Затем мастер выберет адрес электронной почты, но его можно будет изменить.</span><span class="sxs-lookup"><span data-stu-id="6c277-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Присвойте имя общему почтовому ящику.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="6c277-126">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="6c277-126">Select **Add**.</span></span> <span data-ttu-id="6c277-127">Через несколько минут вы сможете добавить участников.</span><span class="sxs-lookup"><span data-stu-id="6c277-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="6c277-128">В разделе **Дальнейшие действия** щелкните **Добавить участников в этот почтовый ящик**.</span><span class="sxs-lookup"><span data-stu-id="6c277-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="6c277-129">Участники — это люди, которые смогут просматривать входящую почту и исходящие ответы в этом почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="6c277-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Нажмите "Добавить участников"](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="6c277-131">Нажмите кнопку **+ Добавить участников**.</span><span class="sxs-lookup"><span data-stu-id="6c277-131">Select the **+Add members** button.</span></span> <span data-ttu-id="6c277-132">Установите флажки напротив пользователей, которым вы хотите разрешить использовать этот общий почтовый ящик, и нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6c277-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Назначение участников в общий почтовый ящик](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="6c277-134">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6c277-134">Select **Close**.</span></span>

<span data-ttu-id="6c277-135">У вас есть общий почтовый ящик, содержащий общий календарь.</span><span class="sxs-lookup"><span data-stu-id="6c277-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="6c277-136">Теперь перейдите к следующему шагу: блокирование входа для учетной записи общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="6c277-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="which-permissions-should-you-use"></a><span data-ttu-id="6c277-137">Какие разрешения следует использовать?</span><span class="sxs-lookup"><span data-stu-id="6c277-137">Which permissions should you use?</span></span>

<span data-ttu-id="6c277-138">Для общего почтового ящика можно использовать следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="6c277-138">You can use the following permissions with a shared mailbox:</span></span>

- <span data-ttu-id="6c277-139">**Полный доступ**. Разрешение на полный доступ позволяет пользователю открывать общий почтовый ящик и действовать с правами владельца этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="6c277-139">**Full Access**: The Full Access permission lets a user open the shared mailbox and act as the owner of that mailbox.</span></span> <span data-ttu-id="6c277-140">Получив доступ к общему почтовому ящику, пользователь может создавать элементы календаря; читать, просматривать, удалять и изменять сообщения электронной почты; создавать задачи и контакты в календаре.</span><span class="sxs-lookup"><span data-stu-id="6c277-140">After accessing the shared mailbox, a user can create calendar items, read, view, delete, and change email messages, and create tasks and calendar contacts.</span></span> <span data-ttu-id="6c277-141">Тем не менее, пользователь с разрешением на полный доступ не может отправлять электронную почту из общего почтового ящика, если у него нет также разрешения "Отправить как" или "Отправить от имени".</span><span class="sxs-lookup"><span data-stu-id="6c277-141">However, a user with Full Access permission can't send email from the shared mailbox unless they also have Send As or Send on Behalf permission.</span></span>

- <span data-ttu-id="6c277-142">**Отправить как**. Разрешение "Отправить как" позволяет пользователю олицетворять общий почтовый ящик при отправке почты.</span><span class="sxs-lookup"><span data-stu-id="6c277-142">**Send As**: The Send As permission lets a user impersonate the shared mailbox when sending mail.</span></span> <span data-ttu-id="6c277-143">Например, если Катерина войдет в общий почтовый ящик отдела маркетинга и отправит из него сообщение, отправителем будет считаться отдел маркетинга.</span><span class="sxs-lookup"><span data-stu-id="6c277-143">For example, if Katerina logs into the shared mailbox Marketing Department and sends an email, it will look like the Marketing Department sent the email.</span></span>

- <span data-ttu-id="6c277-144">**Отправить от имени.** Разрешение "Отправить от имени" позволяет пользователю отправлять электронную почту от имени общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="6c277-144">**Send on Behalf**: The Send on Behalf permission lets a user send email on behalf of the shared mailbox.</span></span> <span data-ttu-id="6c277-145">Например, если Алексей войдет в общий почтовый ящик приемной, здание 32, и отправит из него сообщение, отправителем будет считаться Алексей от имени приемной, здание 32.</span><span class="sxs-lookup"><span data-stu-id="6c277-145">For example, if John logs into the shared mailbox Reception Building 32 and sends an email, it will look like the mail was sent by "John on behalf of Reception Building 32".</span></span> <span data-ttu-id="6c277-146">Разрешение "Отправить от имени" невозможно предоставить с помощью Центра администрирования Exchange. Для этого необходимо использовать командлет **Set-Mailbox** с параметром _GrantSendonBehalf_.</span><span class="sxs-lookup"><span data-stu-id="6c277-146">You can't use the EAC to grant Send on Behalf permissions, you must use the **Set-Mailbox** cmdlet with the _GrantSendonBehalf_ parameter.</span></span>

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a><span data-ttu-id="6c277-147">Изменение делегирования общего почтового ящика с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="6c277-147">Use the EAC to edit shared mailbox delegation</span></span>

1. <span data-ttu-id="6c277-148">В Центре администрирования Exchange выберите **Получатели** \> **Общий**.</span><span class="sxs-lookup"><span data-stu-id="6c277-148">In the EAC, go to **Recipients** \> **Shared**.</span></span> <span data-ttu-id="6c277-149">Выберите общий почтовый ящик и нажмите **Изменить** ![Значок "Изменить"](../../media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="6c277-149">Select the shared mailbox, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="6c277-150">Выберите **Делегирование почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="6c277-150">Select **Mailbox delegation**.</span></span>

3. <span data-ttu-id="6c277-151">Чтобы предоставить или удалить разрешение на полный доступ или "Отправить как", нажмите **Добавить** ![Значок "Добавить"](../../media/ITPro-EAC-AddIcon.png) или **Удалить** ![Значок "Удалить"](../../media/ITPro-EAC-RemoveIcon.gif) и выберите соответствующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="6c277-151">To grant or remove Full Access and Send As permissions, select **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) and then select the users you want to grant permissions to.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6c277-p115">Разрешение "Полный доступ" позволяет пользователю открывать почтовый ящик, а также создавать из изменять в нем элементы. Разрешение "Отправлять как" позволяет всем пользователям, кроме владельца почтового ящика, отправлять электронную почту из этого общего почтового ящика. Для эффективной работы с общим почтовым ящиком необходимы оба разрешения.</span><span class="sxs-lookup"><span data-stu-id="6c277-p115">The Full Access permission allows a user to open the mailbox as well as create and modify items in it. The Send As permission allows anyone other than the mailbox owner to send email from this shared mailbox. Both permissions are required for successful shared mailbox operation.</span></span>

4. <span data-ttu-id="6c277-155">Нажмите кнопку **Сохранить**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="6c277-155">Select **Save** to save your changes.</span></span>


## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="6c277-156">Блокирование входа для учетной записи общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="6c277-156">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="6c277-157">У каждого общего почтового ящика есть соответствующая учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="6c277-157">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="6c277-158">Вы заметили, что вам не потребовалось указывать пароль при создании общего почтового ящика?</span><span class="sxs-lookup"><span data-stu-id="6c277-158">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="6c277-159">У этой учетной записи есть пароль, но он создается системой (неизвестен).</span><span class="sxs-lookup"><span data-stu-id="6c277-159">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="6c277-160">Вы не должны использовать учетную запись для входа в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="6c277-160">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="6c277-161">Но что если администратор просто сбросит пароль учетной записи общего почтового ящика?</span><span class="sxs-lookup"><span data-stu-id="6c277-161">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="6c277-162">Или злоумышленник получит доступ к учетным данным общего почтового ящика?</span><span class="sxs-lookup"><span data-stu-id="6c277-162">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="6c277-163">Это позволило бы с помощью учетной записи пользователя выполнять вход в общий почтовый ящик и отправлять электронную почту.</span><span class="sxs-lookup"><span data-stu-id="6c277-163">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="6c277-164">Чтобы не допустить этого, требуется заблокировать вход для учетной записи, связанной с общим почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="6c277-164">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6c277-165">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="6c277-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6c277-166">В списке учетных записей пользователей найдите учетную запись общего почтового ящика (например, примените фильтр **Нелицензированные пользователи**).</span><span class="sxs-lookup"><span data-stu-id="6c277-166">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="6c277-167">Выберите пользователя, чтобы открыть область свойств, и щелкните значок **Заблокировать этого пользователя** ![Снимок экрана: значок "Заблокировать этого пользователя"](../../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="6c277-167">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="6c277-168">**Примечание**. Если учетная запись уже заблокирована, вверху отобразится надпись **Вход заблокирован**, а для значка выводится текст **Разблокировать этого пользователя**.</span><span class="sxs-lookup"><span data-stu-id="6c277-168">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="6c277-169">В области **Заблокировать этого пользователя?** выберите **Запретить этому пользователю вход** и нажмите **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="6c277-169">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6c277-170">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="6c277-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6c277-171">В списке учетных записей пользователей найдите учетную запись общего почтового ящика (например, выберите представление **Нелицензированные пользователи**) и выберите эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="6c277-171">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="6c277-172">Во всплывающей области свойств нажмите **Заблокировать вход**.</span><span class="sxs-lookup"><span data-stu-id="6c277-172">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="6c277-173">**Примечание.** Если учетная запись уже заблокирована, на кнопке отображается текст **Разблокировать вход**.</span><span class="sxs-lookup"><span data-stu-id="6c277-173">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="6c277-174">Во всплывающей области **Изменение состояния входа** проверьте, что установлен флажок "Запретить пользователю вход", нажмите **Сохранить** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6c277-174">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6c277-175">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="6c277-175">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6c277-176">В списке учетных записей пользователей найдите учетную запись общего почтового ящика (например, выберите представление **Нелицензированные пользователи**) и выберите эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="6c277-176">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="6c277-177">Во всплывающей области свойств нажмите **Заблокировать вход**.</span><span class="sxs-lookup"><span data-stu-id="6c277-177">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="6c277-178">**Примечание.** Если учетная запись уже заблокирована, на кнопке отображается текст **Разблокировать вход**.</span><span class="sxs-lookup"><span data-stu-id="6c277-178">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="6c277-179">Во всплывающей области **Изменение состояния входа** проверьте, что установлен флажок "Запретить пользователю вход", нажмите **Сохранить** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6c277-179">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="6c277-180">Инструкции по блокированию входа для учетных записей с помощью Azure AD PowerShell (в том числе для нескольких учетных записей одновременно) см. в статье [Блокировка учетных записей пользователей с помощью PowerShell в Office 365](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6c277-180">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="6c277-181">Добавление общего почтового ящика в Outlook</span><span class="sxs-lookup"><span data-stu-id="6c277-181">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="6c277-182">Если в вашей организации включена функция AutoMapping (чаще всего она включена по умолчанию), общий почтовый ящик появится у пользователей в Outlook автоматически после закрытия и перезапуска приложения.</span><span class="sxs-lookup"><span data-stu-id="6c277-182">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="6c277-183">Функция AutoMapping применяется к почтовому ящику пользователя, а не к общему почтовому ящику.  </span><span class="sxs-lookup"><span data-stu-id="6c277-183">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="6c277-184">Это означает, что при попытке использовать группу безопасности для управления доступом к общему почтовому ящику функция AutoMapping работать не будет.</span><span class="sxs-lookup"><span data-stu-id="6c277-184">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="6c277-185">Таким образом, чтобы работала функция AutoMapping, необходимо явно назначить разрешения.</span><span class="sxs-lookup"><span data-stu-id="6c277-185">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="6c277-186">Функция AutoMapping включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6c277-186">Automapping is on by default.</span></span> <span data-ttu-id="6c277-187">Сведения о ее отключении см. в статье [Удаление функции AutoMapping для общего почтового ящика](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="6c277-187">To learn how to turn it off, see [Remove automapping for a shared mailbox](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="6c277-188">Дополнительные сведения об общих почтовых ящиках в Outlook:</span><span class="sxs-lookup"><span data-stu-id="6c277-188">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="6c277-189"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Открытие и использование общего почтового ящика в Outlook</a></span><span class="sxs-lookup"><span data-stu-id="6c277-189"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="6c277-190"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Добавление общего почтового ящика в Outlook в Интернете</a></span><span class="sxs-lookup"><span data-stu-id="6c277-190"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="6c277-191"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Добавление общего почтового ящика в Outlook Mobile</a></span><span class="sxs-lookup"><span data-stu-id="6c277-191"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="6c277-192"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Открытие общей папки или почтового ящика в Outlook для Mac</a></span><span class="sxs-lookup"><span data-stu-id="6c277-192"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="6c277-193"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Добавление правил в общий почтовый ящик</a></span><span class="sxs-lookup"><span data-stu-id="6c277-193"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="6c277-194">Использование общего почтового ящика на мобильных устройствах (смартфонах и планшетах)</span><span class="sxs-lookup"><span data-stu-id="6c277-194">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="6c277-195">Вы можете получить доступ к общему почтовому ящику на мобильном устройстве двумя способами:</span><span class="sxs-lookup"><span data-stu-id="6c277-195">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="6c277-196">Добавьте общий почтовый ящик в <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">приложении Outlook для iOS</a> или <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">мобильном приложении Outlook для Android</a>.</span><span class="sxs-lookup"><span data-stu-id="6c277-196">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="6c277-197">Инструкции см. в статье <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Добавление общего почтового ящика в Outlook Mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="6c277-197">For instructions, see <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="6c277-198">Откройте браузер, выполните вход и перейдите в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="6c277-198">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="6c277-199">Через приложение Outlook в Интернете вы можете открыть общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="6c277-199">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="6c277-200">Инструкции см. в статье <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Добавление общего почтового ящика в Outlook в Интернете</a>.</span><span class="sxs-lookup"><span data-stu-id="6c277-200">For instructions, see <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6c277-201">Общий почтовый ящик можно добавить только в приложение Outlook для iOS или мобильное приложение Outlook для Android.</span><span class="sxs-lookup"><span data-stu-id="6c277-201">Shared mailbox can only be added to Outlook for iOS app or the Outlook for Android mobile app</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="6c277-202">Использование общего календаря</span><span class="sxs-lookup"><span data-stu-id="6c277-202">Use the shared calendar</span></span>

<span data-ttu-id="6c277-203">При создании общего почтового ящика автоматически создается общий календарь.</span><span class="sxs-lookup"><span data-stu-id="6c277-203">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="6c277-204">Для отслеживания встреч и местонахождения пользователей предпочтительнее использовать календарь общего почтового ящика, а не календарь SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6c277-204">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="6c277-205">Общий календарь интегрирован с Outlook и работать с ним проще, чем с календарем SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6c277-205">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="6c277-206">В приложении Outlook перейдите в представление календаря и выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="6c277-206">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="6c277-207">Если вы добавите встречи, они будут видны всем участникам общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="6c277-207">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="6c277-208">Любой участник общего почтового ящика может создавать, просматривать и управлять встречами в календаре так же, как личными встречами.</span><span class="sxs-lookup"><span data-stu-id="6c277-208">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="6c277-209">Изменения общего календаря будут видны всем участникам общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="6c277-209">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6c277-210">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="6c277-210">Related articles</span></span>

[<span data-ttu-id="6c277-211">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="6c277-211">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="6c277-212">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="6c277-212">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="6c277-213">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="6c277-213">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="6c277-214">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="6c277-214">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="6c277-215">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="6c277-215">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)