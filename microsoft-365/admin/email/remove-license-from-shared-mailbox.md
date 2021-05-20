---
title: Удаление лицензии из общего почтового ящика
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Удалите лицензию из общего почтового ящика, чтобы назначить ее другому пользователю. '
ms.openlocfilehash: d552cfb77ff0ab2853939c6cb25fd4737f8c17d3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537587"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="3c07a-103">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="3c07a-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="3c07a-104">Общие почтовые ящики обычно не требуют лицензии.</span><span class="sxs-lookup"><span data-stu-id="3c07a-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="3c07a-105">Следуйте этим инструкциям, чтобы удалить лицензию из общего почтового ящика, чтобы можно было назначить ее пользователю или вернуть лицензию, чтобы не платить за не нужная лицензия.</span><span class="sxs-lookup"><span data-stu-id="3c07a-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="3c07a-106">Лицензия требуется в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="3c07a-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="3c07a-107">Общий почтовый ящик имеет более 50 ГБ используемого хранилища.</span><span class="sxs-lookup"><span data-stu-id="3c07a-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="3c07a-108">Общий почтовый ящик использует архивативную передачу на месте.</span><span class="sxs-lookup"><span data-stu-id="3c07a-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="3c07a-109">Общий почтовый ящик помещается в удержание судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="3c07a-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="3c07a-110">Общий почтовый ящик имеет лицензию Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="3c07a-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

## <a name="remove-the-license"></a><span data-ttu-id="3c07a-111">Удаление лицензии</span><span class="sxs-lookup"><span data-stu-id="3c07a-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3c07a-112">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3c07a-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="3c07a-113">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3c07a-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="3c07a-114">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3c07a-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

   > [!NOTE]
   > <span data-ttu-id="3c07a-115">Необходимо удалить лицензию со страницы Активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="3c07a-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3c07a-116">Вы не можете удалить лицензию со страницы Общих почтовых ящиков, так как лицензии — это параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c07a-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>
  
2. <span data-ttu-id="3c07a-117">Выберите общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3c07a-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="3c07a-118">Одна **вкладка Лицензии и Приложения,** развяжите **лицензии** и снимите поле для лицензии, необходимой для удаления.</span><span class="sxs-lookup"><span data-stu-id="3c07a-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="3c07a-119">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="3c07a-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="3c07a-120">При возвращении на страницу **Активные** пользователи состояние общего почтового ящика будет **нелицензионным.**</span><span class="sxs-lookup"><span data-stu-id="3c07a-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3c07a-121">Вы по-прежнему платите за лицензию.</span><span class="sxs-lookup"><span data-stu-id="3c07a-121">You're still paying for the license.</span></span> <span data-ttu-id="3c07a-122">Чтобы перестать платить за это, [снимите лицензию из подписки.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="3c07a-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="3c07a-123">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="3c07a-123">Related articles</span></span>

[<span data-ttu-id="3c07a-124">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="3c07a-124">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="3c07a-125">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="3c07a-125">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="3c07a-126">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="3c07a-126">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="3c07a-127">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="3c07a-127">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="3c07a-128">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="3c07a-128">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
