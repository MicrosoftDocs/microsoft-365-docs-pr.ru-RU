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
description: 'Удалите лицензию из общего почтового ящика, чтобы назначить ее другому пользователю. '
ms.openlocfilehash: 11d5185cc3f79899a737ddccc0a93160acb380bc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698307"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="f3994-103">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="f3994-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f3994-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="f3994-104">The admin center is changing.</span></span> <span data-ttu-id="f3994-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f3994-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="f3994-106">Для общих почтовых ящиков обычно не требуется лицензия.</span><span class="sxs-lookup"><span data-stu-id="f3994-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="f3994-107">Следуйте этим инструкциям, чтобы удалить лицензию из общего почтового ящика, чтобы назначить ее пользователю или вернуть лицензию, чтобы не платить за лицензию, которая вам не нужна.</span><span class="sxs-lookup"><span data-stu-id="f3994-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="f3994-108">Лицензия требуется в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="f3994-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="f3994-109">Общий почтовый ящик использует более 50 ГБ памяти.</span><span class="sxs-lookup"><span data-stu-id="f3994-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="f3994-110">Общий почтовый ящик использует архив на месте.</span><span class="sxs-lookup"><span data-stu-id="f3994-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="f3994-111">Общий почтовый ящик помещается на судебное удержание.</span><span class="sxs-lookup"><span data-stu-id="f3994-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="f3994-112">Общему почтовому ящику назначена лицензия Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="f3994-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="f3994-113">Удаление лицензии</span><span class="sxs-lookup"><span data-stu-id="f3994-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f3994-114">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="f3994-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f3994-115">Необходимо удалить лицензию со страницы "Активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="f3994-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f3994-116">Лицензию нельзя удалить со страницы общего почтового ящика, так как лицензии являются пользовательскими настройками.</span><span class="sxs-lookup"><span data-stu-id="f3994-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="f3994-117">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="f3994-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="f3994-118">На одной **вкладке "Лицензии и** приложения" разоберите "Лицензии" и снимите этот список. </span><span class="sxs-lookup"><span data-stu-id="f3994-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="f3994-119">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="f3994-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="f3994-120">Когда вы вернетесь на страницу **"Активные** пользователи", состояние общего почтового ящика будет **нелицензным.**</span><span class="sxs-lookup"><span data-stu-id="f3994-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f3994-121">Вы по-прежнему платите за лицензию.</span><span class="sxs-lookup"><span data-stu-id="f3994-121">You're still paying for the license.</span></span> <span data-ttu-id="f3994-122">Чтобы прекратить оплату, [удалите лицензию из подписки.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="f3994-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="f3994-123">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="f3994-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f3994-124">Необходимо удалить лицензию со страницы "Активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="f3994-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f3994-125">Лицензию нельзя удалить со страницы общего почтового ящика, так как лицензии являются пользовательскими настройками.</span><span class="sxs-lookup"><span data-stu-id="f3994-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="f3994-126">Выберите общий почтовый ящик и выберите "Изменить **рядом** с **лицензиями на продукты".**</span><span class="sxs-lookup"><span data-stu-id="f3994-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="f3994-127">На одной **странице "Лицензии на** продукты" установите для отключаемой лицензии выключение. </span><span class="sxs-lookup"><span data-stu-id="f3994-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="f3994-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f3994-128">Select **Save**.</span></span>

5. <span data-ttu-id="f3994-129">Когда вы вернетесь на страницу **"Активные** пользователи", состояние общего почтового ящика будет **нелицензным.**</span><span class="sxs-lookup"><span data-stu-id="f3994-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f3994-130">Вы по-прежнему платите за лицензию.</span><span class="sxs-lookup"><span data-stu-id="f3994-130">You're still paying for the license.</span></span> <span data-ttu-id="f3994-131">Чтобы прекратить оплату, [удалите лицензию из подписки.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="f3994-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="f3994-132">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="f3994-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f3994-133">Необходимо удалить лицензию со страницы "Активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="f3994-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f3994-134">Лицензию нельзя удалить со страницы общего почтового ящика, так как лицензии являются пользовательскими настройками.</span><span class="sxs-lookup"><span data-stu-id="f3994-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="f3994-135">Выберите общий почтовый ящик и выберите "Изменить **рядом** с **лицензиями на продукты".**</span><span class="sxs-lookup"><span data-stu-id="f3994-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="f3994-136">На одной **странице "Лицензии на** продукты" установите для отключаемой лицензии выключение. </span><span class="sxs-lookup"><span data-stu-id="f3994-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="f3994-137">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f3994-137">Select **Save**.</span></span>

5. <span data-ttu-id="f3994-138">Когда вы вернетесь на страницу **"Активные** пользователи", состояние общего почтового ящика будет **нелицензным.**</span><span class="sxs-lookup"><span data-stu-id="f3994-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f3994-139">Вы по-прежнему платите за лицензию.</span><span class="sxs-lookup"><span data-stu-id="f3994-139">You're still paying for the license.</span></span> <span data-ttu-id="f3994-140">Чтобы прекратить оплату, [удалите лицензию из подписки.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="f3994-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="f3994-141">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="f3994-141">Related articles</span></span>

[<span data-ttu-id="f3994-142">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="f3994-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="f3994-143">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="f3994-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="f3994-144">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="f3994-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="f3994-145">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="f3994-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="f3994-146">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="f3994-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
