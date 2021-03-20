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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Узнайте, как можно использовать несколько адресов электронной почты, называемых псевдонимом электронной почты, связанных с учетной записью Microsoft 365 для бизнеса. '
ms.openlocfilehash: 590782f7b22b1d26abef83f884d45da567f0425c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915954"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="0017e-103">Добавление дополнительных псевдонимов электронной почты для пользователя</span><span class="sxs-lookup"><span data-stu-id="0017e-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0017e-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="0017e-104">The admin center is changing.</span></span> <span data-ttu-id="0017e-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="0017e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="0017e-106">Эта статья для администраторов Microsoft 365, у которых есть бизнес-подписки.</span><span class="sxs-lookup"><span data-stu-id="0017e-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="0017e-107">Она не предназначена для домашних пользователей.</span><span class="sxs-lookup"><span data-stu-id="0017e-107">It's not for home users.</span></span>
  
<span data-ttu-id="0017e-108">Основной адрес электронной почты в Microsoft 365 обычно является адресом электронной почты, который был назначен пользователю при его учетной записи.</span><span class="sxs-lookup"><span data-stu-id="0017e-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="0017e-109">Когда пользователь отправляет сообщения другим людям, именно этот адрес, как правило, указывается в поле  *От*  .</span><span class="sxs-lookup"><span data-stu-id="0017e-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="0017e-110">Кроме того, у них может быть несколько адресов электронной почты, связанных с учетной записью Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0017e-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="0017e-111">Дополнительные адреса называются псевдонимами.</span><span class="sxs-lookup"><span data-stu-id="0017e-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="0017e-112">Например, предположим, что у Дженны есть адрес электронной почты jenna@contosoco.com, но она также хочет получать электронную почту в jen@contosoco.com, так как некоторые люди ссылаются на нее по этому имени.</span><span class="sxs-lookup"><span data-stu-id="0017e-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="0017e-113">Вы можете создать псевдонимы для нее, чтобы оба адреса электронной почты перейти в почтовый ящик Дженны.</span><span class="sxs-lookup"><span data-stu-id="0017e-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="0017e-114">Для одного пользователя можно создать до 400 псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="0017e-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="0017e-115">Дополнительные расходы и лицензии не требуются.</span><span class="sxs-lookup"><span data-stu-id="0017e-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="0017e-116">Если вы хотите, чтобы несколько людей могли управлять электронной почтой, отправленной на один адрес электронной почты info@NodPublishers.com или sales@NodPublishers.com, создайте общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0017e-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="0017e-117">Дополнительные возможности см. в [раздел Создание общего почтового ящика.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="0017e-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="0017e-118">Добавление псевдонимов электронной почты</span><span class="sxs-lookup"><span data-stu-id="0017e-118">Add email aliases to a user</span></span>
<span data-ttu-id="0017e-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="0017e-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="0017e-120">Для этого необходимо [иметь разрешения](../add-users/about-admin-roles.md) администратора.</span><span class="sxs-lookup"><span data-stu-id="0017e-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="0017e-121">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="0017e-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="0017e-122">На странице **Активные пользователи** выберите имя пользователя> **управление псевдонимами электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="0017e-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="0017e-123">Вы не увидите этот параметр, если ему не назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="0017e-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="0017e-124">Выберите **+ Добавьте псевдоним** и введите новый псевдоним для пользователя.</span><span class="sxs-lookup"><span data-stu-id="0017e-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="0017e-125">Если вы получаете сообщение об ошибке " Параметр не может быть найден, который совпадает с именем параметра **"EmailAddresses",** это означает, что для завершения настройки клиента или пользовательского домена, если вы недавно добавили его, нужно немного больше времени.</span><span class="sxs-lookup"><span data-stu-id="0017e-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="0017e-126">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="0017e-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="0017e-127">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="0017e-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="0017e-128">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="0017e-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="0017e-129">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="0017e-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="0017e-130">Псевдоним электронной почты должен закончиться доменом из выпадаемого списка.</span><span class="sxs-lookup"><span data-stu-id="0017e-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="0017e-131">Чтобы добавить другое доменное имя в список, см. в примере [Добавление домена в Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="0017e-131">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="0017e-132">После этого выберите сохранить **изменения.**</span><span class="sxs-lookup"><span data-stu-id="0017e-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="0017e-133">Подождите 24 часа, чтобы новые псевдонимы заполнялись в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0017e-133">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="0017e-134">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="0017e-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="0017e-135">Например, вся почта, отправленная на основной адрес Элизы Хоффман, Eliza@NodPublishers.com и ее псевдоним Sales@NodPublishers.com, будет отправлена в почтовый ящик Элизы.</span><span class="sxs-lookup"><span data-stu-id="0017e-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="0017e-136">**Когда пользователь отвечает, адрес *From*  будет ее основным псевдонимом электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="0017e-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="0017e-137">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в почтовый ящик Eliza.</span><span class="sxs-lookup"><span data-stu-id="0017e-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="0017e-138">Когда Элиза отвечает на сообщение, ее основной адрес электронной почты будет отображаться как отправитель, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="0017e-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="0017e-139">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="0017e-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="0017e-140">На странице **Активные пользователи** выберите нужного пользователя.</span><span class="sxs-lookup"><span data-stu-id="0017e-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="0017e-141">Рядом с **имям пользователя / Псевдонимы** электронной почты , выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="0017e-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="0017e-142">Если вы получаете сообщение об ошибке " Параметр не может быть найден, который совпадает с именем параметра **"EmailAddresses",** это означает, что для завершения настройки клиента или пользовательского домена, если вы недавно добавили его, нужно немного больше времени.</span><span class="sxs-lookup"><span data-stu-id="0017e-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="0017e-143">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="0017e-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="0017e-144">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="0017e-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="0017e-145">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="0017e-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="0017e-146">В текстовом поле **под псевдонимом** введите первую часть нового псевдонима электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0017e-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="0017e-147">Если вы добавили в Microsoft 365 собственный домен, его можно выбрать для нового псевдонима в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="0017e-147">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="0017e-148">Затем нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0017e-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0017e-149">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="0017e-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="0017e-150">Псевдоним электронной почты должен закончиться доменом из выпадаемого списка.</span><span class="sxs-lookup"><span data-stu-id="0017e-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="0017e-151">Чтобы добавить другое доменное имя в список, см. в примере [Добавление домена в Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="0017e-151">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="0017e-152">Когда все будет готово, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0017e-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="0017e-153">Подождите 24 часа, чтобы новые псевдонимы заполнялись в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0017e-153">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="0017e-154">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="0017e-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="0017e-155">Например, вся почта, отправленная на основной адрес Элизы Хоффман, Eliza@NodPublishers.com и ее псевдоним Sales@NodPublishers.com, будет отправлена в почтовый ящик Элизы.</span><span class="sxs-lookup"><span data-stu-id="0017e-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="0017e-156">**Когда пользователь отвечает, адрес *From*  будет ее основным псевдонимом электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="0017e-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="0017e-157">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в почтовый ящик Eliza.</span><span class="sxs-lookup"><span data-stu-id="0017e-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="0017e-158">Когда Элиза отвечает на сообщение, ее основной адрес электронной почты будет отображаться как отправитель, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="0017e-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0017e-159">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="0017e-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="0017e-160">На странице **Активные пользователи** выберите нужного пользователя.</span><span class="sxs-lookup"><span data-stu-id="0017e-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="0017e-161">Рядом с **имям пользователя / Псевдонимы** электронной почты , выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="0017e-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="0017e-162">Если вы получаете сообщение об ошибке " Параметр не может быть найден, который совпадает с именем параметра **"EmailAddresses",** это означает, что для завершения настройки клиента или пользовательского домена, если вы недавно добавили его, нужно немного больше времени.</span><span class="sxs-lookup"><span data-stu-id="0017e-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="0017e-163">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="0017e-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="0017e-164">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="0017e-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="0017e-165">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="0017e-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="0017e-166">В текстовом поле **под псевдонимом** введите первую часть нового псевдонима электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0017e-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="0017e-167">Если вы добавили в Microsoft 365 собственный домен, его можно выбрать для нового псевдонима в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="0017e-167">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="0017e-168">Затем нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0017e-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0017e-169">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="0017e-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="0017e-170">Псевдоним электронной почты должен закончиться доменом из выпадаемого списка.</span><span class="sxs-lookup"><span data-stu-id="0017e-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="0017e-171">Чтобы добавить другое доменное имя в список, см. в примере [Добавление домена в Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="0017e-171">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="0017e-172">Когда все будет готово, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0017e-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="0017e-173">Подождите 24 часа, чтобы новые псевдонимы заполнялись в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0017e-173">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="0017e-174">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="0017e-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="0017e-175">Например, вся почта, отправленная на основной адрес Элизы Хоффман, Eliza@NodPublishers.com и ее псевдоним Sales@NodPublishers.com, будет отправлена в почтовый ящик Элизы.</span><span class="sxs-lookup"><span data-stu-id="0017e-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="0017e-176">**Когда пользователь отвечает, адрес *From*  будет ее основным псевдонимом электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="0017e-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="0017e-177">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в почтовый ящик Eliza.</span><span class="sxs-lookup"><span data-stu-id="0017e-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="0017e-178">Когда Элиза отвечает на сообщение, ее основной адрес электронной почты будет отображаться как отправитель, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="0017e-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="0017e-179">Вы получаете "Параметр не может быть найден, который соответствует имени параметра EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="0017e-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="0017e-180">Если вы получаете сообщение об ошибке " Параметр не может быть найден, который совпадает с именем параметра **EmailAddresses**" это означает, что для завершения настройки клиента или пользовательского домена, если вы недавно добавили его, нужно немного больше времени.</span><span class="sxs-lookup"><span data-stu-id="0017e-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="0017e-181">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="0017e-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="0017e-182">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="0017e-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="0017e-183">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="0017e-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="0017e-184">Вы приобрели подписку у GoDaddy или другого партнера?</span><span class="sxs-lookup"><span data-stu-id="0017e-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="0017e-185">Если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="0017e-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="0017e-186">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0017e-186">Related articles</span></span>

[<span data-ttu-id="0017e-187">Отправка почты с другого адреса</span><span class="sxs-lookup"><span data-stu-id="0017e-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="0017e-188">Изменение имени пользователя и адреса электронной почты</span><span class="sxs-lookup"><span data-stu-id="0017e-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
