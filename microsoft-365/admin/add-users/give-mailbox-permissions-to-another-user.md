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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Узнайте, как предоставить пользователю право доступа к почтовому ящику другого пользователя. В результате пользователь будет иметь право на чтение почты и отправку почты из почтового ящика другого пользователя. '
ms.openlocfilehash: af12cfe3acad9e12ca3983c9fa13f52b72f0a467
ms.sourcegitcommit: 16e018f8b6eef5dad48eabf179691ead3cebe533
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2020
ms.locfileid: "49725157"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="c895a-104">Предоставление другому пользователю разрешений доступа к почтовому ящику — справка для администраторов</span><span class="sxs-lookup"><span data-stu-id="c895a-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="c895a-105">Как администратору вам, возможно, потребуется разрешить некоторым пользователям получать доступ к почтовому ящику другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="c895a-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="c895a-106">Например, это можно сделать для того, чтобы помощник мог отправлять почту из почтового ящика своего руководителя или один сотрудник отправлял сообщения от имени другого.</span><span class="sxs-lookup"><span data-stu-id="c895a-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="c895a-107">В этой статье показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="c895a-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="c895a-108">Если вы ищете сведения о создании и настройке общих почтовых ящиков, ознакомьтесь со статьей [Создание общего почтового ящика](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="c895a-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="c895a-109">Хотите настроить разрешения для почтового ящика?</span><span class="sxs-lookup"><span data-stu-id="c895a-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="c895a-p103">Разрешения для почтового ящика позволяют предоставить другому пользователю доступ на чтение и запись к почтовому ящику. В перечисленных ниже статьях вы найдете инструкции по настройке и использованию этой функции:</span><span class="sxs-lookup"><span data-stu-id="c895a-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="c895a-112">**Настройка разрешений**:</span><span class="sxs-lookup"><span data-stu-id="c895a-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="c895a-p104">перед предоставлением разрешений нужно решить, какие действия другие пользователи смогут выполнять в определенном почтовом ящике. Вы можете разрешить им читать сообщения, отправлять письма от имени другого пользователя или отправлять сообщения с адреса этого почтового ящика. Сведения о том, как настроить разрешения таких типов, см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="c895a-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="c895a-116">Чтение сообщений электронной почты из почтового ящика другого пользователя</span><span class="sxs-lookup"><span data-stu-id="c895a-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="c895a-117">Отправка почты из почтового ящика другого пользователя</span><span class="sxs-lookup"><span data-stu-id="c895a-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="c895a-118">Отправка почты от имени другого пользователя</span><span class="sxs-lookup"><span data-stu-id="c895a-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="c895a-119">**Распространение изменений**:</span><span class="sxs-lookup"><span data-stu-id="c895a-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="c895a-120">После настройки разрешения может потребоваться до 60 минут, чтобы изменения распространились по системе.</span><span class="sxs-lookup"><span data-stu-id="c895a-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="c895a-121">**Использование почтового ящика после настройки разрешений**:</span><span class="sxs-lookup"><span data-stu-id="c895a-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="c895a-p105">После предоставления доступа в почтовый ящик можно будет входить несколькими способами. Дополнительные сведения см. в следующей статье: [Доступ к почтовому ящику другого пользователя](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span><span class="sxs-lookup"><span data-stu-id="c895a-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="c895a-124">Разрешения можно настраивать только в текущем клиенте организации.</span><span class="sxs-lookup"><span data-stu-id="c895a-124">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="c895a-125">Разрешения для почтового ящика невозможно настроить без пользователей клиента.</span><span class="sxs-lookup"><span data-stu-id="c895a-125">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="c895a-126">Отправка почты из почтового ящика другого пользователя</span><span class="sxs-lookup"><span data-stu-id="c895a-126">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c895a-127">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="c895a-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="c895a-128">Выберите имя пользователя (от которого вы планируете дать разрешение на отправку), чтобы открыть панель его свойств.</span><span class="sxs-lookup"><span data-stu-id="c895a-128">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="c895a-129">На вкладке **почта** выберите **разрешения для почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="c895a-129">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="c895a-130">Рядом с полем **отправить как** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-130">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="c895a-131">Нажмите кнопку **добавить разрешения**, а затем выберите имя человека, которому вы хотите, чтобы он мог отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="c895a-131">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="c895a-132">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-132">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c895a-133">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="c895a-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="c895a-134">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="c895a-134">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="c895a-135">Рядом с полем **отправить как** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-135">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="c895a-136">Нажмите кнопку **добавить разрешения**, а затем выберите имя человека, которому вы хотите, чтобы он мог отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="c895a-136">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="c895a-137">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-137">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c895a-138">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="c895a-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="c895a-139">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="c895a-139">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="c895a-140">Рядом с полем **отправить как** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-140">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="c895a-141">Нажмите кнопку **добавить разрешения**, а затем выберите имя человека, которому вы хотите, чтобы он мог отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="c895a-141">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="c895a-142">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-142">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="c895a-143">Чтение почты в почтовом ящике другого пользователя</span><span class="sxs-lookup"><span data-stu-id="c895a-143">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c895a-144">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="c895a-144">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="c895a-145">Выберите имя пользователя (почтовый ящик которого вы хотите разрешить чтение), чтобы открыть область его свойств.</span><span class="sxs-lookup"><span data-stu-id="c895a-145">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="c895a-146">На вкладке **почта** выберите **разрешения для почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="c895a-146">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="c895a-147">Рядом с пунктом **чтение** и управление им выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-147">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="c895a-148">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите предоставить доступ к электронной почте из этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c895a-148">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="c895a-149">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-149">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="c895a-150">Разрешения на **чтение** и **управление**, выдаваемые в Центре администрирования Exchange, называются разрешениями на **полный доступ**.</span><span class="sxs-lookup"><span data-stu-id="c895a-150">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="c895a-151">Разрешение на полный доступ не включает в себя разрешений на **отправку в качестве** и **отправку от имени**.</span><span class="sxs-lookup"><span data-stu-id="c895a-151">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c895a-152">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="c895a-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="c895a-153">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="c895a-153">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="c895a-154">Рядом с пунктом **чтение** и управление им выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-154">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="c895a-155">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите предоставить доступ к электронной почте из этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c895a-155">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="c895a-156">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-156">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c895a-157">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="c895a-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="c895a-158">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="c895a-158">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="c895a-159">Рядом с пунктом **чтение** и управление им выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-159">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="c895a-160">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите предоставить доступ к электронной почте из этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c895a-160">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="c895a-161">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-161">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="c895a-162">Отправка почты от имени другого пользователя</span><span class="sxs-lookup"><span data-stu-id="c895a-162">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c895a-163">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="c895a-163">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="c895a-164">Чтобы открыть область свойств, выберите имя пользователя (от которого вы собираетесь предоставлять **отправлять от имени** разрешения).</span><span class="sxs-lookup"><span data-stu-id="c895a-164">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="c895a-165">На вкладке **почта** выберите **разрешения для почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="c895a-165">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="c895a-166">Рядом с полем **отправить от имени** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-166">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="c895a-167">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите разрешить отправлять электронную почту от имени этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c895a-167">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="c895a-168">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-168">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c895a-169">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="c895a-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="c895a-170">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="c895a-170">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="c895a-171">Рядом с полем **отправить от имени** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-171">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="c895a-172">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите разрешить отправлять электронную почту от имени этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c895a-172">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="c895a-173">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-173">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c895a-174">В центре администрирования перейдите в раздел **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="c895a-174">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="c895a-175">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="c895a-175">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="c895a-176">Рядом с полем **отправить от имени** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-176">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="c895a-177">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите разрешить отправлять электронную почту от имени этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c895a-177">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="c895a-178">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c895a-178">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="c895a-179">Отправка и чтение почты в Outlook и Outlook в Интернете для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c895a-179">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="c895a-p108">Хотите узнать, как отправлять почту из почтового ящика другого пользователя? Ознакомьтесь со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="c895a-p108">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="c895a-182">Управление элементами почты и календаря другого пользователя</span><span class="sxs-lookup"><span data-stu-id="c895a-182">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="c895a-183">Отправка почты от имени другого пользователя или группы</span><span class="sxs-lookup"><span data-stu-id="c895a-183">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
