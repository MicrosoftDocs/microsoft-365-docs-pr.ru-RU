---
title: Закрытие, повторное открытие и удаление основных вариантов обнаружения электронных данных
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
description: В этой статье описывается, как управлять основными случаями обнаружения электронных данных. Это включает в себя закрытие случая, повторное открытие закрытого дела и удаление обращения.
ms.openlocfilehash: 41ba622a58b0abb5ce668e6d94d89b1694a328c9
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551426"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="2d317-104">Закрытие, повторное открытие и удаление основного случая обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="2d317-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="2d317-105">В этой статье описывается, как закрыть, повторно открыть и удалить основные случаи обнаружения электронных данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d317-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="2d317-106">Закрытие обращения</span><span class="sxs-lookup"><span data-stu-id="2d317-106">Close a case</span></span>

<span data-ttu-id="2d317-107">При наличии судебного разбирательства или расследования, поддерживаемого основным вариантом обнаружения электронных данных, можно закрыть обращение.</span><span class="sxs-lookup"><span data-stu-id="2d317-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="2d317-108">Вот что происходит при закрытии дела:</span><span class="sxs-lookup"><span data-stu-id="2d317-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="2d317-109">Если обращение содержит какие – либо расположения контента при удержании электронных данных, эти удержания будут отключены.</span><span class="sxs-lookup"><span data-stu-id="2d317-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="2d317-110">Это может привести к необратимому удалению или очистке контента либо пользователем, либо автоматическим процессом, например политики удаления.</span><span class="sxs-lookup"><span data-stu-id="2d317-110">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="2d317-111">При закрытии обращения отключаются только удержания, связанные с этим обращением.</span><span class="sxs-lookup"><span data-stu-id="2d317-111">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="2d317-112">Если другие удержания размещаются в местоположении контента (например, хранение для судебного разбирательства, политика хранения или удержание из другого основного случая обнаружения электронных данных), эти удержания по-прежнему будут поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="2d317-112">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="2d317-113">В этом случае все еще отображается на основной странице обнаружения электронных данных в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d317-113">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2d317-114">Сохраняются сведения, удержания, Поиск и элементы закрытого обращения.</span><span class="sxs-lookup"><span data-stu-id="2d317-114">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="2d317-115">Вы можете изменить обращение после его закрытия.</span><span class="sxs-lookup"><span data-stu-id="2d317-115">You can edit a case after it's closed.</span></span> <span data-ttu-id="2d317-116">Например, вы можете добавлять и удалять участников, создавать поисковые запросы и экспортировать результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="2d317-116">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="2d317-117">Основное различие между активными и закрытыми случаями заключается в том, что удержания электронных данных при закрытии обращения отключены.</span><span class="sxs-lookup"><span data-stu-id="2d317-117">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="2d317-118">Чтобы закрыть ситуацию, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2d317-118">To close a case:</span></span>
  
1. <span data-ttu-id="2d317-119">В разделе соответствие требованиям Microsoft 365 щелкните ядро **обнаружения электронных** > **Core** данных, чтобы отобразить список основных вариантов обнаружения электронных данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="2d317-119">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="2d317-120">Щелкните имя обращения, которое нужно закрыть.</span><span class="sxs-lookup"><span data-stu-id="2d317-120">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="2d317-121">Отображается раскрывающаяся страница **Управление этим обращением** .</span><span class="sxs-lookup"><span data-stu-id="2d317-121">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="2d317-122">В разделе **Управление состоянием обращения**нажмите кнопку **Закрыть регистр**.</span><span class="sxs-lookup"><span data-stu-id="2d317-122">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="2d317-123">Отображается предупреждение о том, что удержания, связанные с обращением, будут отключены.</span><span class="sxs-lookup"><span data-stu-id="2d317-123">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="2d317-124">Нажмите кнопку **Да** , чтобы закрыть обращение.</span><span class="sxs-lookup"><span data-stu-id="2d317-124">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="2d317-125">Состояние на всплывающей странице " **Управление этим обращением** " изменяется с " **активно** " на " **закрытие**".</span><span class="sxs-lookup"><span data-stu-id="2d317-125">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="2d317-126">Закройте страницу **Управление этим обращением** .</span><span class="sxs-lookup"><span data-stu-id="2d317-126">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="2d317-127">На странице **основные обнаружения электронных** данных нажмите кнопку **Обновить** , чтобы обновить состояние закрытого дела.</span><span class="sxs-lookup"><span data-stu-id="2d317-127">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="2d317-128">Завершение процесса закрытия может занимать до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="2d317-128">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="2d317-129">По завершении процесса состояние обращения изменяется на " **закрыто** " на **основной странице обнаружения электронных** данных.</span><span class="sxs-lookup"><span data-stu-id="2d317-129">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="2d317-130">Щелкните имя этого случая еще раз, чтобы отобразить раскрывающуюся страницу **Управление этим обращением** , которая содержит сведения о том, когда обращение было закрыто и кто его закрыл.</span><span class="sxs-lookup"><span data-stu-id="2d317-130">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="2d317-131">Повторное открытие закрытого дела</span><span class="sxs-lookup"><span data-stu-id="2d317-131">Reopen a closed case</span></span>

<span data-ttu-id="2d317-132">При повторном открытии такого случая все удержания электронных данных, которые были на месте, когда обращение было закрыто, не будут автоматически возобновлены.</span><span class="sxs-lookup"><span data-stu-id="2d317-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="2d317-133">После повторного открытия обращения необходимо перейти на страницу **удержания** и включить предыдущие удержания.</span><span class="sxs-lookup"><span data-stu-id="2d317-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="2d317-134">Чтобы включить удержание, выберите его, чтобы отобразить раскрывающуюся страницу, а затем установите для параметра **Status** значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="2d317-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="2d317-135">В разделе соответствие требованиям Microsoft 365 щелкните ядро **обнаружения электронных** > **Core** данных, чтобы отобразить список основных вариантов обнаружения электронных данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="2d317-135">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="2d317-136">Щелкните имя обращения, которое необходимо повторно открыть.</span><span class="sxs-lookup"><span data-stu-id="2d317-136">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="2d317-137">Отображается раскрывающаяся страница **Управление этим обращением** .</span><span class="sxs-lookup"><span data-stu-id="2d317-137">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="2d317-138">В разделе **Управление состоянием обращения**нажмите кнопку **повторно открыть регистр**.</span><span class="sxs-lookup"><span data-stu-id="2d317-138">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="2d317-139">Отображается предупреждение о том, что удержания, связанные с обращением, когда оно было закрыто, не будут включены автоматически.</span><span class="sxs-lookup"><span data-stu-id="2d317-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="2d317-140">Нажмите кнопку **Да** , чтобы снова открыть обращение.</span><span class="sxs-lookup"><span data-stu-id="2d317-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="2d317-141">Состояние всплывающей страницы " **Управление этим обращением** " меняется с " **закрыто** " на " **активно**".</span><span class="sxs-lookup"><span data-stu-id="2d317-141">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="2d317-142">Закройте страницу **Управление этим обращением** .</span><span class="sxs-lookup"><span data-stu-id="2d317-142">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="2d317-143">На странице **основные обнаружения электронных** данных нажмите кнопку **Обновить** , чтобы обновить состояние повторно открытого случая.</span><span class="sxs-lookup"><span data-stu-id="2d317-143">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="2d317-144">Для завершения процесса повторного открытия может потребоваться до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="2d317-144">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="2d317-145">По завершении процесса состояние обращения изменяется на " **активно** " на **основной странице обнаружения электронных** данных.</span><span class="sxs-lookup"><span data-stu-id="2d317-145">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="2d317-146">Удаление обращения</span><span class="sxs-lookup"><span data-stu-id="2d317-146">Delete a case</span></span>

<span data-ttu-id="2d317-147">Вы также можете удалять активные и закрытые базовые случаи обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="2d317-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="2d317-148">При удалении случая все операции поиска и экспорта в случае удаляются, а обращение удаляется из списка обращений на **основной странице обнаружения электронных** данных в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d317-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2d317-149">Невозможно повторно открыть удаленное обращение.</span><span class="sxs-lookup"><span data-stu-id="2d317-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="2d317-150">Прежде чем можно будет удалить обращение (независимо от того, является ли оно активным или закрытым), необходимо сначала удалить *все* удержания электронных данных, связанные с этим обращением.</span><span class="sxs-lookup"><span data-stu-id="2d317-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="2d317-151">Включает в себя удаление удержаний со статусом " **отключено**".</span><span class="sxs-lookup"><span data-stu-id="2d317-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="2d317-152">Чтобы удалить удержание обнаружения электронных данных, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2d317-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="2d317-153">Перейдите на вкладку **удержания** в том случае, которое нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="2d317-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="2d317-154">Щелкните удержание, которое нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="2d317-154">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="2d317-155">На всплывающей странице нажмите кнопку **Удалить удержание**.</span><span class="sxs-lookup"><span data-stu-id="2d317-155">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="2d317-156">Чтобы удалить обращение:</span><span class="sxs-lookup"><span data-stu-id="2d317-156">To delete a case:</span></span>

1. <span data-ttu-id="2d317-157">В разделе соответствие требованиям Microsoft 365 щелкните ядро **обнаружения электронных** > **Core** данных, чтобы отобразить список основных вариантов обнаружения электронных данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="2d317-157">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="2d317-158">Щелкните имя случая, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="2d317-158">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="2d317-159">В разделе **Управление состоянием дел** на всплывающей странице щелкните **Удалить обращение**.</span><span class="sxs-lookup"><span data-stu-id="2d317-159">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="2d317-160">Если попытка удалить все еще содержит обнаружение электронных данных, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="2d317-160">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="2d317-161">Необходимо удалить все удержания, связанные с обращением, а затем попробовать еще раз, чтобы удалить обращение.</span><span class="sxs-lookup"><span data-stu-id="2d317-161">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
