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
description: 'Узнайте, как можно использовать несколько адресов электронной почты, называемых псевдонимом электронной почты, связанных с Microsoft 365 учетной записью бизнеса. '
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572109"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="080b8-103">Добавление дополнительных псевдонимов электронной почты для пользователя</span><span class="sxs-lookup"><span data-stu-id="080b8-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="080b8-104">Эта статья для администраторов Microsoft 365, у которых есть бизнес-подписки.</span><span class="sxs-lookup"><span data-stu-id="080b8-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="080b8-105">Она не предназначена для домашних пользователей.</span><span class="sxs-lookup"><span data-stu-id="080b8-105">It's not for home users.</span></span>
  
<span data-ttu-id="080b8-106">Основной адрес электронной почты в Microsoft 365 обычно является адресом электронной почты, который был назначен пользователю при его учетной записи.</span><span class="sxs-lookup"><span data-stu-id="080b8-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="080b8-107">Когда пользователь отправляет сообщения другим людям, именно этот адрес, как правило, указывается в поле  *От*  .</span><span class="sxs-lookup"><span data-stu-id="080b8-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="080b8-108">Они также могут иметь несколько адресов электронной почты, связанных с их Microsoft 365 для учетной записи бизнеса.</span><span class="sxs-lookup"><span data-stu-id="080b8-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="080b8-109">Дополнительные адреса называются псевдонимами.</span><span class="sxs-lookup"><span data-stu-id="080b8-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="080b8-110">Например, предположим, что у Дженны есть адрес электронной почты jenna@contosoco.com, но она также хочет получать электронную почту в jen@contosoco.com, так как некоторые люди ссылаются на нее по этому имени.</span><span class="sxs-lookup"><span data-stu-id="080b8-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="080b8-111">Вы можете создать псевдонимы для нее, чтобы оба адреса электронной почты перейти в почтовый ящик Дженны.</span><span class="sxs-lookup"><span data-stu-id="080b8-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
  
<span data-ttu-id="080b8-p104">Для одного пользователя можно создать до 400 псевдонимов. Дополнительные расходы и лицензии не требуются.</span><span class="sxs-lookup"><span data-stu-id="080b8-p104">You can create up to 400 aliases for a user. No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="080b8-114">Если вы хотите, чтобы несколько людей могли управлять электронной почтой, отправленной на один адрес электронной почты info@NodPublishers.com или sales@NodPublishers.com, создайте общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="080b8-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="080b8-115">Дополнительные возможности см. в [раздел Создание общего почтового ящика.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="080b8-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="080b8-116">Добавление псевдонимов электронной почты</span><span class="sxs-lookup"><span data-stu-id="080b8-116">Add email aliases to a user</span></span>

<span data-ttu-id="080b8-117">Для этого необходимо [иметь разрешения](../add-users/about-admin-roles.md) администратора.</span><span class="sxs-lookup"><span data-stu-id="080b8-117">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

1. <span data-ttu-id="080b8-118">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="080b8-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="080b8-119">На странице **Активные пользователи** выберите имя пользователя > имя пользователя **и электронную почту.**</span><span class="sxs-lookup"><span data-stu-id="080b8-119">On the **Active Users** page, select the user > **Manage username and email**.</span></span> <span data-ttu-id="080b8-120">Вы не увидите этот параметр, если ему не назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="080b8-120">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="080b8-121">Выберите **+ Добавьте псевдоним** и введите новый псевдоним для пользователя.</span><span class="sxs-lookup"><span data-stu-id="080b8-121">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="080b8-122">Если вы получаете сообщение об ошибке " Параметр не может быть найден, который совпадает с именем параметра **"EmailAddresses",** это означает, что для завершения настройки клиента или пользовательского домена, если вы недавно добавили его, нужно немного больше времени.</span><span class="sxs-lookup"><span data-stu-id="080b8-122">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="080b8-123">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="080b8-123">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="080b8-124">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="080b8-124">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="080b8-125">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="080b8-125">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="080b8-126">если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="080b8-126">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="080b8-127">Псевдоним электронной почты должен закончиться доменом из выпадаемого списка.</span><span class="sxs-lookup"><span data-stu-id="080b8-127">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="080b8-128">Чтобы добавить другое доменное имя в список, см. в примере [Добавление домена в Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="080b8-128">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="080b8-129">После этого выберите сохранить **изменения.**</span><span class="sxs-lookup"><span data-stu-id="080b8-129">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="080b8-130">Подождите 24 часа, пока новые псевдонимы будут заполняться во Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="080b8-130">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="080b8-131">Теперь у пользователя будет основной адрес и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="080b8-131">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="080b8-132">Например, вся почта, отправленная на основной адрес Элизы Хоффман, Eliza@NodPublishers.com и ее псевдоним Sales@NodPublishers.com, будет отправлена в почтовый ящик Элизы.</span><span class="sxs-lookup"><span data-stu-id="080b8-132">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="080b8-133">**Когда пользователь отвечает, адрес *From* будет зависеть от Outlook клиента. Outlook в Интернете будет использовать псевдоним, по которому было получено сообщение (мы назовем это принципом пин-понга). Outlook рабочего стола будет использовать ее основной псевдоним электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="080b8-133">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="080b8-134">Например, предположим, что сообщение отправляется в Sales@NodPublishers.com и поступает в почтовый ящик Eliza.</span><span class="sxs-lookup"><span data-stu-id="080b8-134">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="080b8-135">Когда Элиза отвечает на сообщение с Outlook рабочего стола, ее основной адрес электронной почты будет отображаться как Eliza@NodPublishers.com, а не Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="080b8-135">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="080b8-136">Вы получаете "Параметр не может быть найден, который соответствует имени параметра EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="080b8-136">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>

<span data-ttu-id="080b8-137">Если вы получаете сообщение об ошибке " Параметр не может быть найден, который совпадает с именем параметра **EmailAddresses**" это означает, что для завершения настройки клиента или пользовательского домена, если вы недавно добавили его, нужно немного больше времени.</span><span class="sxs-lookup"><span data-stu-id="080b8-137">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="080b8-138">На настройку может потребоваться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="080b8-138">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="080b8-139">Дождитесь ее окончания, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="080b8-139">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="080b8-140">Если проблема сохранится, обратитесь в службу поддержки, и ее специалисты выполнят для вас полную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="080b8-140">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="080b8-141">Вы приобрели подписку у GoDaddy или другого партнера?</span><span class="sxs-lookup"><span data-stu-id="080b8-141">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="080b8-142">Если вы приобрели подписку у GoDaddy или другого партнера, для настройки нового псевдонима в качестве основного следует использовать консоль управления GoDaddy или партнера.</span><span class="sxs-lookup"><span data-stu-id="080b8-142">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>

## <a name="sending-email-from-the-proxy-address-easily"></a><span data-ttu-id="080b8-143">Отправка электронной почты с прокси-адреса легко</span><span class="sxs-lookup"><span data-stu-id="080b8-143">Sending email from the proxy address easily</span></span>

<span data-ttu-id="080b8-144">В апреле 2021 г. выходит новая функция, которая позволяет пользователям легко отправлять их псевдонимы при использовании Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="080b8-144">A new feature is rolling out in April 2021 that allows users to send from their aliases easily when using Outlook on the web.</span></span> <span data-ttu-id="080b8-145">Когда функция выходит в аренду, где администратор клиента использует этот кодлет, пользователи в аренде получат доступ к списку контрольных ящиков, где каждая запись соответствует псевдониму в Outlook `Set-OrganizationConfig -SendFromAliasEnabled $true` параметров.</span><span class="sxs-lookup"><span data-stu-id="080b8-145">When the feature rolls out to a tenancy where the tenant admin uses the `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, users within the tenancy will get access to a list of checkboxes where each entry corresponds to an alias in their Outlook settings.</span></span> <span data-ttu-id="080b8-146">При выборе псевдонима он появится в формате From dropdown в форме Compose.</span><span class="sxs-lookup"><span data-stu-id="080b8-146">Selecting an alias will make it appear in the From dropdown in the Compose form.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="080b8-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="080b8-147">Related content</span></span>

<span data-ttu-id="080b8-148">[Отправка электронной почты с другого адреса](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (статья)</span><span class="sxs-lookup"><span data-stu-id="080b8-148">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>

<span data-ttu-id="080b8-149">[Изменение имени пользователя и адреса электронной почты](../add-users/change-a-user-name-and-email-address.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="080b8-149">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>

<span data-ttu-id="080b8-150">[Настройка переадресации электронной почты в Microsoft 365](configure-email-forwarding.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="080b8-150">[Configure email forwarding in Microsoft 365](configure-email-forwarding.md) (article)</span></span>
