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
ms.openlocfilehash: 4003dcfca29a722ccdf9b86cca5aa1141fbdb367
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892809"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="c83c2-103">Добавление дополнительных псевдонимов электронной почты для пользователя</span><span class="sxs-lookup"><span data-stu-id="c83c2-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="c83c2-104">Эта статья для администраторов Microsoft 365, у которых есть бизнес-подписки.</span><span class="sxs-lookup"><span data-stu-id="c83c2-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="c83c2-105">Она не предназначена для домашних пользователей.</span><span class="sxs-lookup"><span data-stu-id="c83c2-105">It's not for home users.</span></span>
  
<span data-ttu-id="c83c2-106">Основной адрес электронной почты в Microsoft 365 обычно является адресом электронной почты, который был назначен пользователю при его учетной записи.</span><span class="sxs-lookup"><span data-stu-id="c83c2-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="c83c2-107">Когда пользователь отправляет сообщения другим людям, именно этот адрес, как правило, указывается в поле  *От*  .</span><span class="sxs-lookup"><span data-stu-id="c83c2-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="c83c2-108">Кроме того, у них может быть несколько адресов электронной почты, связанных с учетной записью Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c83c2-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="c83c2-109">Дополнительные адреса называются псевдонимами.</span><span class="sxs-lookup"><span data-stu-id="c83c2-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="c83c2-110">Например, предположим, что у Дженны есть адрес электронной почты jenna@contosoco.com, но она также хочет получать электронную почту в jen@contosoco.com, так как некоторые люди ссылаются на нее по этому имени.</span><span class="sxs-lookup"><span data-stu-id="c83c2-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="c83c2-111">Вы можете создать псевдонимы для нее, чтобы оба адреса электронной почты перейти в почтовый ящик Дженны.</span><span class="sxs-lookup"><span data-stu-id="c83c2-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="c83c2-112">Для одного пользователя можно создать до 400 псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="c83c2-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="c83c2-113">Дополнительные расходы и лицензии не требуются.</span><span class="sxs-lookup"><span data-stu-id="c83c2-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="c83c2-114">Если вы хотите, чтобы несколько людей могли управлять электронной почтой, отправленной на один адрес электронной почты info@NodPublishers.com или sales@NodPublishers.com, создайте общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="c83c2-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="c83c2-115">Дополнительные возможности см. в [раздел Создание общего почтового ящика.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="c83c2-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="c83c2-116">Добавление псевдонимов электронной почты</span><span class="sxs-lookup"><span data-stu-id="c83c2-116">Add email aliases to a user</span></span>
<span data-ttu-id="c83c2-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="c83c2-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="c83c2-118">Для этого необходимо [иметь разрешения](../add-users/about-admin-roles.md) администратора.</span><span class="sxs-lookup"><span data-stu-id="c83c2-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="c83c2-119">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="c83c2-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="c83c2-120">На странице **Активные пользователи** выберите имя пользователя> **управление псевдонимами электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="c83c2-120">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="c83c2-121">Вы не увидите этот параметр, если ему не назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="c83c2-121">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="c83c2-122">Выберите **+ Добавьте псевдоним** и введите новый псевдоним для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c83c2-122">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="c83c2-123">Если вы получаете сообщение об ошибке " Параметр не может быть найден, который совпадает с именем параметра **"EmailAddresses",** это означает, что для завершения настройки клиента или пользовательского домена, если вы недавно добавили его, нужно немного больше времени.</span><span class="sxs-lookup"><span data-stu-id="c83c2-123">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="c83c2-124">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="c83c2-124">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="c83c2-125">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="c83c2-125">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="c83c2-126">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="c83c2-126">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="c83c2-127">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="c83c2-127">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="c83c2-128">Псевдоним электронной почты должен закончиться доменом из выпадаемого списка.</span><span class="sxs-lookup"><span data-stu-id="c83c2-128">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="c83c2-129">Чтобы добавить другое доменное имя в список, см. в примере [Добавление домена в Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="c83c2-129">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="c83c2-130">После этого выберите сохранить **изменения.**</span><span class="sxs-lookup"><span data-stu-id="c83c2-130">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="c83c2-131">Подождите 24 часа, чтобы новые псевдонимы заполнялись в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c83c2-131">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="c83c2-132">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="c83c2-132">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="c83c2-133">Например, вся почта, отправленная на основной адрес Элизы Хоффман, Eliza@NodPublishers.com и ее псевдоним Sales@NodPublishers.com, будет отправлена в почтовый ящик Элизы.</span><span class="sxs-lookup"><span data-stu-id="c83c2-133">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="c83c2-134">**Когда пользователь отвечает, адрес *From* будет зависеть от клиента Outlook. Outlook в Интернете будет использовать псевдоним, по которому было получено сообщение (мы назовем это принципом пин-понга). Рабочий стол Outlook будет использовать ее основной псевдоним электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="c83c2-134">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="c83c2-135">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в почтовый ящик Eliza.</span><span class="sxs-lookup"><span data-stu-id="c83c2-135">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="c83c2-136">Когда Элиза отвечает на сообщение с помощью рабочего стола Outlook, ее основной электронный адрес будет отображаться как Eliza@NodPublishers.com, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="c83c2-136">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="c83c2-137">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="c83c2-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="c83c2-138">На странице **Активные пользователи** выберите нужного пользователя.</span><span class="sxs-lookup"><span data-stu-id="c83c2-138">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="c83c2-139">Рядом с **имям пользователя / Псевдонимы** электронной почты , выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="c83c2-139">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="c83c2-140">Если вы получаете сообщение об ошибке " Параметр не может быть найден, который совпадает с именем параметра **"EmailAddresses",** это означает, что для завершения настройки клиента или пользовательского домена, если вы недавно добавили его, нужно немного больше времени.</span><span class="sxs-lookup"><span data-stu-id="c83c2-140">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="c83c2-141">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="c83c2-141">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="c83c2-142">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="c83c2-142">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="c83c2-143">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="c83c2-143">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="c83c2-144">В текстовом поле **под псевдонимом** введите первую часть нового псевдонима электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c83c2-144">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="c83c2-145">Если вы добавили в Microsoft 365 собственный домен, его можно выбрать для нового псевдонима в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="c83c2-145">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="c83c2-146">Затем нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c83c2-146">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c83c2-147">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="c83c2-147">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="c83c2-148">Псевдоним электронной почты должен закончиться доменом из выпадаемого списка.</span><span class="sxs-lookup"><span data-stu-id="c83c2-148">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="c83c2-149">Чтобы добавить другое доменное имя в список, см. в примере [Добавление домена в Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="c83c2-149">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="c83c2-150">Когда все будет готово, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c83c2-150">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="c83c2-151">Подождите 24 часа, чтобы новые псевдонимы заполнялись в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c83c2-151">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="c83c2-152">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="c83c2-152">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="c83c2-153">Например, вся почта, отправленная на основной адрес Элизы Хоффман, Eliza@NodPublishers.com и ее псевдоним Sales@NodPublishers.com, будет отправлена в почтовый ящик Элизы.</span><span class="sxs-lookup"><span data-stu-id="c83c2-153">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="c83c2-154">**Когда пользователь отвечает, адрес *From* будет зависеть от клиента Outlook. Outlook в Интернете будет использовать псевдоним, по которому было получено сообщение (мы назовем это принципом пин-понга). Рабочий стол Outlook будет использовать ее основной псевдоним электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="c83c2-154">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="c83c2-155">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в почтовый ящик Eliza.</span><span class="sxs-lookup"><span data-stu-id="c83c2-155">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="c83c2-156">Когда Элиза отвечает на сообщение с помощью рабочего стола Outlook, ее основной электронный адрес будет отображаться как Eliza@NodPublishers.com, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="c83c2-156">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c83c2-157">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="c83c2-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="c83c2-158">На странице **Активные пользователи** выберите нужного пользователя.</span><span class="sxs-lookup"><span data-stu-id="c83c2-158">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="c83c2-159">Рядом с **имям пользователя / Псевдонимы** электронной почты , выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="c83c2-159">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="c83c2-160">Если вы получаете сообщение об ошибке " Параметр не может быть найден, который совпадает с именем параметра **"EmailAddresses",** это означает, что для завершения настройки клиента или пользовательского домена, если вы недавно добавили его, нужно немного больше времени.</span><span class="sxs-lookup"><span data-stu-id="c83c2-160">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="c83c2-161">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="c83c2-161">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="c83c2-162">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="c83c2-162">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="c83c2-163">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="c83c2-163">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="c83c2-164">В текстовом поле **под псевдонимом** введите первую часть нового псевдонима электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c83c2-164">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="c83c2-165">Если вы добавили в Microsoft 365 собственный домен, его можно выбрать для нового псевдонима в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="c83c2-165">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="c83c2-166">Затем нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c83c2-166">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c83c2-167">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="c83c2-167">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="c83c2-168">Псевдоним электронной почты должен закончиться доменом из выпадаемого списка.</span><span class="sxs-lookup"><span data-stu-id="c83c2-168">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="c83c2-169">Чтобы добавить другое доменное имя в список, см. в примере [Добавление домена в Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="c83c2-169">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="c83c2-170">Когда все будет готово, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c83c2-170">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="c83c2-171">Подождите 24 часа, чтобы новые псевдонимы заполнялись в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c83c2-171">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="c83c2-172">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="c83c2-172">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="c83c2-173">Например, вся почта, отправленная на основной адрес Элизы Хоффман, Eliza@NodPublishers.com и ее псевдоним Sales@NodPublishers.com, будет отправлена в почтовый ящик Элизы.</span><span class="sxs-lookup"><span data-stu-id="c83c2-173">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="c83c2-174">**Когда пользователь отвечает, адрес *From* будет зависеть от клиента Outlook. Outlook в Интернете будет использовать псевдоним, по которому было получено сообщение (мы назовем это принципом пин-понга). Рабочий стол Outlook будет использовать ее основной псевдоним электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="c83c2-174">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="c83c2-175">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в почтовый ящик Eliza.</span><span class="sxs-lookup"><span data-stu-id="c83c2-175">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="c83c2-176">Когда Элиза отвечает на сообщение с помощью рабочего стола Outlook, ее основной электронный адрес будет отображаться как Eliza@NodPublishers.com, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="c83c2-176">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="c83c2-177">Вы получаете "Параметр не может быть найден, который соответствует имени параметра EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="c83c2-177">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="c83c2-178">Если вы получаете сообщение об ошибке " Параметр не может быть найден, который совпадает с именем параметра **EmailAddresses**" это означает, что для завершения настройки клиента или пользовательского домена, если вы недавно добавили его, нужно немного больше времени.</span><span class="sxs-lookup"><span data-stu-id="c83c2-178">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="c83c2-179">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="c83c2-179">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="c83c2-180">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="c83c2-180">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="c83c2-181">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="c83c2-181">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="c83c2-182">Вы приобрели подписку у GoDaddy или другого партнера?</span><span class="sxs-lookup"><span data-stu-id="c83c2-182">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="c83c2-183">Если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="c83c2-183">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>

## <a name="sending-email-from-the-proxy-address-easily"></a><span data-ttu-id="c83c2-184">Отправка электронной почты с прокси-адреса легко</span><span class="sxs-lookup"><span data-stu-id="c83c2-184">Sending email from the proxy address easily</span></span>

<span data-ttu-id="c83c2-185">В апреле 2021 г. выходит новая функция, которая позволяет пользователям легко отправлять из псевдонимов при использовании Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="c83c2-185">A new feature is rolling out in April 2021 that allows users to send from their aliases easily when using Outlook on the web.</span></span> <span data-ttu-id="c83c2-186">Когда функция выходит в аренду, где администратор клиента использует этот кодлет, пользователи в аренде получат доступ к списку почтовых ящиков, где каждая запись соответствует псевдониму в параметрах `Set-OrganizationConfig -SendFromAliasEnabled $true` Outlook.</span><span class="sxs-lookup"><span data-stu-id="c83c2-186">When the feature rolls out to a tenancy where the tenant admin uses the `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, users within the tenancy will get access to a list of checkboxes where each entry corresponds to an alias in their Outlook settings.</span></span> <span data-ttu-id="c83c2-187">При выборе псевдонима он появится в формате From dropdown в форме Compose.</span><span class="sxs-lookup"><span data-stu-id="c83c2-187">Selecting an alias will make it appear in the From dropdown in the Compose form.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="c83c2-188">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c83c2-188">Related articles</span></span>

[<span data-ttu-id="c83c2-189">Отправка почты с другого адреса</span><span class="sxs-lookup"><span data-stu-id="c83c2-189">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="c83c2-190">Изменение имени пользователя и адреса электронной почты</span><span class="sxs-lookup"><span data-stu-id="c83c2-190">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
