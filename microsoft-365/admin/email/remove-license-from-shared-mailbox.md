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
ms.openlocfilehash: 1acd549936212db7f722355ed1f2518ff6bbac18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915690"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="98341-103">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="98341-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="98341-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="98341-104">The admin center is changing.</span></span> <span data-ttu-id="98341-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="98341-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="98341-106">Общие почтовые ящики обычно не требуют лицензии.</span><span class="sxs-lookup"><span data-stu-id="98341-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="98341-107">Следуйте этим инструкциям, чтобы удалить лицензию из общего почтового ящика, чтобы можно было назначить ее пользователю или вернуть лицензию, чтобы не платить за не нужная лицензия.</span><span class="sxs-lookup"><span data-stu-id="98341-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="98341-108">Лицензия требуется в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="98341-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="98341-109">Общий почтовый ящик имеет более 50 ГБ используемого хранилища.</span><span class="sxs-lookup"><span data-stu-id="98341-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="98341-110">Общий почтовый ящик использует архивативную передачу на месте.</span><span class="sxs-lookup"><span data-stu-id="98341-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="98341-111">Общий почтовый ящик помещается в удержание судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="98341-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="98341-112">Общий почтовый ящик имеет лицензию Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="98341-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="98341-113">Удаление лицензии</span><span class="sxs-lookup"><span data-stu-id="98341-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="98341-114">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="98341-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="98341-115">Необходимо удалить лицензию со страницы Активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="98341-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="98341-116">Вы не можете удалить лицензию со страницы Общих почтовых ящиков, так как лицензии — это параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="98341-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="98341-117">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="98341-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="98341-118">Одна **вкладка Лицензии и Приложения,** развяжите **лицензии** и снимите поле для лицензии, необходимой для удаления.</span><span class="sxs-lookup"><span data-stu-id="98341-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="98341-119">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="98341-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="98341-120">При возвращении на страницу **Активные** пользователи состояние общего почтового ящика будет **нелицензионным.**</span><span class="sxs-lookup"><span data-stu-id="98341-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="98341-121">Вы по-прежнему платите за лицензию.</span><span class="sxs-lookup"><span data-stu-id="98341-121">You're still paying for the license.</span></span> <span data-ttu-id="98341-122">Чтобы перестать платить за это, [снимите лицензию из подписки.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="98341-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="98341-123">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="98341-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98341-124">Необходимо удалить лицензию со страницы Активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="98341-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="98341-125">Вы не можете удалить лицензию со страницы Общих почтовых ящиков, так как лицензии — это параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="98341-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="98341-126">Выберите общий почтовый ящик, а затем **выберите Изменить** рядом с **лицензиями продукта.**</span><span class="sxs-lookup"><span data-stu-id="98341-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="98341-127">На одной **странице лицензий на** продукт  установите переключению для лицензии, необходимой для удаления.</span><span class="sxs-lookup"><span data-stu-id="98341-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="98341-128">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="98341-128">Select **Save**.</span></span>

5. <span data-ttu-id="98341-129">При возвращении на страницу **Активные** пользователи состояние общего почтового ящика будет **нелицензионным.**</span><span class="sxs-lookup"><span data-stu-id="98341-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="98341-130">Вы по-прежнему платите за лицензию.</span><span class="sxs-lookup"><span data-stu-id="98341-130">You're still paying for the license.</span></span> <span data-ttu-id="98341-131">Чтобы перестать платить за это, [снимите лицензию из подписки.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="98341-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="98341-132">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="98341-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98341-133">Необходимо удалить лицензию со страницы Активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="98341-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="98341-134">Вы не можете удалить лицензию со страницы Общих почтовых ящиков, так как лицензии — это параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="98341-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="98341-135">Выберите общий почтовый ящик, а затем **выберите Изменить** рядом с **лицензиями продукта.**</span><span class="sxs-lookup"><span data-stu-id="98341-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="98341-136">На одной **странице лицензий на** продукт  установите переключению для лицензии, необходимой для удаления.</span><span class="sxs-lookup"><span data-stu-id="98341-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="98341-137">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="98341-137">Select **Save**.</span></span>

5. <span data-ttu-id="98341-138">При возвращении на страницу **Активные** пользователи состояние общего почтового ящика будет **нелицензионным.**</span><span class="sxs-lookup"><span data-stu-id="98341-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="98341-139">Вы по-прежнему платите за лицензию.</span><span class="sxs-lookup"><span data-stu-id="98341-139">You're still paying for the license.</span></span> <span data-ttu-id="98341-140">Чтобы перестать платить за это, [снимите лицензию из подписки.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="98341-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="98341-141">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="98341-141">Related articles</span></span>

[<span data-ttu-id="98341-142">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="98341-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="98341-143">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="98341-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="98341-144">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="98341-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="98341-145">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="98341-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="98341-146">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="98341-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)