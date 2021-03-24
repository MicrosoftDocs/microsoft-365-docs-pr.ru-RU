---
title: Просмотр и управление действиями в центре действий
description: Используйте Центр действий для просмотра и управления действиями по исправлению
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 01/29/2021
ms.technology: m365d
ms.openlocfilehash: d78bf3689020b5a24863e5a0f1ec817af50178ad
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073942"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="8a487-104">Просмотр и управление действиями в центре действий</span><span class="sxs-lookup"><span data-stu-id="8a487-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8a487-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8a487-105">**Applies to:**</span></span>
- <span data-ttu-id="8a487-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a487-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8a487-107">Функции защиты от угроз в Microsoft 365 Defender могут привести к определенным действиям по исправлению.</span><span class="sxs-lookup"><span data-stu-id="8a487-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="8a487-108">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="8a487-108">Here are some examples:</span></span>
- <span data-ttu-id="8a487-109">[Автоматические расследования могут](m365d-autoir.md) привести к действиям по исправлению, которые принимаются автоматически или ожидают утверждения.</span><span class="sxs-lookup"><span data-stu-id="8a487-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await approval.</span></span>
- <span data-ttu-id="8a487-110">Антивирусные, антивирусные и другие функции защиты от угроз могут привести к действиям по исправлению, например блокировке файла, URL-адреса или процесса или отправке артефакта на карантин.</span><span class="sxs-lookup"><span data-stu-id="8a487-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="8a487-111">Ваша группа операций безопасности может принимать действия по [](advanced-hunting-overview.md) исправлению в ручном режиме, например во время предварительной охоты или при расследовании оповещений [или](investigate-alerts.md) [инцидентов.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="8a487-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8a487-112">Чтобы утвердить или отклонить действия по исправлению, необходимы [соответствующие разрешения](m365d-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="8a487-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="8a487-113">Дополнительные сведения см. в дополнительных сведениях, необходимых для автоматического расследования и ответа [в Microsoft 365 Defender.](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="8a487-113">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="8a487-114">Просмотр ожидающих действий в центре действий</span><span class="sxs-lookup"><span data-stu-id="8a487-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="8a487-115">Необходимо как можно скорее утвердить (или отклонить) ожидающие выполнения действия, чтобы автоматизированный анализ угроз мог продолжить работу и своевременно завершить ее.</span><span class="sxs-lookup"><span data-stu-id="8a487-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

![Утверждение или отклонение действия](../../media/air-actioncenter-itemselected.png)

1. <span data-ttu-id="8a487-117">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="8a487-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="8a487-118">В панели навигации щелкните **Центр уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="8a487-118">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="8a487-119">В центре уведомлений на вкладке **Ожидание** выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="8a487-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="8a487-120">Откроется его поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="8a487-120">Its flyout pane opens.</span></span>
4. <span data-ttu-id="8a487-121">Просмотрите сведения в области вылетов и примите один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="8a487-121">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="8a487-122">Выберите **страницу Open investigation,** чтобы просмотреть дополнительные сведения о расследовании.</span><span class="sxs-lookup"><span data-stu-id="8a487-122">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="8a487-123">Выберите **Утверждение,** чтобы инициировать ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="8a487-123">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="8a487-124">Выберите **Отклонение,** чтобы предотвратить ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="8a487-124">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="8a487-125">Выберите **go hunt,** чтобы перейти в [расширенный поиск.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8a487-125">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="8a487-126">Отмена завершенных действий</span><span class="sxs-lookup"><span data-stu-id="8a487-126">Undo completed actions</span></span>

<span data-ttu-id="8a487-127">Если установлено, что устройство или файл не представляют угрозы, можно отменить принятые действия по исправлению, независимо от того, были ли эти действия приняты автоматически или вручную.</span><span class="sxs-lookup"><span data-stu-id="8a487-127">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="8a487-128">В центре действий на **вкладке История** можно отменить любое из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="8a487-128">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="8a487-129">Источник действий</span><span class="sxs-lookup"><span data-stu-id="8a487-129">Action source</span></span> | <span data-ttu-id="8a487-130">Поддерживаемые действия</span><span class="sxs-lookup"><span data-stu-id="8a487-130">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="8a487-131">- Автоматическое расследование</span><span class="sxs-lookup"><span data-stu-id="8a487-131">- Automated investigation</span></span> <br/><span data-ttu-id="8a487-132">- Антивирус Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8a487-132">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="8a487-133">- Действия ручного ответа</span><span class="sxs-lookup"><span data-stu-id="8a487-133">- Manual response actions</span></span> | <span data-ttu-id="8a487-134">- Изолировать устройство</span><span class="sxs-lookup"><span data-stu-id="8a487-134">- Isolate device</span></span> <br/><span data-ttu-id="8a487-135">- Ограничение выполнения кода</span><span class="sxs-lookup"><span data-stu-id="8a487-135">- Restrict code execution</span></span> <br/><span data-ttu-id="8a487-136">- Карантин файла</span><span class="sxs-lookup"><span data-stu-id="8a487-136">- Quarantine a file</span></span> <br/><span data-ttu-id="8a487-137">- Удаление ключа реестра</span><span class="sxs-lookup"><span data-stu-id="8a487-137">- Remove a registry key</span></span> <br/><span data-ttu-id="8a487-138">- Остановка службы</span><span class="sxs-lookup"><span data-stu-id="8a487-138">- Stop a service</span></span> <br/><span data-ttu-id="8a487-139">- Отключить драйвер</span><span class="sxs-lookup"><span data-stu-id="8a487-139">- Disable a driver</span></span> <br/><span data-ttu-id="8a487-140">- Удаление запланированной задачи</span><span class="sxs-lookup"><span data-stu-id="8a487-140">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="8a487-141">Отмена одного действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="8a487-141">Undo one remediation action</span></span>

1. <span data-ttu-id="8a487-142">Перейдите в центр действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="8a487-142">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="8a487-143">На **вкладке История** выберите действие, которое необходимо отменить.</span><span class="sxs-lookup"><span data-stu-id="8a487-143">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="8a487-144">В области справа от экрана выберите **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="8a487-144">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="8a487-145">Отмена нескольких действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="8a487-145">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="8a487-146">Перейдите в центр действий https://security.microsoft.com/action-center) (и войдите.</span><span class="sxs-lookup"><span data-stu-id="8a487-146">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="8a487-147">На **вкладке История** выберите действия, которые необходимо отменить.</span><span class="sxs-lookup"><span data-stu-id="8a487-147">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="8a487-148">Убедитесь, что выберите элементы с одинаковым типом действия.</span><span class="sxs-lookup"><span data-stu-id="8a487-148">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="8a487-149">Открывается поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="8a487-149">A flyout pane opens.</span></span>
3. <span data-ttu-id="8a487-150">В области вылетов выберите **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="8a487-150">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="8a487-151">Удаление файла из карантина на нескольких устройствах</span><span class="sxs-lookup"><span data-stu-id="8a487-151">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="8a487-152">Перейдите в центр действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="8a487-152">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="8a487-153">На **вкладке История** выберите файл с карантиным файлом типа **Action.**</span><span class="sxs-lookup"><span data-stu-id="8a487-153">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="8a487-154">В области справа от экрана выберите **Применить** к X дополнительные экземпляры этого файла, а затем **отменить**.</span><span class="sxs-lookup"><span data-stu-id="8a487-154">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8a487-155">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="8a487-155">Next steps</span></span>

- [<span data-ttu-id="8a487-156">Просмотр сведений и результатов автоматического исследования</span><span class="sxs-lookup"><span data-stu-id="8a487-156">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="8a487-157">Узнайте, как обращаться с ложными срабатыва-</span><span class="sxs-lookup"><span data-stu-id="8a487-157">Learn how to handle false positives/negatives (if you get one)</span></span>](m365d-autoir-report-false-positives-negatives.md)
