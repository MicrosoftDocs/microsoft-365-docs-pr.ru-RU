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
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f3dba2116e0f13f265937ef65fd3b69bcb1e725b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274656"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="f43c1-104">Просмотр и управление действиями в центре действий</span><span class="sxs-lookup"><span data-stu-id="f43c1-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f43c1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f43c1-105">**Applies to:**</span></span>
- <span data-ttu-id="f43c1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f43c1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f43c1-107">Функции защиты от угроз в Microsoft 365 Defender могут привести к определенным действиям по исправлению.</span><span class="sxs-lookup"><span data-stu-id="f43c1-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="f43c1-108">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="f43c1-108">Here are some examples:</span></span>

- <span data-ttu-id="f43c1-109">[Автоматические расследования могут](m365d-autoir.md) привести к действиям по исправлению, которые принимаются автоматически или ожидают вашего утверждения.</span><span class="sxs-lookup"><span data-stu-id="f43c1-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await your approval.</span></span>
- <span data-ttu-id="f43c1-110">Антивирусные, антивирусные и другие функции защиты от угроз могут привести к действиям по исправлению, например блокировке файла, URL-адреса или процесса или отправке артефакта на карантин.</span><span class="sxs-lookup"><span data-stu-id="f43c1-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="f43c1-111">Ваша группа операций безопасности может принимать действия по [](advanced-hunting-overview.md) исправлению в ручном режиме, например во время предварительной охоты или при расследовании оповещений [или](investigate-alerts.md) [инцидентов.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="f43c1-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f43c1-112">Чтобы утвердить или отклонить действия по исправлению, необходимы [соответствующие разрешения](m365d-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="f43c1-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="f43c1-113">Дополнительные сведения см. в [дополнительных сведениях.](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="f43c1-113">For more information, see the [prerequisites](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="f43c1-114">Просмотр ожидающих действий в центре действий</span><span class="sxs-lookup"><span data-stu-id="f43c1-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="f43c1-115">Необходимо как можно скорее утвердить (или отклонить) ожидающие выполнения действия, чтобы автоматизированный анализ угроз мог продолжить работу и своевременно завершить ее.</span><span class="sxs-lookup"><span data-stu-id="f43c1-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

1. <span data-ttu-id="f43c1-116">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="f43c1-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="f43c1-117">В панели навигации щелкните **Центр уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="f43c1-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="f43c1-118">В центре уведомлений на вкладке **Ожидание** выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="f43c1-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="f43c1-119">Откроется его поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="f43c1-119">Its flyout pane opens.</span></span> <span data-ttu-id="f43c1-120">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="f43c1-120">Here's an example.</span></span>

   ![Утверждение или отклонение действия](../../media/air-actioncenter-itemselected.png)

4. <span data-ttu-id="f43c1-122">Просмотрите сведения в области вылетов и примите один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f43c1-122">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="f43c1-123">Выберите **страницу Open investigation,** чтобы просмотреть дополнительные сведения о расследовании.</span><span class="sxs-lookup"><span data-stu-id="f43c1-123">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="f43c1-124">Выберите **Утверждение,** чтобы инициировать ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="f43c1-124">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="f43c1-125">Выберите **Отклонение,** чтобы предотвратить ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="f43c1-125">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="f43c1-126">Выберите **go hunt,** чтобы перейти в [расширенный поиск.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f43c1-126">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="f43c1-127">Отмена завершенных действий</span><span class="sxs-lookup"><span data-stu-id="f43c1-127">Undo completed actions</span></span>

<span data-ttu-id="f43c1-128">Если установлено, что устройство или файл не представляют угрозы, можно отменить принятые действия по исправлению, независимо от того, были ли эти действия приняты автоматически или вручную.</span><span class="sxs-lookup"><span data-stu-id="f43c1-128">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="f43c1-129">В центре действий на **вкладке История** можно отменить любое из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f43c1-129">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="f43c1-130">Источник действий</span><span class="sxs-lookup"><span data-stu-id="f43c1-130">Action source</span></span> | <span data-ttu-id="f43c1-131">Поддерживаемые действия</span><span class="sxs-lookup"><span data-stu-id="f43c1-131">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="f43c1-132">- Автоматическое расследование</span><span class="sxs-lookup"><span data-stu-id="f43c1-132">- Automated investigation</span></span> <br/><span data-ttu-id="f43c1-133">- Антивирус Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f43c1-133">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="f43c1-134">- Действия ручного ответа</span><span class="sxs-lookup"><span data-stu-id="f43c1-134">- Manual response actions</span></span> | <span data-ttu-id="f43c1-135">- Изолировать устройство</span><span class="sxs-lookup"><span data-stu-id="f43c1-135">- Isolate device</span></span> <br/><span data-ttu-id="f43c1-136">- Ограничение выполнения кода</span><span class="sxs-lookup"><span data-stu-id="f43c1-136">- Restrict code execution</span></span> <br/><span data-ttu-id="f43c1-137">- Карантин файла</span><span class="sxs-lookup"><span data-stu-id="f43c1-137">- Quarantine a file</span></span> <br/><span data-ttu-id="f43c1-138">- Удаление ключа реестра</span><span class="sxs-lookup"><span data-stu-id="f43c1-138">- Remove a registry key</span></span> <br/><span data-ttu-id="f43c1-139">- Остановка службы</span><span class="sxs-lookup"><span data-stu-id="f43c1-139">- Stop a service</span></span> <br/><span data-ttu-id="f43c1-140">- Отключить драйвер</span><span class="sxs-lookup"><span data-stu-id="f43c1-140">- Disable a driver</span></span> <br/><span data-ttu-id="f43c1-141">- Удаление запланированной задачи</span><span class="sxs-lookup"><span data-stu-id="f43c1-141">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="f43c1-142">Отмена одного действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="f43c1-142">Undo one remediation action</span></span>

1. <span data-ttu-id="f43c1-143">Перейдите в центр действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="f43c1-143">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="f43c1-144">На **вкладке История** выберите действие, которое необходимо отменить.</span><span class="sxs-lookup"><span data-stu-id="f43c1-144">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="f43c1-145">В области справа от экрана выберите **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="f43c1-145">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="f43c1-146">Отмена нескольких действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="f43c1-146">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="f43c1-147">Перейдите в центр действий https://security.microsoft.com/action-center) (и войдите.</span><span class="sxs-lookup"><span data-stu-id="f43c1-147">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="f43c1-148">На **вкладке История** выберите действия, которые необходимо отменить.</span><span class="sxs-lookup"><span data-stu-id="f43c1-148">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="f43c1-149">Убедитесь, что выберите элементы с одинаковым типом действия.</span><span class="sxs-lookup"><span data-stu-id="f43c1-149">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="f43c1-150">Открывается поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="f43c1-150">A flyout pane opens.</span></span>

3. <span data-ttu-id="f43c1-151">В области вылетов выберите **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="f43c1-151">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="f43c1-152">Удаление файла из карантина на нескольких устройствах</span><span class="sxs-lookup"><span data-stu-id="f43c1-152">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="f43c1-153">Перейдите в центр действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="f43c1-153">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="f43c1-154">На **вкладке История** выберите файл с типом действия карантиного файла. </span><span class="sxs-lookup"><span data-stu-id="f43c1-154">On the **History** tab, select a file that has a **Quarantine file** Action type.</span></span>

3. <span data-ttu-id="f43c1-155">В области справа от экрана выберите **Применить** к X дополнительные экземпляры этого файла, а затем **отменить**.</span><span class="sxs-lookup"><span data-stu-id="f43c1-155">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f43c1-156">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f43c1-156">Next steps</span></span>

- [<span data-ttu-id="f43c1-157">Просмотр сведений и результатов автоматического исследования</span><span class="sxs-lookup"><span data-stu-id="f43c1-157">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="f43c1-158">Адрес false positives or false negatives)</span><span class="sxs-lookup"><span data-stu-id="f43c1-158">Address false positives or false negatives)</span></span>](m365d-autoir-report-false-positives-negatives.md)
