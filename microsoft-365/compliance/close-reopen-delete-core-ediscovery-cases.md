---
title: Закрыть, открыть и удалить случаи открытия core eDiscovery
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
description: В этой статье описывается управление делами по обнаружению основных электронных обнаружений. Это включает закрытие дела, открытие закрытого дела и удаление дела.
ms.openlocfilehash: d729c91d4e81ad12d0b4b16574aa4edad8e239a3
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684103"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="a364d-104">Закрыть, открыть и удалить дело об обнаружении основных электронных данных</span><span class="sxs-lookup"><span data-stu-id="a364d-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="a364d-105">В этой статье описывается, как закрыть, открыть и удалить случаи открытия основных электронных данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a364d-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="a364d-106">Закрыть дело</span><span class="sxs-lookup"><span data-stu-id="a364d-106">Close a case</span></span>

<span data-ttu-id="a364d-107">По завершению судебного дела или расследования, поддерживаемого случаем проверки основных электронных расследований, вы можете закрыть дело.</span><span class="sxs-lookup"><span data-stu-id="a364d-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="a364d-108">Вот что происходит при закрытии дела:</span><span class="sxs-lookup"><span data-stu-id="a364d-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="a364d-109">Если в случае содержится любое удерживает eDiscovery, они будут отключены.</span><span class="sxs-lookup"><span data-stu-id="a364d-109">If the case contains any eDiscovery holds, they will be turned off.</span></span> <span data-ttu-id="a364d-110">После отключения удержания 30-дневный льготный период (называемый удержанием задержки) применяется к расположениям контента, которые были на удержании.</span><span class="sxs-lookup"><span data-stu-id="a364d-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="a364d-111">Это позволяет предотвратить немедленное удаление контента и предоставляет администраторам возможность поиска и восстановления контента, прежде чем он может быть окончательно удален по истечении срока задержки.</span><span class="sxs-lookup"><span data-stu-id="a364d-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="a364d-112">Дополнительные сведения см. в [статью Удаление местоположений контента из удержания электронных данных.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="a364d-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="a364d-113">При закрытии дела отключаются только связанные с ним удержания.</span><span class="sxs-lookup"><span data-stu-id="a364d-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="a364d-114">Если другие удержания размещаются на расположении контента (например, удержание для судебного разбирательства, политика хранения или удержание из другого дела об обнаружении core eDiscovery), эти удержания по-прежнему будут сохранены.</span><span class="sxs-lookup"><span data-stu-id="a364d-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="a364d-115">Случай по-прежнему указан на странице Core eDiscovery в центре Microsoft 365 соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a364d-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a364d-116">Сведения, удержания, поисковые запросы и участники закрытого дела сохраняются.</span><span class="sxs-lookup"><span data-stu-id="a364d-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="a364d-117">Вы можете изменить дело после его закрытия.</span><span class="sxs-lookup"><span data-stu-id="a364d-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="a364d-118">Например, можно добавлять или удалять участников, создавать поиски и экспортировать результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="a364d-118">For example, you can add or remove members, create searches, and export search results.</span></span> <span data-ttu-id="a364d-119">Основное отличие между активными и закрытыми случаями состоит в том, что при закрытии дела отключается хлам для электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="a364d-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="a364d-120">Закрытие дела</span><span class="sxs-lookup"><span data-stu-id="a364d-120">To close a case:</span></span>
  
1. <span data-ttu-id="a364d-121">В центре Microsoft 365 для проверки соответствия требованиям щелкните **ядро eDiscovery,** чтобы отобразить список случаев проверки основных электронных данных  >   в организации.</span><span class="sxs-lookup"><span data-stu-id="a364d-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="a364d-122">Щелкните имя дела, которое нужно закрыть.</span><span class="sxs-lookup"><span data-stu-id="a364d-122">Click the name of the case that you want to close.</span></span>

   ![Закрыть дело на домашней странице дела](../media/eDiscoveryCaseHomePage.png)

3. <span data-ttu-id="a364d-124">На домашней странице в **статье Состояние** нажмите кнопку **Закрыть дело**.</span><span class="sxs-lookup"><span data-stu-id="a364d-124">On the home page, under **Status**, click **Close case**.</span></span>

    <span data-ttu-id="a364d-125">Отображается предупреждение о том, что хламы, связанные с случаем, будут отключены.</span><span class="sxs-lookup"><span data-stu-id="a364d-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="a364d-126">Нажмите **кнопку Да,** чтобы закрыть дело.</span><span class="sxs-lookup"><span data-stu-id="a364d-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="a364d-127">Состояние на домашней странице дела изменено с **Active** на **Закрытие**.</span><span class="sxs-lookup"><span data-stu-id="a364d-127">The status on the case home page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="a364d-128">На странице **Core eDiscovery** щелкните **Обновление,** чтобы обновить состояние закрытого дела.</span><span class="sxs-lookup"><span data-stu-id="a364d-128">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="a364d-129">Процесс закрытия может занимать до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="a364d-129">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="a364d-130">По завершению процесса состояние дела будет изменено на **Закрытое** на странице **Core eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="a364d-130">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="a364d-131">Повторное открытие закрытого дела</span><span class="sxs-lookup"><span data-stu-id="a364d-131">Reopen a closed case</span></span>

<span data-ttu-id="a364d-132">При повторном открытии дела любые удерживаемые электронные ружье, которые были на месте при закрытии дела, не будут автоматически восстановлены.</span><span class="sxs-lookup"><span data-stu-id="a364d-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="a364d-133">После повторного открытия дела необходимо перейти на страницу **Удерживает** и включить предыдущие удерживает.</span><span class="sxs-lookup"><span data-stu-id="a364d-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="a364d-134">Для включения удержания выберите его, чтобы отобразить страницу, а затем установите для параметра **Состояние** значение **Вкл.**</span><span class="sxs-lookup"><span data-stu-id="a364d-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="a364d-135">В центре Microsoft 365 для проверки соответствия требованиям щелкните **ядро eDiscovery,** чтобы отобразить список случаев проверки основных электронных данных  >   в организации.</span><span class="sxs-lookup"><span data-stu-id="a364d-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="a364d-136">Щелкните имя случая, которое необходимо открыть.</span><span class="sxs-lookup"><span data-stu-id="a364d-136">Click the name of the case that you want to reopen.</span></span>

   ![Повторное открытие закрытого дела](../media/eDiscoveryCaseHomePageReopen.png)

3. <span data-ttu-id="a364d-138">На домашней странице в статье Состояние нажмите **кнопку** **Открыть дело**.</span><span class="sxs-lookup"><span data-stu-id="a364d-138">On the home page, under **Status**, click **Reopen case**.</span></span>

    <span data-ttu-id="a364d-139">Отображается предупреждение о том, что holds, которые были связаны с случаем, когда он был закрыт, не будут автоматически включены.</span><span class="sxs-lookup"><span data-stu-id="a364d-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="a364d-140">Щелкните **Да,** чтобы открыть дело.</span><span class="sxs-lookup"><span data-stu-id="a364d-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="a364d-141">Состояние на странице вылетов домашней страницы дела изменено с **закрытой на** **активную.**</span><span class="sxs-lookup"><span data-stu-id="a364d-141">The status on the case home page flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="a364d-142">На странице **Core eDiscovery** щелкните **Обновление,** чтобы обновить состояние вновь открытого дела.</span><span class="sxs-lookup"><span data-stu-id="a364d-142">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="a364d-143">Процесс открытия может занять до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="a364d-143">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="a364d-144">По завершению процесса состояние дела меняется на **Active** на странице **Core eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="a364d-144">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span>

6. <span data-ttu-id="a364d-145">(Необязательный) Чтобы включить все удержания, связанные с вновь открытым случаем, перейдите на  вкладку **Удержание,** выберите удержание, а затем выберите флажки под состоянием на странице флажка удержания.</span><span class="sxs-lookup"><span data-stu-id="a364d-145">(Optional) To turn on any holds associated with the reopened case, go to **Holds** tab, select a hold, and then select the checkbox under **Status** on the hold flyout page.</span></span>
  
## <a name="delete-a-case"></a><span data-ttu-id="a364d-146">Удаление случая</span><span class="sxs-lookup"><span data-stu-id="a364d-146">Delete a case</span></span>

<span data-ttu-id="a364d-147">Кроме того, можно удалить активные и закрытые кейсы по обнаружению основных электронных данных.</span><span class="sxs-lookup"><span data-stu-id="a364d-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="a364d-148">При удалении дела все поиски и экспорты в этом случае удаляются, а дело удаляется из списка случаев на странице **Core eDiscovery** в центре Microsoft 365 соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a364d-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a364d-149">Вы не можете открыть удаленный случай.</span><span class="sxs-lookup"><span data-stu-id="a364d-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="a364d-150">Прежде чем удалить случай (активен он или закрыт), сначала  необходимо удалить все хламы eDiscovery, связанные с этим случаем.</span><span class="sxs-lookup"><span data-stu-id="a364d-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="a364d-151">Это включает удаление удерживающих данных со статусом **Off**.</span><span class="sxs-lookup"><span data-stu-id="a364d-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="a364d-152">Удаление удержания электронных данных:</span><span class="sxs-lookup"><span data-stu-id="a364d-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="a364d-153">Перейдите на **вкладку Держит** в случае, если вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="a364d-153">Go to the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="a364d-154">Выберите удержание, которое необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="a364d-154">Select the hold that you want to delete.</span></span>

3. <span data-ttu-id="a364d-155">На странице вылет нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a364d-155">On the flyout page, click **Delete**.</span></span>

      ![Удаление удержания для электронных данных](../media/DeleteeDiscoveryHold.png)

<span data-ttu-id="a364d-157">Удаление дела</span><span class="sxs-lookup"><span data-stu-id="a364d-157">To delete a case:</span></span>

1. <span data-ttu-id="a364d-158">В центре Microsoft 365 для проверки соответствия требованиям щелкните **ядро eDiscovery,** чтобы отобразить список случаев проверки основных электронных данных  >   в организации.</span><span class="sxs-lookup"><span data-stu-id="a364d-158">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="a364d-159">Щелкните имя случая, которое необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="a364d-159">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="a364d-160">На домашней странице дела, в **статье Состояние,** нажмите **кнопку Удалить случае**.</span><span class="sxs-lookup"><span data-stu-id="a364d-160">On the case home page, under **Status**, click **Delete case**.</span></span>

      ![Удаление случая](../media/eDiscoveryCaseHomePageDelete.png)

<span data-ttu-id="a364d-162">Если случай, который вы пытаетесь удалить, по-прежнему содержит удерживает данные об обнаружении электронных данных, вы получите сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a364d-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="a364d-163">Вам придется удалить все хламы, связанные с делом, а затем еще раз попытаться удалить дело.</span><span class="sxs-lookup"><span data-stu-id="a364d-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
