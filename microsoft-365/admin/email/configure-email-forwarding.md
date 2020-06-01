---
title: Настройка переадресации электронной почты
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Настройка переадресации электронной почты на одну или несколько учетных записей электронной почты с помощью Office365.
ms.openlocfilehash: 3ce82d514e1342ac6110ca74106477e3cf7820cb
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432305"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="fd0b6-103">Настройка переадресации электронной почты</span><span class="sxs-lookup"><span data-stu-id="fd0b6-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="fd0b6-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-104">The admin center is changing.</span></span> <span data-ttu-id="fd0b6-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="fd0b6-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="fd0b6-106">Администратор организации может иметь требования к настройке переадресации электронной почты для почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="fd0b6-107">Переадресация позволяет пересылать сообщения, отправленные в почтовый ящик пользователя, в другой почтовый ящик в организации или за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="fd0b6-108">Настройка переадресации электронной почты</span><span class="sxs-lookup"><span data-stu-id="fd0b6-108">Configure email forwarding</span></span>

 <span data-ttu-id="fd0b6-109">Перед настройкой переадресации электронной почты Обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="fd0b6-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="fd0b6-110">После настройки переадресации электронной почты будут фовардед только **новые** сообщения, отправленные в почтовый ящик *из* почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="fd0b6-111">Для переадресации электронной почты необходимо, чтобы у учетной записи " *от* " была лицензия.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="fd0b6-112">Если вы настраиваете переадресацию электронной почты, так как пользователь оставил вашу организацию, другой вариант заключается в [преобразовании его почтового ящика в общий почтовый ящик](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="fd0b6-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="fd0b6-113">Это позволит нескольким людям получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-113">This way several people can access it.</span></span> <span data-ttu-id="fd0b6-114">Однако общий почтовый ящик не может превышать 50 ГБ.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="fd0b6-115">Для выполнения этих действий необходимо быть администратором Exchange или глобальным администратором в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="fd0b6-116">Для получения дополнительных сведений ознакомьтесь с разделом ["роли администратора"](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fd0b6-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fd0b6-117">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-117">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="fd0b6-118">Выберите имя пользователя, для которого необходимо переслать сообщение, чтобы открыть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-118">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="fd0b6-119">На вкладке **почта** выберите **Управление переадресацией электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-119">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="fd0b6-120">На странице переадресация электронной почты выберите **Переслать все сообщения, отправленные в этот почтовый ящик**, введите адрес переадресации и выберите, следует ли хранить копию пересылаемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="fd0b6-121">Если вы не видите этот параметр, убедитесь, что учетной записи пользователя назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="fd0b6-122">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-122">Select **Save changes**.</span></span>
    
    <span data-ttu-id="fd0b6-123">**Чтобы переслать на несколько адресов электронной почты**, можно попросить пользователя настроить правило в Outlook для пересылки по адресам.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="fd0b6-124">Чтобы узнать больше, ознакомьтесь [со статьей использование правил для автоматической пересылки сообщений](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="fd0b6-124">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="fd0b6-125">В центре администрирования [Создайте группу рассылки](../setup/create-distribution-lists.md), [добавьте в нее адреса](add-user-or-contact-to-distribution-list.md), а затем настройте перенаправление на адрес списка рассылки, выполнив инструкции, приведенные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="fd0b6-126">Не удаляйте учетную запись пользователя, который пересылается или удаляет лицензию.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="fd0b6-127">В противном случае переадресация электронной почты прекратится.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-127">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="fd0b6-128">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="fd0b6-129">Выберите имя пользователя, для которого необходимо переслать сообщение, чтобы открыть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-129">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="fd0b6-130">Разверните узел **Параметры почты**, а затем в разделе **переадресация электронной почты** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-130">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="fd0b6-131">На странице переадресация электронной почты установите переключатель в значение **вкл**., введите адрес перенаправления и выберите, нужно ли хранить копию пересылаемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-131">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="fd0b6-132">Если вы не видите этот параметр, убедитесь, что учетной записи пользователя назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-132">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="fd0b6-133">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-133">Select **Save**.</span></span>
    
    <span data-ttu-id="fd0b6-134">**Чтобы переслать на несколько адресов электронной почты**, можно попросить пользователя настроить правило в Outlook для пересылки по адресам.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-134">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="fd0b6-135">Чтобы узнать больше, ознакомьтесь [со статьей использование правил для автоматической пересылки сообщений](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="fd0b6-135">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="fd0b6-136">В центре администрирования [Создайте группу рассылки](../setup/create-distribution-lists.md), [добавьте в нее адреса](add-user-or-contact-to-distribution-list.md), а затем настройте перенаправление на адрес списка рассылки, выполнив инструкции, приведенные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-136">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="fd0b6-137">Не удаляйте учетную запись пользователя, который пересылается или удаляет лицензию.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-137">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="fd0b6-138">В противном случае переадресация электронной почты прекратится.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-138">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="fd0b6-139">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="fd0b6-140">Выберите имя пользователя, для которого необходимо переслать сообщение, чтобы открыть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-140">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="fd0b6-141">Разверните узел **Параметры почты**, а затем в разделе **переадресация электронной почты** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-141">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="fd0b6-142">На странице переадресация электронной почты установите переключатель в значение **вкл**., введите адрес перенаправления и выберите, нужно ли хранить копию пересылаемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-142">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="fd0b6-143">Если вы не видите этот параметр, убедитесь, что учетной записи пользователя назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-143">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="fd0b6-144">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-144">Select **Save**.</span></span>
    
    <span data-ttu-id="fd0b6-145">**Чтобы переслать на несколько адресов электронной почты**, можно попросить пользователя настроить правило в Outlook для пересылки по адресам.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-145">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="fd0b6-146">Чтобы узнать больше, ознакомьтесь [со статьей использование правил для автоматической пересылки сообщений](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="fd0b6-146">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="fd0b6-147">В центре администрирования [Создайте группу рассылки](../setup/create-distribution-lists.md), [добавьте в нее адреса](add-user-or-contact-to-distribution-list.md), а затем настройте перенаправление на адрес списка рассылки, выполнив инструкции, приведенные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-147">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="fd0b6-148">Не удаляйте учетную запись пользователя, который пересылается или удаляет лицензию.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-148">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="fd0b6-149">В противном случае переадресация электронной почты прекратится.</span><span class="sxs-lookup"><span data-stu-id="fd0b6-149">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
