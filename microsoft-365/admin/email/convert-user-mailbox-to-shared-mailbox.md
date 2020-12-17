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
ms.openlocfilehash: fa8e37b5e924f1b38755a953f40d8b70011213d0
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698283"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="d7aae-103">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="d7aae-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="d7aae-104">При преобразовании почтового ящика пользователя в общий почтовый ящик все сообщения и элементы календаря сохраняются.</span><span class="sxs-lookup"><span data-stu-id="d7aae-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="d7aae-105">Однако теперь к ним могут иметь доступ несколько человек.</span><span class="sxs-lookup"><span data-stu-id="d7aae-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="d7aae-106">Позднее можно будет преобразовать общий почтовый ящик обратно в пользовательский (частный) почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="d7aae-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="d7aae-107">**Вот некоторые важные моменты, которые необходимо знать.**</span><span class="sxs-lookup"><span data-stu-id="d7aae-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="d7aae-108">Перед преобразованием почтового ящика пользователя в общий почтовый ящик ему должна быть назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="d7aae-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="d7aae-109">В противном случае вы не увидите соответствующей команды.</span><span class="sxs-lookup"><span data-stu-id="d7aae-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="d7aae-110">Если вы удалили лицензию, верните ее, чтобы преобразовать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="d7aae-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="d7aae-111">После преобразования лицензию можно удалить из учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7aae-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="d7aae-112">Общие почтовые ящики могут иметь до 50 ГБ данных без назначенной им лицензии.</span><span class="sxs-lookup"><span data-stu-id="d7aae-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="d7aae-113">Для хранения большего объема данных необходимо назначит ему лицензию.</span><span class="sxs-lookup"><span data-stu-id="d7aae-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="d7aae-114">Вам может потребоваться удалить из общего почтового ящика крупные сообщения электронной почты (например, те, которые содержат вложения), чтобы уменьшить его размер и удалить лицензию.</span><span class="sxs-lookup"><span data-stu-id="d7aae-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="d7aae-p104">Не удаляйте старую учетную запись пользователя. К ней привязан общий почтовый ящик. Если вы уже удалили ее, см. раздел [Преобразование почтового ящика удаленного пользователя](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="d7aae-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="d7aae-118">Правила не меняются после преобразования почтового ящика в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="d7aae-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="d7aae-119">Преобразование почтового ящика с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="d7aae-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="d7aae-120">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="d7aae-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="d7aae-121">Выберите  \> **почтовые ящики получателей.**</span><span class="sxs-lookup"><span data-stu-id="d7aae-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="d7aae-122">Выберите почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7aae-122">Select the user mailbox.</span></span> <span data-ttu-id="d7aae-123">В **области "Преобразовать в общий почтовый ящик"** выберите **"Преобразовать".**</span><span class="sxs-lookup"><span data-stu-id="d7aae-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="d7aae-124">Если размер почтового ящика меньше 50 ГБ, вы можете удалить лицензию у пользователя и прекратить ее оплату. [](../manage/remove-licenses-from-users.md)</span><span class="sxs-lookup"><span data-stu-id="d7aae-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="d7aae-125">Не удаляйте учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7aae-125">Don't delete the user's account.</span></span> <span data-ttu-id="d7aae-126">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="d7aae-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="d7aae-127">При преобразовании почтового ящика сотрудника, который покидает организацию, необходимо предпринять дополнительные действия, чтобы убедиться, что он больше не может войти в систему.</span><span class="sxs-lookup"><span data-stu-id="d7aae-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="d7aae-128">См. ["Удаление бывшего сотрудника из Microsoft 365".](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="d7aae-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="d7aae-129">При преобразовании почтового ящика не требуется сбрасывать пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7aae-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="d7aae-130">Однако если пароль не **сбрасывается,** исходное имя пользователя и пароль продолжат работать после завершения преобразования почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="d7aae-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="d7aae-131">Все остальное, что нужно знать об общих почтовых ящиках, см. в дополнительных сообщениях об общих почтовых ящиках и создании [общего почтового ящика.](create-a-shared-mailbox.md) [](about-shared-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="d7aae-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d7aae-132">Для общих почтовых ящиков не нужна отдельная лицензия.</span><span class="sxs-lookup"><span data-stu-id="d7aae-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="d7aae-133">Однако если вы хотите включить архив In-Place или поместить удержание In-Place или судебное удержание для общего почтового ящика, необходимо назначить ему лицензию на Exchange Online (план 1) с архивация на базе Exchange Online или Exchange Online (план 2).</span><span class="sxs-lookup"><span data-stu-id="d7aae-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="d7aae-134">Преобразование почтового ящика удаленного пользователя</span><span class="sxs-lookup"><span data-stu-id="d7aae-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="d7aae-p109">Предположим, что вы удалили учетную запись пользователя, а теперь хотите преобразовать его почтовый ящик в общий. Вот что вам нужно будет сделать:</span><span class="sxs-lookup"><span data-stu-id="d7aae-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="d7aae-137">[Восстановим учетную запись пользователя.](../add-users/restore-user.md)</span><span class="sxs-lookup"><span data-stu-id="d7aae-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="d7aae-138">Убедитесь, что ему назначена лицензия Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d7aae-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="d7aae-139">Сброс пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7aae-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="d7aae-140">Подождите 20-30 минут, пока почтовый ящик не восстановится.</span><span class="sxs-lookup"><span data-stu-id="d7aae-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="d7aae-141">Затем следуйте инструкциям на этой странице, чтобы преобразовать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="d7aae-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="d7aae-142">После этого вы можете удалить лицензию из почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7aae-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="d7aae-143">Не удаляйте старый почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7aae-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="d7aae-144">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="d7aae-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="d7aae-145">Добавьте участников в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="d7aae-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="d7aae-146">Преобразование общего почтового ящика обратно в (частный) почтовый ящик пользователя</span><span class="sxs-lookup"><span data-stu-id="d7aae-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="d7aae-147">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="d7aae-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="d7aae-148">Select **Recipients** \> **Shared**.</span><span class="sxs-lookup"><span data-stu-id="d7aae-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="d7aae-149">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="d7aae-149">Select the shared mailbox.</span></span> <span data-ttu-id="d7aae-150">В **списке "Преобразовать в обычный почтовый ящик"** выберите **"Преобразовать".**</span><span class="sxs-lookup"><span data-stu-id="d7aae-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="d7aae-151">Перейдите в Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="d7aae-151">Go back to the admin center.</span></span> <span data-ttu-id="d7aae-152">В разделе **Пользователи** выберите учетную запись, связанную с общим почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="d7aae-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="d7aae-153">Назначьте ей лицензию и сбросьте пароль.</span><span class="sxs-lookup"><span data-stu-id="d7aae-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="d7aae-p113">Настройка почтового ящика займет несколько минут. После этого его можно будет использовать. После входа пользователь увидит почту и календарь, которые были в общем почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="d7aae-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="d7aae-156">Преобразование почтового ящика пользователя в гибридной среде</span><span class="sxs-lookup"><span data-stu-id="d7aae-156">Convert a user's mailbox in a hybrid environment</span></span>

> [!NOTE] 
> <span data-ttu-id="d7aae-157">Начиная с 11 октября 2018 г. гибридное развертывание Exchange поддерживает создание удаленных общих почтовых ящиков, начиная с накопительного обновления 21 для Exchange Server 2013 и накопительного обновления 10 для Exchange Server 2016 в локальной среде Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d7aae-157">Starting October 11th, 2018, Exchange hybrid deployment supports the creation of remote shared mailboxes starting in Cumulative Update 21 for Exchange Server 2013 and Cumulative Update 10 for Exchange Server 2016 in an on-premises Exchange Server environment.</span></span> <span data-ttu-id="d7aae-158">Вы можете напрямую создать или изменить удаленный общий почтовый ящик с помощью нового _параметра -shared._</span><span class="sxs-lookup"><span data-stu-id="d7aae-158">You can directly create or modify a remote shared mailbox by using the new _-shared_ parameter.</span></span> <span data-ttu-id="d7aae-159">Дополнительные сведения см. в [cmdlets](https://support.microsoft.com/help/4133605/cmdlets-to-create-modify-remote-shared-mailbox-in-on-premises-exchange)для создания или изменения удаленного общего почтового ящика в локальной среде Exchange.</span><span class="sxs-lookup"><span data-stu-id="d7aae-159">For more information, visit [Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment](https://support.microsoft.com/help/4133605/cmdlets-to-create-modify-remote-shared-mailbox-in-on-premises-exchange).</span></span>

<span data-ttu-id="d7aae-160">Если этот общий почтовый ящик находится в гибридной среде и не подпадает под вышеперечисленный сценарий, настоятельно рекомендуется **(почти** обязательно!) переместить почтовый ящик пользователя обратно в локальное, преобразовать почтовый ящик пользователя в общий почтовый ящик, а затем переместить общий почтовый ящик обратно в облако.</span><span class="sxs-lookup"><span data-stu-id="d7aae-160">If this shared mailbox is in a hybrid environment and not falling under the above scenario, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="d7aae-161">Вот почему: если вы преобразуете почтовый ящик в облаке, он может быть преобразован, но в локальной сети по-прежнему считает, что почтовый ящик является почтовым ящиком пользователя, так как новая реальность не синхронизируется с локальной.</span><span class="sxs-lookup"><span data-stu-id="d7aae-161">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="d7aae-162">Обычно это не является проблемой, но в некоторых случаях атрибуты локальной сети (которые считают, что почтовым ящиком является почтовый ящик пользователя) могут переоформить новые облачные версии этих атрибутов, в результате чего почтовый ящик может быть преобразован обратно.</span><span class="sxs-lookup"><span data-stu-id="d7aae-162">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="d7aae-163">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days!**</span><span class="sxs-lookup"><span data-stu-id="d7aae-163">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="d7aae-164">Мы рассмотрели большинство причин, по которым это происходит, но по-прежнему может происходить, хотя и редко.</span><span class="sxs-lookup"><span data-stu-id="d7aae-164">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="d7aae-165">Лучше всего быть безопасным и переместить почтовый ящик обратно в локальное решение, преобразовать его, а затем переместить общий почтовый ящик обратно в облако.</span><span class="sxs-lookup"><span data-stu-id="d7aae-165">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="d7aae-166">Это рекомендуемое решение не нарушает лицензионное соглашение для гибридных сред, так как наличие локального почтового ящика пользователя является временным.</span><span class="sxs-lookup"><span data-stu-id="d7aae-166">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="d7aae-167">Если вы сохранили почтовый ящик пользователя или общий почтовый ящик в локальной организации и не переместили его обратно в облако, вы нарушаете свою лицензию.</span><span class="sxs-lookup"><span data-stu-id="d7aae-167">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>


> [!NOTE]
> <span data-ttu-id="d7aae-168">Если вы входите в группу ролей "Управление организацией" или "Управление получателями", с помощью оболочки управления Exchange можно изменить почтовый ящик пользователя на общий почтовый ящик в локальной организации.</span><span class="sxs-lookup"><span data-stu-id="d7aae-168">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="d7aae-169">Например, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="d7aae-169">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="d7aae-170">См. обходное решение в этом решении поддержки для случаев, когда общие почтовые ящики неожиданно преобразуются [в почтовые](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)ящики пользователей.</span><span class="sxs-lookup"><span data-stu-id="d7aae-170">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="d7aae-171">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="d7aae-171">Related articles</span></span>

[<span data-ttu-id="d7aae-172">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="d7aae-172">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="d7aae-173">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="d7aae-173">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="d7aae-174">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="d7aae-174">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="d7aae-175">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="d7aae-175">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="d7aae-176">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="d7aae-176">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
