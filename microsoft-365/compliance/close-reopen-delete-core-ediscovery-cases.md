---
title: Закрыть, повторно открыть и удалить основные дела eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: В этой статье описывается управление основными делами eDiscovery. Это включает закрытие дела, повторное открытие закрытого дела и удаление дела.
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412798"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="e25cb-104">Close, reopen, and delete a Core eDiscovery case</span><span class="sxs-lookup"><span data-stu-id="e25cb-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="e25cb-105">В этой статье описывается, как закрыть, повторно открыть и удалить основные дела eDiscovery в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e25cb-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="e25cb-106">Закрыть дело</span><span class="sxs-lookup"><span data-stu-id="e25cb-106">Close a case</span></span>

<span data-ttu-id="e25cb-107">После завершения судебного разбирательства или расследования, поддерживаемого основным делом eDiscovery, вы можете закрыть дело.</span><span class="sxs-lookup"><span data-stu-id="e25cb-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="e25cb-108">Вот что происходит при закрытии дела:</span><span class="sxs-lookup"><span data-stu-id="e25cb-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="e25cb-109">Если дело содержит какие-либо расположения содержимого для удержания eDiscovery, эти удержания будут отключены.</span><span class="sxs-lookup"><span data-stu-id="e25cb-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="e25cb-110">После отключения удержания к расположениям содержимого, которые находились на удержании, применяется 30-дневный льготный период (называемый удержанием задержки).</span><span class="sxs-lookup"><span data-stu-id="e25cb-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="e25cb-111">Это помогает предотвратить немедленное удаление контента и дает администраторам возможность искать и восстанавливать контент, прежде чем он может быть окончательно удален по истечении периода удержания задержки.</span><span class="sxs-lookup"><span data-stu-id="e25cb-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="e25cb-112">Дополнительные сведения см. в удалении [местоположений контента из удержания eDiscovery.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="e25cb-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="e25cb-113">Закрытие дела отключит только те дела, которые связаны с этим делом.</span><span class="sxs-lookup"><span data-stu-id="e25cb-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="e25cb-114">Если к расположению контента были помещены другие удержания (например, хранение для судебного разбирательства, политика хранения или удержание из другого основного дела eDiscovery), эти удержания по-прежнему будут сохранены.</span><span class="sxs-lookup"><span data-stu-id="e25cb-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="e25cb-115">Дело по-прежнему находится на странице core eDiscovery в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e25cb-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e25cb-116">Сведения, удержания, поиск и члены закрытого дела сохраняются.</span><span class="sxs-lookup"><span data-stu-id="e25cb-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="e25cb-117">Вы можете изменить дело после его закрытия.</span><span class="sxs-lookup"><span data-stu-id="e25cb-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="e25cb-118">Например, можно добавлять или удалять участников, создавать поиск и экспортировать результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="e25cb-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="e25cb-119">Основное различие между активными и закрытыми делами состоит в том, что при закрытии дела операции eDiscovery отключаются.</span><span class="sxs-lookup"><span data-stu-id="e25cb-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="e25cb-120">Чтобы закрыть дело:</span><span class="sxs-lookup"><span data-stu-id="e25cb-120">To close a case:</span></span>
  
1. <span data-ttu-id="e25cb-121">В Центре соответствия требованиям Microsoft 365 щелкните **ядро eDiscovery,** чтобы отобразить список основных дел  >   eDiscovery в организации.</span><span class="sxs-lookup"><span data-stu-id="e25cb-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="e25cb-122">Щелкните имя дела, которое нужно закрыть.</span><span class="sxs-lookup"><span data-stu-id="e25cb-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="e25cb-123">**Отобразится страница "Управление этим** делом".</span><span class="sxs-lookup"><span data-stu-id="e25cb-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="e25cb-124">В **области "Управление состоянием дела"** щелкните **"Закрыть дело".**</span><span class="sxs-lookup"><span data-stu-id="e25cb-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="e25cb-125">Отобразилось предупреждение о том, что связанные с делом удерживающие знаки будут отключены.</span><span class="sxs-lookup"><span data-stu-id="e25cb-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="e25cb-126">Нажмите **кнопку** "Да", чтобы закрыть дело.</span><span class="sxs-lookup"><span data-stu-id="e25cb-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="e25cb-127">Состояние на странице **"Управление этим делом"** изменено с **"Активный"** на **"Закрытие".**</span><span class="sxs-lookup"><span data-stu-id="e25cb-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="e25cb-128">**Закроем страницу "Управление этим делом".**</span><span class="sxs-lookup"><span data-stu-id="e25cb-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="e25cb-129">На странице **"Основное eDiscovery"** нажмите кнопку **"Обновить",** чтобы обновить состояние закрытого дела.</span><span class="sxs-lookup"><span data-stu-id="e25cb-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="e25cb-130">Завершение процесса закрытия может занять до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="e25cb-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="e25cb-131">После завершения процесса состояние дела меняется на **"Закрыто"** на странице **"Основное eDiscovery".**</span><span class="sxs-lookup"><span data-stu-id="e25cb-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="e25cb-132">Щелкните имя дела еще раз, чтобы отобразить на странице "Управление этим делом", которая содержит сведения о том, когда дело было закрыто и кто его закрыл. </span><span class="sxs-lookup"><span data-stu-id="e25cb-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="e25cb-133">Повторное открытие закрытого дела</span><span class="sxs-lookup"><span data-stu-id="e25cb-133">Reopen a closed case</span></span>

<span data-ttu-id="e25cb-134">При повторном открытии дела все операции eDiscovery, которые были на месте при закрытии дела, не будут восстановлены автоматически.</span><span class="sxs-lookup"><span data-stu-id="e25cb-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="e25cb-135">После повторного открытия дела необходимо перейти на  страницу "Удерживает" и включить предыдущие.</span><span class="sxs-lookup"><span data-stu-id="e25cb-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="e25cb-136">Чтобы включить удержание, выберите его, чтобы отобразить отображаемую страницу, а затем установите в положение "Состояние" положение **"Вкл."** </span><span class="sxs-lookup"><span data-stu-id="e25cb-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="e25cb-137">В Центре соответствия требованиям Microsoft 365 щелкните **ядро eDiscovery,** чтобы отобразить список основных дел  >   eDiscovery в организации.</span><span class="sxs-lookup"><span data-stu-id="e25cb-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="e25cb-138">Щелкните имя дела, которое нужно повторно открыть.</span><span class="sxs-lookup"><span data-stu-id="e25cb-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="e25cb-139">**Отобразится страница "Управление этим** делом".</span><span class="sxs-lookup"><span data-stu-id="e25cb-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="e25cb-140">В **области "Управление состоянием дела"** щелкните **"Повторное открытие дела".**</span><span class="sxs-lookup"><span data-stu-id="e25cb-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="e25cb-141">Отобразилось предупреждение о том, что режимы, связанные с делом при закрытии, не будут включены автоматически.</span><span class="sxs-lookup"><span data-stu-id="e25cb-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="e25cb-142">Нажмите **кнопку "Да",** чтобы повторно открыть дело.</span><span class="sxs-lookup"><span data-stu-id="e25cb-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="e25cb-143">Состояние на странице "Управление **этим делом"** изменено с **"Закрытая"** на **"Активная".**</span><span class="sxs-lookup"><span data-stu-id="e25cb-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="e25cb-144">**Закроем страницу "Управление этим делом".**</span><span class="sxs-lookup"><span data-stu-id="e25cb-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="e25cb-145">На странице **"Основное eDiscovery"** нажмите кнопку **"Обновить",** чтобы обновить состояние повторно открытого дела.</span><span class="sxs-lookup"><span data-stu-id="e25cb-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="e25cb-146">Процесс повторного открытия может занять до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="e25cb-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="e25cb-147">После завершения процесса состояние дела меняется на **"Активный"** на странице **"Основное eDiscovery".**</span><span class="sxs-lookup"><span data-stu-id="e25cb-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="e25cb-148">Удаление дела</span><span class="sxs-lookup"><span data-stu-id="e25cb-148">Delete a case</span></span>

<span data-ttu-id="e25cb-149">Вы также можете удалить активные и закрытые дела core eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="e25cb-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="e25cb-150">При удалении дела все операции поиска и экспорта в этом случае удаляются, а дело удаляется из списка дел на странице **core eDiscovery** в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e25cb-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e25cb-151">Удаленное дело нельзя повторно открыть.</span><span class="sxs-lookup"><span data-stu-id="e25cb-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="e25cb-152">Прежде чем удалить дело (активное или закрытое), необходимо  сначала удалить все операции eDiscovery, связанные с делом.</span><span class="sxs-lookup"><span data-stu-id="e25cb-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="e25cb-153">Это относится к удаляемой химки со статусом **"Вы отключено".**</span><span class="sxs-lookup"><span data-stu-id="e25cb-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="e25cb-154">Чтобы удалить удержание при обнаружении электронных данных:</span><span class="sxs-lookup"><span data-stu-id="e25cb-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="e25cb-155">Перейдите **на вкладку "Содержит"** в случае, если вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="e25cb-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="e25cb-156">Щелкните удержание, которое нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="e25cb-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="e25cb-157">На странице flyout нажмите кнопку **"Удалить удержание".**</span><span class="sxs-lookup"><span data-stu-id="e25cb-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="e25cb-158">Чтобы удалить дело:</span><span class="sxs-lookup"><span data-stu-id="e25cb-158">To delete a case:</span></span>

1. <span data-ttu-id="e25cb-159">В Центре соответствия требованиям Microsoft 365 щелкните **ядро eDiscovery,** чтобы отобразить список основных дел  >   eDiscovery в организации.</span><span class="sxs-lookup"><span data-stu-id="e25cb-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="e25cb-160">Щелкните имя дела, которое нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="e25cb-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="e25cb-161">В **области "Управление состоянием дела"** на странице "Flyout" щелкните **"Удалить дело".**</span><span class="sxs-lookup"><span data-stu-id="e25cb-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="e25cb-162">Если дело, которое вы пытаетесь удалить, по-прежнему содержит сведения об обнаружении электронных данных, вы получите сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e25cb-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="e25cb-163">Вам придется удалить все дела, связанные с делом, а затем повторить попытку, чтобы удалить дело.</span><span class="sxs-lookup"><span data-stu-id="e25cb-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
