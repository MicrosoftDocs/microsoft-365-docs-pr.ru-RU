---
title: Закрытие или удаление дела
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, что происходит при закрытии или удалении расследования или юридического дела, поддерживаемого делом Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419065"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="78dc2-103">Закрыть или удалить дело Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="78dc2-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="78dc2-104">После завершения судебного разбирательства или расследования, поддерживаемого делом Advanced eDiscovery, вы можете закрыть или удалить дело.</span><span class="sxs-lookup"><span data-stu-id="78dc2-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="78dc2-105">Вы также можете повторно открыть закрытое дело.</span><span class="sxs-lookup"><span data-stu-id="78dc2-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="78dc2-106">Закрыть дело</span><span class="sxs-lookup"><span data-stu-id="78dc2-106">Close a case</span></span>

<span data-ttu-id="78dc2-107">Вот что происходит при закрытии дела Advanced eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="78dc2-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="78dc2-108">Если дело содержит какие-либо расположения контента на удержании, эти удержания будут отключены.</span><span class="sxs-lookup"><span data-stu-id="78dc2-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="78dc2-109">После отключения удержания к расположениям контента, которые находились на удержании, применяется 30-дневный льготный период (называемый удержанием задержки).</span><span class="sxs-lookup"><span data-stu-id="78dc2-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="78dc2-110">Это помогает предотвратить немедленное удаление контента и дает администраторам возможность искать или восстанавливать содержимое, которое будет окончательно удалено по истечении периода удержания задержки.</span><span class="sxs-lookup"><span data-stu-id="78dc2-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="78dc2-111">Дополнительные сведения см. в удалении [местоположений контента из удержания eDiscovery.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="78dc2-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="78dc2-112">Закрытие дела отключит только те дела, которые связаны с этим делом.</span><span class="sxs-lookup"><span data-stu-id="78dc2-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="78dc2-113">Если в расположении контента находятся другие удержания (например, удержание для судебного разбирательства, основное удержание при обнаружении электронных данных или удержание по другому делу Advanced eDiscovery), эти удержания по-прежнему будут сохранены.</span><span class="sxs-lookup"><span data-stu-id="78dc2-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="78dc2-114">Дело по-прежнему находится на странице "EDiscovery" в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78dc2-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="78dc2-115">Сведения, удержания, поиск и члены закрытого дела сохраняются.</span><span class="sxs-lookup"><span data-stu-id="78dc2-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="78dc2-116">Вы можете изменить дело после его закрытия.</span><span class="sxs-lookup"><span data-stu-id="78dc2-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="78dc2-117">Например, можно добавить или удалить участников, создать поиск, экспортировать результаты поиска и подготовить результаты поиска для анализа в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="78dc2-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="78dc2-118">Основное различие между активными и закрытыми случаями состоит в том, что при закрытии дела отключается удерживаемая связь.</span><span class="sxs-lookup"><span data-stu-id="78dc2-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="78dc2-119">Чтобы закрыть дело:</span><span class="sxs-lookup"><span data-stu-id="78dc2-119">To close a case:</span></span>

1. <span data-ttu-id="78dc2-120">На странице **Advanced eDiscovery** выберите дело, которое нужно закрыть.</span><span class="sxs-lookup"><span data-stu-id="78dc2-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="78dc2-121">На **вкладке "Параметры"** в **области "Сведения о деле"** нажмите кнопку **"Выбрать".**</span><span class="sxs-lookup"><span data-stu-id="78dc2-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="78dc2-122">Нажмите **кнопку "Закрыть дело"**.</span><span class="sxs-lookup"><span data-stu-id="78dc2-122">Click **Close case**.</span></span>

   <span data-ttu-id="78dc2-123">Завершение процесса закрытия может занять до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="78dc2-123">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="78dc2-124">Повторное открытие закрытого дела</span><span class="sxs-lookup"><span data-stu-id="78dc2-124">Reopen a closed case</span></span>

<span data-ttu-id="78dc2-125">При повторном открытии дела Advanced eDiscovery все операции, которые были на месте при закрытии дела, не будут восстановлены автоматически.</span><span class="sxs-lookup"><span data-stu-id="78dc2-125">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="78dc2-126">После повторного открытия дела необходимо перейти на  вкладку "Удерживает" и включить предыдущие.</span><span class="sxs-lookup"><span data-stu-id="78dc2-126">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="78dc2-127">Чтобы включить удержание, выберите его, чтобы отобразить отображаемую страницу, а затем установите в положение "Состояние" положение **"Вкл."** </span><span class="sxs-lookup"><span data-stu-id="78dc2-127">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="78dc2-128">Чтобы повторно открыть закрытое дело:</span><span class="sxs-lookup"><span data-stu-id="78dc2-128">To reopen a closed case:</span></span>

1. <span data-ttu-id="78dc2-129">На странице **Advanced eDiscovery** выберите дело, которое требуется повторно открыть.</span><span class="sxs-lookup"><span data-stu-id="78dc2-129">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="78dc2-130">На **вкладке "Параметры"** в **области "Сведения о деле"** нажмите кнопку **"Выбрать".**</span><span class="sxs-lookup"><span data-stu-id="78dc2-130">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="78dc2-131">Щелкните **"Дело повторного открытия".**</span><span class="sxs-lookup"><span data-stu-id="78dc2-131">Click **Reopen case**.</span></span>

   <span data-ttu-id="78dc2-132">Процесс повторного открытия может занять до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="78dc2-132">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="78dc2-133">Удаление дела</span><span class="sxs-lookup"><span data-stu-id="78dc2-133">Delete a case</span></span>

<span data-ttu-id="78dc2-134">Вы можете удалить как активные, так и закрытые дела Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="78dc2-134">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="78dc2-135">При удалении дела удаляются все компоненты, связанные с делом, такие как список хранителей, коммуникации, поиски, наборы для проверки и задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="78dc2-135">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="78dc2-136">Дело удаляется из списка дел на странице **Advanced eDiscovery** в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78dc2-136">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="78dc2-137">Вы не можете восстановить или повторно открыть удаленный случай.</span><span class="sxs-lookup"><span data-stu-id="78dc2-137">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="78dc2-138">В сценариях утечки данных единственный способ удалить элементы в наборе для проверки — удалить дело Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="78dc2-138">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="78dc2-139">Другие методы поиска и очистки не удаляют элементы из набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="78dc2-139">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="78dc2-140">Перед удалением дела (активного или закрытого) необходимо сначала  удалить все связанные с ним дела.</span><span class="sxs-lookup"><span data-stu-id="78dc2-140">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="78dc2-141">Это относится к удаляемой химки со статусом **"Вы отключено".**</span><span class="sxs-lookup"><span data-stu-id="78dc2-141">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="78dc2-142">Чтобы удалить удерживаемую запись, связанную с делом:</span><span class="sxs-lookup"><span data-stu-id="78dc2-142">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="78dc2-143">Перейдите **на вкладку "Содержит"** в случае Advanced eDiscovery, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="78dc2-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="78dc2-144">Щелкните удержание, которое нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="78dc2-144">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="78dc2-145">На странице flyout нажмите кнопку **"Удалить удержание".**</span><span class="sxs-lookup"><span data-stu-id="78dc2-145">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="78dc2-146">Чтобы удалить дело:</span><span class="sxs-lookup"><span data-stu-id="78dc2-146">To delete a case:</span></span>

1. <span data-ttu-id="78dc2-147">На странице **Advanced eDiscovery** выберите дело, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="78dc2-147">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="78dc2-148">На **вкладке "Параметры"** в **области "Сведения о деле"** нажмите кнопку **"Выбрать".**</span><span class="sxs-lookup"><span data-stu-id="78dc2-148">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="78dc2-149">Щелкните **"Удалить дело"**.</span><span class="sxs-lookup"><span data-stu-id="78dc2-149">Click **Delete case**.</span></span>
