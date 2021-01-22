---
title: Настройка параметров общего почтового ящика
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: После создания общего почтового ящика необходимо настроить некоторые параметры для его пользователей, такие как пересылание электронной почты и автоматические ответы. Позднее может потребоваться изменить другие параметры, например имя или члены почтового ящика.
ms.openlocfilehash: fe5d35be556b8edf5456bc2c0b820dc0ce77e323
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926610"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="9a457-104">Настройка параметров общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="9a457-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="9a457-105">После создания [общего почтового](create-a-shared-mailbox.md)ящика необходимо настроить некоторые параметры для пользователей почтовых ящиков, такие как пересылание электронной почты и автоматические ответы.</span><span class="sxs-lookup"><span data-stu-id="9a457-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="9a457-106">Позднее может потребоваться изменить другие параметры, такие как имя почтового ящика, члены или разрешения участников.</span><span class="sxs-lookup"><span data-stu-id="9a457-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="9a457-107">Изменение имени или псевдонима общего почтового ящика или изменение основного адреса электронной почты</span><span class="sxs-lookup"><span data-stu-id="9a457-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9a457-108">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="9a457-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="9a457-109">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9a457-110">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="9a457-111">Выберите общий почтовый ящик, который нужно  изменить, а затем выберите "Изменить рядом с **именем", "Электронная почта", "Псевдонимы электронной почты".**</span><span class="sxs-lookup"><span data-stu-id="9a457-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="9a457-112">Введите новое имя или добавьте другой псевдоним.</span><span class="sxs-lookup"><span data-stu-id="9a457-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="9a457-113">Если вы хотите изменить основной адрес электронной почты, ваш почтовый ящик должен иметь несколько псевдонимов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9a457-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="9a457-114">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9a457-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="9a457-115">Пересылка сообщений, отправленных на общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="9a457-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="9a457-116">Вам не нужно назначать лицензию общему почтовому ящику, чтобы пересылать отправленные в него сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9a457-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="9a457-117">Вы можете переадпределять сообщения на любой действительный адрес электронной почты или в список рассылки.</span><span class="sxs-lookup"><span data-stu-id="9a457-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9a457-118">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="9a457-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="9a457-119">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9a457-120">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="9a457-121">Выберите общий почтовый ящик, который нужно изменить, а затем выберите "Изменить **пересылку** \> **электронной почты".**</span><span class="sxs-lookup"><span data-stu-id="9a457-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="9a457-122">Установите для этого toggle **"Вкл."** и введите один адрес электронной почты, на который будут переададратовать сообщения.</span><span class="sxs-lookup"><span data-stu-id="9a457-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="9a457-123">Это может быть любой допустимый адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9a457-123">It can be any valid email address.</span></span> <span data-ttu-id="9a457-124">Чтобы переад вперед на несколько [](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists) адресов, необходимо создать группу рассылки для этих адресов, а затем ввести имя группы в этом поле.</span><span class="sxs-lookup"><span data-stu-id="9a457-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="9a457-125">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9a457-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="9a457-126">Отправка автоматических ответов с общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="9a457-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9a457-127">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="9a457-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="9a457-128">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9a457-129">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="9a457-130">Выберите общий почтовый ящик, который нужно изменить, а затем выберите **"Изменить автоматические** \> **ответы".**</span><span class="sxs-lookup"><span data-stu-id="9a457-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="9a457-131">Установите для этого toggle **"Вкл."** и выберите, следует ли отправлять ответ людям внутри организации или за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="9a457-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="9a457-132">Введите текст ответа, который должен отправляться пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="9a457-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="9a457-133">Добавить можно только текст без изображений.</span><span class="sxs-lookup"><span data-stu-id="9a457-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="9a457-134">Если вы хотите *также* отправить ответ людям за пределами вашей организации, уберите его и введите текст.</span><span class="sxs-lookup"><span data-stu-id="9a457-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="9a457-135">Сделать так, чтобы ответ отправлялся только пользователям за пределами организации и не отправлялся пользователям внутри нее, невозможно.</span><span class="sxs-lookup"><span data-stu-id="9a457-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="9a457-136">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9a457-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="9a457-137">Предоставление всем пользователям разрешения на просмотр отправленных сообщений (ответов)</span><span class="sxs-lookup"><span data-stu-id="9a457-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="9a457-p108">По умолчанию сообщения, отправленные с общего почтового ящика, не сохраняются в папке "Отправленные" этого почтового ящика. Вместо этого они сохраняются в папке "Отправленные" отправителя.</span><span class="sxs-lookup"><span data-stu-id="9a457-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="9a457-140">Если вы хотите, чтобы все могли видеть отправленную электронную почту, в Центре  администрирования отредактируете параметры общего почтового ящика и выберите пункт "Изменить \> **отправленные"**.</span><span class="sxs-lookup"><span data-stu-id="9a457-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="9a457-141">Выбор приложений, которые общий почтовый ящик может использовать для доступа к электронной почте Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9a457-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9a457-142">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="9a457-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="9a457-143">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9a457-144">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="9a457-145">Выберите общий почтовый ящик, который нужно изменить, а затем выберите "Изменить **приложения электронной** \> **почты".**</span><span class="sxs-lookup"><span data-stu-id="9a457-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="9a457-146">Установите для всех  приложений, которые участники должны использовать для доступа к общему почтовому ящику, вкл.</span><span class="sxs-lookup"><span data-stu-id="9a457-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="9a457-147">Установите выключение для **всех** приложений, которые вы не хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="9a457-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="9a457-148">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9a457-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="9a457-149">Поместить общий почтовый ящик на судебное удержание</span><span class="sxs-lookup"><span data-stu-id="9a457-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="9a457-150">Дополнительные информацию о удержании для судебного разбирательства см. в [под вопросе "Создание судебного удержания".](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)</span><span class="sxs-lookup"><span data-stu-id="9a457-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9a457-151">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="9a457-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="9a457-152">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9a457-153">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="9a457-154">Выберите общий почтовый ящик, который нужно изменить, а затем выберите **"Изменить** для \> **судебного удержания".**</span><span class="sxs-lookup"><span data-stu-id="9a457-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="9a457-155">Установите для этого toggle **вкл.**</span><span class="sxs-lookup"><span data-stu-id="9a457-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="9a457-156">При желании введите длительность, примечание о удержании и URL-адрес с дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="9a457-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="9a457-157">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9a457-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="9a457-158">Добавление или удаление участников</span><span class="sxs-lookup"><span data-stu-id="9a457-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9a457-159">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="9a457-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="9a457-160">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9a457-161">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="9a457-162">Выберите общий почтовый ящик, который нужно изменить, а затем выберите **"Участники"** \> **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="9a457-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="9a457-163">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9a457-163">Do one of the following:</span></span>
   - <span data-ttu-id="9a457-164">Чтобы добавить участников, выберите **"Добавить членов",** найщите или выберите добавляемую и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="9a457-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="9a457-165">Чтобы удалить участников, при необходимости используйте поле поиска, чтобы найти его, выберите **X** рядом с именем участника, а затем выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="9a457-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="9a457-166">Снова **выберите "Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="9a457-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="9a457-167">Добавление и удаление разрешений участников</span><span class="sxs-lookup"><span data-stu-id="9a457-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9a457-168">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="9a457-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="9a457-169">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9a457-170">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="9a457-171">Выберите общий почтовый ящик, который нужно изменить, а затем выберите **"Участники"** \> **для настройки разрешений.**</span><span class="sxs-lookup"><span data-stu-id="9a457-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="9a457-172">Select **Edit** next to the permission you want to change for a member.</span><span class="sxs-lookup"><span data-stu-id="9a457-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="9a457-173">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9a457-173">Do one of the following:</span></span>
   - <span data-ttu-id="9a457-174">Чтобы предоставить это разрешение дополнительному члену, выберите "Добавить разрешения", "Найти или выбрать участника для добавления", а затем выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="9a457-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="9a457-175">Чтобы удалить разрешение у участника, при необходимости используйте поле поиска, чтобы найти его, выберите **X** рядом с именем участника, а затем выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="9a457-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="9a457-176">Снова **выберите "Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="9a457-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="9a457-177">Показать или скрыть общий почтовый ящик в глобальном списке адресов</span><span class="sxs-lookup"><span data-stu-id="9a457-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="9a457-178">Если общий почтовый ящик не будет отображаться в глобальном списке адресов, он не будет отображаться в списке адресов организации, но по-прежнему будет получать отправленную ему электронную почту.</span><span class="sxs-lookup"><span data-stu-id="9a457-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9a457-179">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="9a457-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="9a457-180">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9a457-181">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="9a457-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="9a457-182">Выберите общий почтовый ящик, который нужно изменить, а затем выберите "Показать в глобальном списке **адресов"** \> **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="9a457-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="9a457-183">Установите для этого переключия **"Вкл."** или **"Выкл."**</span><span class="sxs-lookup"><span data-stu-id="9a457-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="9a457-184">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9a457-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="9a457-185">Скрытие общего почтового ящика из списка адресов сделает невозможным добавление скрытого почтового ящика в профиль Outlook новыми участниками общего почтового ящика до тех пор, пока общий почтовый ящик не будет снова показан в списке адресов.</span><span class="sxs-lookup"><span data-stu-id="9a457-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="9a457-186">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="9a457-186">Related articles</span></span>

[<span data-ttu-id="9a457-187">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="9a457-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="9a457-188">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="9a457-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="9a457-189">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="9a457-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="9a457-190">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="9a457-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="9a457-191">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="9a457-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
