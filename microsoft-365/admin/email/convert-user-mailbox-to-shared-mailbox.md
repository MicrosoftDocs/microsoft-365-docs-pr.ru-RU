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
description: 'Сведения о преобразовании личного почтового ящика в общий почтовый ящик, к которому можно получить доступ несколько пользователей. '
ms.openlocfilehash: bc867c9b43656e40149eb7cd7a7e5ce186c10798
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445691"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="c996b-103">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="c996b-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="c996b-104">При преобразовании почтового ящика пользователя в общий почтовый ящик все сообщения и элементы календаря сохраняются.</span><span class="sxs-lookup"><span data-stu-id="c996b-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="c996b-105">Однако теперь к ним могут иметь доступ несколько человек.</span><span class="sxs-lookup"><span data-stu-id="c996b-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="c996b-106">Позднее вы можете преобразовать общий почтовый ящик обратно в почтовый ящик пользователя (частный).</span><span class="sxs-lookup"><span data-stu-id="c996b-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="c996b-107">**Ниже приведены некоторые важные моменты, которые необходимо знать:**</span><span class="sxs-lookup"><span data-stu-id="c996b-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="c996b-108">Перед преобразованием почтового ящика пользователя к общему почтовому ящику требуется лицензия, назначенная для этого почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="c996b-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="c996b-109">В противном случае вы не увидите соответствующей команды.</span><span class="sxs-lookup"><span data-stu-id="c996b-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="c996b-110">Если вы удалили лицензию, верните ее, чтобы преобразовать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="c996b-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="c996b-111">После преобразования лицензию можно удалить из учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="c996b-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="c996b-112">Общие почтовые ящики могут иметь до 50 ГБ данных без назначенной лицензии.</span><span class="sxs-lookup"><span data-stu-id="c996b-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="c996b-113">Для хранения большего объема данных необходимо назначит ему лицензию.</span><span class="sxs-lookup"><span data-stu-id="c996b-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="c996b-114">Вам может потребоваться удалить из общего почтового ящика крупные сообщения электронной почты (например, те, которые содержат вложения), чтобы уменьшить его размер и удалить лицензию.</span><span class="sxs-lookup"><span data-stu-id="c996b-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="c996b-p104">Не удаляйте старую учетную запись пользователя. К ней привязан общий почтовый ящик. Если вы уже удалили ее, см. раздел [Преобразование почтового ящика удаленного пользователя](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="c996b-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="c996b-118">Правила не изменяются после преобразования почтового ящика в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="c996b-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="c996b-119">Использование центра администрирования Exchange для преобразования почтового ящика</span><span class="sxs-lookup"><span data-stu-id="c996b-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="c996b-120">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="c996b-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="c996b-121">Выберите **Recipients** пункт \> **почтовые ящики**получателей.</span><span class="sxs-lookup"><span data-stu-id="c996b-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="c996b-122">Выберите почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="c996b-122">Select the user mailbox.</span></span> <span data-ttu-id="c996b-123">В разделе **Преобразование в общий почтовый ящик**нажмите кнопку **преобразовать**.</span><span class="sxs-lookup"><span data-stu-id="c996b-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="c996b-124">Если размер почтового ящика меньше 50 ГБ, вы можете удалить [лицензию у пользователя](../manage/remove-licenses-from-users.md)и приостановить ее.</span><span class="sxs-lookup"><span data-stu-id="c996b-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="c996b-125">Не удаляйте учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="c996b-125">Don't delete the user's account.</span></span> <span data-ttu-id="c996b-126">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="c996b-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="c996b-127">При преобразовании почтового ящика сотрудника, который выходит из Организации, необходимо выполнить дополнительные действия, чтобы убедиться в том, что они больше не могут войти в систему.</span><span class="sxs-lookup"><span data-stu-id="c996b-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="c996b-128">Ознакомьтесь со статьей [Удаление бывшего сотрудника из Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="c996b-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c996b-129">Не требуется сбрасывать пароль пользователя при преобразовании почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c996b-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="c996b-130">Однако если пароль не сброшен, **исходное имя пользователя и пароль продолжают работать** после преобразования почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c996b-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="c996b-131">Все, что вам нужно знать о общих почтовых ящиках, можно узнать в статье [Общие](about-shared-mailboxes.md) почтовые ящики и [создать общий почтовый ящик](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="c996b-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c996b-132">Для общих почтовых ящиков не нужна отдельная лицензия.</span><span class="sxs-lookup"><span data-stu-id="c996b-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="c996b-133">Тем не менее, если вы хотите включить In-Placeный Архив или помещать In-Place удержание или удержание для судебного разбирательства в общий почтовый ящик, необходимо назначить почтовому ящику Exchange Online Plan 1 с помощью архивации на базе Exchange Online или Exchange Online (план 2).</span><span class="sxs-lookup"><span data-stu-id="c996b-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="c996b-134">Преобразование почтового ящика удаленного пользователя</span><span class="sxs-lookup"><span data-stu-id="c996b-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="c996b-p109">Предположим, что вы удалили учетную запись пользователя, а теперь хотите преобразовать его почтовый ящик в общий. Вот что вам нужно будет сделать:</span><span class="sxs-lookup"><span data-stu-id="c996b-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="c996b-137">[Восстановите учетную запись пользователя](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="c996b-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="c996b-138">Убедитесь, что ей назначена лицензия Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c996b-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="c996b-139">Сброс пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="c996b-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="c996b-140">Подождите 20-30 минут, пока почтовый ящик не восстановится.</span><span class="sxs-lookup"><span data-stu-id="c996b-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="c996b-141">Затем следуйте инструкциям на этой странице, чтобы преобразовать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="c996b-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="c996b-142">После этого вы можете удалить лицензию из почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="c996b-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="c996b-143">Не удаляйте старый почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="c996b-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="c996b-144">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="c996b-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="c996b-145">Добавьте участников в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="c996b-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="c996b-146">Преобразование общего почтового ящика обратно в личный почтовый ящик пользователя</span><span class="sxs-lookup"><span data-stu-id="c996b-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="c996b-147">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="c996b-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="c996b-148">Выберите пункт **получатели** \> , к **которым предоставлен общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="c996b-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="c996b-149">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="c996b-149">Select the shared mailbox.</span></span> <span data-ttu-id="c996b-150">В разделе **Преобразование в обычный почтовый ящик**нажмите кнопку **преобразовать**.</span><span class="sxs-lookup"><span data-stu-id="c996b-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="c996b-151">Вернитесь в центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="c996b-151">Go back to the admin center.</span></span> <span data-ttu-id="c996b-152">В разделе **Пользователи** выберите учетную запись, связанную с общим почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="c996b-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="c996b-153">Назначьте ей лицензию и сбросьте пароль.</span><span class="sxs-lookup"><span data-stu-id="c996b-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="c996b-p113">Настройка почтового ящика займет несколько минут. После этого его можно будет использовать. После входа пользователь увидит почту и календарь, которые были в общем почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="c996b-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="c996b-156">Преобразование почтового ящика пользователя в гибридной среде</span><span class="sxs-lookup"><span data-stu-id="c996b-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="c996b-157">Если этот общий почтовый ящик находится в гибридной среде, **настоятельно рекомендуется** (почти обязательно) переместить почтовый ящик пользователя обратно в локальную систему, преобразовать почтовый ящик пользователя в общий почтовый ящик, а затем переместить общий почтовый ящик обратно в облако.</span><span class="sxs-lookup"><span data-stu-id="c996b-157">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="c996b-158">Вот почему: при преобразовании почтового ящика в облаке он может быть преобразован, но в локальной системе все еще будет расмнению почтовый ящик пользователя, так как новая реальность не синхронизируется с локальной средой.</span><span class="sxs-lookup"><span data-stu-id="c996b-158">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="c996b-159">Как правило, это не проблема, но существуют некоторые сценарии, в которых локальные атрибуты (которые считают, что почтовый ящик является почтовым ящиком пользователя), могут переопределять новые облачные версии этих атрибутов, а это может привести к обратному преобразованию почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c996b-159">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="c996b-160">Это проблема, так как почтовые ящики пользователей нуждаются в лицензиях **или обратимо удалены через 30 дней**.</span><span class="sxs-lookup"><span data-stu-id="c996b-160">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="c996b-161">Мы предоставили основные причины, по которым это происходит, но это по-прежнему может произойти, хотя и нечасто.</span><span class="sxs-lookup"><span data-stu-id="c996b-161">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="c996b-162">Лучше всего обеспечить безопасность и переместить почтовый ящик обратно в локальную среду, преобразовать его, а затем переместить в облако.</span><span class="sxs-lookup"><span data-stu-id="c996b-162">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="c996b-163">Это рекомендуемое решение не нарушает лицензионное соглашение для гибридных сред, так как существование локального почтового ящика пользователя является временным.</span><span class="sxs-lookup"><span data-stu-id="c996b-163">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="c996b-164">Если вы сохранили почтовый ящик пользователя или общий почтовый ящик в локальной организации и не переместит его обратно в облако, вы будете присутствовать в нарушении лицензии.</span><span class="sxs-lookup"><span data-stu-id="c996b-164">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="c996b-165">Если вы являетесь членом группы ролей "Управление организацией" или "Управление получателями", вы можете использовать командную консоль Exchange для изменения почтового ящика пользователя на локальный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="c996b-165">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="c996b-166">Например, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="c996b-166">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="c996b-167">Если [Общие почтовые ящики неожиданно преобразуются в почтовые ящики пользователей](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di), ознакомьтесь с разрешениями в этом решении.</span><span class="sxs-lookup"><span data-stu-id="c996b-167">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="c996b-168">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="c996b-168">Related articles</span></span>

[<span data-ttu-id="c996b-169">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="c996b-169">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="c996b-170">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="c996b-170">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="c996b-171">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="c996b-171">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="c996b-172">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="c996b-172">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="c996b-173">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="c996b-173">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
