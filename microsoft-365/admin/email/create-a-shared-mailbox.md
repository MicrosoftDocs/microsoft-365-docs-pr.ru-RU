---
title: Создание общего почтового ящика
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Создайте общий почтовый ящик, чтобы позволить сразу нескольким сотрудникам организации читать электронную почту и отвечать на сообщения, отправленные на один адрес.
ms.openlocfilehash: aac4966efca3dabc0edac1ceada96d2238cb266f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400104"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="0d98e-103">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="0d98e-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="0d98e-104">Если ваша организация использует гибридную среду Exchange, вам следует использовать локальный Центр администрирования Exchange (EAC) для создания общих почтовых ящиков и управления ими.</span><span class="sxs-lookup"><span data-stu-id="0d98e-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="0d98e-105">См. статью [Создание общих почтовых ящиков в Центре администрирования Exchange](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span><span class="sxs-lookup"><span data-stu-id="0d98e-105">See [Create shared mailboxes in the Exchange admin center](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span></span><br><br>
> <span data-ttu-id="0d98e-106">Если вы не знаете, нужен ли вам общий почтовый ящик или группа Microsoft 365 для Outlook, см. инструкции в статье [Сравнение групп](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0d98e-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="0d98e-107">Обратите внимание, что в настоящее время невозможно перенести общий почтовый ящик в группу Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d98e-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="0d98e-108">Если вам нужна эта возможность, дайте нам знать, [проголосовав здесь](https://go.microsoft.com/fwlink/?linkid=871518).</span><span class="sxs-lookup"><span data-stu-id="0d98e-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="0d98e-p103">Общие почтовые ящики позволяют группе пользователей отслеживать и отправлять сообщения с общего адреса, например info@contoso.com. Когда пользователь из группы отвечает на сообщение, отправленное на общий почтовый ящик, оно отображается как отправленное с общего почтового ящика, а не от отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="0d98e-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="0d98e-111">Общие почтовые ящики включают общий календарь.</span><span class="sxs-lookup"><span data-stu-id="0d98e-111">Shared mailboxes include a shared calendar.</span></span> <span data-ttu-id="0d98e-112">На многих малых предприятиях сотрудники отмечают в общем календаре свои встречи.</span><span class="sxs-lookup"><span data-stu-id="0d98e-112">A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments.</span></span> <span data-ttu-id="0d98e-113">Например, если посещение клиентов входит в обязанности трех сотрудников, все они могут отмечать свои встречи в общем календаре.</span><span class="sxs-lookup"><span data-stu-id="0d98e-113">For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments.</span></span> <span data-ttu-id="0d98e-114">Таким образом все будут знать, кто и где находится.</span><span class="sxs-lookup"><span data-stu-id="0d98e-114">This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="0d98e-115">Перед созданием общего почтового ящика ознакомьтесь со статьей [Сведения об общих почтовых ящиках](about-shared-mailboxes.md) для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="0d98e-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="0d98e-116">Создание общего почтового ящика и добавление участников</span><span class="sxs-lookup"><span data-stu-id="0d98e-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="0d98e-117">Войдите с помощью учетной записи глобального администратора Exchange.</span><span class="sxs-lookup"><span data-stu-id="0d98e-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="0d98e-118">Если появится сообщение "**Вам не предоставлены разрешения на доступ к этой странице или выполнение этого действия**", у вас нет прав администратора.</span><span class="sxs-lookup"><span data-stu-id="0d98e-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="0d98e-119">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="0d98e-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="0d98e-120">В [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=848041) откройте страницу **Группы** \> **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="0d98e-121">В [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=850627) откройте страницу **Группы** \> **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="0d98e-122">На странице **Общие почтовые ящики** нажмите **+ Добавить почтовый ящик**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="0d98e-123">Введите имя для общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="0d98e-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="0d98e-124">Затем мастер выберет адрес электронной почты, но его можно будет изменить.</span><span class="sxs-lookup"><span data-stu-id="0d98e-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Присвойте имя общему почтовому ящику.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="0d98e-126">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-126">Select **Add**.</span></span> <span data-ttu-id="0d98e-127">Через несколько минут вы сможете добавить участников.</span><span class="sxs-lookup"><span data-stu-id="0d98e-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="0d98e-128">В разделе **Дальнейшие действия** щелкните **Добавить участников в этот почтовый ящик**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="0d98e-129">Участники — это люди, которые смогут просматривать входящую почту и исходящие ответы в этом почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="0d98e-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Нажмите "Добавить участников"](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="0d98e-131">Нажмите кнопку **+ Добавить участников**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-131">Select the **+Add members** button.</span></span> <span data-ttu-id="0d98e-132">Установите флажки напротив пользователей, которым вы хотите разрешить использовать этот общий почтовый ящик, и нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Назначение участников в общий почтовый ящик](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="0d98e-134">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-134">Select **Close**.</span></span>

<span data-ttu-id="0d98e-135">У вас есть общий почтовый ящик, содержащий общий календарь.</span><span class="sxs-lookup"><span data-stu-id="0d98e-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="0d98e-136">Теперь перейдите к следующему шагу: блокирование входа для учетной записи общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="0d98e-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="0d98e-137">Блокирование входа для учетной записи общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="0d98e-137">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="0d98e-138">У каждого общего почтового ящика есть соответствующая учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="0d98e-138">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="0d98e-139">Вы заметили, что вам не потребовалось указывать пароль при создании общего почтового ящика?</span><span class="sxs-lookup"><span data-stu-id="0d98e-139">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="0d98e-140">У этой учетной записи есть пароль, но он создается системой (неизвестен).</span><span class="sxs-lookup"><span data-stu-id="0d98e-140">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="0d98e-141">Вы не должны использовать учетную запись для входа в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0d98e-141">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="0d98e-142">Но что если администратор просто сбросит пароль учетной записи общего почтового ящика?</span><span class="sxs-lookup"><span data-stu-id="0d98e-142">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="0d98e-143">Или злоумышленник получит доступ к учетным данным общего почтового ящика?</span><span class="sxs-lookup"><span data-stu-id="0d98e-143">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="0d98e-144">Это позволило бы с помощью учетной записи пользователя выполнять вход в общий почтовый ящик и отправлять электронную почту.</span><span class="sxs-lookup"><span data-stu-id="0d98e-144">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="0d98e-145">Чтобы не допустить этого, требуется заблокировать вход для учетной записи, связанной с общим почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="0d98e-145">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="0d98e-146">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="0d98e-146">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="0d98e-147">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="0d98e-147">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="0d98e-148">В списке учетных записей пользователей найдите учетную запись общего почтового ящика (например, примените фильтр **Нелицензированные пользователи**).</span><span class="sxs-lookup"><span data-stu-id="0d98e-148">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="0d98e-149">Выберите пользователя, чтобы открыть область свойств, и щелкните значок **Заблокировать этого пользователя** ![Снимок экрана: значок "Заблокировать этого пользователя"](../../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="0d98e-149">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="0d98e-150">**Примечание**. Если учетная запись уже заблокирована, вверху отобразится надпись **Вход заблокирован**, а для значка выводится текст **Разблокировать этого пользователя**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-150">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="0d98e-151">В области **Заблокировать этого пользователя?** выберите **Запретить этому пользователю вход** и нажмите **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-151">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0d98e-152">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="0d98e-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="0d98e-153">В списке учетных записей пользователей найдите учетную запись общего почтового ящика (например, выберите представление **Нелицензированные пользователи**) и выберите эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="0d98e-153">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="0d98e-154">Во всплывающей области свойств нажмите **Заблокировать вход**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-154">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="0d98e-155">**Примечание.** Если учетная запись уже заблокирована, на кнопке отображается текст **Разблокировать вход**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-155">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="0d98e-156">Во всплывающей области **Изменение состояния входа** проверьте, что установлен флажок "Запретить пользователю вход", нажмите **Сохранить** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-156">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0d98e-157">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="0d98e-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="0d98e-158">В списке учетных записей пользователей найдите учетную запись общего почтового ящика (например, выберите представление **Нелицензированные пользователи**) и выберите эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="0d98e-158">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="0d98e-159">Во всплывающей области свойств нажмите **Заблокировать вход**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-159">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="0d98e-160">**Примечание.** Если учетная запись уже заблокирована, на кнопке отображается текст **Разблокировать вход**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-160">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="0d98e-161">Во всплывающей области **Изменение состояния входа** проверьте, что установлен флажок "Запретить пользователю вход", нажмите **Сохранить** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="0d98e-161">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="0d98e-162">Инструкции по блокированию входа для учетных записей с помощью Azure AD PowerShell (в том числе для нескольких учетных записей одновременно) см. в статье [Блокировка учетных записей пользователей с помощью PowerShell в Office 365](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="0d98e-162">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="0d98e-163">Добавление общего почтового ящика в Outlook</span><span class="sxs-lookup"><span data-stu-id="0d98e-163">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="0d98e-164">Если в вашей организации включена функция AutoMapping (чаще всего она включена по умолчанию), общий почтовый ящик появится у пользователей в Outlook автоматически после закрытия и перезапуска приложения.</span><span class="sxs-lookup"><span data-stu-id="0d98e-164">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="0d98e-165">Функция AutoMapping применяется к почтовому ящику пользователя, а не к общему почтовому ящику.  </span><span class="sxs-lookup"><span data-stu-id="0d98e-165">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="0d98e-166">Это означает, что при попытке использовать группу безопасности для управления доступом к общему почтовому ящику функция AutoMapping работать не будет.</span><span class="sxs-lookup"><span data-stu-id="0d98e-166">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="0d98e-167">Таким образом, чтобы работала функция AutoMapping, необходимо явно назначить разрешения.</span><span class="sxs-lookup"><span data-stu-id="0d98e-167">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="0d98e-168">Функция AutoMapping включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0d98e-168">Automapping is on by default.</span></span> <span data-ttu-id="0d98e-169">Сведения о ее отключении см. в статье [Удаление функции AutoMapping для общего почтового ящика](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="0d98e-169">To learn how to turn it off, see [Remove automapping for a shared mailbox](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="0d98e-170">Дополнительные сведения об общих почтовых ящиках в Outlook:</span><span class="sxs-lookup"><span data-stu-id="0d98e-170">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="0d98e-171"><a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Открытие и использование общего почтового ящика в Outlook</a></span><span class="sxs-lookup"><span data-stu-id="0d98e-171"><a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="0d98e-172"><a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Добавление общего почтового ящика в Outlook в Интернете</a></span><span class="sxs-lookup"><span data-stu-id="0d98e-172"><a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="0d98e-173"><a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Добавление общего почтового ящика в Outlook Mobile</a></span><span class="sxs-lookup"><span data-stu-id="0d98e-173"><a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="0d98e-174"><a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Открытие общей папки или почтового ящика в Outlook для Mac</a></span><span class="sxs-lookup"><span data-stu-id="0d98e-174"><a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="0d98e-175"><a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Добавление правил в общий почтовый ящик</a></span><span class="sxs-lookup"><span data-stu-id="0d98e-175"><a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="0d98e-176">Использование общего почтового ящика на мобильных устройствах (смартфонах и планшетах)</span><span class="sxs-lookup"><span data-stu-id="0d98e-176">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="0d98e-177">Вы можете получить доступ к общему почтовому ящику на мобильном устройстве двумя способами:</span><span class="sxs-lookup"><span data-stu-id="0d98e-177">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="0d98e-178">Добавьте общий почтовый ящик в <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">приложении Outlook для iOS</a> или <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">мобильном приложении Outlook для Android</a>.</span><span class="sxs-lookup"><span data-stu-id="0d98e-178">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="0d98e-179">Инструкции см. в статье <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Добавление общего почтового ящика в Outlook Mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="0d98e-179">For instructions, see <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="0d98e-180">Откройте браузер, выполните вход и перейдите в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0d98e-180">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="0d98e-181">Через приложение Outlook в Интернете вы можете открыть общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0d98e-181">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="0d98e-182">Инструкции см. в статье <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Добавление общего почтового ящика в Outlook в Интернете</a>.</span><span class="sxs-lookup"><span data-stu-id="0d98e-182">For instructions, see <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="0d98e-183">Использование общего календаря</span><span class="sxs-lookup"><span data-stu-id="0d98e-183">Use the shared calendar</span></span>

<span data-ttu-id="0d98e-184">При создании общего почтового ящика автоматически создается общий календарь.</span><span class="sxs-lookup"><span data-stu-id="0d98e-184">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="0d98e-185">Для отслеживания встреч и местонахождения пользователей предпочтительнее использовать календарь общего почтового ящика, а не календарь SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0d98e-185">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="0d98e-186">Общий календарь интегрирован с Outlook и работать с ним проще, чем с календарем SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0d98e-186">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="0d98e-187">В приложении Outlook перейдите в представление календаря и выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0d98e-187">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="0d98e-188">Если вы добавите встречи, они будут видны всем участникам общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="0d98e-188">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="0d98e-189">Любой участник общего почтового ящика может создавать, просматривать и управлять встречами в календаре так же, как личными встречами.</span><span class="sxs-lookup"><span data-stu-id="0d98e-189">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="0d98e-190">Изменения общего календаря будут видны всем участникам общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="0d98e-190">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0d98e-191">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="0d98e-191">Related articles</span></span>

[<span data-ttu-id="0d98e-192">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="0d98e-192">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="0d98e-193">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="0d98e-193">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="0d98e-194">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="0d98e-194">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="0d98e-195">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="0d98e-195">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="0d98e-196">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="0d98e-196">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)





