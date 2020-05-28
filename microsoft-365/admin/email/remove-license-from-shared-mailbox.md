---
title: Удаление лицензии из общего почтового ящика
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Удалить лицензию из общего почтового ящика, чтобы назначить ее другому пользователю. '
ms.openlocfilehash: 1f69cd6f0e572da18abf7253832604ad3ac0ab8f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400032"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="3fd43-103">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="3fd43-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3fd43-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="3fd43-104">The admin center is changing.</span></span> <span data-ttu-id="3fd43-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="3fd43-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="3fd43-106">Для общих почтовых ящиков обычно не требуется лицензия.</span><span class="sxs-lookup"><span data-stu-id="3fd43-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="3fd43-107">Следуйте этим инструкциям, чтобы удалить лицензию из общего почтового ящика, чтобы ее можно было назначить пользователю или вернуть лицензию, чтобы не платить за ненужные лицензии.</span><span class="sxs-lookup"><span data-stu-id="3fd43-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="3fd43-108">Лицензия необходима в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="3fd43-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="3fd43-109">Общий почтовый ящик содержит более 50 ГБ дискового пространства для использования.</span><span class="sxs-lookup"><span data-stu-id="3fd43-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="3fd43-110">В общем почтовом ящике используется Архивация на месте.</span><span class="sxs-lookup"><span data-stu-id="3fd43-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="3fd43-111">Общий почтовый ящик находится в режиме хранения для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="3fd43-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="3fd43-112">Удаление лицензии</span><span class="sxs-lookup"><span data-stu-id="3fd43-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="3fd43-113">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="3fd43-113">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="3fd43-114">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3fd43-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3fd43-115">Эту лицензию необходимо удалить на странице "активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="3fd43-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3fd43-116">Вы не можете удалить лицензию со страницы общего почтового ящика, так как лицензии являются параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="3fd43-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="3fd43-117">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3fd43-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="3fd43-118">На вкладке **лицензии и приложения** разверните узел **лицензии** и снимите флажок рядом с удаляемой лицензией.</span><span class="sxs-lookup"><span data-stu-id="3fd43-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="3fd43-119">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="3fd43-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="3fd43-120">Когда вы вернетесь на страницу **Активные пользователи** , состояние общего почтового ящика будет **нелицензионным**.</span><span class="sxs-lookup"><span data-stu-id="3fd43-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3fd43-121">Вы по-прежнему оплачиваете лицензию.</span><span class="sxs-lookup"><span data-stu-id="3fd43-121">You're still paying for the license.</span></span> <span data-ttu-id="3fd43-122">Чтобы прекратить оплату, [удалите лицензию из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3fd43-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="3fd43-123">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3fd43-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3fd43-124">Эту лицензию необходимо удалить на странице "активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="3fd43-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3fd43-125">Вы не можете удалить лицензию со страницы общего почтового ящика, так как лицензии являются параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="3fd43-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="3fd43-126">Выберите общий почтовый ящик, а затем нажмите кнопку **изменить** рядом с пунктом **лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="3fd43-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="3fd43-127">Одну страницу " **лицензии продукта** ", установите переключатель в состояние " **выключен** " для удаляемой лицензии.</span><span class="sxs-lookup"><span data-stu-id="3fd43-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="3fd43-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3fd43-128">Select **Save**.</span></span>

5. <span data-ttu-id="3fd43-129">Когда вы вернетесь на страницу **Активные пользователи** , состояние общего почтового ящика будет **нелицензионным**.</span><span class="sxs-lookup"><span data-stu-id="3fd43-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3fd43-130">Вы по-прежнему оплачиваете лицензию.</span><span class="sxs-lookup"><span data-stu-id="3fd43-130">You're still paying for the license.</span></span> <span data-ttu-id="3fd43-131">Чтобы прекратить оплату, [удалите лицензию из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3fd43-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="3fd43-132">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3fd43-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3fd43-133">Эту лицензию необходимо удалить на странице "активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="3fd43-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3fd43-134">Вы не можете удалить лицензию со страницы общего почтового ящика, так как лицензии являются параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="3fd43-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="3fd43-135">Выберите общий почтовый ящик, а затем нажмите кнопку **изменить** рядом с пунктом **лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="3fd43-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="3fd43-136">Одну страницу " **лицензии продукта** ", установите переключатель в состояние " **выключен** " для удаляемой лицензии.</span><span class="sxs-lookup"><span data-stu-id="3fd43-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="3fd43-137">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3fd43-137">Select **Save**.</span></span>

5. <span data-ttu-id="3fd43-138">Когда вы вернетесь на страницу **Активные пользователи** , состояние общего почтового ящика будет **нелицензионным**.</span><span class="sxs-lookup"><span data-stu-id="3fd43-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3fd43-139">Вы по-прежнему оплачиваете лицензию.</span><span class="sxs-lookup"><span data-stu-id="3fd43-139">You're still paying for the license.</span></span> <span data-ttu-id="3fd43-140">Чтобы прекратить оплату, [удалите лицензию из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3fd43-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="3fd43-141">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="3fd43-141">Related articles</span></span>

[<span data-ttu-id="3fd43-142">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="3fd43-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="3fd43-143">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="3fd43-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="3fd43-144">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="3fd43-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="3fd43-145">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="3fd43-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="3fd43-146">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="3fd43-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
