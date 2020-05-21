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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Удалить лицензию из общего почтового ящика, чтобы назначить ее другому пользователю. '
ms.openlocfilehash: 9ba411c614fee93e37ac45e58fd40bf246a9c2ab
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327246"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="3f458-103">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="3f458-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3f458-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="3f458-104">The admin center is changing.</span></span> <span data-ttu-id="3f458-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="3f458-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="3f458-106">Для общих почтовых ящиков обычно не требуется лицензия.</span><span class="sxs-lookup"><span data-stu-id="3f458-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="3f458-107">Следуйте этим инструкциям, чтобы удалить лицензию из общего почтового ящика, чтобы ее можно было назначить пользователю или вернуть лицензию, чтобы не платить за ненужные лицензии.</span><span class="sxs-lookup"><span data-stu-id="3f458-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="3f458-108">Лицензия необходима в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="3f458-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="3f458-109">Общий почтовый ящик содержит более 50 ГБ дискового пространства для использования.</span><span class="sxs-lookup"><span data-stu-id="3f458-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="3f458-110">В общем почтовом ящике используется Архивация на месте.</span><span class="sxs-lookup"><span data-stu-id="3f458-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="3f458-111">Общий почтовый ящик находится в режиме хранения для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="3f458-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="3f458-112">Удаление лицензии</span><span class="sxs-lookup"><span data-stu-id="3f458-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="3f458-113">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="3f458-113">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="3f458-114">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3f458-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3f458-115">Эту лицензию необходимо удалить на странице "активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="3f458-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3f458-116">Вы не можете удалить лицензию со страницы общего почтового ящика, так как лицензии являются параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="3f458-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="3f458-117">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3f458-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="3f458-118">На вкладке **лицензии и приложения** разверните узел **лицензии** и снимите флажок рядом с удаляемой лицензией.</span><span class="sxs-lookup"><span data-stu-id="3f458-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="3f458-119">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="3f458-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="3f458-120">Когда вы вернетесь на страницу **Активные пользователи** , состояние общего почтового ящика будет **нелицензионным**.</span><span class="sxs-lookup"><span data-stu-id="3f458-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3f458-121">Вы по-прежнему оплачиваете лицензию.</span><span class="sxs-lookup"><span data-stu-id="3f458-121">You're still paying for the license.</span></span> <span data-ttu-id="3f458-122">Чтобы прекратить оплату, [удалите лицензию из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3f458-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="3f458-123">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3f458-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3f458-124">Эту лицензию необходимо удалить на странице "активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="3f458-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3f458-125">Вы не можете удалить лицензию со страницы общего почтового ящика, так как лицензии являются параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="3f458-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="3f458-126">Выберите общий почтовый ящик, а затем нажмите кнопку **изменить** рядом с пунктом **лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="3f458-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="3f458-127">Одну страницу " **лицензии продукта** ", установите переключатель в состояние " **выключен** " для удаляемой лицензии.</span><span class="sxs-lookup"><span data-stu-id="3f458-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="3f458-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3f458-128">Select **Save**.</span></span>

5. <span data-ttu-id="3f458-129">Когда вы вернетесь на страницу **Активные пользователи** , состояние общего почтового ящика будет **нелицензионным**.</span><span class="sxs-lookup"><span data-stu-id="3f458-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3f458-130">Вы по-прежнему оплачиваете лицензию.</span><span class="sxs-lookup"><span data-stu-id="3f458-130">You're still paying for the license.</span></span> <span data-ttu-id="3f458-131">Чтобы прекратить оплату, [удалите лицензию из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3f458-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="3f458-132">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3f458-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3f458-133">Эту лицензию необходимо удалить на странице "активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="3f458-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3f458-134">Вы не можете удалить лицензию со страницы общего почтового ящика, так как лицензии являются параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="3f458-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="3f458-135">Выберите общий почтовый ящик, а затем нажмите кнопку **изменить** рядом с пунктом **лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="3f458-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="3f458-136">Одну страницу " **лицензии продукта** ", установите переключатель в состояние " **выключен** " для удаляемой лицензии.</span><span class="sxs-lookup"><span data-stu-id="3f458-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="3f458-137">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3f458-137">Select **Save**.</span></span>

5. <span data-ttu-id="3f458-138">Когда вы вернетесь на страницу **Активные пользователи** , состояние общего почтового ящика будет **нелицензионным**.</span><span class="sxs-lookup"><span data-stu-id="3f458-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3f458-139">Вы по-прежнему оплачиваете лицензию.</span><span class="sxs-lookup"><span data-stu-id="3f458-139">You're still paying for the license.</span></span> <span data-ttu-id="3f458-140">Чтобы прекратить оплату, [удалите лицензию из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3f458-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="3f458-141">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="3f458-141">Related articles</span></span>

[<span data-ttu-id="3f458-142">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="3f458-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="3f458-143">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="3f458-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="3f458-144">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="3f458-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="3f458-145">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="3f458-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="3f458-146">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="3f458-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
