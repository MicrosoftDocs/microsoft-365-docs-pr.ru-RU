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
ms.openlocfilehash: 3fb920fb6f15a2ca48c5676e9b25afd1aa5263f1
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431669"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="08a01-104">Предоставление другому пользователю разрешений доступа к почтовому ящику — справка для администраторов</span><span class="sxs-lookup"><span data-stu-id="08a01-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="08a01-105">Как администратору вам, возможно, потребуется разрешить некоторым пользователям получать доступ к почтовому ящику другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="08a01-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="08a01-106">Например, это можно сделать для того, чтобы помощник мог отправлять почту из почтового ящика своего руководителя или один сотрудник отправлял сообщения от имени другого.</span><span class="sxs-lookup"><span data-stu-id="08a01-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="08a01-107">В этой статье показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="08a01-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="08a01-108">Если вы ищете сведения о создании и настройке общих почтовых ящиков, ознакомьтесь со статьей [Создание общего почтового ящика](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="08a01-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="08a01-109">Хотите настроить разрешения для почтового ящика?</span><span class="sxs-lookup"><span data-stu-id="08a01-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="08a01-p103">Разрешения для почтового ящика позволяют предоставить другому пользователю доступ на чтение и запись к почтовому ящику. В перечисленных ниже статьях вы найдете инструкции по настройке и использованию этой функции:</span><span class="sxs-lookup"><span data-stu-id="08a01-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="08a01-112">**Настройка разрешений**:</span><span class="sxs-lookup"><span data-stu-id="08a01-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="08a01-p104">перед предоставлением разрешений нужно решить, какие действия другие пользователи смогут выполнять в определенном почтовом ящике. Вы можете разрешить им читать сообщения, отправлять письма от имени другого пользователя или отправлять сообщения с адреса этого почтового ящика. Сведения о том, как настроить разрешения таких типов, см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="08a01-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="08a01-116">Чтение сообщений электронной почты из почтового ящика другого пользователя</span><span class="sxs-lookup"><span data-stu-id="08a01-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="08a01-117">Отправка почты из почтового ящика другого пользователя</span><span class="sxs-lookup"><span data-stu-id="08a01-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="08a01-118">Отправка почты от имени другого пользователя</span><span class="sxs-lookup"><span data-stu-id="08a01-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="08a01-119">**Распространение изменений**:</span><span class="sxs-lookup"><span data-stu-id="08a01-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="08a01-120">После настройки разрешения может потребоваться до 60 минут, чтобы изменения распространились по системе.</span><span class="sxs-lookup"><span data-stu-id="08a01-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="08a01-121">**Использование почтового ящика после настройки разрешений**:</span><span class="sxs-lookup"><span data-stu-id="08a01-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="08a01-p105">после предоставления доступа в почтовый ящик можно будет входить несколькими способами. Дополнительные сведения см. в следующей статье: [Доступ к почтовому ящику другого пользователя](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span><span class="sxs-lookup"><span data-stu-id="08a01-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="08a01-124">Отправка почты из почтового ящика другого пользователя</span><span class="sxs-lookup"><span data-stu-id="08a01-124">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="08a01-125">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="08a01-125">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="08a01-126">Выберите имя пользователя (от которого вы планируете дать разрешение на отправку), чтобы открыть панель его свойств.</span><span class="sxs-lookup"><span data-stu-id="08a01-126">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="08a01-127">На вкладке **почта** выберите **разрешения для почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="08a01-127">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="08a01-128">Рядом с полем **отправить как**выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-128">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="08a01-129">Нажмите кнопку **добавить разрешения**, а затем выберите имя человека, которому вы хотите, чтобы он мог отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="08a01-129">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="08a01-130">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-130">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="08a01-131">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="08a01-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="08a01-132">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="08a01-132">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="08a01-133">Рядом с полем **отправить как**выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-133">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="08a01-134">Нажмите кнопку **добавить разрешения**, а затем выберите имя человека, которому вы хотите, чтобы он мог отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="08a01-134">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="08a01-135">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-135">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="08a01-136">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="08a01-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="08a01-137">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="08a01-137">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="08a01-138">Рядом с полем **отправить как**выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-138">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="08a01-139">Нажмите кнопку **добавить разрешения**, а затем выберите имя человека, которому вы хотите, чтобы он мог отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="08a01-139">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="08a01-140">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-140">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="08a01-141">Чтение почты в почтовом ящике другого пользователя</span><span class="sxs-lookup"><span data-stu-id="08a01-141">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="08a01-142">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="08a01-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="08a01-143">Выберите имя пользователя (почтовый ящик которого вы хотите разрешить чтение), чтобы открыть область его свойств.</span><span class="sxs-lookup"><span data-stu-id="08a01-143">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="08a01-144">На вкладке **почта** выберите **разрешения для почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="08a01-144">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="08a01-145">Рядом с пунктом **чтение**и управление им выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-145">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="08a01-146">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите предоставить доступ к электронной почте из этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="08a01-146">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="08a01-147">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-147">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="08a01-148">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="08a01-148">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="08a01-149">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="08a01-149">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="08a01-150">Рядом с пунктом **чтение**и управление им выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-150">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="08a01-151">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите предоставить доступ к электронной почте из этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="08a01-151">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="08a01-152">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-152">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="08a01-153">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="08a01-153">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="08a01-154">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="08a01-154">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="08a01-155">Рядом с пунктом **чтение**и управление им выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-155">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="08a01-156">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите предоставить доступ к электронной почте из этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="08a01-156">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="08a01-157">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-157">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="08a01-158">Отправка почты от имени другого пользователя</span><span class="sxs-lookup"><span data-stu-id="08a01-158">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="08a01-159">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="08a01-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="08a01-160">Чтобы открыть область свойств, выберите имя пользователя (от которого вы собираетесь предоставлять **отправлять от имени** разрешения).</span><span class="sxs-lookup"><span data-stu-id="08a01-160">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="08a01-161">На вкладке **почта** выберите **разрешения для почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="08a01-161">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="08a01-162">Рядом с полем **отправить от имени**выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-162">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="08a01-163">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите разрешить отправлять электронную почту от имени этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="08a01-163">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="08a01-164">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-164">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="08a01-165">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="08a01-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="08a01-166">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="08a01-166">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="08a01-167">Рядом с полем **отправить от имени**выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-167">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="08a01-168">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите разрешить отправлять электронную почту от имени этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="08a01-168">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="08a01-169">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-169">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="08a01-170">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="08a01-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="08a01-171">Выберите нужного пользователя, разверните раздел **параметры почты**, а затем нажмите кнопку **изменить** рядом с разрешениями на **почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="08a01-171">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="08a01-172">Рядом с полем **отправить от имени**выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-172">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="08a01-173">Нажмите кнопку **добавить разрешения**, а затем выберите имена пользователей, которым вы хотите разрешить отправлять электронную почту от имени этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="08a01-173">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="08a01-174">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a01-174">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="08a01-175">Отправка и чтение почты в Outlook и Outlook в Интернете для бизнеса</span><span class="sxs-lookup"><span data-stu-id="08a01-175">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="08a01-p106">Хотите узнать, как отправлять почту из почтового ящика другого пользователя? Ознакомьтесь со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="08a01-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="08a01-178">Управление элементами почты и календаря другого пользователя</span><span class="sxs-lookup"><span data-stu-id="08a01-178">Manage another person's mail and calendar items</span></span>](https://support.office.com/article/afb79d6b-2967-43b9-a944-a6b953190af5.aspx)
    
- [<span data-ttu-id="08a01-179">Отправка почты от имени другого пользователя или группы</span><span class="sxs-lookup"><span data-stu-id="08a01-179">Send email from another person or group</span></span>](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)
