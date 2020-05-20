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
description: Сведения о том, что происходит при закрытии или удалении судебного разбирательства, поддерживаемого расширенным вариантом обнаружения электронных данных.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292415"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="34ee1-103">Закрытие или удаление расширенного случая обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="34ee1-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="34ee1-104">Если вы закончили судебное обращение или исследование, поддерживаемое расширенным вариантом обнаружения электронных данных, вы можете закрыть или удалить обращение.</span><span class="sxs-lookup"><span data-stu-id="34ee1-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="34ee1-105">Кроме того, можно повторно открыть Закрытое обращение.</span><span class="sxs-lookup"><span data-stu-id="34ee1-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="34ee1-106">Закрытие обращения</span><span class="sxs-lookup"><span data-stu-id="34ee1-106">Close a case</span></span>

<span data-ttu-id="34ee1-107">Ниже показано, что происходит при закрытии расширенного случая обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="34ee1-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="34ee1-108">Если обращение содержит какие – либо расположения контента на удержании, эти удержания будут отключены.</span><span class="sxs-lookup"><span data-stu-id="34ee1-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="34ee1-109">Это может привести к необратимому удалению или очистке контента либо пользователем, либо автоматическим процессом, например политики удаления.</span><span class="sxs-lookup"><span data-stu-id="34ee1-109">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="34ee1-110">При закрытии обращения отключаются только удержания, связанные с этим обращением.</span><span class="sxs-lookup"><span data-stu-id="34ee1-110">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="34ee1-111">Если другие удержания находятся в расположении контента (например, хранение для судебного разбирательства, основное удержание для обнаружения электронных данных или удержание из другого дополнительного случая обнаружения электронных данных), эти удержания по-прежнему будут поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="34ee1-111">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="34ee1-112">Обращение по-прежнему отображается на странице Обнаружение электронных данных в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34ee1-112">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="34ee1-113">Сохраняются сведения, удержания, Поиск и элементы закрытого обращения.</span><span class="sxs-lookup"><span data-stu-id="34ee1-113">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="34ee1-114">Вы можете изменить обращение после его закрытия.</span><span class="sxs-lookup"><span data-stu-id="34ee1-114">You can edit a case after it's closed.</span></span> <span data-ttu-id="34ee1-115">Например, вы можете добавлять и удалять элементы, создавать поисковые запросы, экспортировать результаты поиска и подготавливать результаты поиска для анализа в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="34ee1-115">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="34ee1-116">Основное различие между активными и закрытыми случаями заключается в том, что при закрытом обращении удержания отключаются.</span><span class="sxs-lookup"><span data-stu-id="34ee1-116">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="34ee1-117">Чтобы закрыть ситуацию, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="34ee1-117">To close a case:</span></span>

1. <span data-ttu-id="34ee1-118">На странице **Advanced eDiscovery (Advanced eDiscovery** ) выберите обращение, которое нужно закрыть.</span><span class="sxs-lookup"><span data-stu-id="34ee1-118">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="34ee1-119">На вкладке **Параметры** в разделе **сведения о варианте case**нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="34ee1-119">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="34ee1-120">Нажмите кнопку **Закрыть обращение**.</span><span class="sxs-lookup"><span data-stu-id="34ee1-120">Click **Close case**.</span></span>

   <span data-ttu-id="34ee1-121">Завершение процесса закрытия может занимать до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="34ee1-121">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="34ee1-122">Повторное открытие закрытого дела</span><span class="sxs-lookup"><span data-stu-id="34ee1-122">Reopen a closed case</span></span>

<span data-ttu-id="34ee1-123">При повторном открытии расширенного дела eDiscovery все удержания, которые были выполнены, когда обращение было закрыто, не будут автоматически возобновлены.</span><span class="sxs-lookup"><span data-stu-id="34ee1-123">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="34ee1-124">После повторного открытия обращения необходимо перейти на вкладку **удержания** и включить предыдущее удержание.</span><span class="sxs-lookup"><span data-stu-id="34ee1-124">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="34ee1-125">Чтобы включить удержание, выберите его, чтобы отобразить раскрывающуюся страницу, а затем установите для параметра **Status** значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="34ee1-125">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="34ee1-126">Чтобы повторно открыть Закрытое обращение:</span><span class="sxs-lookup"><span data-stu-id="34ee1-126">To reopen a closed case:</span></span>

1. <span data-ttu-id="34ee1-127">На странице **Advanced eDiscovery (Advanced eDiscovery** ) выберите вариант, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="34ee1-127">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="34ee1-128">На вкладке **Параметры** в разделе **сведения о варианте case**нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="34ee1-128">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="34ee1-129">Нажмите кнопку **повторно открыть**.</span><span class="sxs-lookup"><span data-stu-id="34ee1-129">Click **Reopen case**.</span></span>

   <span data-ttu-id="34ee1-130">Для завершения процесса повторного открытия может потребоваться до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="34ee1-130">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="34ee1-131">Удаление обращения</span><span class="sxs-lookup"><span data-stu-id="34ee1-131">Delete a case</span></span>

<span data-ttu-id="34ee1-132">Вы можете удалить как активные, так и закрытые случаи расширенного обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="34ee1-132">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="34ee1-133">При удалении дела все компоненты, связанные с этим обращением, такие как список custodians, связь, результаты поиска, проверки наборов и задание экспорта, удаляются.</span><span class="sxs-lookup"><span data-stu-id="34ee1-133">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="34ee1-134">Это обращение будет удалено из списка вариантов на странице **Advanced eDiscovery** в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34ee1-134">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="34ee1-135">Вы не можете восстановить или повторно открыть удаленное обращение.</span><span class="sxs-lookup"><span data-stu-id="34ee1-135">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="34ee1-136">В сценариях с продолжением переноса данных единственный способ удалить элементы в наборе рецензирования — удалить расширенное дело обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="34ee1-136">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="34ee1-137">Другие методы "Поиск и очистка" не удаляют элементы из набора рецензирования.</span><span class="sxs-lookup"><span data-stu-id="34ee1-137">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="34ee1-138">Прежде чем можно будет удалить обращение (независимо от того, является ли оно активным или закрытым), необходимо сначала удалить *все* удержания, связанные с обращением.</span><span class="sxs-lookup"><span data-stu-id="34ee1-138">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="34ee1-139">Включает в себя удаление удержаний со статусом " **отключено**".</span><span class="sxs-lookup"><span data-stu-id="34ee1-139">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="34ee1-140">Чтобы удалить удержания, связанные с делами, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="34ee1-140">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="34ee1-141">Перейдите на вкладку **удержания** в расширенном случае обнаружения электронных данных, которое нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="34ee1-141">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="34ee1-142">Щелкните удержание, которое нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="34ee1-142">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="34ee1-143">На всплывающей странице нажмите кнопку **Удалить удержание**.</span><span class="sxs-lookup"><span data-stu-id="34ee1-143">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="34ee1-144">Чтобы удалить обращение:</span><span class="sxs-lookup"><span data-stu-id="34ee1-144">To delete a case:</span></span>

1. <span data-ttu-id="34ee1-145">На странице **Advanced eDiscovery (Advanced eDiscovery** ) выберите вариант, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="34ee1-145">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="34ee1-146">На вкладке **Параметры** в разделе **сведения о варианте case**нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="34ee1-146">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="34ee1-147">Нажмите кнопку **Удалить обращение**.</span><span class="sxs-lookup"><span data-stu-id="34ee1-147">Click **Delete case**.</span></span>
