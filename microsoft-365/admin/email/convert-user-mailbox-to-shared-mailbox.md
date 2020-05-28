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
ms.openlocfilehash: c4f71f12b430e239f5ea5791ba5b98a3109452b0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400116"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="37d0d-103">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="37d0d-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="37d0d-104">При преобразовании почтового ящика пользователя в общий почтовый ящик все сообщения и элементы календаря сохраняются.</span><span class="sxs-lookup"><span data-stu-id="37d0d-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="37d0d-105">Однако теперь к ним могут иметь доступ несколько человек.</span><span class="sxs-lookup"><span data-stu-id="37d0d-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="37d0d-106">Позднее вы можете преобразовать общий почтовый ящик обратно в почтовый ящик пользователя (частный).</span><span class="sxs-lookup"><span data-stu-id="37d0d-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="37d0d-107">**Ниже приведены некоторые важные моменты, которые необходимо знать:**</span><span class="sxs-lookup"><span data-stu-id="37d0d-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="37d0d-108">Перед преобразованием почтового ящика пользователя к общему почтовому ящику требуется лицензия, назначенная для этого почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="37d0d-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="37d0d-109">В противном случае вы не увидите соответствующей команды.</span><span class="sxs-lookup"><span data-stu-id="37d0d-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="37d0d-110">Если вы удалили лицензию, верните ее, чтобы преобразовать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="37d0d-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="37d0d-111">После преобразования лицензию можно удалить из учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="37d0d-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="37d0d-p103">Если в общем почтовом ящике до 50 ГБ данных, лицензия не требуется. Для хранения большего объема данных необходимо назначит ему лицензию. Вам может потребоваться удалить из общего почтового ящика крупные сообщения электронной почты (например, те, которые содержат вложения), чтобы уменьшить его размер и удалить лицензию.</span><span class="sxs-lookup"><span data-stu-id="37d0d-p103">Shared mailboxes can have up to 50GB of data without a license assigned to them. To hold more data than that, you need a license assigned to it. You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="37d0d-p104">Не удаляйте старую учетную запись пользователя. К ней привязан общий почтовый ящик. Если вы уже удалили ее, см. раздел [Преобразование почтового ящика удаленного пользователя](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="37d0d-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="37d0d-118">Правила не изменяются после преобразования почтового ящика в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="37d0d-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="37d0d-119">Использование центра администрирования Exchange для преобразования почтового ящика</span><span class="sxs-lookup"><span data-stu-id="37d0d-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="37d0d-120">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="37d0d-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="37d0d-121">Выберите **Recipients** пункт \> **почтовые ящики**получателей.</span><span class="sxs-lookup"><span data-stu-id="37d0d-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="37d0d-122">Выберите почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="37d0d-122">Select the user mailbox.</span></span> <span data-ttu-id="37d0d-123">В разделе **Преобразование в общий почтовый ящик**нажмите кнопку **преобразовать**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="37d0d-124">Если размер почтового ящика меньше 50 ГБ, вы можете удалить [лицензию пользователя](../manage/remove-licenses-from-users.md), чтобы не платить за нее.</span><span class="sxs-lookup"><span data-stu-id="37d0d-124">If the mailbox is smaller than 50GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="37d0d-125">Не удаляйте учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="37d0d-125">Don't delete the user's account.</span></span> <span data-ttu-id="37d0d-126">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="37d0d-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="37d0d-127">При преобразовании почтового ящика сотрудника, который выходит из Организации, необходимо выполнить дополнительные действия, чтобы убедиться в том, что они больше не могут войти в систему.</span><span class="sxs-lookup"><span data-stu-id="37d0d-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="37d0d-128">Ознакомьтесь со статьей [Удаление бывшего сотрудника из Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="37d0d-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="37d0d-129">Все, что вам нужно знать о общих почтовых ящиках, можно узнать в статье [Общие](about-shared-mailboxes.md) почтовые ящики и [создать общий почтовый ящик](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="37d0d-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="37d0d-130">Использование центра администрирования Microsoft 365 для преобразования почтового ящика</span><span class="sxs-lookup"><span data-stu-id="37d0d-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="37d0d-131">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="37d0d-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="37d0d-132">Выберите имя пользователя, чей почтовый ящик требуется преобразовать.</span><span class="sxs-lookup"><span data-stu-id="37d0d-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="37d0d-133">Сброс пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="37d0d-133">Reset the user's password.</span></span>

> [!NOTE]
> <span data-ttu-id="37d0d-134">Не требуется сбрасывать пароль пользователя при преобразовании почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="37d0d-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="37d0d-135">Однако если пароль не сброшен, **исходное имя пользователя и пароль продолжают работать** после преобразования почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="37d0d-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="37d0d-136">На вкладке **почта** в разделе **Дополнительные действия**выберите команду **преобразовать в общий почтовый ящик**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="37d0d-137">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="37d0d-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="37d0d-138">Выберите пользователя, чей почтовый ящик требуется преобразовать.</span><span class="sxs-lookup"><span data-stu-id="37d0d-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="37d0d-139">В правой области разверните узел **Параметры почты**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="37d0d-140">Рядом с пунктом **Дополнительные параметры**выберите пункт **преобразовать в общий почтовый ящик**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="37d0d-141">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="37d0d-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="37d0d-142">Выберите пользователя, чей почтовый ящик требуется преобразовать.</span><span class="sxs-lookup"><span data-stu-id="37d0d-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="37d0d-143">В правой области разверните узел **Параметры почты**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="37d0d-144">Рядом с пунктом **Дополнительные параметры**выберите пункт **преобразовать в общий почтовый ящик**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="37d0d-145">Если размер почтового ящика меньше 50 ГБ, вы можете [удалить лицензию у пользователя](../manage/remove-licenses-from-users.md)и приостановить ее.</span><span class="sxs-lookup"><span data-stu-id="37d0d-145">If the mailbox is smaller than 50GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="37d0d-146">Не удаляйте старый почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="37d0d-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="37d0d-147">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="37d0d-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="37d0d-148">При преобразовании почтового ящика сотрудника, который выходит из Организации, необходимо выполнить дополнительные действия, чтобы убедиться в том, что они больше не могут войти в систему.</span><span class="sxs-lookup"><span data-stu-id="37d0d-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="37d0d-149">Ознакомьтесь [со статьей удаление бывшего сотрудника из Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="37d0d-149">See [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="37d0d-150">Все, что вам нужно знать о общих почтовых ящиках, можно узнать в статье [Общие](about-shared-mailboxes.md) почтовые ящики и [создать общий почтовый ящик](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="37d0d-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="37d0d-151">Преобразование почтового ящика удаленного пользователя</span><span class="sxs-lookup"><span data-stu-id="37d0d-151">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="37d0d-p111">Предположим, что вы удалили учетную запись пользователя, а теперь хотите преобразовать его почтовый ящик в общий. Вот что вам нужно будет сделать:</span><span class="sxs-lookup"><span data-stu-id="37d0d-p111">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="37d0d-154">[Восстановите учетную запись пользователя](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="37d0d-154">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="37d0d-155">Убедитесь, что ей назначена лицензия Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37d0d-155">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="37d0d-156">Сброс пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="37d0d-156">Reset the user's password.</span></span>
    
4. <span data-ttu-id="37d0d-157">Подождите 20-30 минут, пока почтовый ящик не восстановится.</span><span class="sxs-lookup"><span data-stu-id="37d0d-157">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="37d0d-158">Затем следуйте инструкциям на этой странице, чтобы преобразовать почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="37d0d-158">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="37d0d-159">После этого вы можете удалить лицензию из почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="37d0d-159">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="37d0d-160">Не удаляйте старый почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="37d0d-160">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="37d0d-161">К нему привязан общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="37d0d-161">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="37d0d-162">Добавьте участников в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="37d0d-162">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="37d0d-163">Преобразование общего почтового ящика обратно в личный почтовый ящик пользователя</span><span class="sxs-lookup"><span data-stu-id="37d0d-163">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="37d0d-164">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="37d0d-164">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="37d0d-165">Выберите пункт **получатели** \> , к **которым предоставлен общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-165">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="37d0d-166">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="37d0d-166">Select the shared mailbox.</span></span> <span data-ttu-id="37d0d-167">В разделе **Преобразование в обычный почтовый ящик**нажмите кнопку **преобразовать**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-167">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="37d0d-168">Вернитесь в центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="37d0d-168">Go back to the admin center.</span></span> <span data-ttu-id="37d0d-169">В разделе **Пользователи** выберите учетную запись, связанную с общим почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="37d0d-169">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="37d0d-170">Назначьте ей лицензию и сбросьте пароль.</span><span class="sxs-lookup"><span data-stu-id="37d0d-170">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="37d0d-p115">Настройка почтового ящика займет несколько минут. После этого его можно будет использовать. После входа пользователь увидит почту и календарь, которые были в общем почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="37d0d-p115">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="37d0d-173">Преобразование почтового ящика пользователя в гибридной среде</span><span class="sxs-lookup"><span data-stu-id="37d0d-173">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="37d0d-174">Если этот общий почтовый ящик находится в гибридной среде, **настоятельно рекомендуется** (почти обязательно) переместить почтовый ящик пользователя обратно в локальную систему, преобразовать почтовый ящик пользователя в общий почтовый ящик, а затем переместить общий почтовый ящик обратно в облако.</span><span class="sxs-lookup"><span data-stu-id="37d0d-174">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span>

<span data-ttu-id="37d0d-175">Вот почему: при преобразовании почтового ящика в облаке он может быть преобразован, но в локальной системе все еще будет расмнению почтовый ящик пользователя, так как новая реальность не синхронизируется с локальной средой.</span><span class="sxs-lookup"><span data-stu-id="37d0d-175">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="37d0d-176">Как правило, это не проблема, но существуют некоторые сценарии, в которых локальные атрибуты (которые считают, что почтовый ящик является почтовым ящиком пользователя), могут переопределять новые облачные версии этих атрибутов, а это может привести к обратному преобразованию почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="37d0d-176">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="37d0d-177">Это проблема, так как почтовые ящики пользователей нуждаются в лицензиях **или обратимо удалены через 30 дней**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-177">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="37d0d-178">Мы предоставили основные причины, по которым это происходит, но это по-прежнему может произойти, хотя и нечасто.</span><span class="sxs-lookup"><span data-stu-id="37d0d-178">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="37d0d-179">Лучше всего обеспечить безопасность и переместить почтовый ящик обратно в локальное.</span><span class="sxs-lookup"><span data-stu-id="37d0d-179">It's best to be safe and move the mailbox back to on-premises.</span></span>

> [!NOTE]
> <span data-ttu-id="37d0d-180">Если вы участвуете в управлении организацией или получателем, вы можете использовать командную консоль Exchange для изменения почтового ящика пользователя на локальный общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="37d0d-180">If you are a part of Organization Management or Recipient Management, you can use the  Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="37d0d-181">Например, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="37d0d-181">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="37d0d-182">В этом решении можно найти обходной путь для экземпляров [, когда общие почтовые ящики неожиданно преобразуются в почтовые ящики](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span><span class="sxs-lookup"><span data-stu-id="37d0d-182">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="37d0d-183">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="37d0d-183">Related articles</span></span>

[<span data-ttu-id="37d0d-184">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="37d0d-184">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="37d0d-185">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="37d0d-185">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="37d0d-186">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="37d0d-186">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="37d0d-187">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="37d0d-187">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="37d0d-188">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="37d0d-188">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
