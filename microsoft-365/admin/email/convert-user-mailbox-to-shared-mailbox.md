---
title: Преобразование почтового ящика пользователя в общий почтовый ящик
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Узнайте, как преобразовать частный почтовый ящик в общий почтовый ящик, к нему могут получить доступ несколько пользователей. '
ms.openlocfilehash: d5b33731908d2d555a8dd12d5d7fbbd462bd83ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915870"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="0fa03-103">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="0fa03-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="0fa03-104">При преобразовании почтового ящика пользователя в общий почтовый ящик все сообщения и элементы календаря сохраняются.</span><span class="sxs-lookup"><span data-stu-id="0fa03-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="0fa03-105">Однако теперь к ним могут иметь доступ несколько человек.</span><span class="sxs-lookup"><span data-stu-id="0fa03-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="0fa03-106">Позднее можно преобразовать общий почтовый ящик обратно в пользовательский (частный) почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0fa03-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="0fa03-107">**Вот некоторые действительно важные вещи, которые необходимо знать:**</span><span class="sxs-lookup"><span data-stu-id="0fa03-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="0fa03-108">Почтовый ящик пользователя, который вы преобразуете, нуждается в лицензии, назначенной ему, прежде чем преобразовать его в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0fa03-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="0fa03-109">В противном случае вы не увидите соответствующей команды.</span><span class="sxs-lookup"><span data-stu-id="0fa03-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="0fa03-110">Если вы удалили лицензию, верните ее, чтобы преобразовать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0fa03-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="0fa03-111">После преобразования лицензию можно удалить из учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fa03-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="0fa03-112">Общие почтовые ящики могут иметь до 50 ГБ данных без назначенной им лицензии.</span><span class="sxs-lookup"><span data-stu-id="0fa03-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="0fa03-113">Для хранения большего объема данных необходимо назначит ему лицензию.</span><span class="sxs-lookup"><span data-stu-id="0fa03-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="0fa03-114">Вам может потребоваться удалить из общего почтового ящика крупные сообщения электронной почты (например, те, которые содержат вложения), чтобы уменьшить его размер и удалить лицензию.</span><span class="sxs-lookup"><span data-stu-id="0fa03-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="0fa03-p104">Не удаляйте старую учетную запись пользователя. К ней привязан общий почтовый ящик. Если вы уже удалили ее, см. раздел [Преобразование почтового ящика удаленного пользователя](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="0fa03-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="0fa03-118">Правила не повреждены после преобразования почтового ящика в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0fa03-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="0fa03-119">Используйте центр администрирования Exchange для преобразования почтового ящика</span><span class="sxs-lookup"><span data-stu-id="0fa03-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="0fa03-120">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="0fa03-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="0fa03-121">Выбор  \> **почтовых ящиков получателей**.</span><span class="sxs-lookup"><span data-stu-id="0fa03-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="0fa03-122">Выберите почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fa03-122">Select the user mailbox.</span></span> <span data-ttu-id="0fa03-123">В **статье Преобразование в общий почтовый ящик** выберите **Преобразование**.</span><span class="sxs-lookup"><span data-stu-id="0fa03-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="0fa03-124">Если размер почтового ящика меньше 50 ГБ, вы можете удалить лицензию у пользователя [и](../manage/remove-licenses-from-users.md)перестать платить за нее.</span><span class="sxs-lookup"><span data-stu-id="0fa03-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="0fa03-125">Не удаляйте учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fa03-125">Don't delete the user's account.</span></span> <span data-ttu-id="0fa03-126">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0fa03-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="0fa03-127">При преобразовании почтового ящика сотрудника, который покидает организацию, необходимо предпринять дополнительные действия, чтобы убедиться, что он больше не может войти в систему.</span><span class="sxs-lookup"><span data-stu-id="0fa03-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="0fa03-128">См. в этой записи Удаление [бывшего сотрудника из Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="0fa03-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="0fa03-129">Во время преобразования почтовых ящиков не требуется сбросить пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fa03-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="0fa03-130">Однако, если пароль не  сброшен, исходное имя пользователя и пароль продолжают работать после завершения преобразования почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="0fa03-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="0fa03-131">Все остальное, что необходимо знать об общих почтовых ящиках, см. в разделе [О](about-shared-mailboxes.md) общих почтовых ящиках и [создании общего почтового ящика.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="0fa03-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0fa03-132">Для общих почтовых ящиков не нужна отдельная лицензия.</span><span class="sxs-lookup"><span data-stu-id="0fa03-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="0fa03-133">Однако если вы хотите включить In-Place архив или поместить In-Place удержание или удержание судебного разбирательства на общий почтовый ящик, необходимо назначить почтовый ящик exchange Online Plan 1 с архивация на базе Exchange Online или Exchange Online Plan 2.</span><span class="sxs-lookup"><span data-stu-id="0fa03-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="0fa03-134">Преобразование почтового ящика удаленного пользователя</span><span class="sxs-lookup"><span data-stu-id="0fa03-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="0fa03-p109">Предположим, что вы удалили учетную запись пользователя, а теперь хотите преобразовать его почтовый ящик в общий. Вот что вам нужно будет сделать:</span><span class="sxs-lookup"><span data-stu-id="0fa03-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="0fa03-137">[Восстановление учетной записи пользователя.](../add-users/restore-user.md)</span><span class="sxs-lookup"><span data-stu-id="0fa03-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="0fa03-138">Убедитесь, что ему назначена лицензия Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0fa03-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="0fa03-139">Сброс пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fa03-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="0fa03-140">Подождите 20-30 минут, пока почтовый ящик не восстановится.</span><span class="sxs-lookup"><span data-stu-id="0fa03-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="0fa03-141">Затем следуйте инструкциям на этой странице, чтобы преобразовать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0fa03-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="0fa03-142">После этого можно удалить лицензию из почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fa03-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="0fa03-143">Не удаляйте старый почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fa03-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="0fa03-144">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0fa03-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="0fa03-145">Добавьте участников в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0fa03-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="0fa03-146">Преобразование общего почтового ящика обратно в (частный) почтовый ящик пользователя</span><span class="sxs-lookup"><span data-stu-id="0fa03-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="0fa03-147">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="0fa03-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="0fa03-148">Выбор **общих** \> **получателей**.</span><span class="sxs-lookup"><span data-stu-id="0fa03-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="0fa03-149">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0fa03-149">Select the shared mailbox.</span></span> <span data-ttu-id="0fa03-150">В **статье Преобразование в обычный почтовый ящик** выберите **Преобразование**.</span><span class="sxs-lookup"><span data-stu-id="0fa03-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="0fa03-151">Возвращайся в центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="0fa03-151">Go back to the admin center.</span></span> <span data-ttu-id="0fa03-152">В разделе **Пользователи** выберите учетную запись, связанную с общим почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="0fa03-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="0fa03-153">Назначьте ей лицензию и сбросьте пароль.</span><span class="sxs-lookup"><span data-stu-id="0fa03-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="0fa03-p113">Настройка почтового ящика займет несколько минут. После этого его можно будет использовать. После входа пользователь увидит почту и календарь, которые были в общем почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="0fa03-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="0fa03-156">Преобразование почтового ящика пользователя в гибридной среде</span><span class="sxs-lookup"><span data-stu-id="0fa03-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="0fa03-157">Дополнительные сведения о преобразовании почтового ящика пользователя в общий почтовый ящик в гибридной среде Exchange см. в примере:</span><span class="sxs-lookup"><span data-stu-id="0fa03-157">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="0fa03-158">Cmdlets для создания или изменения удаленного общего почтового ящика в локальной среде Exchange</span><span class="sxs-lookup"><span data-stu-id="0fa03-158">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="0fa03-159">Общие почтовые ящики неожиданно преобразуются в почтовые ящики пользователей после того, как синхронизация каталогов выполняется в гибридном развертывании Exchange</span><span class="sxs-lookup"><span data-stu-id="0fa03-159">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="0fa03-160">Если вы входите в группу ролей "Управление организацией" или "Управление получателями", вы можете использовать оболочку управления Exchange для изменения почтового ящика пользователя на общий почтовый ящик на локальном.</span><span class="sxs-lookup"><span data-stu-id="0fa03-160">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="0fa03-161">Например, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="0fa03-161">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0fa03-162">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="0fa03-162">Related articles</span></span>

[<span data-ttu-id="0fa03-163">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="0fa03-163">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="0fa03-164">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="0fa03-164">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="0fa03-165">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="0fa03-165">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="0fa03-166">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="0fa03-166">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="0fa03-167">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="0fa03-167">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)