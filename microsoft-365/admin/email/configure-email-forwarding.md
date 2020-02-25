---
title: Настройка переадресации электронной почты в Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Настройка переадресации электронной почты на одну или несколько учетных записей электронной почты с помощью Office365.
ms.openlocfilehash: b6ad4032748c35db8e8c18b609915aef4231cb6c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255274"
---
# <a name="configure-email-forwarding-in-office-365"></a><span data-ttu-id="085a5-103">Настройка переадресации электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="085a5-103">Configure email forwarding in Office 365</span></span>
  
<span data-ttu-id="085a5-p101">Администратору Office 365 может потребоваться настроить переадресацию электронной почты для почтового ящика пользователя. Переадресация позволяет пересылать сообщения, отправленные в почтовый ящик пользователя, в другой почтовый ящик в организации или за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="085a5-p101">As the admin of an Office 365 organization, you might have company requirements to set up email forwarding for a user's mailbox. Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="085a5-106">Настройка переадресации электронной почты</span><span class="sxs-lookup"><span data-stu-id="085a5-106">Configure email forwarding</span></span>

 <span data-ttu-id="085a5-107">Перед настройкой переадресации электронной почты Обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="085a5-107">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="085a5-108">После настройки переадресации электронной почты будут фовардед только **новые** сообщения, отправленные в почтовый ящик *из* почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="085a5-108">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="085a5-109">Для переадресации электронной почты необходимо, чтобы у учетной записи " *от* " была лицензия.</span><span class="sxs-lookup"><span data-stu-id="085a5-109">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="085a5-110">Если вы настраиваете переадресацию электронной почты, так как пользователь оставил вашу организацию, другой вариант заключается в [преобразовании его почтового ящика в общий почтовый ящик](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="085a5-110">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="085a5-111">Это позволит нескольким людям получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="085a5-111">This way several people can access it.</span></span> <span data-ttu-id="085a5-112">Однако общий почтовый ящик не может превышать 50 ГБ.</span><span class="sxs-lookup"><span data-stu-id="085a5-112">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="085a5-113">Для выполнения этих действий необходимо быть администратором Exchange или глобальным администратором в Office 365.</span><span class="sxs-lookup"><span data-stu-id="085a5-113">You must be an Exchange administrator or Global administrator in Office 365 to do these steps.</span></span> <span data-ttu-id="085a5-114">Для получения дополнительных сведений ознакомьтесь с разделом ["роли администратора"](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="085a5-114">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="085a5-115">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="085a5-115">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="085a5-116">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="085a5-116">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="085a5-117">Выберите имя пользователя, для которого необходимо переслать сообщение, чтобы открыть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="085a5-117">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="085a5-118">На вкладке **почта** выберите **Управление переадресацией электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="085a5-118">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="085a5-119">На странице переадресация электронной почты выберите **Переслать все сообщения, отправленные в этот почтовый ящик**, введите адрес переадресации и выберите, следует ли хранить копию пересылаемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="085a5-119">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="085a5-120">Если вы не видите этот параметр, убедитесь, что учетной записи пользователя назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="085a5-120">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="085a5-121">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="085a5-121">Select **Save changes**.</span></span>
    
    <span data-ttu-id="085a5-122">**Чтобы переслать на несколько адресов электронной почты**, можно попросить пользователя настроить правило в Outlook для пересылки по адресам.</span><span class="sxs-lookup"><span data-stu-id="085a5-122">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="085a5-123">Чтобы узнать больше, ознакомьтесь [со статьей использование правил для автоматической пересылки сообщений](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="085a5-123">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="085a5-124">В центре администрирования [Создайте группу рассылки](../setup/create-distribution-lists.md), [добавьте в нее адреса](add-user-or-contact-to-distribution-list.md), а затем настройте перенаправление на адрес списка рассылки, выполнив инструкции, приведенные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="085a5-124">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="085a5-125">Не удаляйте учетную запись пользователя, который пересылается или удаляет лицензию.</span><span class="sxs-lookup"><span data-stu-id="085a5-125">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="085a5-126">В противном случае переадресация электронной почты прекратится.</span><span class="sxs-lookup"><span data-stu-id="085a5-126">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="085a5-127">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="085a5-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="085a5-128">Выберите имя пользователя, для которого необходимо переслать сообщение, чтобы открыть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="085a5-128">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="085a5-129">Разверните узел **Параметры почты**, а затем в разделе **переадресация электронной почты** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="085a5-129">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="085a5-130">На странице переадресация электронной почты установите переключатель в значение **вкл**., введите адрес перенаправления и выберите, нужно ли хранить копию пересылаемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="085a5-130">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="085a5-131">Если вы не видите этот параметр, убедитесь, что учетной записи пользователя назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="085a5-131">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="085a5-132">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="085a5-132">Select **Save**.</span></span>
    
    <span data-ttu-id="085a5-133">**Чтобы переслать на несколько адресов электронной почты**, можно попросить пользователя настроить правило в Outlook для пересылки по адресам.</span><span class="sxs-lookup"><span data-stu-id="085a5-133">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="085a5-134">Чтобы узнать больше, ознакомьтесь [со статьей использование правил для автоматической пересылки сообщений](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="085a5-134">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="085a5-135">В центре администрирования [Создайте группу рассылки](../setup/create-distribution-lists.md), [добавьте в нее адреса](add-user-or-contact-to-distribution-list.md), а затем настройте перенаправление на адрес списка рассылки, выполнив инструкции, приведенные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="085a5-135">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="085a5-136">Не удаляйте учетную запись пользователя, который пересылается или удаляет лицензию.</span><span class="sxs-lookup"><span data-stu-id="085a5-136">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="085a5-137">В противном случае переадресация электронной почты прекратится.</span><span class="sxs-lookup"><span data-stu-id="085a5-137">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="085a5-138">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="085a5-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="085a5-139">Выберите имя пользователя, для которого необходимо переслать сообщение, чтобы открыть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="085a5-139">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="085a5-140">Разверните узел **Параметры почты**, а затем в разделе **переадресация электронной почты** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="085a5-140">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="085a5-141">На странице переадресация электронной почты установите переключатель в значение **вкл**., введите адрес перенаправления и выберите, нужно ли хранить копию пересылаемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="085a5-141">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="085a5-142">Если вы не видите этот параметр, убедитесь, что учетной записи пользователя назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="085a5-142">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="085a5-143">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="085a5-143">Select **Save**.</span></span>
    
    <span data-ttu-id="085a5-144">**Чтобы переслать на несколько адресов электронной почты**, можно попросить пользователя настроить правило в Outlook для пересылки по адресам.</span><span class="sxs-lookup"><span data-stu-id="085a5-144">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="085a5-145">Чтобы узнать больше, ознакомьтесь [со статьей использование правил для автоматической пересылки сообщений](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="085a5-145">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="085a5-146">В центре администрирования [Создайте группу рассылки](../setup/create-distribution-lists.md), [добавьте в нее адреса](add-user-or-contact-to-distribution-list.md), а затем настройте перенаправление на адрес списка рассылки, выполнив инструкции, приведенные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="085a5-146">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="085a5-147">Не удаляйте учетную запись пользователя, который пересылается или удаляет лицензию.</span><span class="sxs-lookup"><span data-stu-id="085a5-147">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="085a5-148">В противном случае переадресация электронной почты прекратится.</span><span class="sxs-lookup"><span data-stu-id="085a5-148">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
