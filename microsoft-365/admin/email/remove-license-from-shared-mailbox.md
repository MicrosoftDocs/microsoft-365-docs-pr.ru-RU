---
title: Удаление лицензии из общего почтового ящика
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
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Удалить лицензию из общего почтового ящика, чтобы назначить ее другому пользователю. '
ms.openlocfilehash: 43d32744afe42a8f244160ace20c1d989f501b28
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445499"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="1c063-103">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="1c063-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1c063-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="1c063-104">The admin center is changing.</span></span> <span data-ttu-id="1c063-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="1c063-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="1c063-106">Для общих почтовых ящиков обычно не требуется лицензия.</span><span class="sxs-lookup"><span data-stu-id="1c063-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="1c063-107">Следуйте этим инструкциям, чтобы удалить лицензию из общего почтового ящика, чтобы ее можно было назначить пользователю или вернуть лицензию, чтобы не платить за ненужные лицензии.</span><span class="sxs-lookup"><span data-stu-id="1c063-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="1c063-108">Лицензия необходима в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="1c063-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="1c063-109">Общий почтовый ящик содержит более 50 ГБ дискового пространства для использования.</span><span class="sxs-lookup"><span data-stu-id="1c063-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="1c063-110">В общем почтовом ящике используется Архивация на месте.</span><span class="sxs-lookup"><span data-stu-id="1c063-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="1c063-111">Общий почтовый ящик находится в режиме хранения для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="1c063-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="1c063-112">Удаление лицензии</span><span class="sxs-lookup"><span data-stu-id="1c063-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1c063-113">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="1c063-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1c063-114">Эту лицензию необходимо удалить на странице "активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="1c063-114">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="1c063-115">Вы не можете удалить лицензию со страницы общего почтового ящика, так как лицензии являются параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="1c063-115">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="1c063-116">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="1c063-116">Select the shared mailbox.</span></span>

3. <span data-ttu-id="1c063-117">На вкладке **лицензии и приложения** разверните узел **лицензии** и снимите флажок рядом с удаляемой лицензией.</span><span class="sxs-lookup"><span data-stu-id="1c063-117">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="1c063-118">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="1c063-118">Select **Save changes**.</span></span>

5. <span data-ttu-id="1c063-119">Когда вы вернетесь на страницу **Активные пользователи** , состояние общего почтового ящика будет **нелицензионным**.</span><span class="sxs-lookup"><span data-stu-id="1c063-119">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="1c063-120">Вы по-прежнему оплачиваете лицензию.</span><span class="sxs-lookup"><span data-stu-id="1c063-120">You're still paying for the license.</span></span> <span data-ttu-id="1c063-121">Чтобы прекратить оплату, [удалите лицензию из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="1c063-121">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="1c063-122">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="1c063-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1c063-123">Эту лицензию необходимо удалить на странице "активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="1c063-123">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="1c063-124">Вы не можете удалить лицензию со страницы общего почтового ящика, так как лицензии являются параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="1c063-124">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="1c063-125">Выберите общий почтовый ящик, а затем нажмите кнопку **изменить** рядом с пунктом **лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="1c063-125">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="1c063-126">Одну страницу " **лицензии продукта** ", установите переключатель в состояние " **выключен** " для удаляемой лицензии.</span><span class="sxs-lookup"><span data-stu-id="1c063-126">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="1c063-127">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1c063-127">Select **Save**.</span></span>

5. <span data-ttu-id="1c063-128">Когда вы вернетесь на страницу **Активные пользователи** , состояние общего почтового ящика будет **нелицензионным**.</span><span class="sxs-lookup"><span data-stu-id="1c063-128">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="1c063-129">Вы по-прежнему оплачиваете лицензию.</span><span class="sxs-lookup"><span data-stu-id="1c063-129">You're still paying for the license.</span></span> <span data-ttu-id="1c063-130">Чтобы прекратить оплату, [удалите лицензию из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="1c063-130">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="1c063-131">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="1c063-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1c063-132">Эту лицензию необходимо удалить на странице "активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="1c063-132">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="1c063-133">Вы не можете удалить лицензию со страницы общего почтового ящика, так как лицензии являются параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="1c063-133">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="1c063-134">Выберите общий почтовый ящик, а затем нажмите кнопку **изменить** рядом с пунктом **лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="1c063-134">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="1c063-135">Одну страницу " **лицензии продукта** ", установите переключатель в состояние " **выключен** " для удаляемой лицензии.</span><span class="sxs-lookup"><span data-stu-id="1c063-135">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="1c063-136">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1c063-136">Select **Save**.</span></span>

5. <span data-ttu-id="1c063-137">Когда вы вернетесь на страницу **Активные пользователи** , состояние общего почтового ящика будет **нелицензионным**.</span><span class="sxs-lookup"><span data-stu-id="1c063-137">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="1c063-138">Вы по-прежнему оплачиваете лицензию.</span><span class="sxs-lookup"><span data-stu-id="1c063-138">You're still paying for the license.</span></span> <span data-ttu-id="1c063-139">Чтобы прекратить оплату, [удалите лицензию из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="1c063-139">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="1c063-140">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="1c063-140">Related articles</span></span>

[<span data-ttu-id="1c063-141">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="1c063-141">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="1c063-142">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="1c063-142">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="1c063-143">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="1c063-143">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="1c063-144">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="1c063-144">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="1c063-145">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="1c063-145">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
