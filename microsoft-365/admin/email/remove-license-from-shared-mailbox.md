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
ms.openlocfilehash: 82ec863d5c2ae550fb401e71744715a27c89d382
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470623"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="c635f-103">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="c635f-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="c635f-104">Общие почтовые ящики обычно не требуют лицензии.</span><span class="sxs-lookup"><span data-stu-id="c635f-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="c635f-105">Следуйте этим инструкциям, чтобы удалить лицензию из общего почтового ящика, чтобы можно было назначить ее пользователю или вернуть лицензию, чтобы не платить за не нужная лицензия.</span><span class="sxs-lookup"><span data-stu-id="c635f-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="c635f-106">Лицензия требуется в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="c635f-106">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="c635f-107">Общий почтовый ящик имеет более 50 ГБ используемого хранилища.</span><span class="sxs-lookup"><span data-stu-id="c635f-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="c635f-108">Общий почтовый ящик использует архивативную передачу на месте.</span><span class="sxs-lookup"><span data-stu-id="c635f-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="c635f-109">Общий почтовый ящик помещается в удержание судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="c635f-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="c635f-110">Общий почтовый ящик имеет лицензию Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c635f-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="c635f-111">Удаление лицензии</span><span class="sxs-lookup"><span data-stu-id="c635f-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c635f-112">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="c635f-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c635f-113">Необходимо удалить лицензию со страницы Активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="c635f-113">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="c635f-114">Вы не можете удалить лицензию со страницы Общих почтовых ящиков, так как лицензии — это параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="c635f-114">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="c635f-115">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="c635f-115">Select the shared mailbox.</span></span>

3. <span data-ttu-id="c635f-116">Одна **вкладка Лицензии и Приложения,** развяжите **лицензии** и снимите поле для лицензии, необходимой для удаления.</span><span class="sxs-lookup"><span data-stu-id="c635f-116">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="c635f-117">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="c635f-117">Select **Save changes**.</span></span>

5. <span data-ttu-id="c635f-118">При возвращении на страницу **Активные** пользователи состояние общего почтового ящика будет **нелицензионным.**</span><span class="sxs-lookup"><span data-stu-id="c635f-118">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="c635f-119">Вы по-прежнему платите за лицензию.</span><span class="sxs-lookup"><span data-stu-id="c635f-119">You're still paying for the license.</span></span> <span data-ttu-id="c635f-120">Чтобы перестать платить за это, [снимите лицензию из подписки.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="c635f-120">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="c635f-121">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="c635f-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c635f-122">Необходимо удалить лицензию со страницы Активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="c635f-122">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="c635f-123">Вы не можете удалить лицензию со страницы Общих почтовых ящиков, так как лицензии — это параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="c635f-123">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="c635f-124">Выберите общий почтовый ящик, а затем **выберите Изменить** рядом с **лицензиями продукта.**</span><span class="sxs-lookup"><span data-stu-id="c635f-124">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="c635f-125">На одной **странице лицензий на** продукт  установите переключению для лицензии, необходимой для удаления.</span><span class="sxs-lookup"><span data-stu-id="c635f-125">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="c635f-126">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c635f-126">Select **Save**.</span></span>

5. <span data-ttu-id="c635f-127">При возвращении на страницу **Активные** пользователи состояние общего почтового ящика будет **нелицензионным.**</span><span class="sxs-lookup"><span data-stu-id="c635f-127">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="c635f-128">Вы по-прежнему платите за лицензию.</span><span class="sxs-lookup"><span data-stu-id="c635f-128">You're still paying for the license.</span></span> <span data-ttu-id="c635f-129">Чтобы перестать платить за это, [снимите лицензию из подписки.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="c635f-129">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="c635f-130">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="c635f-130">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c635f-131">Необходимо удалить лицензию со страницы Активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="c635f-131">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="c635f-132">Вы не можете удалить лицензию со страницы Общих почтовых ящиков, так как лицензии — это параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="c635f-132">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="c635f-133">Выберите общий почтовый ящик, а затем **выберите Изменить** рядом с **лицензиями продукта.**</span><span class="sxs-lookup"><span data-stu-id="c635f-133">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="c635f-134">На одной **странице лицензий на** продукт  установите переключению для лицензии, необходимой для удаления.</span><span class="sxs-lookup"><span data-stu-id="c635f-134">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="c635f-135">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c635f-135">Select **Save**.</span></span>

5. <span data-ttu-id="c635f-136">При возвращении на страницу **Активные** пользователи состояние общего почтового ящика будет **нелицензионным.**</span><span class="sxs-lookup"><span data-stu-id="c635f-136">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="c635f-137">Вы по-прежнему платите за лицензию.</span><span class="sxs-lookup"><span data-stu-id="c635f-137">You're still paying for the license.</span></span> <span data-ttu-id="c635f-138">Чтобы перестать платить за это, [снимите лицензию из подписки.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="c635f-138">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="c635f-139">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="c635f-139">Related articles</span></span>

[<span data-ttu-id="c635f-140">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="c635f-140">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="c635f-141">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="c635f-141">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="c635f-142">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="c635f-142">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="c635f-143">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="c635f-143">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="c635f-144">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="c635f-144">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)