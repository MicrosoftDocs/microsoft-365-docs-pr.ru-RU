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
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412798"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="298ae-104">Закрытие, повторное открытие и удаление основного случая обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="298ae-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="298ae-105">В этой статье описывается, как закрыть, повторно открыть и удалить основные случаи обнаружения электронных данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="298ae-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="298ae-106">Закрытие обращения</span><span class="sxs-lookup"><span data-stu-id="298ae-106">Close a case</span></span>

<span data-ttu-id="298ae-107">При наличии судебного разбирательства или расследования, поддерживаемого основным вариантом обнаружения электронных данных, можно закрыть обращение.</span><span class="sxs-lookup"><span data-stu-id="298ae-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="298ae-108">Вот что происходит при закрытии дела:</span><span class="sxs-lookup"><span data-stu-id="298ae-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="298ae-109">Если обращение содержит какие – либо расположения контента при удержании электронных данных, эти удержания будут отключены.</span><span class="sxs-lookup"><span data-stu-id="298ae-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="298ae-110">После выключения удержания к расположениям, которые были заблокированы, применяется 30-дневный льготный период (называемый *задержками задержки*).</span><span class="sxs-lookup"><span data-stu-id="298ae-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="298ae-111">Это помогает предотвратить немедленный доступ к контенту и предоставляет администраторам возможность поиска и восстановления контента, прежде чем он может быть окончательно удален после истечения периода задержки.</span><span class="sxs-lookup"><span data-stu-id="298ae-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="298ae-112">Для получения дополнительных сведений ознакомьтесь с разделом [Удаление расположений содержимого из удержания обнаружения электронных данных](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span><span class="sxs-lookup"><span data-stu-id="298ae-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="298ae-113">При закрытии обращения отключаются только удержания, связанные с этим обращением.</span><span class="sxs-lookup"><span data-stu-id="298ae-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="298ae-114">Если другие удержания размещаются в местоположении контента (например, хранение для судебного разбирательства, политика хранения или удержание из другого основного случая обнаружения электронных данных), эти удержания по-прежнему будут поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="298ae-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="298ae-115">В этом случае все еще отображается на основной странице обнаружения электронных данных в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="298ae-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="298ae-116">Сохраняются сведения, удержания, Поиск и элементы закрытого обращения.</span><span class="sxs-lookup"><span data-stu-id="298ae-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="298ae-117">Вы можете изменить обращение после его закрытия.</span><span class="sxs-lookup"><span data-stu-id="298ae-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="298ae-118">Например, вы можете добавлять и удалять участников, создавать поисковые запросы и экспортировать результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="298ae-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="298ae-119">Основное различие между активными и закрытыми случаями заключается в том, что удержания электронных данных при закрытии обращения отключены.</span><span class="sxs-lookup"><span data-stu-id="298ae-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="298ae-120">Чтобы закрыть ситуацию, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="298ae-120">To close a case:</span></span>
  
1. <span data-ttu-id="298ae-121">В центре соответствия требованиям Microsoft 365 щелкните ядро **обнаружения электронных**данных,  >  **Core** чтобы отобразить список основных вариантов обнаружения электронных данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="298ae-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="298ae-122">Щелкните имя обращения, которое нужно закрыть.</span><span class="sxs-lookup"><span data-stu-id="298ae-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="298ae-123">Отображается раскрывающаяся страница **Управление этим обращением** .</span><span class="sxs-lookup"><span data-stu-id="298ae-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="298ae-124">В разделе **Управление состоянием обращения**нажмите кнопку **Закрыть регистр**.</span><span class="sxs-lookup"><span data-stu-id="298ae-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="298ae-125">Отображается предупреждение о том, что удержания, связанные с обращением, будут отключены.</span><span class="sxs-lookup"><span data-stu-id="298ae-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="298ae-126">Нажмите кнопку **Да** , чтобы закрыть обращение.</span><span class="sxs-lookup"><span data-stu-id="298ae-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="298ae-127">Состояние на всплывающей странице " **Управление этим обращением** " изменяется с " **активно** " на " **закрытие**".</span><span class="sxs-lookup"><span data-stu-id="298ae-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="298ae-128">Закройте страницу **Управление этим обращением** .</span><span class="sxs-lookup"><span data-stu-id="298ae-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="298ae-129">На странице **основные обнаружения электронных** данных нажмите кнопку **Обновить** , чтобы обновить состояние закрытого дела.</span><span class="sxs-lookup"><span data-stu-id="298ae-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="298ae-130">Завершение процесса закрытия может занимать до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="298ae-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="298ae-131">По завершении процесса состояние обращения изменяется на " **закрыто** " на **основной странице обнаружения электронных** данных.</span><span class="sxs-lookup"><span data-stu-id="298ae-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="298ae-132">Щелкните имя этого случая еще раз, чтобы отобразить раскрывающуюся страницу **Управление этим обращением** , которая содержит сведения о том, когда обращение было закрыто и кто его закрыл.</span><span class="sxs-lookup"><span data-stu-id="298ae-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="298ae-133">Повторное открытие закрытого дела</span><span class="sxs-lookup"><span data-stu-id="298ae-133">Reopen a closed case</span></span>

<span data-ttu-id="298ae-134">При повторном открытии такого случая все удержания электронных данных, которые были на месте, когда обращение было закрыто, не будут автоматически возобновлены.</span><span class="sxs-lookup"><span data-stu-id="298ae-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="298ae-135">После повторного открытия обращения необходимо перейти на страницу **удержания** и включить предыдущие удержания.</span><span class="sxs-lookup"><span data-stu-id="298ae-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="298ae-136">Чтобы включить удержание, выберите его, чтобы отобразить раскрывающуюся страницу, а затем установите для параметра **Status** значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="298ae-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="298ae-137">В центре соответствия требованиям Microsoft 365 щелкните ядро **обнаружения электронных**данных,  >  **Core** чтобы отобразить список основных вариантов обнаружения электронных данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="298ae-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="298ae-138">Щелкните имя обращения, которое необходимо повторно открыть.</span><span class="sxs-lookup"><span data-stu-id="298ae-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="298ae-139">Отображается раскрывающаяся страница **Управление этим обращением** .</span><span class="sxs-lookup"><span data-stu-id="298ae-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="298ae-140">В разделе **Управление состоянием обращения**нажмите кнопку **повторно открыть регистр**.</span><span class="sxs-lookup"><span data-stu-id="298ae-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="298ae-141">Отображается предупреждение о том, что удержания, связанные с обращением, когда оно было закрыто, не будут включены автоматически.</span><span class="sxs-lookup"><span data-stu-id="298ae-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="298ae-142">Нажмите кнопку **Да** , чтобы снова открыть обращение.</span><span class="sxs-lookup"><span data-stu-id="298ae-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="298ae-143">Состояние всплывающей страницы " **Управление этим обращением** " меняется с " **закрыто** " на " **активно**".</span><span class="sxs-lookup"><span data-stu-id="298ae-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="298ae-144">Закройте страницу **Управление этим обращением** .</span><span class="sxs-lookup"><span data-stu-id="298ae-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="298ae-145">На странице **основные обнаружения электронных** данных нажмите кнопку **Обновить** , чтобы обновить состояние повторно открытого случая.</span><span class="sxs-lookup"><span data-stu-id="298ae-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="298ae-146">Для завершения процесса повторного открытия может потребоваться до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="298ae-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="298ae-147">По завершении процесса состояние обращения изменяется на " **активно** " на **основной странице обнаружения электронных** данных.</span><span class="sxs-lookup"><span data-stu-id="298ae-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="298ae-148">Удаление обращения</span><span class="sxs-lookup"><span data-stu-id="298ae-148">Delete a case</span></span>

<span data-ttu-id="298ae-149">Вы также можете удалять активные и закрытые базовые случаи обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="298ae-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="298ae-150">При удалении случая все операции поиска и экспорта в случае удаляются, а обращение удаляется из списка обращений на **основной странице обнаружения электронных** данных в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="298ae-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="298ae-151">Невозможно повторно открыть удаленное обращение.</span><span class="sxs-lookup"><span data-stu-id="298ae-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="298ae-152">Прежде чем можно будет удалить обращение (независимо от того, является ли оно активным или закрытым), необходимо сначала удалить *все* удержания электронных данных, связанные с этим обращением.</span><span class="sxs-lookup"><span data-stu-id="298ae-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="298ae-153">Включает в себя удаление удержаний со статусом " **отключено**".</span><span class="sxs-lookup"><span data-stu-id="298ae-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="298ae-154">Чтобы удалить удержание обнаружения электронных данных, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="298ae-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="298ae-155">Перейдите на вкладку **удержания** в том случае, которое нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="298ae-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="298ae-156">Щелкните удержание, которое нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="298ae-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="298ae-157">На всплывающей странице нажмите кнопку **Удалить удержание**.</span><span class="sxs-lookup"><span data-stu-id="298ae-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="298ae-158">Чтобы удалить обращение:</span><span class="sxs-lookup"><span data-stu-id="298ae-158">To delete a case:</span></span>

1. <span data-ttu-id="298ae-159">В центре соответствия требованиям Microsoft 365 щелкните ядро **обнаружения электронных**данных,  >  **Core** чтобы отобразить список основных вариантов обнаружения электронных данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="298ae-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="298ae-160">Щелкните имя случая, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="298ae-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="298ae-161">В разделе **Управление состоянием дел** на всплывающей странице щелкните **Удалить обращение**.</span><span class="sxs-lookup"><span data-stu-id="298ae-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="298ae-162">Если попытка удалить все еще содержит обнаружение электронных данных, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="298ae-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="298ae-163">Необходимо удалить все удержания, связанные с обращением, а затем попробовать еще раз, чтобы удалить обращение.</span><span class="sxs-lookup"><span data-stu-id="298ae-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
