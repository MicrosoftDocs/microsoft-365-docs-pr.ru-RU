---
title: 'Предоставление разрешений для почтового ящика другому пользователю Office 365: справка для администраторов'
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Узнайте, как предоставить пользователю право доступа к почтовому ящику другого пользователя. В результате пользователь будет иметь право на чтение почты и отправку почты из почтового ящика другого пользователя. '
ms.openlocfilehash: 8c3572cf543545de4a2825012f6c2e8e906cd8dd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245711"
---
# <a name="give-mailbox-permissions-to-another-user-in-office-365---admin-help"></a><span data-ttu-id="3c225-104">Предоставление разрешений для почтового ящика другому пользователю Office 365: справка для администраторов</span><span class="sxs-lookup"><span data-stu-id="3c225-104">Give mailbox permissions to another user in Office 365 - Admin Help</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="3c225-105">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="3c225-105">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="3c225-106">Как администратору вам, возможно, потребуется разрешить некоторым пользователям получать доступ к почтовому ящику другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c225-106">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="3c225-107">Например, это можно сделать для того, чтобы помощник мог отправлять почту из почтового ящика своего руководителя или один сотрудник отправлял сообщения от имени другого.</span><span class="sxs-lookup"><span data-stu-id="3c225-107">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="3c225-108">В этой статье показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="3c225-108">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="3c225-109">Если вы ищете сведения о создании и настройке общих почтовых ящиков, ознакомьтесь со статьей [Создание общего почтового ящика](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="3c225-109">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="3c225-110">Хотите настроить разрешения для почтового ящика?</span><span class="sxs-lookup"><span data-stu-id="3c225-110">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="3c225-p103">Разрешения для почтового ящика позволяют предоставить другому пользователю доступ на чтение и запись к почтовому ящику. В перечисленных ниже статьях вы найдете инструкции по настройке и использованию этой функции:</span><span class="sxs-lookup"><span data-stu-id="3c225-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="3c225-113">**Настройка разрешений**:</span><span class="sxs-lookup"><span data-stu-id="3c225-113">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="3c225-p104">перед предоставлением разрешений нужно решить, какие действия другие пользователи смогут выполнять в определенном почтовом ящике. Вы можете разрешить им читать сообщения, отправлять письма от имени другого пользователя или отправлять сообщения с адреса этого почтового ящика. Сведения о том, как настроить разрешения таких типов, см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="3c225-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="3c225-117">Чтение сообщений электронной почты из почтового ящика другого пользователя</span><span class="sxs-lookup"><span data-stu-id="3c225-117">Read email from another user's mailbox</span></span>](https://support.office.com/article/Read-email-from-another-user-s-mailbox-in-Office-365-cb3b6a8a-c6e8-4342-803c-3e54b6428cc2?#bkmk_reademailanotheruser)
    
- [<span data-ttu-id="3c225-118">Отправка почты из почтового ящика другого пользователя</span><span class="sxs-lookup"><span data-stu-id="3c225-118">Send email from another user's mailbox</span></span>](https://support.office.com/article/Send-email-from-another-user-s-mailbox-in-Office-365-2B828C5F-41AB-4904-97B9-3B63D8129C4E?#bkmk_sendemailanotheruser)
    
- [<span data-ttu-id="3c225-119">Отправка сообщения электронной почты от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="3c225-119">Send email on behalf of a user</span></span>](https://support.office.com/article/Send-email-on-behalf-of-another-user-in-Office-365-C5E7749D-244E-477F-998E-55D3876C22EC?#bkmk_sendbehalflanotheruser)
    
 <span data-ttu-id="3c225-120">**Распространение изменений**:</span><span class="sxs-lookup"><span data-stu-id="3c225-120">**Changing propagation:**</span></span>
  
<span data-ttu-id="3c225-121">После настройки разрешения может потребоваться до 60 минут, чтобы изменения распространились по системе.</span><span class="sxs-lookup"><span data-stu-id="3c225-121">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="3c225-122">**Использование почтового ящика после настройки разрешений**:</span><span class="sxs-lookup"><span data-stu-id="3c225-122">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="3c225-p105">после предоставления доступа в почтовый ящик можно будет входить несколькими способами. Дополнительные сведения см. в следующей статье: [Доступ к почтовому ящику другого пользователя](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span><span class="sxs-lookup"><span data-stu-id="3c225-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="3c225-125">Отправка почты из почтового ящика другого пользователя</span><span class="sxs-lookup"><span data-stu-id="3c225-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3c225-126">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="3c225-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="3c225-127">Выберите имя пользователя (от которого вы планируете дать разрешение на отправку), чтобы открыть панель его свойств.</span><span class="sxs-lookup"><span data-stu-id="3c225-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="3c225-128">На вкладке **почта** выберите **разрешения для почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="3c225-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="3c225-129">Рядом с полем **отправить как**выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="3c225-130">Нажмите кнопку **добавить разрешения**, а затем выберите имя человека, которому вы хотите, чтобы он мог отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="3c225-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="3c225-131">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3c225-132">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="3c225-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="3c225-133">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="3c225-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="3c225-134">Рядом с полем **отправить как**выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="3c225-135">Нажмите кнопку **добавить разрешения**, а затем выберите имя человека, которому вы хотите, чтобы он мог отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="3c225-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="3c225-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3c225-137">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="3c225-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="3c225-138">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="3c225-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="3c225-139">Рядом с полем **отправить как**выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="3c225-140">Нажмите кнопку **добавить разрешения**, а затем выберите имя человека, которому вы хотите, чтобы он мог отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="3c225-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="3c225-141">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="3c225-142">Чтение почты в почтовом ящике другого пользователя</span><span class="sxs-lookup"><span data-stu-id="3c225-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3c225-143">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="3c225-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="3c225-144">Выберите имя пользователя (почтовый ящик которого вы хотите разрешить чтение), чтобы открыть область его свойств.</span><span class="sxs-lookup"><span data-stu-id="3c225-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="3c225-145">На вкладке **почта** выберите **разрешения для почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="3c225-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="3c225-146">Рядом с пунктом **чтение**и управление им выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="3c225-147">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите предоставить доступ к электронной почте из этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="3c225-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="3c225-148">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-148">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3c225-149">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="3c225-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="3c225-150">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="3c225-150">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="3c225-151">Рядом с пунктом **чтение**и управление им выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-151">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="3c225-152">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите предоставить доступ к электронной почте из этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="3c225-152">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="3c225-153">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-153">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3c225-154">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="3c225-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="3c225-155">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="3c225-155">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="3c225-156">Рядом с пунктом **чтение**и управление им выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-156">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="3c225-157">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите предоставить доступ к электронной почте из этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="3c225-157">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="3c225-158">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-158">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="3c225-159">Отправка почты от имени другого пользователя</span><span class="sxs-lookup"><span data-stu-id="3c225-159">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3c225-160">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="3c225-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="3c225-161">Чтобы открыть область свойств, выберите имя пользователя (от которого вы собираетесь предоставлять **отправлять от имени** разрешения).</span><span class="sxs-lookup"><span data-stu-id="3c225-161">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="3c225-162">На вкладке **почта** выберите **разрешения для почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="3c225-162">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="3c225-163">Рядом с полем **отправить от имени**выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-163">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="3c225-164">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите разрешить отправлять электронную почту от имени этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="3c225-164">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="3c225-165">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-165">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3c225-166">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="3c225-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="3c225-167">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="3c225-167">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="3c225-168">Рядом с полем **отправить от имени**выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-168">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="3c225-169">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите разрешить отправлять электронную почту от имени этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="3c225-169">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="3c225-170">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-170">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3c225-171">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="3c225-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="3c225-172">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="3c225-172">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="3c225-173">Рядом с полем **отправить от имени**выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-173">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="3c225-174">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите разрешить отправлять электронную почту от имени этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="3c225-174">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="3c225-175">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3c225-175">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="3c225-176">Отправка и чтение почты в Outlook и Outlook в Интернете для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3c225-176">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="3c225-p106">Хотите узнать, как отправлять почту из почтового ящика другого пользователя? Ознакомьтесь со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="3c225-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="3c225-179">Управление элементами почты и календаря другого пользователя</span><span class="sxs-lookup"><span data-stu-id="3c225-179">Manage another person's mail and calendar items</span></span>](https://support.office.com/article/afb79d6b-2967-43b9-a944-a6b953190af5.aspx)
    
- [<span data-ttu-id="3c225-180">Отправка почты от имени другого пользователя или группы</span><span class="sxs-lookup"><span data-stu-id="3c225-180">Send email from another person or group</span></span>](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)
