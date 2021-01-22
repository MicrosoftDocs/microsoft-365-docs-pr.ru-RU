---
title: Утверждение или отклонение ожидающих действий после автоматического исследования
description: Используйте центр уведомлений для управления действиями, связанными с автоматизированным анализом угроз и реакцией на угрозы
keywords: действие, центр, автоматизированный анализ угроз и реакция на угрозы, автоматизированный, анализ угроз, реакция на угрозы, исправление
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930382"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="3b800-104">Утверждение или отклонение ожидающих действий после автоматического исследования</span><span class="sxs-lookup"><span data-stu-id="3b800-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3b800-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3b800-105">**Applies to:**</span></span>
- <span data-ttu-id="3b800-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b800-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3b800-107">При выполнении автоматического анализа угроз может возникать одно или несколько [действий по исправлению](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions), для которых требуется утверждение.</span><span class="sxs-lookup"><span data-stu-id="3b800-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="3b800-108">Например, может потребоваться удалить кластер сообщений электронной почты или файл из карантина.</span><span class="sxs-lookup"><span data-stu-id="3b800-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="3b800-109">Необходимо как можно скорее утвердить (или отклонить) ожидающие выполнения действия, чтобы автоматизированный анализ угроз мог продолжить работу и своевременно завершить ее.</span><span class="sxs-lookup"><span data-stu-id="3b800-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="3b800-110">Если вы считаете, что функции автоматического исследования и реагирования в Защитнике Microsoft 365 что-то было пропущено или неправильно обнаружено, дайте нам знать!</span><span class="sxs-lookup"><span data-stu-id="3b800-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="3b800-111">Узнайте, как сообщать о ложных срабатываах и отрицательных результатах в автоматизированных исследованиях и [ответах (AIR) в Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="3b800-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="3b800-112">Ожидающих действий можно просмотреть и утвердить с помощью Центра действий [или](#review-a-pending-action-in-the-action-center) представления [сведений об анализе.](#review-a-pending-action-in-the-investigation-details-view)</span><span class="sxs-lookup"><span data-stu-id="3b800-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="3b800-113">Чтобы утвердить или отклонить действия по исправлению, необходимы [соответствующие разрешения](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="3b800-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="3b800-114">Дополнительные сведения см. в предварительных условия для автоматического исследования и реагирования [в Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="3b800-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="3b800-115">Просмотр ожидающего действия в центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="3b800-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="3b800-116">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="3b800-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="3b800-117">В панели навигации щелкните **Центр уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="3b800-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="3b800-118">В центре уведомлений на вкладке **Ожидание** выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="3b800-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="3b800-119">При выборе элемента в столбце **Номер анализа** откроется страница сведений об анализе угроз.</span><span class="sxs-lookup"><span data-stu-id="3b800-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="3b800-120">На ней вы можете просмотреть результаты анализа угроз и утвердить или отклонить рекомендуемое действие.</span><span class="sxs-lookup"><span data-stu-id="3b800-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="3b800-121">При выборе строки в списке откроется всплывающее окно, в котором можно просмотреть сведения об этом элементе.</span><span class="sxs-lookup"><span data-stu-id="3b800-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Утверждение или отклонение действия](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="3b800-123">Используйте ссылки для просмотра связанного предупреждения или анализа, а также для утверждения или отклонения действия.</span><span class="sxs-lookup"><span data-stu-id="3b800-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="3b800-124">Просмотр ожидающего действия в представлении со сведениями об анализе угроз</span><span class="sxs-lookup"><span data-stu-id="3b800-124">Review a pending action in the investigation details view</span></span>

![Сведения об анализе](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="3b800-126">На странице [сведений анализа](mtp-autoir-results.md) выберите вкладку **Ожидающие действия** (или **Действия**). Здесь перечислены элементы, ожидающие утверждения.</span><span class="sxs-lookup"><span data-stu-id="3b800-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="3b800-127">Выберите элемент в списке, а затем выберите **утвердить** или **отклонить**.</span><span class="sxs-lookup"><span data-stu-id="3b800-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="undo-completed-actions"></a><span data-ttu-id="3b800-128">Отмена завершенных действий</span><span class="sxs-lookup"><span data-stu-id="3b800-128">Undo completed actions</span></span>

<span data-ttu-id="3b800-129">Если вы определили, что устройство или файл не являются угрозой, вы можете отменить предпринятые действия по исправлению, независимо от того, были ли эти действия предприняты автоматически или вручную.</span><span class="sxs-lookup"><span data-stu-id="3b800-129">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="3b800-130">В центре действий на вкладке **"История"** можно отменить любое из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="3b800-130">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="3b800-131">Источник действия</span><span class="sxs-lookup"><span data-stu-id="3b800-131">Action source</span></span> | <span data-ttu-id="3b800-132">Поддерживаемые действия</span><span class="sxs-lookup"><span data-stu-id="3b800-132">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="3b800-133">- Автоматизированное исследование</span><span class="sxs-lookup"><span data-stu-id="3b800-133">- Automated investigation</span></span> <br/><span data-ttu-id="3b800-134">- Антивирусная программа "Microsoft Defender"</span><span class="sxs-lookup"><span data-stu-id="3b800-134">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="3b800-135">- Действия ответа вручную</span><span class="sxs-lookup"><span data-stu-id="3b800-135">- Manual response actions</span></span> | <span data-ttu-id="3b800-136">- Изолировать устройство</span><span class="sxs-lookup"><span data-stu-id="3b800-136">- Isolate device</span></span> <br/><span data-ttu-id="3b800-137">- Ограничить выполнение кода</span><span class="sxs-lookup"><span data-stu-id="3b800-137">- Restrict code execution</span></span> <br/><span data-ttu-id="3b800-138">- Карантин файла</span><span class="sxs-lookup"><span data-stu-id="3b800-138">- Quarantine a file</span></span> <br/><span data-ttu-id="3b800-139">- Удаление ключа реестра</span><span class="sxs-lookup"><span data-stu-id="3b800-139">- Remove a registry key</span></span> <br/><span data-ttu-id="3b800-140">- Остановка службы</span><span class="sxs-lookup"><span data-stu-id="3b800-140">- Stop a service</span></span> <br/><span data-ttu-id="3b800-141">- Отключить драйвер</span><span class="sxs-lookup"><span data-stu-id="3b800-141">- Disable a driver</span></span> <br/><span data-ttu-id="3b800-142">- Удалить запланированную задачу</span><span class="sxs-lookup"><span data-stu-id="3b800-142">- Remove a scheduled task</span></span> |

### <a name="to-undo-a-remediation-action"></a><span data-ttu-id="3b800-143">Отмена действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="3b800-143">To undo a remediation action</span></span>

1. <span data-ttu-id="3b800-144">Перейдите в центр действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="3b800-144">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="3b800-145">На **вкладке "История"** выберите действие, которое нужно отменить.</span><span class="sxs-lookup"><span data-stu-id="3b800-145">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="3b800-146">В области в правой части экрана выберите **"Отменить".**</span><span class="sxs-lookup"><span data-stu-id="3b800-146">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="3b800-147">Удаление файла из карантина на нескольких устройствах</span><span class="sxs-lookup"><span data-stu-id="3b800-147">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="3b800-148">Перейдите в центр действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="3b800-148">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="3b800-149">На **вкладке "История"** выберите файл с типом действия **"Карантин".**</span><span class="sxs-lookup"><span data-stu-id="3b800-149">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="3b800-150">В области в правой части экрана выберите "Применить к **X"** дополнительных экземпляров этого файла, а затем выберите **"Отменить".**</span><span class="sxs-lookup"><span data-stu-id="3b800-150">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b800-151">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="3b800-151">Next steps</span></span>

- [<span data-ttu-id="3b800-152">Просмотр сведений и результатов автоматического исследования</span><span class="sxs-lookup"><span data-stu-id="3b800-152">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="3b800-153">Обработка ложных срабатывавай и отрицательных результатов в автоматизированном расследовании и реагировании на них</span><span class="sxs-lookup"><span data-stu-id="3b800-153">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
