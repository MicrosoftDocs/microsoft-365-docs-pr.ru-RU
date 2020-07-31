---
title: Преобразование почтового ящика пользователя в общий почтовый ящик
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Сведения о преобразовании личного почтового ящика в общий почтовый ящик, к которому можно получить доступ несколько пользователей. '
ms.openlocfilehash: a4b2e9ce53051feb07ea035adc0c959bbb1a0948
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521033"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="86e75-103">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="86e75-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="86e75-104">При преобразовании почтового ящика пользователя в общий почтовый ящик все сообщения и элементы календаря сохраняются.</span><span class="sxs-lookup"><span data-stu-id="86e75-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="86e75-105">Однако теперь к ним могут иметь доступ несколько человек.</span><span class="sxs-lookup"><span data-stu-id="86e75-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="86e75-106">Позднее вы можете преобразовать общий почтовый ящик обратно в почтовый ящик пользователя (частный).</span><span class="sxs-lookup"><span data-stu-id="86e75-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="86e75-107">**Ниже приведены некоторые важные моменты, которые необходимо знать:**</span><span class="sxs-lookup"><span data-stu-id="86e75-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="86e75-108">Перед преобразованием почтового ящика пользователя к общему почтовому ящику требуется лицензия, назначенная для этого почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="86e75-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="86e75-109">В противном случае вы не увидите соответствующей команды.</span><span class="sxs-lookup"><span data-stu-id="86e75-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="86e75-110">Если вы удалили лицензию, верните ее, чтобы преобразовать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="86e75-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="86e75-111">После преобразования лицензию можно удалить из учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="86e75-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="86e75-112">Общие почтовые ящики могут иметь до 50 ГБ данных без назначенной лицензии.</span><span class="sxs-lookup"><span data-stu-id="86e75-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="86e75-113">Для хранения большего объема данных необходимо назначит ему лицензию.</span><span class="sxs-lookup"><span data-stu-id="86e75-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="86e75-114">Вам может потребоваться удалить из общего почтового ящика крупные сообщения электронной почты (например, те, которые содержат вложения), чтобы уменьшить его размер и удалить лицензию.</span><span class="sxs-lookup"><span data-stu-id="86e75-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="86e75-p104">Не удаляйте старую учетную запись пользователя. К ней привязан общий почтовый ящик. Если вы уже удалили ее, см. раздел [Преобразование почтового ящика удаленного пользователя](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="86e75-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="86e75-118">Правила не изменяются после преобразования почтового ящика в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="86e75-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="86e75-119">Использование центра администрирования Exchange для преобразования почтового ящика</span><span class="sxs-lookup"><span data-stu-id="86e75-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="86e75-120">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="86e75-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="86e75-121">Выберите **Recipients** пункт \> **почтовые ящики**получателей.</span><span class="sxs-lookup"><span data-stu-id="86e75-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="86e75-122">Выберите почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="86e75-122">Select the user mailbox.</span></span> <span data-ttu-id="86e75-123">В разделе **Преобразование в общий почтовый ящик**нажмите кнопку **преобразовать**.</span><span class="sxs-lookup"><span data-stu-id="86e75-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="86e75-124">Если размер почтового ящика меньше 50 ГБ, вы можете удалить [лицензию у пользователя](../manage/remove-licenses-from-users.md)и приостановить ее.</span><span class="sxs-lookup"><span data-stu-id="86e75-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="86e75-125">Не удаляйте учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="86e75-125">Don't delete the user's account.</span></span> <span data-ttu-id="86e75-126">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="86e75-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="86e75-127">При преобразовании почтового ящика сотрудника, который выходит из Организации, необходимо выполнить дополнительные действия, чтобы убедиться в том, что они больше не могут войти в систему.</span><span class="sxs-lookup"><span data-stu-id="86e75-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="86e75-128">Ознакомьтесь со статьей [Удаление бывшего сотрудника из Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="86e75-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="86e75-129">Все, что вам нужно знать о общих почтовых ящиках, можно узнать в статье [Общие](about-shared-mailboxes.md) почтовые ящики и [создать общий почтовый ящик](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="86e75-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="86e75-130">Использование центра администрирования Microsoft 365 для преобразования почтового ящика</span><span class="sxs-lookup"><span data-stu-id="86e75-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="86e75-131">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="86e75-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="86e75-132">Выберите имя пользователя, чей почтовый ящик требуется преобразовать.</span><span class="sxs-lookup"><span data-stu-id="86e75-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="86e75-133">Сброс пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="86e75-133">Reset the user's password.</span></span>

   > [!NOTE]
   > <span data-ttu-id="86e75-134">Не требуется сбрасывать пароль пользователя при преобразовании почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="86e75-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="86e75-135">Однако если пароль не сброшен, **исходное имя пользователя и пароль продолжают работать** после преобразования почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="86e75-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="86e75-136">На вкладке **почта** в разделе **Дополнительные действия**выберите команду **преобразовать в общий почтовый ящик**.</span><span class="sxs-lookup"><span data-stu-id="86e75-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="86e75-137">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="86e75-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="86e75-138">Выберите пользователя, чей почтовый ящик требуется преобразовать.</span><span class="sxs-lookup"><span data-stu-id="86e75-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="86e75-139">В правой области разверните узел **Параметры почты**.</span><span class="sxs-lookup"><span data-stu-id="86e75-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="86e75-140">Рядом с пунктом **Дополнительные параметры**выберите пункт **преобразовать в общий почтовый ящик**.</span><span class="sxs-lookup"><span data-stu-id="86e75-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="86e75-141">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="86e75-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="86e75-142">Выберите пользователя, чей почтовый ящик требуется преобразовать.</span><span class="sxs-lookup"><span data-stu-id="86e75-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="86e75-143">В правой области разверните узел **Параметры почты**.</span><span class="sxs-lookup"><span data-stu-id="86e75-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="86e75-144">Рядом с пунктом **Дополнительные параметры**выберите пункт **преобразовать в общий почтовый ящик**.</span><span class="sxs-lookup"><span data-stu-id="86e75-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="86e75-145">Если размер почтового ящика меньше 50 ГБ, вы можете [удалить лицензию у пользователя](../manage/remove-licenses-from-users.md)и приостановить ее.</span><span class="sxs-lookup"><span data-stu-id="86e75-145">If the mailbox is smaller than 50 GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="86e75-146">Не удаляйте старый почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="86e75-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="86e75-147">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="86e75-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="86e75-148">При преобразовании почтового ящика сотрудника, который выходит из Организации, необходимо выполнить дополнительные действия, чтобы убедиться в том, что они больше не могут войти в систему.</span><span class="sxs-lookup"><span data-stu-id="86e75-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="86e75-149">Ознакомьтесь [со статьей удаление бывшего сотрудника из Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="86e75-149">See [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="86e75-150">Все, что вам нужно знать о общих почтовых ящиках, можно узнать в статье [Общие](about-shared-mailboxes.md) почтовые ящики и [создать общий почтовый ящик](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="86e75-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="86e75-151">Для общих почтовых ящиков не нужна отдельная лицензия.</span><span class="sxs-lookup"><span data-stu-id="86e75-151">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="86e75-152">Тем не менее, если вы хотите включить архивацию на месте или разместить на месте общий почтовый ящик, необходимо назначить почтовому ящику Exchange Online Plan 1 с помощью архивации на базе Exchange Online или Exchange Online (план 2).</span><span class="sxs-lookup"><span data-stu-id="86e75-152">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="86e75-153">Преобразование почтового ящика удаленного пользователя</span><span class="sxs-lookup"><span data-stu-id="86e75-153">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="86e75-p112">Предположим, что вы удалили учетную запись пользователя, а теперь хотите преобразовать его почтовый ящик в общий. Вот что вам нужно будет сделать:</span><span class="sxs-lookup"><span data-stu-id="86e75-p112">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="86e75-156">[Восстановите учетную запись пользователя](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="86e75-156">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="86e75-157">Убедитесь, что ей назначена лицензия Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86e75-157">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="86e75-158">Сброс пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="86e75-158">Reset the user's password.</span></span>
    
4. <span data-ttu-id="86e75-159">Подождите 20-30 минут, пока почтовый ящик не восстановится.</span><span class="sxs-lookup"><span data-stu-id="86e75-159">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="86e75-160">Затем следуйте инструкциям на этой странице, чтобы преобразовать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="86e75-160">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="86e75-161">После этого вы можете удалить лицензию из почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="86e75-161">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="86e75-162">Не удаляйте старый почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="86e75-162">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="86e75-163">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="86e75-163">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="86e75-164">Добавьте участников в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="86e75-164">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="86e75-165">Преобразование общего почтового ящика обратно в личный почтовый ящик пользователя</span><span class="sxs-lookup"><span data-stu-id="86e75-165">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="86e75-166">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="86e75-166">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="86e75-167">Выберите пункт **получатели** \> , к **которым предоставлен общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="86e75-167">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="86e75-168">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="86e75-168">Select the shared mailbox.</span></span> <span data-ttu-id="86e75-169">В разделе **Преобразование в обычный почтовый ящик**нажмите кнопку **преобразовать**.</span><span class="sxs-lookup"><span data-stu-id="86e75-169">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="86e75-170">Вернитесь в центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="86e75-170">Go back to the admin center.</span></span> <span data-ttu-id="86e75-171">В разделе **Пользователи** выберите учетную запись, связанную с общим почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="86e75-171">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="86e75-172">Назначьте ей лицензию и сбросьте пароль.</span><span class="sxs-lookup"><span data-stu-id="86e75-172">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="86e75-p116">Настройка почтового ящика займет несколько минут. После этого его можно будет использовать. После входа пользователь увидит почту и календарь, которые были в общем почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="86e75-p116">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="86e75-175">Преобразование почтового ящика пользователя в гибридной среде</span><span class="sxs-lookup"><span data-stu-id="86e75-175">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="86e75-176">Если этот общий почтовый ящик находится в гибридной среде, **настоятельно рекомендуется** (почти обязательно) переместить почтовый ящик пользователя обратно в локальную систему, преобразовать почтовый ящик пользователя в общий почтовый ящик, а затем переместить общий почтовый ящик обратно в облако.</span><span class="sxs-lookup"><span data-stu-id="86e75-176">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="86e75-177">Вот почему: при преобразовании почтового ящика в облаке он может быть преобразован, но в локальной системе все еще будет расмнению почтовый ящик пользователя, так как новая реальность не синхронизируется с локальной средой.</span><span class="sxs-lookup"><span data-stu-id="86e75-177">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="86e75-178">Как правило, это не проблема, но существуют некоторые сценарии, в которых локальные атрибуты (которые считают, что почтовый ящик является почтовым ящиком пользователя), могут переопределять новые облачные версии этих атрибутов, а это может привести к обратному преобразованию почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="86e75-178">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="86e75-179">Это проблема, так как почтовые ящики пользователей нуждаются в лицензиях **или обратимо удалены через 30 дней**.</span><span class="sxs-lookup"><span data-stu-id="86e75-179">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="86e75-180">Мы предоставили основные причины, по которым это происходит, но это по-прежнему может произойти, хотя и нечасто.</span><span class="sxs-lookup"><span data-stu-id="86e75-180">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="86e75-181">Лучше всего обеспечить безопасность и переместить почтовый ящик обратно в локальную среду, преобразовать его, а затем переместить в облако.</span><span class="sxs-lookup"><span data-stu-id="86e75-181">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="86e75-182">Это рекомендуемое решение не нарушает лицензионное соглашение для гибридных сред, так как существование локального почтового ящика пользователя является временным.</span><span class="sxs-lookup"><span data-stu-id="86e75-182">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="86e75-183">Если вы сохранили почтовый ящик пользователя или общий почтовый ящик в локальной организации и не переместит его обратно в облако, вы будете присутствовать в нарушении лицензии.</span><span class="sxs-lookup"><span data-stu-id="86e75-183">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="86e75-184">Если вы являетесь членом группы ролей "Управление организацией" или "Управление получателями", вы можете использовать командную консоль Exchange для изменения почтового ящика пользователя на локальный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="86e75-184">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="86e75-185">Например, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="86e75-185">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="86e75-186">Если [Общие почтовые ящики неожиданно преобразуются в почтовые ящики пользователей](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di), ознакомьтесь с разрешениями в этом решении.</span><span class="sxs-lookup"><span data-stu-id="86e75-186">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="86e75-187">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="86e75-187">Related articles</span></span>

[<span data-ttu-id="86e75-188">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="86e75-188">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="86e75-189">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="86e75-189">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="86e75-190">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="86e75-190">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="86e75-191">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="86e75-191">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="86e75-192">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="86e75-192">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
