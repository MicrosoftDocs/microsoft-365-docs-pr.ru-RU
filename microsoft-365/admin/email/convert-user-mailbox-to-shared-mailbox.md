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
description: 'Узнайте, как преобразовать частный почтовый ящик в общий почтовый ящик, к нему могут получить доступ несколько человек, а не только один человек. '
ms.openlocfilehash: 0beb85e5a69b72bcd244cd654c399e91ded06ba7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635478"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="ff8be-103">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="ff8be-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="ff8be-104">При преобразовании почтового ящика пользователя в общий почтовый ящик все сообщения и элементы календаря сохраняются.</span><span class="sxs-lookup"><span data-stu-id="ff8be-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="ff8be-105">Однако теперь к ним могут иметь доступ несколько человек.</span><span class="sxs-lookup"><span data-stu-id="ff8be-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="ff8be-106">Позднее можно преобразовать общий почтовый ящик обратно в пользовательский (частный) почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="ff8be-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ff8be-107">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="ff8be-107">Before you begin</span></span>

<span data-ttu-id="ff8be-108">**Вот некоторые действительно важные вещи, которые необходимо знать:**</span><span class="sxs-lookup"><span data-stu-id="ff8be-108">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="ff8be-109">Почтовый ящик пользователя, который вы преобразуете, нуждается в лицензии, назначенной ему, прежде чем преобразовать его в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="ff8be-109">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="ff8be-110">В противном случае вы не увидите соответствующей команды.</span><span class="sxs-lookup"><span data-stu-id="ff8be-110">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="ff8be-111">Если вы удалили лицензию, верните ее, чтобы преобразовать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="ff8be-111">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="ff8be-112">После преобразования лицензию можно удалить из учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff8be-112">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="ff8be-113">Общие почтовые ящики могут иметь до 50 ГБ данных без назначенной им лицензии.</span><span class="sxs-lookup"><span data-stu-id="ff8be-113">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="ff8be-114">Для хранения большего объема данных необходимо назначит ему лицензию.</span><span class="sxs-lookup"><span data-stu-id="ff8be-114">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="ff8be-115">Вам может потребоваться удалить из общего почтового ящика крупные сообщения электронной почты (например, те, которые содержат вложения), чтобы уменьшить его размер и удалить лицензию.</span><span class="sxs-lookup"><span data-stu-id="ff8be-115">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="ff8be-p104">Не удаляйте старую учетную запись пользователя. К ней привязан общий почтовый ящик. Если вы уже удалили ее, см. раздел [Преобразование почтового ящика удаленного пользователя](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="ff8be-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="ff8be-119">Правила не повреждены после преобразования почтового ящика в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="ff8be-119">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="ff8be-120">Используйте центр администрирования Exchange для преобразования почтового ящика</span><span class="sxs-lookup"><span data-stu-id="ff8be-120">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="ff8be-121">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="ff8be-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="ff8be-122">Выбор  \> **почтовых ящиков получателей**.</span><span class="sxs-lookup"><span data-stu-id="ff8be-122">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="ff8be-123">Выберите почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff8be-123">Select the user mailbox.</span></span> <span data-ttu-id="ff8be-124">В **статье Преобразование в общий почтовый ящик** выберите **Преобразование**.</span><span class="sxs-lookup"><span data-stu-id="ff8be-124">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="ff8be-125">Если размер почтового ящика меньше 50 ГБ, вы можете удалить лицензию у пользователя [и](../manage/remove-licenses-from-users.md)перестать платить за нее.</span><span class="sxs-lookup"><span data-stu-id="ff8be-125">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="ff8be-126">Не удаляйте учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff8be-126">Don't delete the user's account.</span></span> <span data-ttu-id="ff8be-127">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="ff8be-127">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="ff8be-128">При преобразовании почтового ящика сотрудника, который покидает организацию, необходимо предпринять дополнительные действия, чтобы убедиться, что он больше не может войти в систему.</span><span class="sxs-lookup"><span data-stu-id="ff8be-128">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="ff8be-129">См. в этой ленте Удаление [бывшего сотрудника из Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="ff8be-129">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="ff8be-130">Во время преобразования почтовых ящиков не требуется сбросить пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff8be-130">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="ff8be-131">Однако, если пароль не  сброшен, исходное имя пользователя и пароль продолжают работать после завершения преобразования почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="ff8be-131">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="ff8be-132">Все остальное, что необходимо знать об общих почтовых ящиках, см. в разделе [О](about-shared-mailboxes.md) общих почтовых ящиках и [создании общего почтового ящика.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="ff8be-132">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ff8be-133">Для общих почтовых ящиков не нужна отдельная лицензия.</span><span class="sxs-lookup"><span data-stu-id="ff8be-133">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="ff8be-134">Однако если вы хотите включить In-Place Архив или поместить In-Place удержание или удержание судебного разбирательства на общий почтовый ящик, необходимо назначить в почтовый ящик Exchange Online Plan 1 с лицензией Exchange Online Archiving или Exchange Online Plan 2.</span><span class="sxs-lookup"><span data-stu-id="ff8be-134">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>

## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="ff8be-135">Преобразование почтового ящика удаленного пользователя</span><span class="sxs-lookup"><span data-stu-id="ff8be-135">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="ff8be-p109">Предположим, что вы удалили учетную запись пользователя, а теперь хотите преобразовать его почтовый ящик в общий. Вот что вам нужно будет сделать:</span><span class="sxs-lookup"><span data-stu-id="ff8be-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="ff8be-138">[Восстановление учетной записи пользователя.](../add-users/restore-user.md)</span><span class="sxs-lookup"><span data-stu-id="ff8be-138">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="ff8be-139">Убедитесь, Microsoft 365 ему назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="ff8be-139">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="ff8be-140">Сброс пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff8be-140">Reset the user's password.</span></span>
    
4. <span data-ttu-id="ff8be-141">Подождите 20-30 минут, пока почтовый ящик не восстановится.</span><span class="sxs-lookup"><span data-stu-id="ff8be-141">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="ff8be-142">Затем следуйте инструкциям на этой странице, чтобы преобразовать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="ff8be-142">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="ff8be-143">После этого можно удалить лицензию из почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff8be-143">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="ff8be-144">Не удаляйте старый почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff8be-144">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="ff8be-145">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="ff8be-145">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="ff8be-146">Добавьте участников в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="ff8be-146">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="ff8be-147">Преобразование общего почтового ящика обратно в (частный) почтовый ящик пользователя</span><span class="sxs-lookup"><span data-stu-id="ff8be-147">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="ff8be-148">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="ff8be-148">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="ff8be-149">Выбор **общих** \> **получателей**.</span><span class="sxs-lookup"><span data-stu-id="ff8be-149">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="ff8be-150">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="ff8be-150">Select the shared mailbox.</span></span> <span data-ttu-id="ff8be-151">В **статье Преобразование в обычный почтовый ящик** выберите **Преобразование**.</span><span class="sxs-lookup"><span data-stu-id="ff8be-151">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="ff8be-152">Возвращайся в центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="ff8be-152">Go back to the admin center.</span></span> <span data-ttu-id="ff8be-153">В разделе **Пользователи** выберите учетную запись, связанную с общим почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="ff8be-153">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="ff8be-154">Назначьте ей лицензию и сбросьте пароль.</span><span class="sxs-lookup"><span data-stu-id="ff8be-154">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="ff8be-p113">Настройка почтового ящика займет несколько минут. После этого его можно будет использовать. После входа пользователь увидит почту и календарь, которые были в общем почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="ff8be-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="ff8be-157">Преобразование почтового ящика пользователя в гибридной среде</span><span class="sxs-lookup"><span data-stu-id="ff8be-157">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="ff8be-158">Дополнительные сведения о преобразовании почтового ящика пользователя в общий почтовый ящик в гибридной среде Exchange см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="ff8be-158">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="ff8be-159">Cmdlets для создания или изменения удаленного общего почтового ящика в локальной Exchange среде</span><span class="sxs-lookup"><span data-stu-id="ff8be-159">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="ff8be-160">Общие почтовые ящики неожиданно преобразуются в почтовые ящики пользователей после того, как синхронизация каталогов выполняется Exchange гибридного развертывания</span><span class="sxs-lookup"><span data-stu-id="ff8be-160">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="ff8be-161">Если вы входите в группу ролей "Управление организацией" или "Управление получателями", вы можете использовать Exchange Management Shell для изменения почтового ящика пользователя на общий почтовый ящик на локальном.</span><span class="sxs-lookup"><span data-stu-id="ff8be-161">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="ff8be-162">Например, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="ff8be-162">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-content"></a><span data-ttu-id="ff8be-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff8be-163">Related content</span></span>

<span data-ttu-id="ff8be-164">[Сведения об общих почтовых ящиках](about-shared-mailboxes.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="ff8be-164">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="ff8be-165">[Создание общего почтового ящика](create-a-shared-mailbox.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="ff8be-165">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="ff8be-166">[Настройка общего почтового ящика](configure-a-shared-mailbox.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="ff8be-166">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="ff8be-167">[Удаление лицензии из общего почтового ящика](remove-license-from-shared-mailbox.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="ff8be-167">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="ff8be-168">[Решение проблем с общими почтовыми ящиками](resolve-issues-with-shared-mailboxes.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="ff8be-168">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>