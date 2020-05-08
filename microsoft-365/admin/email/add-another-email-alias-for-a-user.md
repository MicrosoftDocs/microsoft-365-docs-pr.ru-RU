---
title: Добавление дополнительных псевдонимов электронной почты для пользователя
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Узнайте, как можно использовать несколько адресов электронной почты, называемых псевдонимами электронной почты, связанными с учетной записью Microsoft 365 для бизнеса. '
ms.openlocfilehash: efd0dbf5ae072c803b52d94dd41f16db9bb0413a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048811"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="e7ecf-103">Добавление дополнительных псевдонимов электронной почты для пользователя</span><span class="sxs-lookup"><span data-stu-id="e7ecf-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="e7ecf-104">Эта статья предназначена для администраторов Microsoft 365, у которых есть бизнес-подписки.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="e7ecf-105">Она не предназначена для домашних пользователей.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-105">It's not for home users.</span></span>
  
<span data-ttu-id="e7ecf-106">Основной адрес электронной почты в Microsoft 365 обычно является адресом электронной почты, назначенным пользователем при создании учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="e7ecf-107">Когда пользователь отправляет сообщения другим людям, именно этот адрес, как правило, указывается в поле  *От*  .</span><span class="sxs-lookup"><span data-stu-id="e7ecf-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="e7ecf-108">Они также могут иметь несколько адресов электронной почты, связанных с учетной записью Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="e7ecf-109">Дополнительные адреса называются псевдонимами.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="e7ecf-110">Например, пусть Женна имеет адрес электронной почты jenna@contosoco.com, но он также хочет получать электронную почту на jen@contosoco.com, так как некоторые пользователи ссылаются на него по этому имени.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="e7ecf-111">Вы можете создать псевдонимы так, чтобы оба адреса электронной почты находились в папке "Входящие" Женна.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="e7ecf-112">Для одного пользователя можно создать до 400 псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="e7ecf-113">Дополнительные расходы и лицензии не требуются.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="e7ecf-114">Если требуется, чтобы несколько пользователей могли управлять электронной почтой, отправленной на один адрес электронной почты, например info@NodPublishers.com или sales@NodPublishers.com, создайте общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="e7ecf-115">Чтобы узнать больше, ознакомьтесь [со статьей Создание общего почтового ящика](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="e7ecf-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="e7ecf-116">Добавление псевдонимов электронной почты</span><span class="sxs-lookup"><span data-stu-id="e7ecf-116">Add email aliases to a user</span></span>
<span data-ttu-id="e7ecf-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="e7ecf-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="e7ecf-118">Для этого необходимы [разрешения администратора](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="e7ecf-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e7ecf-119">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="e7ecf-120">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="e7ecf-121">На странице **Активные пользователи** выберите пользователя > **управления псевдонимами электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-121">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="e7ecf-122">Этот параметр не отображается, если для пользователя не назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-122">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="e7ecf-123">Нажмите кнопку **+ Добавить псевдоним** и введите новый псевдоним для пользователя.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-123">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="e7ecf-124">Если получено сообщение об ошибке "**не удается найти параметр, соответствующий имени параметра" EmailAddresses**", это означает, что выполнение настройки клиента или вашего личного домена занимает немного больше времени, если вы недавно добавили его.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-124">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="e7ecf-125">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-125">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="e7ecf-126">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-126">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="e7ecf-127">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-127">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="e7ecf-128">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-128">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="e7ecf-129">Псевдоним электронной почты должен заканчиваться доменом из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-129">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="e7ecf-130">Чтобы добавить в список другое доменное имя, ознакомьтесь со статьей [Добавление домена в Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="e7ecf-130">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="e7ecf-131">Когда все будет готово, нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-131">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="e7ecf-132">Подождите 24 часа, чтобы новые псевдонимы добавились в Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-132">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="e7ecf-133">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-133">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="e7ecf-134">Например, все сообщения, отправленные на основной адрес Ольги Хоффман, Eliza@NodPublishers.com и псевдоним Sales@NodPublishers.com, будут перенаправлены в папку "Входящие" Ольги.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-134">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="e7ecf-135">**Когда пользователь ответит, адрес *отправителя* будет основным псевдонимом электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="e7ecf-135">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="e7ecf-136">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в папку "Входящие" Ольги.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="e7ecf-137">Когда вы Ольги ответы на сообщение, его основной адрес электронной почты будет отображаться как отправитель, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="e7ecf-138">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="e7ecf-139">На странице **Активные пользователи** выберите нужного пользователя.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-139">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="e7ecf-140">Рядом с полем **имя пользователя и псевдонимы электронной почты**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-140">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="e7ecf-141">Если получено сообщение об ошибке "**не удается найти параметр, соответствующий имени параметра" EmailAddresses**", это означает, что выполнение настройки клиента или вашего личного домена занимает немного больше времени, если вы недавно добавили его.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-141">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="e7ecf-142">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-142">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="e7ecf-143">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-143">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="e7ecf-144">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-144">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="e7ecf-145">В текстовом поле в разделе **псевдоним**введите первую часть нового псевдонима электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-145">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="e7ecf-146">Если вы добавили в Office 365 собственный домен, его можно выбрать для нового псевдонима в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-146">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="e7ecf-147">Затем нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-147">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e7ecf-148">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-148">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="e7ecf-149">Псевдоним электронной почты должен заканчиваться доменом из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-149">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="e7ecf-150">Чтобы добавить в список другое доменное имя, ознакомьтесь со статьей [Добавление домена в Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="e7ecf-150">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="e7ecf-151">Когда все будет готово, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-151">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="e7ecf-152">Подождите 24 часа, чтобы новые псевдонимы добавились в Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-152">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="e7ecf-153">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-153">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="e7ecf-154">Например, все сообщения, отправленные на основной адрес Ольги Хоффман, Eliza@NodPublishers.com и псевдоним Sales@NodPublishers.com, будут перенаправлены в папку "Входящие" Ольги.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-154">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="e7ecf-155">**Когда пользователь ответит, адрес *отправителя* будет основным псевдонимом электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="e7ecf-155">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="e7ecf-156">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в папку "Входящие" Ольги.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="e7ecf-157">Когда вы Ольги ответы на сообщение, его основной адрес электронной почты будет отображаться как отправитель, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e7ecf-158">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="e7ecf-159">На странице **Активные пользователи** выберите нужного пользователя.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-159">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="e7ecf-160">Рядом с полем **имя пользователя и псевдонимы электронной почты**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-160">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="e7ecf-161">Если получено сообщение об ошибке "**не удается найти параметр, соответствующий имени параметра" EmailAddresses**", это означает, что выполнение настройки клиента или вашего личного домена занимает немного больше времени, если вы недавно добавили его.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-161">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="e7ecf-162">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-162">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="e7ecf-163">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-163">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="e7ecf-164">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-164">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="e7ecf-165">В текстовом поле в разделе **псевдоним**введите первую часть нового псевдонима электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-165">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="e7ecf-166">Если вы добавили в Office 365 собственный домен, его можно выбрать для нового псевдонима в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-166">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="e7ecf-167">Затем нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-167">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e7ecf-168">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-168">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="e7ecf-169">Псевдоним электронной почты должен заканчиваться доменом из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-169">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="e7ecf-170">Чтобы добавить в список другое доменное имя, ознакомьтесь со статьей [Добавление домена в Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="e7ecf-170">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="e7ecf-171">Когда все будет готово, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-171">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="e7ecf-172">Подождите 24 часа, чтобы новые псевдонимы добавились в Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-172">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="e7ecf-173">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-173">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="e7ecf-174">Например, все сообщения, отправленные на основной адрес Ольги Хоффман, Eliza@NodPublishers.com и псевдоним Sales@NodPublishers.com, будут перенаправлены в папку "Входящие" Ольги.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-174">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="e7ecf-175">**Когда пользователь ответит, адрес *отправителя* будет основным псевдонимом электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="e7ecf-175">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="e7ecf-176">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в папку "Входящие" Ольги.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="e7ecf-177">Когда вы Ольги ответы на сообщение, его основной адрес электронной почты будет отображаться как отправитель, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="e7ecf-178">Получено "не удается найти параметр, соответствующий имени параметра EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="e7ecf-178">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="e7ecf-179">Если получено сообщение об ошибке "**не удается найти параметр, соответствующий имени параметра EmailAddresses**", это означает, что установка клиента или личного домена длится немного дольше, если вы недавно добавили его.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-179">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="e7ecf-180">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-180">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="e7ecf-181">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-181">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="e7ecf-182">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-182">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="e7ecf-183">Вы приобрели подписку у GoDaddy или другого партнера?</span><span class="sxs-lookup"><span data-stu-id="e7ecf-183">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="e7ecf-184">Если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="e7ecf-184">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="e7ecf-185">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="e7ecf-185">Related articles</span></span>

[<span data-ttu-id="e7ecf-186">Отправка почты с другого адреса</span><span class="sxs-lookup"><span data-stu-id="e7ecf-186">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="e7ecf-187">Изменение имени пользователя и адреса электронной почты</span><span class="sxs-lookup"><span data-stu-id="e7ecf-187">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

