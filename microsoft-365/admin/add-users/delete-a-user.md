---
title: Удаление пользователя из организации
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
- SPO_Content
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Сведения об удалении учетной записи пользователя. Определите, что делать с электронной почтой пользователя, контентом OneDrive и следует ли оставить лицензию на продукт или прекратить ее оплату.
ms.openlocfilehash: a179915ae92def2a967dc86378346bb905c923e4
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049463"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="e7b24-104">Удаление пользователя из организации</span><span class="sxs-lookup"><span data-stu-id="e7b24-104">Delete a user from your organization</span></span>
  
||
|:-----|
|<span data-ttu-id="e7b24-105">**Вы хотите удалить *собственную* учетную запись пользователя Microsoft 365, которую вы используете на работе или учебном заведении? Чтобы выполнить эти действия, обратитесь в службу технической поддержки в вашей работе или в университетах.**</span><span class="sxs-lookup"><span data-stu-id="e7b24-105">**Looking for how to delete your *own* Microsoft 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>|
   
## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="e7b24-106">Что нужно знать об удалении пользователей?</span><span class="sxs-lookup"><span data-stu-id="e7b24-106">What you need to know about deleting users</span></span>

- <span data-ttu-id="e7b24-107">Удалять учетные записи пользователей могут только те пользователи, у которых есть разрешения [Microsoft 365 на глобальном администраторе](about-admin-roles.md) или управление пользователями для организации или учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="e7b24-107">Only people who have [Microsoft 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span> 
    
- <span data-ttu-id="e7b24-108">Вы можете [восстановить](restore-user.md) ее в течение 30 дней, пока данные не удалены окончательно.</span><span class="sxs-lookup"><span data-stu-id="e7b24-108">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span> 
    
- <span data-ttu-id="e7b24-p102">Если вы хотите сохранить данные пользователя из OneDrive, перенесите их в другое место. Это можно сделать в течение 30 дней после удаления учетной записи. См. статью [Получение доступа к данным бывшего пользователя и создание их резервной копии](get-access-to-and-back-up-a-former-user-s-data.md). Файлы пользователя из SharePoint перемещать не нужно, они останутся вам доступны.</span><span class="sxs-lookup"><span data-stu-id="e7b24-p102">If you want to keep the user's OneDrive data, move it to a different location. You can even do this up to 30 days after deleting the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md). You don't need to move their SharePoint files; you'll still have access to them.</span></span>
    
- <span data-ttu-id="e7b24-p103">Если вы хотите сохранить электронную почту пользователя, перенесите ее в другое место **ПЕРЕД** удалением учетной записи. Если вы уже удалили учетную запись, в течение 30 дней ее можно восстановить, перенести данные электронной почты, а затем снова удалить. См. статью [Получение доступа к данным бывшего пользователя и создание их резервной копии](get-access-to-and-back-up-a-former-user-s-data.md).</span><span class="sxs-lookup"><span data-stu-id="e7b24-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
    
- <span data-ttu-id="e7b24-116">Если вы используете корпоративную подписку, например Office 365 корпоративный E3, вы можете сохранить данные почтового ящика удаленной учетной записи пользователя, переключив ее в *Неактивный почтовый ящик*.</span><span class="sxs-lookup"><span data-stu-id="e7b24-116">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="e7b24-117">Дополнительные сведения см в разделе [Manage Неактивные почтовые ящики в Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="e7b24-117">To learn more, see [Manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span>


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="e7b24-118">Глобальный администратор: Удаление пользователя, прекращение оплаты за лицензию и выбор действий, выполняемых с электронной почтой и контентом OneDrive</span><span class="sxs-lookup"><span data-stu-id="e7b24-118">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="e7b24-119">Если вы являетесь глобальным администратором, то при удалении пользователя Вы также можете предоставить другому пользователю доступ к своей электронной почте и выбрать, что делать с контентом OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e7b24-119">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span> 

  
### <a name="things-to-consider"></a><span data-ttu-id="e7b24-120">Важные факторы...</span><span class="sxs-lookup"><span data-stu-id="e7b24-120">Things to consider...</span></span>

<span data-ttu-id="e7b24-121">Прежде чем приступать к работе, подумайте о том, что вы хотите сделать с почтой пользователя и контентом OneDrive, и хотите ли вы оставить лицензию или прекратить ее оплату.</span><span class="sxs-lookup"><span data-stu-id="e7b24-121">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e7b24-122">Лицензии на продукты</span><span class="sxs-lookup"><span data-stu-id="e7b24-122">Product licenses</span></span>  <br/> |<span data-ttu-id="e7b24-123">Вы можете удалить лицензию у пользователя и удалить ее из ваших подписок, чтобы прекратить оплату за эту лицензию.</span><span class="sxs-lookup"><span data-stu-id="e7b24-123">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="e7b24-124">Если выбран этот параметр, лицензия будет автоматически удалена из ваших подписок.</span><span class="sxs-lookup"><span data-stu-id="e7b24-124">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="e7b24-125">**Вы не можете удалить лицензию** , если она была приобретена через партнера или корпоративного лицензирования.</span><span class="sxs-lookup"><span data-stu-id="e7b24-125">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="e7b24-126">Если вы оплачиваете годовой план или в середину цикла выставления счетов, вы не сможете удалить лицензию из подписки, пока не будет завершена ваша фиксация.</span><span class="sxs-lookup"><span data-stu-id="e7b24-126">If you are paying for an annual plan or if you are in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="e7b24-127">Контент OneDrive</span><span class="sxs-lookup"><span data-stu-id="e7b24-127">OneDrive content</span></span>  <br/> |<span data-ttu-id="e7b24-128">Если пользователь сохранил свои файлы в OneDrive, вы можете предоставить другому пользователю доступ к этим файлам.</span><span class="sxs-lookup"><span data-stu-id="e7b24-128">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="e7b24-129">Необходимо переместить файлы, которые необходимо сохранить, в течение срока хранения, настроенного для файлов OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e7b24-129">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="e7b24-130">**По умолчанию срок хранения составляет 30 дней.**</span><span class="sxs-lookup"><span data-stu-id="e7b24-130">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="e7b24-131">Если вы не перемещаете файлы в течение срока хранения после удаления пользователя, контент OneDrive будет окончательно удален.</span><span class="sxs-lookup"><span data-stu-id="e7b24-131">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="e7b24-132">Чтобы увеличить число дней хранения файлов OneDrive для удаленных учетных записей, ознакомьтесь со статьей [Настройка хранения onedrive для удаленных пользователей](https://docs.microsoft.com/onedrive/set-retention).</span><span class="sxs-lookup"><span data-stu-id="e7b24-132">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](https://docs.microsoft.com/onedrive/set-retention).</span></span>  <br/><br/> <span data-ttu-id="e7b24-133">**Важно!**</span><span class="sxs-lookup"><span data-stu-id="e7b24-133">**Important!**</span></span> <span data-ttu-id="e7b24-134">Если удаленный пользователь использовал персональный компьютер для загрузки файлов из SharePoint и OneDrive, вы не можете очистить эти файлы, хранящиеся на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="e7b24-134">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="e7b24-135">Они продолжат доступ ко всем файлам, синхронизированным из OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e7b24-135">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="e7b24-136">Электронная почта</span><span class="sxs-lookup"><span data-stu-id="e7b24-136">Email</span></span>  <br/> | <span data-ttu-id="e7b24-137">Предоставление другому пользователю доступа к почтовому ящику удаленного пользователя приводит к преобразованию почтового ящика удаленного пользователя в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="e7b24-137">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="e7b24-138">После этого новый владелец почтового ящика может получить доступ к почтовому ящику и монитору для новых сообщений.</span><span class="sxs-lookup"><span data-stu-id="e7b24-138">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="e7b24-139">Кроме того, вы можете использовать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e7b24-139">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="e7b24-140">Измените отображаемое имя — мы рекомендуем изменить отображаемое имя так, чтобы оно было легко определять общий почтовый ящик в списке Активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="e7b24-140">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the Active users list.</span></span>  <br/>  <span data-ttu-id="e7b24-141">Включите автоматические ответы — мы уже написали автоматический ответ.</span><span class="sxs-lookup"><span data-stu-id="e7b24-141">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="e7b24-142">Вы можете отправлять различные автоматические ответы пользователям в вашей организации и людям за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e7b24-142">You can send a different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="e7b24-143">Очистка псевдонимов псевдонимов — дополнительные адреса электронной почты для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e7b24-143">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="e7b24-144">Некоторые организации не используют их, поэтому если у вас нет необходимости выполнять какие-либо действия здесь.</span><span class="sxs-lookup"><span data-stu-id="e7b24-144">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="e7b24-145">Если у пользователя есть псевдонимы, рекомендуем удалить их, чтобы можно было повторно использовать эти адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e7b24-145">If the user does have aliases, we recommend removing them so that you can re-use those email addresses.</span></span> <span data-ttu-id="e7b24-146">В противном случае вы не сможете повторно использовать эти адреса электронной почты, пока не пройдет срок хранения для удаленных почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="e7b24-146">Otherwise, you can't re-use those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="e7b24-147">По умолчанию удаленный почтовый ящик можно восстановить в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="e7b24-147">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="e7b24-148">Дополнительные сведения см. [в статье Удаление или восстановление почтовых ящиков пользователей в Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span><span class="sxs-lookup"><span data-stu-id="e7b24-148">For more information, see  [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="e7b24-149">Active Directory</span><span class="sxs-lookup"><span data-stu-id="e7b24-149">Active Directory</span></span>  <br/> |<span data-ttu-id="e7b24-150">Если ваша организация использует **службу Active Directory** , которая синхронизируется с Azure AD, необходимо удалить учетную запись пользователя из Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e7b24-150">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="e7b24-151">В Office 365 сделать это нельзя.</span><span class="sxs-lookup"><span data-stu-id="e7b24-151">You can't do it through Office 365.</span></span> <span data-ttu-id="e7b24-152">Инструкции приведены в разделе [Удаление учетной записи пользователя](https://go.microsoft.com/fwlink/p/?linkid=841808).</span><span class="sxs-lookup"><span data-stu-id="e7b24-152">For instructions, see [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808).</span></span>  <br/> |
   
### <a name="get-started"></a><span data-ttu-id="e7b24-153">Начало работы</span><span class="sxs-lookup"><span data-stu-id="e7b24-153">Get started</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e7b24-154">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="e7b24-154">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="e7b24-155">Так как руководство посвящено удалению пользователя, приведенные ниже инструкции помогут приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="e7b24-155">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e7b24-156">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="e7b24-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e7b24-157">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="e7b24-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e7b24-158">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="e7b24-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="e7b24-159">Выберите пользователя, которого нужно удалить, а затем нажмите кнопку **удалить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="e7b24-159">Select the user you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="e7b24-160">Администратор управления пользователями: Удаление одного или нескольких пользователей из Office 365</span><span class="sxs-lookup"><span data-stu-id="e7b24-160">User management admin: Delete one or more users from Office 365</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e7b24-161">Не удаляйте учетную запись пользователя, если [она была преобразована в общий почтовый ящик](../email/convert-user-mailbox-to-shared-mailbox.md) , или если вы настроили переадресацию электронной почты на эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="e7b24-161">Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account.</span></span> <span data-ttu-id="e7b24-162">Этим функциям по-прежнему нужна учетная запись.</span><span class="sxs-lookup"><span data-stu-id="e7b24-162">Those functions still need the account.</span></span> <span data-ttu-id="e7b24-163">Для общего почтового ящика не требуется лицензия.</span><span class="sxs-lookup"><span data-stu-id="e7b24-163">A shared mailbox doesn't require a license.</span></span> <span data-ttu-id="e7b24-164">Если вы преобразовали учетную запись в общий почтовый ящик, вы можете [прекратить оплату лицензии](#stop-paying-for-the-license).</span><span class="sxs-lookup"><span data-stu-id="e7b24-164">If you've converted the account to a shared mailbox you can [Stop paying for the license](#stop-paying-for-the-license).</span></span> <span data-ttu-id="e7b24-165">Если вы настроили переадресацию электронной почты для учетной записи, вы не можете удалить лицензию.</span><span class="sxs-lookup"><span data-stu-id="e7b24-165">If you've set up email forwarding on the account, you can't remove the license.</span></span> <span data-ttu-id="e7b24-166">Это приведет к остановке переадресации электронной почты и отключению почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="e7b24-166">Doing so will stop email forwarding and deactivate the mailbox.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="e7b24-167">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="e7b24-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="e7b24-168">Выберите имена пользователей, которых нужно удалить, нажмите кнопку **Дополнительные параметры** (**...**), а затем выберите команду **удалить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="e7b24-168">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="e7b24-169">Несмотря на то, что вы удалили учетную запись пользователя, **вы по-прежнему оплачиваете лицензию**.</span><span class="sxs-lookup"><span data-stu-id="e7b24-169">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="e7b24-170">Для прекращения оплаты лицензии обратитесь к следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="e7b24-170">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="e7b24-171">Кроме того, вы можете назначить лицензию другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="e7b24-171">Or, you can assign the license to another user.</span></span> <span data-ttu-id="e7b24-172">Он не будет назначен пользователю автоматически.</span><span class="sxs-lookup"><span data-stu-id="e7b24-172">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e7b24-173">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="e7b24-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="e7b24-174">Выберите имена пользователей, которых нужно удалить, а затем в области **массовые действия** выберите команду **удалить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="e7b24-174">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="e7b24-175">Несмотря на то, что вы удалили учетную запись пользователя, **вы по-прежнему оплачиваете лицензию**.</span><span class="sxs-lookup"><span data-stu-id="e7b24-175">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="e7b24-176">Для прекращения оплаты лицензии обратитесь к следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="e7b24-176">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="e7b24-177">Кроме того, вы можете назначить лицензию другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="e7b24-177">Or, you can assign the license to another user.</span></span> <span data-ttu-id="e7b24-178">Он не будет назначен пользователю автоматически.</span><span class="sxs-lookup"><span data-stu-id="e7b24-178">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e7b24-179">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="e7b24-179">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="e7b24-180">Выберите имена пользователей, которых нужно удалить, а затем в области **массовые действия** выберите команду **удалить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="e7b24-180">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="e7b24-181">Несмотря на то, что вы удалили учетную запись пользователя, **вы по-прежнему оплачиваете лицензию**.</span><span class="sxs-lookup"><span data-stu-id="e7b24-181">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="e7b24-182">Для прекращения оплаты лицензии обратитесь к следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="e7b24-182">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="e7b24-183">Кроме того, вы можете назначить лицензию другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="e7b24-183">Or, you can assign the license to another user.</span></span> <span data-ttu-id="e7b24-184">Он не будет назначен пользователю автоматически.</span><span class="sxs-lookup"><span data-stu-id="e7b24-184">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="e7b24-185">Прекращение оплаты лицензии</span><span class="sxs-lookup"><span data-stu-id="e7b24-185">Stop paying for the license</span></span>

<span data-ttu-id="e7b24-186">Сокращение числа лицензий — это отдельный шаг, который может выполняться только глобальным администратором или администратором выставления счетов.</span><span class="sxs-lookup"><span data-stu-id="e7b24-186">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="e7b24-187">В центре администрирования перейдите на страницу **выставление счетов** \> по <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">продуктам</a> .</span><span class="sxs-lookup"><span data-stu-id="e7b24-187">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span> <span data-ttu-id="e7b24-188">Если вы не видите этот параметр, вы не обладаете глобальными администраторами или администратором по выставлению счетов и не можете выполнить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="e7b24-188">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="e7b24-189">Выберите подписку (если у вас несколько пользователей), а затем выберите **Добавить/удалить лицензии** , чтобы удалить лицензию, чтобы она не выплачивается до приема другого человека.</span><span class="sxs-lookup"><span data-stu-id="e7b24-189">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="e7b24-190">Когда вы просматриваете шаги, чтобы добавить другого пользователя в свой бизнес, вам будет предложено купить лицензию одновременно с одним действием.</span><span class="sxs-lookup"><span data-stu-id="e7b24-190">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e7b24-191">В Центре администрирования выберите страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="e7b24-191">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="e7b24-192">Если вы не видите этот параметр, вы не обладаете глобальными администраторами или администратором по выставлению счетов и не можете выполнить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="e7b24-192">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="e7b24-193">Выберите подписку (если у вас несколько пользователей), а затем выберите **Добавить/удалить лицензии** , чтобы удалить лицензию, чтобы она не выплачивается до приема другого человека.</span><span class="sxs-lookup"><span data-stu-id="e7b24-193">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="e7b24-194">Когда вы просматриваете шаги, чтобы добавить другого пользователя в свой бизнес, вам будет предложено купить лицензию одновременно с одним действием.</span><span class="sxs-lookup"><span data-stu-id="e7b24-194">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e7b24-195">В Центре администрирования выберите страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="e7b24-195">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="e7b24-196">Если вы не видите этот параметр, вы не обладаете глобальными администраторами или администратором по выставлению счетов и не можете выполнить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="e7b24-196">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="e7b24-197">Выберите подписку (если у вас несколько пользователей), а затем выберите **Добавить/удалить лицензии** , чтобы удалить лицензию, чтобы она не выплачивается до приема другого человека.</span><span class="sxs-lookup"><span data-stu-id="e7b24-197">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="e7b24-198">Когда вы просматриваете шаги, чтобы добавить другого пользователя в свой бизнес, вам будет предложено купить лицензию одновременно с одним действием.</span><span class="sxs-lookup"><span data-stu-id="e7b24-198">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="e7b24-199">Одновременное удаление нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="e7b24-199">Delete many users at the same time</span></span>

<span data-ttu-id="e7b24-200">Обратитесь к разделу командлета PowerShell [Remove – MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) .</span><span class="sxs-lookup"><span data-stu-id="e7b24-200">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="e7b24-201">Устранение проблем с удалением пользователя</span><span class="sxs-lookup"><span data-stu-id="e7b24-201">Fix issues with deleting a user</span></span>

<span data-ttu-id="e7b24-202">Ниже приведены наиболее распространенные проблемы, с которыми сталкиваются пользователи при удалении пользователя:</span><span class="sxs-lookup"><span data-stu-id="e7b24-202">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="e7b24-203">**Появляется сообщение об ошибке в строке "пользователь не может быть удален". Повторите попытку позже. "**</span><span class="sxs-lookup"><span data-stu-id="e7b24-203">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="e7b24-204">Убедитесь, настроена ли для учетной записи Настройка переадресации электронной почты или она преобразована в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="e7b24-204">Doublecheck whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="e7b24-205">Это приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="e7b24-205">Both of these will cause that error.</span></span> <span data-ttu-id="e7b24-206">Не удаляйте учетную запись, если у нее есть переадресация электронной почты или она преобразована в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="e7b24-206">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="e7b24-207">**Нет соответствующих разрешений для удаления пользователя**.</span><span class="sxs-lookup"><span data-stu-id="e7b24-207">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="e7b24-208">Удалять пользователей могут только пользователи, являющиеся [глобальными администраторами Microsoft 365 или администраторами управления пользователями](about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="e7b24-208">Only people who are [Microsoft 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="e7b24-209">Обычно это специалисты службы технической поддержки в организации или учебном заведении.</span><span class="sxs-lookup"><span data-stu-id="e7b24-209">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="e7b24-p122">**Имя удаленного пользователя по-прежнему отображается в глобальной адресной книге**. Это происходит, если в организации используется Active Directory. Необходимо удалить учетную запись пользователя из Active Directory. Инструкции см. в следующей статье на сайте TechNet: [Удаление учетной записи пользователя](https://go.microsoft.com/fwlink/p/?linkid=841808).</span><span class="sxs-lookup"><span data-stu-id="e7b24-p122">**You delete the user but their name continues appear in your global address book**. This happens when a business is using Active Directory. You have to delete the users account from Active Directory. For instructions, see this TechNet article: [Delete a User Account.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span></span>

||
|:-----|
|<span data-ttu-id="e7b24-214">**Вы хотите удалить Microsoft 365 с компьютера? Перейдите к разделу [Отмена подписки](../../commerce/subscriptions/cancel-your-subscription.md).**</span><span class="sxs-lookup"><span data-stu-id="e7b24-214">**Do you want to delete Microsoft 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="e7b24-215">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="e7b24-215">Related articles</span></span>

[<span data-ttu-id="e7b24-216">Восстановление пользователя</span><span class="sxs-lookup"><span data-stu-id="e7b24-216">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="e7b24-217">Безвозвратное удаление почтового ящика</span><span class="sxs-lookup"><span data-stu-id="e7b24-217">Permanently delete a mailbox</span></span>](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[<span data-ttu-id="e7b24-218">Удаление бывшего сотрудника из среды Office 365</span><span class="sxs-lookup"><span data-stu-id="e7b24-218">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="e7b24-219">Добавление нового сотрудника в Office 365</span><span class="sxs-lookup"><span data-stu-id="e7b24-219">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="e7b24-220">[Удаление учетной записи пользователя](https://go.microsoft.com/fwlink/p/?linkid=841808): Используйте эти инструкции, если ваша организация использует **службу Active Directory** , которая синхронизируется с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e7b24-220">[Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="e7b24-221">В Office 365 сделать это нельзя.</span><span class="sxs-lookup"><span data-stu-id="e7b24-221">You can't do it through Office 365.</span></span>