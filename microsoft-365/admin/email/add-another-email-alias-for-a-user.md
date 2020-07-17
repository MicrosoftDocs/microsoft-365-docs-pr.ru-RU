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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Узнайте, как можно использовать несколько адресов электронной почты, называемых псевдонимами электронной почты, связанными с учетной записью Microsoft 365 для бизнеса. '
ms.openlocfilehash: 030d8022a8503f6b383d03b0dd97720f66d8f2f6
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080019"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="f3713-103">Добавление дополнительных псевдонимов электронной почты для пользователя</span><span class="sxs-lookup"><span data-stu-id="f3713-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f3713-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="f3713-104">The admin center is changing.</span></span> <span data-ttu-id="f3713-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="f3713-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="f3713-106">Эта статья предназначена для администраторов Microsoft 365, у которых есть бизнес-подписки.</span><span class="sxs-lookup"><span data-stu-id="f3713-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="f3713-107">Она не предназначена для домашних пользователей.</span><span class="sxs-lookup"><span data-stu-id="f3713-107">It's not for home users.</span></span>
  
<span data-ttu-id="f3713-108">Основной адрес электронной почты в Microsoft 365 обычно является адресом электронной почты, назначенным пользователем при создании учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f3713-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="f3713-109">Когда пользователь отправляет сообщения другим людям, именно этот адрес, как правило, указывается в поле  *От*  .</span><span class="sxs-lookup"><span data-stu-id="f3713-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="f3713-110">Они также могут иметь несколько адресов электронной почты, связанных с учетной записью Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f3713-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="f3713-111">Дополнительные адреса называются псевдонимами.</span><span class="sxs-lookup"><span data-stu-id="f3713-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="f3713-112">Например, пусть Женна имеет адрес электронной почты jenna@contosoco.com, но он также хочет получать электронную почту на jen@contosoco.com, так как некоторые пользователи ссылаются на него по этому имени.</span><span class="sxs-lookup"><span data-stu-id="f3713-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="f3713-113">Вы можете создать псевдонимы так, чтобы оба адреса электронной почты находились в папке "Входящие" Женна.</span><span class="sxs-lookup"><span data-stu-id="f3713-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="f3713-114">Для одного пользователя можно создать до 400 псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="f3713-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="f3713-115">Дополнительные расходы и лицензии не требуются.</span><span class="sxs-lookup"><span data-stu-id="f3713-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="f3713-116">Если требуется, чтобы несколько пользователей могли управлять электронной почтой, отправленной на один адрес электронной почты, например info@NodPublishers.com или sales@NodPublishers.com, создайте общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="f3713-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="f3713-117">Чтобы узнать больше, ознакомьтесь [со статьей Создание общего почтового ящика](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="f3713-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="f3713-118">Добавление псевдонимов электронной почты</span><span class="sxs-lookup"><span data-stu-id="f3713-118">Add email aliases to a user</span></span>
<span data-ttu-id="f3713-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="f3713-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="f3713-120">Для этого необходимы [разрешения администратора](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="f3713-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="f3713-121">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="f3713-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="f3713-122">На странице **Активные пользователи** выберите пользователя > **управления псевдонимами электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="f3713-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="f3713-123">Этот параметр не отображается, если для пользователя не назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="f3713-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="f3713-124">Нажмите кнопку **+ Добавить псевдоним** и введите новый псевдоним для пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3713-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="f3713-125">Если получено сообщение об ошибке "**не удается найти параметр, соответствующий имени параметра" EmailAddresses**", это означает, что выполнение настройки клиента или вашего личного домена занимает немного больше времени, если вы недавно добавили его.</span><span class="sxs-lookup"><span data-stu-id="f3713-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="f3713-126">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="f3713-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="f3713-127">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="f3713-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="f3713-128">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="f3713-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="f3713-129">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="f3713-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="f3713-130">Псевдоним электронной почты должен заканчиваться доменом из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="f3713-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="f3713-131">Чтобы добавить в список другое доменное имя, ознакомьтесь со статьей [Добавление домена в Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="f3713-131">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="f3713-132">Когда все будет готово, нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="f3713-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="f3713-133">Подождите 24 часа, пока новые псевдонимы не заполняются в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3713-133">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="f3713-134">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="f3713-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="f3713-135">Например, все сообщения, отправленные на основной адрес Ольги Хоффман, Eliza@NodPublishers.com и псевдоним Sales@NodPublishers.com, будут перенаправлены в папку "Входящие" Ольги.</span><span class="sxs-lookup"><span data-stu-id="f3713-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="f3713-136">**Когда пользователь ответит, адрес *отправителя* будет основным псевдонимом электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="f3713-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="f3713-137">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в папку "Входящие" Ольги.</span><span class="sxs-lookup"><span data-stu-id="f3713-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="f3713-138">Когда вы Ольги ответы на сообщение, его основной адрес электронной почты будет отображаться как отправитель, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="f3713-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="f3713-139">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="f3713-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="f3713-140">На странице **Активные пользователи** выберите нужного пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3713-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="f3713-141">Рядом с полем **имя пользователя и псевдонимы электронной почты**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="f3713-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="f3713-142">Если получено сообщение об ошибке "**не удается найти параметр, соответствующий имени параметра" EmailAddresses**", это означает, что выполнение настройки клиента или вашего личного домена занимает немного больше времени, если вы недавно добавили его.</span><span class="sxs-lookup"><span data-stu-id="f3713-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="f3713-143">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="f3713-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="f3713-144">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="f3713-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="f3713-145">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="f3713-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="f3713-146">В текстовом поле в разделе **псевдоним**введите первую часть нового псевдонима электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f3713-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="f3713-147">Если вы добавили свой домен в Microsoft 365, вы можете выбрать домен для нового псевдонима электронной почты с помощью раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="f3713-147">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="f3713-148">Затем нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f3713-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f3713-149">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="f3713-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="f3713-150">Псевдоним электронной почты должен заканчиваться доменом из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="f3713-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="f3713-151">Чтобы добавить в список другое доменное имя, ознакомьтесь со статьей [Добавление домена в Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="f3713-151">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="f3713-152">Когда все будет готово, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f3713-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="f3713-153">Подождите 24 часа, пока новые псевдонимы не заполняются в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3713-153">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="f3713-154">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="f3713-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="f3713-155">Например, все сообщения, отправленные на основной адрес Ольги Хоффман, Eliza@NodPublishers.com и псевдоним Sales@NodPublishers.com, будут перенаправлены в папку "Входящие" Ольги.</span><span class="sxs-lookup"><span data-stu-id="f3713-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="f3713-156">**Когда пользователь ответит, адрес *отправителя* будет основным псевдонимом электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="f3713-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="f3713-157">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в папку "Входящие" Ольги.</span><span class="sxs-lookup"><span data-stu-id="f3713-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="f3713-158">Когда вы Ольги ответы на сообщение, его основной адрес электронной почты будет отображаться как отправитель, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="f3713-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f3713-159">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="f3713-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="f3713-160">На странице **Активные пользователи** выберите нужного пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3713-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="f3713-161">Рядом с полем **имя пользователя и псевдонимы электронной почты**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="f3713-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="f3713-162">Если получено сообщение об ошибке "**не удается найти параметр, соответствующий имени параметра" EmailAddresses**", это означает, что выполнение настройки клиента или вашего личного домена занимает немного больше времени, если вы недавно добавили его.</span><span class="sxs-lookup"><span data-stu-id="f3713-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="f3713-163">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="f3713-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="f3713-164">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="f3713-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="f3713-165">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="f3713-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="f3713-166">В текстовом поле в разделе **псевдоним**введите первую часть нового псевдонима электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f3713-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="f3713-167">Если вы добавили свой домен в Microsoft 365, вы можете выбрать домен для нового псевдонима электронной почты с помощью раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="f3713-167">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="f3713-168">Затем нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f3713-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f3713-169">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="f3713-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="f3713-170">Псевдоним электронной почты должен заканчиваться доменом из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="f3713-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="f3713-171">Чтобы добавить в список другое доменное имя, ознакомьтесь со статьей [Добавление домена в Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="f3713-171">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="f3713-172">Когда все будет готово, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f3713-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="f3713-173">Подождите 24 часа, пока новые псевдонимы не заполняются в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3713-173">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="f3713-174">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="f3713-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="f3713-175">Например, все сообщения, отправленные на основной адрес Ольги Хоффман, Eliza@NodPublishers.com и псевдоним Sales@NodPublishers.com, будут перенаправлены в папку "Входящие" Ольги.</span><span class="sxs-lookup"><span data-stu-id="f3713-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="f3713-176">**Когда пользователь ответит, адрес *отправителя* будет основным псевдонимом электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="f3713-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="f3713-177">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в папку "Входящие" Ольги.</span><span class="sxs-lookup"><span data-stu-id="f3713-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="f3713-178">Когда вы Ольги ответы на сообщение, его основной адрес электронной почты будет отображаться как отправитель, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="f3713-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="f3713-179">Получено "не удается найти параметр, соответствующий имени параметра EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="f3713-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="f3713-180">Если получено сообщение об ошибке "**не удается найти параметр, соответствующий имени параметра EmailAddresses**", это означает, что установка клиента или личного домена длится немного дольше, если вы недавно добавили его.</span><span class="sxs-lookup"><span data-stu-id="f3713-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="f3713-181">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="f3713-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="f3713-182">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="f3713-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="f3713-183">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="f3713-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="f3713-184">Вы приобрели подписку у GoDaddy или другого партнера?</span><span class="sxs-lookup"><span data-stu-id="f3713-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="f3713-185">Если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="f3713-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="f3713-186">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f3713-186">Related articles</span></span>

[<span data-ttu-id="f3713-187">Отправка почты с другого адреса</span><span class="sxs-lookup"><span data-stu-id="f3713-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="f3713-188">Изменение имени пользователя и адреса электронной почты</span><span class="sxs-lookup"><span data-stu-id="f3713-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

