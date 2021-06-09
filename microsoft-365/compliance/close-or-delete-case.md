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
description: Узнайте, что происходит при закрытии или удалении Advanced eDiscovery или судебного дела, поддерживаемых Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657655"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="18d7f-103">Закрыть или удалить Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="18d7f-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="18d7f-104">Когда судебное дело или расследование, поддерживаемые Advanced eDiscovery, можно закрыть или удалить.</span><span class="sxs-lookup"><span data-stu-id="18d7f-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="18d7f-105">Кроме того, можно открыть закрытое дело.</span><span class="sxs-lookup"><span data-stu-id="18d7f-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="18d7f-106">Закрыть дело</span><span class="sxs-lookup"><span data-stu-id="18d7f-106">Close a case</span></span>

<span data-ttu-id="18d7f-107">Вот что происходит при закрытии Advanced eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="18d7f-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="18d7f-108">Если в деле есть расположения контента на удержании, это удержание отключается.</span><span class="sxs-lookup"><span data-stu-id="18d7f-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="18d7f-109">После отключения удержания 30-дневный льготный период (называемый удержанием задержки) применяется к расположениям контента, которые были на удержании.</span><span class="sxs-lookup"><span data-stu-id="18d7f-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="18d7f-110">Это помогает предотвратить немедленное удаление контента и предоставляет администраторам возможность поиска или восстановления контента, который будет окончательно удален по истечении срока задержки.</span><span class="sxs-lookup"><span data-stu-id="18d7f-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="18d7f-111">Дополнительные сведения см. в [статью Удаление местоположений контента из удержания электронных данных.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="18d7f-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="18d7f-112">При закрытии дела отключаются только связанные с ним удержания.</span><span class="sxs-lookup"><span data-stu-id="18d7f-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="18d7f-113">Если другие удержания находятся на расположении контента (например, удержание судебного разбирательства, удержание core eDiscovery или удержание из другого Advanced eDiscovery случае), эти удержания по-прежнему будут сохранены.</span><span class="sxs-lookup"><span data-stu-id="18d7f-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="18d7f-114">Случай по-прежнему указан на странице eDiscovery в центре Microsoft 365 соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="18d7f-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="18d7f-115">Сведения, удержания, поисковые запросы и участники закрытого дела сохраняются.</span><span class="sxs-lookup"><span data-stu-id="18d7f-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="18d7f-116">Вы можете изменить дело после его закрытия.</span><span class="sxs-lookup"><span data-stu-id="18d7f-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="18d7f-117">Например, можно добавить или удалить членов, создать поиск, экспортировать результаты поиска и подготовить результаты поиска для анализа в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="18d7f-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="18d7f-118">Основное различие между активными и закрытыми делами заключается в том, что при закрытии дела отключаются удержания.</span><span class="sxs-lookup"><span data-stu-id="18d7f-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="18d7f-119">Закрытие дела</span><span class="sxs-lookup"><span data-stu-id="18d7f-119">To close a case:</span></span>

1. <span data-ttu-id="18d7f-120">На странице **Advanced eDiscovery** выберите дело, которое хотите закрыть.</span><span class="sxs-lookup"><span data-stu-id="18d7f-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="18d7f-121">На вкладке **Параметры** в разделе **Сведения о деле** нажмите кнопку **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="18d7f-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="18d7f-122">В нижней части страницы **вылетной** информации о случаях нажмите кнопку **(...**) **Дополнительные параметры,** а затем нажмите **закрыть случае**.</span><span class="sxs-lookup"><span data-stu-id="18d7f-122">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Close case**.</span></span>

   ![Параметр в меню Дополнительные параметры, чтобы закрыть Advanced eDiscovery случае](..\Media\CloseAdvancedeDiscoveryCase.png)

   <span data-ttu-id="18d7f-124">Процесс закрытия может занимать до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="18d7f-124">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="18d7f-125">Повторное открытие закрытого дела</span><span class="sxs-lookup"><span data-stu-id="18d7f-125">Reopen a closed case</span></span>

<span data-ttu-id="18d7f-126">При повторном Advanced eDiscovery случае все удерживает, которые были на месте, когда дело было закрыто, не будут автоматически восстановлены.</span><span class="sxs-lookup"><span data-stu-id="18d7f-126">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="18d7f-127">После повторного открытия дела необходимо перейти на вкладку **Удерживает** и включить предыдущие удерживает.</span><span class="sxs-lookup"><span data-stu-id="18d7f-127">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="18d7f-128">Для включения удержания выберите его, чтобы отобразить страницу, а затем установите для параметра **Состояние** значение **Вкл.**</span><span class="sxs-lookup"><span data-stu-id="18d7f-128">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="18d7f-129">Чтобы открыть закрытое дело:</span><span class="sxs-lookup"><span data-stu-id="18d7f-129">To reopen a closed case:</span></span>

1. <span data-ttu-id="18d7f-130">На странице **Advanced eDiscovery** выберите дело, которое хотите повторно открыть.</span><span class="sxs-lookup"><span data-stu-id="18d7f-130">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="18d7f-131">На вкладке **Параметры** в разделе **Сведения о деле** нажмите кнопку **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="18d7f-131">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="18d7f-132">В нижней части страницы **вылетной** информации о случаях нажмите кнопку **(...**) **Дополнительные параметры,** а затем нажмите **снова открыть дело**.</span><span class="sxs-lookup"><span data-stu-id="18d7f-132">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Reopen case**.</span></span>

   ![Параметр в меню Дополнительные параметры, чтобы открыть Advanced eDiscovery случае](..\Media\ReopenAdvancedeDiscoveryCase.png)

   <span data-ttu-id="18d7f-134">Процесс открытия может занять до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="18d7f-134">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="18d7f-135">Удаление случая</span><span class="sxs-lookup"><span data-stu-id="18d7f-135">Delete a case</span></span>

<span data-ttu-id="18d7f-136">Можно удалить как активные, так и закрытые Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="18d7f-136">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="18d7f-137">При удалении дела удаляются все компоненты, связанные с делом, такие как список хранителей, коммуникации, поисковые запросы, наборы для проверки и задание экспорта.</span><span class="sxs-lookup"><span data-stu-id="18d7f-137">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="18d7f-138">Случай удаляется из списка случаев на  странице Advanced eDiscovery в центре Microsoft 365 соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="18d7f-138">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="18d7f-139">Вы не можете восстановить или открыть удаленный случай.</span><span class="sxs-lookup"><span data-stu-id="18d7f-139">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="18d7f-140">В сценариях утечки данных единственным способом удаления элементов в наборе обзоров является удаление Advanced eDiscovery случае.</span><span class="sxs-lookup"><span data-stu-id="18d7f-140">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="18d7f-141">Другие методы "поиска и очистки" не удаляют элементы из набора отзывов.</span><span class="sxs-lookup"><span data-stu-id="18d7f-141">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="18d7f-142">Прежде чем удалить случай (активный он или закрытый),  сначала необходимо удалить все хламы, связанные с делом.</span><span class="sxs-lookup"><span data-stu-id="18d7f-142">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="18d7f-143">Это включает удаление удерживающих данных со статусом **Off**.</span><span class="sxs-lookup"><span data-stu-id="18d7f-143">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="18d7f-144">Удаление хламов, связанных с делом:</span><span class="sxs-lookup"><span data-stu-id="18d7f-144">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="18d7f-145">Перейдите на вкладку **Удерживает** в Advanced eDiscovery случае, который необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="18d7f-145">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="18d7f-146">Щелкните удержание, которое необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="18d7f-146">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="18d7f-147">На странице флажок нажмите кнопку **Удалить удержание**.</span><span class="sxs-lookup"><span data-stu-id="18d7f-147">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="18d7f-148">Удаление дела</span><span class="sxs-lookup"><span data-stu-id="18d7f-148">To delete a case:</span></span>

1. <span data-ttu-id="18d7f-149">На странице **Advanced eDiscovery** выберите дело, которое хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="18d7f-149">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="18d7f-150">На вкладке **Параметры** в разделе **Сведения о деле** нажмите кнопку **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="18d7f-150">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="18d7f-151">В нижней части страницы **вылетной** информации о случаях нажмите кнопку **(...**) **Дополнительные параметры,** а затем нажмите **кнопку Удалить случае**.</span><span class="sxs-lookup"><span data-stu-id="18d7f-151">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Delete case**.</span></span>

   ![Параметр в меню Дополнительные параметры, чтобы удалить Advanced eDiscovery случае](..\Media\DeleteAdvancedeDiscoveryCase.png)
