---
title: Предоставление другому пользователю разрешений доступа к почтовому ящику — справка для администраторов
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: Предоставьте пользователю право на доступ к почтовому ящику другого пользователя, что позволит ему читать и отправлять письма из почтового ящика другого пользователя.
ms.openlocfilehash: 3514be02f2ef82b727edfcf86c0bd3f6b8515510
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535966"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="1786f-103">Предоставление другому пользователю разрешений доступа к почтовому ящику — справка для администраторов</span><span class="sxs-lookup"><span data-stu-id="1786f-103">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="1786f-104">Как администратору вам, возможно, потребуется разрешить некоторым пользователям получать доступ к почтовому ящику другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="1786f-104">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="1786f-105">Например, это можно сделать для того, чтобы помощник мог отправлять почту из почтового ящика своего руководителя или один сотрудник отправлял сообщения от имени другого.</span><span class="sxs-lookup"><span data-stu-id="1786f-105">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="1786f-106">В этой статье показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="1786f-106">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="1786f-107">Если вы ищете сведения о создании и настройке общих почтовых ящиков, ознакомьтесь со статьей [Создание общего почтового ящика](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="1786f-107">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="1786f-108">Хотите настроить разрешения для почтового ящика?</span><span class="sxs-lookup"><span data-stu-id="1786f-108">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="1786f-p102">Разрешения для почтового ящика позволяют предоставить другому пользователю доступ на чтение и запись к почтовому ящику. В перечисленных ниже статьях вы найдете инструкции по настройке и использованию этой функции:</span><span class="sxs-lookup"><span data-stu-id="1786f-p102">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="1786f-111">**Настройка разрешений**:</span><span class="sxs-lookup"><span data-stu-id="1786f-111">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="1786f-p103">перед предоставлением разрешений нужно решить, какие действия другие пользователи смогут выполнять в определенном почтовом ящике. Вы можете разрешить им читать сообщения, отправлять письма от имени другого пользователя или отправлять сообщения с адреса этого почтового ящика. Сведения о том, как настроить разрешения таких типов, см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="1786f-p103">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="1786f-115">Чтение сообщений электронной почты из почтового ящика другого пользователя</span><span class="sxs-lookup"><span data-stu-id="1786f-115">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="1786f-116">Отправка почты из почтового ящика другого пользователя</span><span class="sxs-lookup"><span data-stu-id="1786f-116">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="1786f-117">Отправка почты от имени другого пользователя</span><span class="sxs-lookup"><span data-stu-id="1786f-117">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="1786f-118">**Распространение изменений**:</span><span class="sxs-lookup"><span data-stu-id="1786f-118">**Changing propagation:**</span></span>
  
<span data-ttu-id="1786f-119">После настройки разрешения может потребоваться до 60 минут, чтобы изменения распространились по системе.</span><span class="sxs-lookup"><span data-stu-id="1786f-119">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="1786f-120">**Использование почтового ящика после настройки разрешений**:</span><span class="sxs-lookup"><span data-stu-id="1786f-120">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="1786f-p104">После предоставления доступа в почтовый ящик можно будет входить несколькими способами. Дополнительные сведения см. в следующей статье: [Доступ к почтовому ящику другого пользователя](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span><span class="sxs-lookup"><span data-stu-id="1786f-p104">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="1786f-123">Разрешения можно настраивать только в текущем клиенте организации.</span><span class="sxs-lookup"><span data-stu-id="1786f-123">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="1786f-124">Разрешения для почтового ящика невозможно настроить без пользователей клиента.</span><span class="sxs-lookup"><span data-stu-id="1786f-124">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="1786f-125">Отправка почты из почтового ящика другого пользователя</span><span class="sxs-lookup"><span data-stu-id="1786f-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1786f-126">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="1786f-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="1786f-127">Выберите имя пользователя (от которого вы планируете дать разрешение на отправку), чтобы открыть панель его свойств.</span><span class="sxs-lookup"><span data-stu-id="1786f-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="1786f-128">На вкладке **почта** выберите **разрешения для почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="1786f-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="1786f-129">Рядом с полем **отправить как** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="1786f-130">Нажмите кнопку **добавить разрешения**, а затем выберите имя человека, которому вы хотите, чтобы он мог отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="1786f-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="1786f-131">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1786f-132">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="1786f-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="1786f-133">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="1786f-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="1786f-134">Рядом с полем **отправить как** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="1786f-135">Нажмите кнопку **добавить разрешения**, а затем выберите имя человека, которому вы хотите, чтобы он мог отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="1786f-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="1786f-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1786f-137">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="1786f-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="1786f-138">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="1786f-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="1786f-139">Рядом с полем **отправить как** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="1786f-140">Нажмите кнопку **добавить разрешения**, а затем выберите имя человека, которому вы хотите, чтобы он мог отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="1786f-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="1786f-141">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="1786f-142">Чтение почты в почтовом ящике другого пользователя</span><span class="sxs-lookup"><span data-stu-id="1786f-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1786f-143">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="1786f-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="1786f-144">Выберите имя пользователя (почтовый ящик которого вы хотите разрешить чтение), чтобы открыть область его свойств.</span><span class="sxs-lookup"><span data-stu-id="1786f-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="1786f-145">На вкладке **почта** выберите **разрешения для почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="1786f-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="1786f-146">Рядом с пунктом **чтение** и управление им выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="1786f-147">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите предоставить доступ к электронной почте из этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="1786f-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="1786f-148">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-148">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="1786f-149">Разрешения на **чтение** и **управление**, выдаваемые в Центре администрирования Exchange, называются разрешениями на **полный доступ**.</span><span class="sxs-lookup"><span data-stu-id="1786f-149">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="1786f-150">Разрешение на полный доступ не включает в себя разрешений на **отправку в качестве** и **отправку от имени**.</span><span class="sxs-lookup"><span data-stu-id="1786f-150">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1786f-151">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="1786f-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="1786f-152">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="1786f-152">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="1786f-153">Рядом с пунктом **чтение** и управление им выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-153">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="1786f-154">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите предоставить доступ к электронной почте из этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="1786f-154">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="1786f-155">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-155">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1786f-156">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="1786f-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="1786f-157">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="1786f-157">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="1786f-158">Рядом с пунктом **чтение** и управление им выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-158">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="1786f-159">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите предоставить доступ к электронной почте из этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="1786f-159">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="1786f-160">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-160">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="1786f-161">Отправка почты от имени другого пользователя</span><span class="sxs-lookup"><span data-stu-id="1786f-161">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1786f-162">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="1786f-162">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="1786f-163">Чтобы открыть область свойств, выберите имя пользователя (от которого вы собираетесь предоставлять **отправлять от имени** разрешения).</span><span class="sxs-lookup"><span data-stu-id="1786f-163">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="1786f-164">На вкладке **почта** выберите **разрешения для почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="1786f-164">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="1786f-165">Рядом с полем **отправить от имени** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-165">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="1786f-166">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите разрешить отправлять электронную почту от имени этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="1786f-166">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="1786f-167">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-167">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1786f-168">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="1786f-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="1786f-169">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="1786f-169">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="1786f-170">Рядом с полем **отправить от имени** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-170">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="1786f-171">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите разрешить отправлять электронную почту от имени этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="1786f-171">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="1786f-172">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-172">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1786f-173">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="1786f-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="1786f-174">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="1786f-174">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="1786f-175">Рядом с полем **отправить от имени** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-175">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="1786f-176">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите разрешить отправлять электронную почту от имени этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="1786f-176">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="1786f-177">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1786f-177">Select **Save**.</span></span>

::: moniker-end


## <a name="related-content"></a><span data-ttu-id="1786f-178">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="1786f-178">Related content</span></span>
  
<span data-ttu-id="1786f-179">[Управление элементами почты и календаря другого пользователя (статья)](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)</span><span class="sxs-lookup"><span data-stu-id="1786f-179">[Manage another person's mail and calendar items](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (article)</span></span>
    
<span data-ttu-id="1786f-180">[Отправка почты от имени другого пользователя или группы](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (статья)</span><span class="sxs-lookup"><span data-stu-id="1786f-180">[Send email from another person or group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (article)</span></span>

<span data-ttu-id="1786f-181">[Изменение имени пользователя и адреса электронной почты](../add-users/change-a-user-name-and-email-address.md) (видео)</span><span class="sxs-lookup"><span data-stu-id="1786f-181">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (video)</span></span>

