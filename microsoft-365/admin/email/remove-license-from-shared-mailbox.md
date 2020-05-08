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
ms.openlocfilehash: fb09036fc28ea3d9c182395d0a85e467f611dfdc
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140433"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="4c531-103">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="4c531-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4c531-104">Изменяется центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="4c531-104">The admin center is changing.</span></span> <span data-ttu-id="4c531-105">Если ваш интерфейс не отвечает указанным здесь сведениям, ознакомьтесь [со статьей о новом центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="4c531-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="4c531-106">Для общих почтовых ящиков не требуется лицензия, если в почтовом ящике больше 50 ГБ данных.</span><span class="sxs-lookup"><span data-stu-id="4c531-106">Shared mailboxes don't need a license unless the mailbox has over 50GB of data.</span></span> <span data-ttu-id="4c531-107">Следуйте этим инструкциям, чтобы удалить лицензию из общего почтового ящика, чтобы ее можно было назначить пользователю или вернуть лицензию, чтобы не платить за ненужные лицензии.</span><span class="sxs-lookup"><span data-stu-id="4c531-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>
  
## <a name="remove-the-license"></a><span data-ttu-id="4c531-108">Удаление лицензии</span><span class="sxs-lookup"><span data-stu-id="4c531-108">Remove the license</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="4c531-109">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="4c531-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="4c531-110">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="4c531-110">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4c531-111">Эту лицензию необходимо удалить на странице "активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="4c531-111">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="4c531-112">Вы не можете удалить лицензию со страницы общего почтового ящика, так как лицензии являются параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="4c531-112">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="4c531-113">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="4c531-113">Select the shared mailbox.</span></span>

3. <span data-ttu-id="4c531-114">На вкладке **лицензии и приложения** разверните узел **лицензии** и снимите флажок рядом с удаляемой лицензией.</span><span class="sxs-lookup"><span data-stu-id="4c531-114">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="4c531-115">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="4c531-115">Select **Save changes**.</span></span>

5. <span data-ttu-id="4c531-116">Когда вы вернетесь на страницу **Активные пользователи** , состояние общего почтового ящика будет **нелицензионным**.</span><span class="sxs-lookup"><span data-stu-id="4c531-116">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="4c531-117">Вы по-прежнему оплачиваете лицензию.</span><span class="sxs-lookup"><span data-stu-id="4c531-117">You're still paying for the license.</span></span> <span data-ttu-id="4c531-118">Чтобы прекратить оплату, [удалите лицензию из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="4c531-118">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="4c531-119">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="4c531-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4c531-120">Эту лицензию необходимо удалить на странице "активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="4c531-120">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="4c531-121">Вы не можете удалить лицензию со страницы общего почтового ящика, так как лицензии являются параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="4c531-121">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="4c531-122">Выберите общий почтовый ящик, а затем нажмите кнопку **изменить** рядом с пунктом **лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="4c531-122">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="4c531-123">Одну страницу " **лицензии продукта** ", установите переключатель в состояние " **выключен** " для удаляемой лицензии.</span><span class="sxs-lookup"><span data-stu-id="4c531-123">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="4c531-124">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4c531-124">Select **Save**.</span></span>

5. <span data-ttu-id="4c531-125">Когда вы вернетесь на страницу **Активные пользователи** , состояние общего почтового ящика будет **нелицензионным**.</span><span class="sxs-lookup"><span data-stu-id="4c531-125">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="4c531-126">Вы по-прежнему оплачиваете лицензию.</span><span class="sxs-lookup"><span data-stu-id="4c531-126">You're still paying for the license.</span></span> <span data-ttu-id="4c531-127">Чтобы прекратить оплату, [удалите лицензию из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="4c531-127">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="4c531-128">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="4c531-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4c531-129">Эту лицензию необходимо удалить на странице "активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="4c531-129">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="4c531-130">Вы не можете удалить лицензию со страницы общего почтового ящика, так как лицензии являются параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="4c531-130">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="4c531-131">Выберите общий почтовый ящик, а затем нажмите кнопку **изменить** рядом с пунктом **лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="4c531-131">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="4c531-132">Одну страницу " **лицензии продукта** ", установите переключатель в состояние " **выключен** " для удаляемой лицензии.</span><span class="sxs-lookup"><span data-stu-id="4c531-132">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="4c531-133">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4c531-133">Select **Save**.</span></span>

5. <span data-ttu-id="4c531-134">Когда вы вернетесь на страницу **Активные пользователи** , состояние общего почтового ящика будет **нелицензионным**.</span><span class="sxs-lookup"><span data-stu-id="4c531-134">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="4c531-135">Вы по-прежнему оплачиваете лицензию.</span><span class="sxs-lookup"><span data-stu-id="4c531-135">You're still paying for the license.</span></span> <span data-ttu-id="4c531-136">Чтобы прекратить оплату, [удалите лицензию из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="4c531-136">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="4c531-137">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="4c531-137">Related articles</span></span>

[<span data-ttu-id="4c531-138">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="4c531-138">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="4c531-139">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="4c531-139">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="4c531-140">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="4c531-140">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="4c531-141">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="4c531-141">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="4c531-142">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="4c531-142">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
