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
search.appverid:
- BCS160
- MET150
- MOE150
description: Создайте общий почтовый ящик и настройте некоторые параметры для своих пользователей, такие как пересылание электронной почты и автоматические ответы.
ms.openlocfilehash: ab23353f07a24f06d43172e8087819dd915ab720
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582672"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="b4359-103">Настройка параметров общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="b4359-103">Configure shared mailbox settings</span></span>

<span data-ttu-id="b4359-104">После создания [общего](create-a-shared-mailbox.md)почтового ящика необходимо настроить некоторые параметры для пользователей почтовых ящиков, такие как пересылание электронной почты и автоматические ответы.</span><span class="sxs-lookup"><span data-stu-id="b4359-104">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="b4359-105">Позже может потребоваться изменить другие параметры, такие как имя почтового ящика, члены или разрешения участников.</span><span class="sxs-lookup"><span data-stu-id="b4359-105">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="b4359-106">Изменение имени или псевдонима общего почтового ящика или изменение основного адреса электронной почты</span><span class="sxs-lookup"><span data-stu-id="b4359-106">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="b4359-107">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="b4359-107">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="b4359-108">Выберите общий почтовый ящик, который необходимо изменить, а затем выберите **Изменить** рядом с **псевдонимами Name, Email, Email.**</span><span class="sxs-lookup"><span data-stu-id="b4359-108">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="b4359-109">Введите новое имя или добавьте другой псевдоним.</span><span class="sxs-lookup"><span data-stu-id="b4359-109">Enter a new name, or add another alias.</span></span> <span data-ttu-id="b4359-110">Если вы хотите изменить основной адрес электронной почты, ваш почтовый ящик должен иметь несколько псевдонимов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b4359-110">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="b4359-111">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-111">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="b4359-112">Пересылка сообщений, отправленных на общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="b4359-112">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="b4359-113">Вам не нужно назначать лицензию общему почтовому ящику для пересылаемой им электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b4359-113">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="b4359-114">Вы можете переададовать сообщения на любой допустимый адрес электронной почты или список рассылки.</span><span class="sxs-lookup"><span data-stu-id="b4359-114">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="b4359-115">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="b4359-115">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="b4359-116">Выберите общий почтовый ящик, который необходимо изменить, а затем выберите **изменить переададку** \> **электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="b4359-116">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="b4359-117">Установите перенастройку **в On** и введите один адрес электронной почты для отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="b4359-117">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="b4359-118">Это может быть любой допустимый адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b4359-118">It can be any valid email address.</span></span> <span data-ttu-id="b4359-119">Чтобы переадпределить несколько [](/office365/admin/setup/create-distribution-lists) адресов, необходимо создать группу рассылки для адресов, а затем ввести имя группы в этом поле.</span><span class="sxs-lookup"><span data-stu-id="b4359-119">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="b4359-120">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-120">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="b4359-121">Отправка автоматических ответов с общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="b4359-121">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="b4359-122">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="b4359-122">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="b4359-123">Выберите общий почтовый ящик, который необходимо изменить, а затем выберите **Автоматические ответы** \> **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-123">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="b4359-124">Установите toggle **on** и выберите, отправлять ли ответ людям внутри организации или за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="b4359-124">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="b4359-p105">Введите текст ответа, который должен отправляться пользователям в организации. Добавить можно только текст без изображений.</span><span class="sxs-lookup"><span data-stu-id="b4359-p105">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="b4359-127">Если вы хотите *также* отправить ответ людям за пределами организации, выберите контрольный ящик, который вы хотите получить ответ, и введите текст.</span><span class="sxs-lookup"><span data-stu-id="b4359-127">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="b4359-128">Сделать так, чтобы ответ отправлялся только пользователям за пределами организации и не отправлялся пользователям внутри нее, невозможно.</span><span class="sxs-lookup"><span data-stu-id="b4359-128">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="b4359-129">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-129">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="b4359-130">Предоставление всем пользователям разрешения на просмотр отправленных сообщений (ответов)</span><span class="sxs-lookup"><span data-stu-id="b4359-130">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="b4359-p107">По умолчанию сообщения, отправленные с общего почтового ящика, не сохраняются в папке "Отправленные" этого почтового ящика. Вместо этого они сохраняются в папке "Отправленные" отправителя.</span><span class="sxs-lookup"><span data-stu-id="b4359-p107">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="b4359-133">Если вы хотите разрешить всем видеть отправленную электронную почту в центре администрирования, изменить параметры общих почтовых ящиков и выбрать **пункты Sent** \> **Edit**.</span><span class="sxs-lookup"><span data-stu-id="b4359-133">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="b4359-134">Выберите приложения, которые общий почтовый ящик может использовать для доступа к электронной почте Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b4359-134">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="b4359-135">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="b4359-135">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="b4359-136">Выберите общий почтовый ящик, который необходимо изменить, а затем выберите **изменить приложения** \> **электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="b4359-136">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="b4359-137">Установите для всех  приложений, которые пользователи могут использовать для доступа к общему почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="b4359-137">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="b4359-138">Установите отключку **для** любых приложений, которые вы не хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="b4359-138">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="b4359-139">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-139">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="b4359-140">Поместить общий почтовый ящик на удержание судебного разбирательства</span><span class="sxs-lookup"><span data-stu-id="b4359-140">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="b4359-141">Дополнительные дополнительные информацию о удержании судебного разбирательства см. в дополнительных подробной информации [о создании судебного удержания.](../../compliance/create-a-litigation-hold.md)</span><span class="sxs-lookup"><span data-stu-id="b4359-141">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="b4359-142">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="b4359-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="b4359-143">Выберите общий почтовый ящик, который необходимо изменить, а затем выберите **Редактирование удержания** \> **для судебного разбирательства.**</span><span class="sxs-lookup"><span data-stu-id="b4359-143">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="b4359-144">Установите toggle **on**.</span><span class="sxs-lookup"><span data-stu-id="b4359-144">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="b4359-145">Необязательно введите продолжительность, примечание о удержании и URL-адрес с дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="b4359-145">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="b4359-146">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-146">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="b4359-147">Добавление или удаление участников</span><span class="sxs-lookup"><span data-stu-id="b4359-147">Add or remove members</span></span>

1. <span data-ttu-id="b4359-148">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="b4359-148">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="b4359-149">Выберите общий почтовый ящик, который необходимо изменить, а затем выберите **Members** \> **Edit**.</span><span class="sxs-lookup"><span data-stu-id="b4359-149">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="b4359-150">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="b4359-150">Do one of the following:</span></span>
   - <span data-ttu-id="b4359-151">Чтобы добавить участников, выберите **Добавить участников,** найти или выбрать члена, чтобы добавить, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-151">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="b4359-152">Чтобы удалить участников, при необходимости используйте поле Поиск для поиска участника, выберите **X** рядом с именем участника, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-152">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="b4359-153">Выберите **Сохранить** снова.</span><span class="sxs-lookup"><span data-stu-id="b4359-153">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="b4359-154">Добавление или удаление разрешений участников</span><span class="sxs-lookup"><span data-stu-id="b4359-154">Add or remove permissions of members</span></span>

1. <span data-ttu-id="b4359-155">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="b4359-155">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="b4359-156">Выберите общий почтовый ящик, который необходимо изменить, а затем выберите **разрешения На** \> **настройку членов.**</span><span class="sxs-lookup"><span data-stu-id="b4359-156">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="b4359-157">Выберите **Изменить** рядом с разрешением, который необходимо изменить для участника.</span><span class="sxs-lookup"><span data-stu-id="b4359-157">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="b4359-158">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="b4359-158">Do one of the following:</span></span>
   - <span data-ttu-id="b4359-159">Чтобы предоставить это разрешение дополнительному члену, выберите **Добавить** разрешения, найти или выбрать члена, чтобы добавить, а затем **выберите Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-159">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="b4359-160">Чтобы удалить разрешение у участника, в случае необходимости используйте поле Поиск для поиска участника, выберите **X** рядом с именем участника, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-160">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="b4359-161">Выберите **Сохранить** снова.</span><span class="sxs-lookup"><span data-stu-id="b4359-161">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="b4359-162">Показать или скрыть общий почтовый ящик в глобальном списке адресов</span><span class="sxs-lookup"><span data-stu-id="b4359-162">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="b4359-163">Если вы решите не показывать общий почтовый ящик в глобальном списке адресов, почтовый ящик не будет отображаться в списке адресов организации, но он по-прежнему будет получать отправленную им электронную почту.</span><span class="sxs-lookup"><span data-stu-id="b4359-163">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="b4359-164">В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.</span><span class="sxs-lookup"><span data-stu-id="b4359-164">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="b4359-165">Выберите общий почтовый ящик, который необходимо изменить, а затем выберите **Показать в глобальном списке** \> **адресов Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-165">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="b4359-166">Установите переключеть **на или** **отключить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-166">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="b4359-167">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b4359-167">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b4359-168">Сокрытие общего почтового ящика из списка адресов сделает невозможным добавление скрытого почтового ящика в профиль Outlook до тех пор, пока общий почтовый ящик не будет снова показан в списке адресов.</span><span class="sxs-lookup"><span data-stu-id="b4359-168">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="b4359-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4359-169">Related content</span></span>

<span data-ttu-id="b4359-170">[Сведения об общих почтовых ящиках](about-shared-mailboxes.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="b4359-170">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>

<span data-ttu-id="b4359-171">[Создание общего почтового ящика](create-a-shared-mailbox.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="b4359-171">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="b4359-172">[Преобразование почтового ящика пользователя в общий почтовый ящик](convert-user-mailbox-to-shared-mailbox.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="b4359-172">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="b4359-173">[Удаление лицензии из общего почтового ящика](remove-license-from-shared-mailbox.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="b4359-173">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="b4359-174">[Решение проблем с общими почтовыми ящиками](resolve-issues-with-shared-mailboxes.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="b4359-174">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>