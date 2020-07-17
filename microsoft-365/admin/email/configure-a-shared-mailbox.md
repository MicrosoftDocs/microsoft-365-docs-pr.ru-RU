---
title: Настройка параметров общего почтового ящика
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
description: После создания общего почтового ящика необходимо настроить некоторые параметры для пользователей, например переадресацию электронной почты и автоматические ответы. Позже может потребоваться изменить другие параметры, такие как имя или элементы почтового ящика.
ms.openlocfilehash: 3bde856f4db80192f5ed058a18c7942aa6a724b2
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739200"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="38555-104">Настройка параметров общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="38555-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="38555-105">После [создания общего почтового ящика](create-a-shared-mailbox.md)необходимо настроить некоторые параметры для пользователей почтовых ящиков, таких как переадресация электронной почты и автоматические ответы.</span><span class="sxs-lookup"><span data-stu-id="38555-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="38555-106">Позже может потребоваться изменить другие параметры, например имя почтового ящика, участников или разрешения участника.</span><span class="sxs-lookup"><span data-stu-id="38555-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="38555-107">Изменение имени или псевдонима электронной почты для общего почтового ящика или изменение основного адреса электронной почты</span><span class="sxs-lookup"><span data-stu-id="38555-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="38555-108">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="38555-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="38555-109">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="38555-110">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="38555-111">Выберите общий почтовый ящик, который требуется изменить, а затем нажмите кнопку **изменить** рядом с полем **имя, электронная почта, псевдонимы электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="38555-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="38555-112">Введите новое имя или добавьте другой псевдоним.</span><span class="sxs-lookup"><span data-stu-id="38555-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="38555-113">Если вы хотите изменить основной адрес электронной почты, ваш почтовый ящик должен иметь более одного псевдонима электронной почты.</span><span class="sxs-lookup"><span data-stu-id="38555-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="38555-114">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38555-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="38555-115">Пересылка сообщений, отправленных на общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="38555-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="38555-116">Для пересылки отправленного сообщения электронной почты не требуется назначать лицензию для общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="38555-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="38555-117">Сообщения можно пересылать на любой действительный адрес электронной почты или список рассылки.</span><span class="sxs-lookup"><span data-stu-id="38555-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="38555-118">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="38555-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="38555-119">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="38555-120">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="38555-121">Выберите общий почтовый ящик, который требуется изменить, а затем выберите пункт изменение **переадресации электронной почты** \> **Edit**.</span><span class="sxs-lookup"><span data-stu-id="38555-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="38555-122">Установите переключатель в значение **вкл**., а затем введите один адрес электронной почты, на который будет пересылаться сообщение.</span><span class="sxs-lookup"><span data-stu-id="38555-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="38555-123">Это может быть любой действительный адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="38555-123">It can be any valid email address.</span></span> <span data-ttu-id="38555-124">Для пересылки по нескольким адресам необходимо [создать группу рассылки](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) для адресов, а затем ввести в это поле Имя группы.</span><span class="sxs-lookup"><span data-stu-id="38555-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="38555-125">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38555-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="38555-126">Отправка автоматических ответов с общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="38555-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="38555-127">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="38555-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="38555-128">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="38555-129">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="38555-130">Выберите общий почтовый ящик, который требуется изменить, а затем выберите пункт **автоматически отвечать** на \> **Редактирование**.</span><span class="sxs-lookup"><span data-stu-id="38555-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="38555-131">Установите переключатель в значение **вкл**., чтобы отправить ответ пользователям внутри организации или за пределами Организации.</span><span class="sxs-lookup"><span data-stu-id="38555-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="38555-132">Введите текст ответа, который должен отправляться пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="38555-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="38555-133">Добавить можно только текст без изображений.</span><span class="sxs-lookup"><span data-stu-id="38555-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="38555-134">Если вы хотите *также* отправить ответ пользователям, не входящим в вашу организацию, установите флажок, чтобы получить ответ, и введите текст.</span><span class="sxs-lookup"><span data-stu-id="38555-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="38555-135">Сделать так, чтобы ответ отправлялся только пользователям за пределами организации и не отправлялся пользователям внутри нее, невозможно.</span><span class="sxs-lookup"><span data-stu-id="38555-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="38555-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38555-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="38555-137">Предоставление всем пользователям разрешения на просмотр отправленных сообщений (ответов)</span><span class="sxs-lookup"><span data-stu-id="38555-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="38555-p108">По умолчанию сообщения, отправленные с общего почтового ящика, не сохраняются в папке "Отправленные" этого почтового ящика. Вместо этого они сохраняются в папке "Отправленные" отправителя.</span><span class="sxs-lookup"><span data-stu-id="38555-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="38555-140">Если вы хотите разрешить всем пользователям просматривать отправленные сообщения электронной почты, в центре администрирования, изменить параметры общего почтового ящика и выбрать команду Изменить **Отправленные элементы** \> **Edit**.</span><span class="sxs-lookup"><span data-stu-id="38555-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="38555-141">Выбор приложений, которые могут использовать общий почтовый ящик для доступа к электронной почте Майкрософт</span><span class="sxs-lookup"><span data-stu-id="38555-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="38555-142">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="38555-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="38555-143">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="38555-144">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="38555-145">Выберите общий почтовый ящик, который требуется изменить, а затем выберите пункт **почтовые приложения** \> **изменить**.</span><span class="sxs-lookup"><span data-stu-id="38555-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="38555-146">Установите переключатель в значение **вкл** . для всех приложений, которые участники должны иметь возможность использовать для доступа к общему почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="38555-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="38555-147">Установите переключатель **Отключить** для всех приложений, которые не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="38555-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="38555-148">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38555-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="38555-149">Добавление общего почтового ящика на удержание для судебного разбирательства</span><span class="sxs-lookup"><span data-stu-id="38555-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="38555-150">Дополнительные сведения о удержаниях для судебного разбирательства приведены в разделе [Создание удержания для судебного разбирательства](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="38555-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="38555-151">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="38555-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="38555-152">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="38555-153">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="38555-154">Выберите общий почтовый ящик, который требуется изменить, а затем выберите Изменить **удержание для судебного разбирательства** \> **Edit**.</span><span class="sxs-lookup"><span data-stu-id="38555-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="38555-155">Установите переключатель в значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="38555-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="38555-156">При необходимости введите длительность, s Примечание об удержании и URL-адрес с дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="38555-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="38555-157">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38555-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="38555-158">Добавление и удаление участников</span><span class="sxs-lookup"><span data-stu-id="38555-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="38555-159">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="38555-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="38555-160">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="38555-161">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="38555-162">Выберите общий почтовый ящик, который требуется изменить, а затем **Members** нажмите кнопку \> **изменить**элементы.</span><span class="sxs-lookup"><span data-stu-id="38555-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="38555-163">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="38555-163">Do one of the following:</span></span>
   - <span data-ttu-id="38555-164">Чтобы добавить участников, выберите **Добавить участников**, выполните поиск или выберите добавляемого участника, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38555-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="38555-165">Чтобы удалить участников, используйте поле поиска для поиска члена, если это необходимо, выберите **X** рядом с именем участника, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38555-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="38555-166">Снова нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="38555-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="38555-167">Добавление и удаление разрешений членов</span><span class="sxs-lookup"><span data-stu-id="38555-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="38555-168">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="38555-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="38555-169">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="38555-170">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="38555-171">Выберите общий почтовый ящик, который требуется изменить, а затем выберите **элементы** \> **Настройка разрешений**.</span><span class="sxs-lookup"><span data-stu-id="38555-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="38555-172">Нажмите кнопку **изменить** рядом с разрешением, которое нужно изменить для члена.</span><span class="sxs-lookup"><span data-stu-id="38555-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="38555-173">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="38555-173">Do one of the following:</span></span>
   - <span data-ttu-id="38555-174">Чтобы предоставить это разрешение дополнительному участнику, выберите **Добавить разрешения**, выполните поиск или выберите участника, которого требуется добавить, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38555-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="38555-175">Чтобы удалить разрешение для члена, используйте поле поиска для поиска члена, если это необходимо, выберите **X** рядом с именем члена и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38555-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="38555-176">Снова нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="38555-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="38555-177">Отображение или скрытие общего почтового ящика в глобальном списке адресов</span><span class="sxs-lookup"><span data-stu-id="38555-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="38555-178">Если вы отказываетесь от отображения общего почтового ящика в глобальном списке адресов, почтовый ящик не будет отображаться в списке адресов вашей организации, но он по-прежнему будет получать отправленные ему сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="38555-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="38555-179">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="38555-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="38555-180">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="38555-181">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Центре администрирования</a> откройте страницу **Группы** > **Общие почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="38555-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="38555-182">Выберите общий почтовый ящик, который требуется изменить, а затем выберите пункт **Показать в поле глобальный список адресов** \> **Edit**.</span><span class="sxs-lookup"><span data-stu-id="38555-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="38555-183">Установите переключатель **вкл** **.**</span><span class="sxs-lookup"><span data-stu-id="38555-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="38555-184">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="38555-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="38555-185">Скрытие общего почтового ящика из списка адресов сделает невозможным Добавление скрытого почтового ящика в свой профиль Outlook для новых участников почтового ящика, пока общий почтовый ящик не будет снова отображаться в списке адресов.</span><span class="sxs-lookup"><span data-stu-id="38555-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="38555-186">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="38555-186">Related articles</span></span>

[<span data-ttu-id="38555-187">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="38555-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="38555-188">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="38555-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="38555-189">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="38555-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="38555-190">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="38555-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="38555-191">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="38555-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
