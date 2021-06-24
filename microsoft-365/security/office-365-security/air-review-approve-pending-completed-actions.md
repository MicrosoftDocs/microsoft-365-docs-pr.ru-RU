---
title: Просмотр и управление действиями по исправлению в Microsoft Defender для Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, threat, protection
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Узнайте о действиях по исправлению в автоматизированных возможностях расследования и ответа в Microsoft Defender для Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 987771616acfd2f2faf425e525505b320155388e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108539"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="aa455-104">Просмотр и управление действиями по исправлению в Office 365</span><span class="sxs-lookup"><span data-stu-id="aa455-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="aa455-105">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="aa455-105">**Applies to**</span></span>
- [<span data-ttu-id="aa455-106">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="aa455-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="aa455-107">По мере автоматического расследования & контента совместной работы создаются определенные действия по исправлению, например вредоносные или подозрительные. </span><span class="sxs-lookup"><span data-stu-id="aa455-107">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="aa455-108">В Microsoft Defender для Office 365 действий по исправлению можно включить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="aa455-108">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="aa455-109">Мягкое удаление сообщений электронной почты или кластеров</span><span class="sxs-lookup"><span data-stu-id="aa455-109">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="aa455-110">Отключение внешней пересылаемой почты</span><span class="sxs-lookup"><span data-stu-id="aa455-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="aa455-111">Эти действия по исправлению не принимаются до тех пор, пока их не утвердит группа операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="aa455-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="aa455-112">Мы рекомендуем как можно скорее просмотреть и утвердить все ожидающие действия, чтобы автоматические расследования были завершены своевременно.</span><span class="sxs-lookup"><span data-stu-id="aa455-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="aa455-113">В некоторых случаях можно пересмотреть представленные действия.</span><span class="sxs-lookup"><span data-stu-id="aa455-113">In some cases, you can reconsider submitted actions.</span></span>  <span data-ttu-id="aa455-114">Вы должны быть частью роли & очистки перед принятием каких-либо действий.</span><span class="sxs-lookup"><span data-stu-id="aa455-114">You need to be part of Search & purge role before taking any actions.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="aa455-115">Утверждение (или отклонение) ожидающих действий</span><span class="sxs-lookup"><span data-stu-id="aa455-115">Approve (or reject) pending actions</span></span>
<span data-ttu-id="aa455-116">Существует четыре различных способа поиска и проведения действий по автоматическому расследованию:</span><span class="sxs-lookup"><span data-stu-id="aa455-116">There are four different ways to find and take auto investigation actions:</span></span>

- [<span data-ttu-id="aa455-117">Очередь инцидентов</span><span class="sxs-lookup"><span data-stu-id="aa455-117">Incident queue</span></span>](https://security.microsoft.com/incidents)
- [<span data-ttu-id="aa455-118">Центр действий</span><span class="sxs-lookup"><span data-stu-id="aa455-118">Action center</span></span>](https://security.microsoft.com/action-center/pending)
- <span data-ttu-id="aa455-119">Само расследование (доступ к нему через incident или из оповещений)</span><span class="sxs-lookup"><span data-stu-id="aa455-119">Investigation itself (accessed via Incident or from an alert)</span></span>
- [<span data-ttu-id="aa455-120">Очередь расследований и исправлений</span><span class="sxs-lookup"><span data-stu-id="aa455-120">Investigation and remediation investigations queue</span></span>](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a><span data-ttu-id="aa455-121">Очередь инцидентов</span><span class="sxs-lookup"><span data-stu-id="aa455-121">Incident queue</span></span>

1. <span data-ttu-id="aa455-122">Откройте портал Microsoft 365 Defender <https://security.microsoft.com> () и впишитесь.</span><span class="sxs-lookup"><span data-stu-id="aa455-122">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="aa455-123">В области навигации выберите **& оповещения > происшествия**.</span><span class="sxs-lookup"><span data-stu-id="aa455-123">In the navigation pane, select **Incidents & alerts > Incidents**.</span></span>
3. <span data-ttu-id="aa455-124">Выберите имя инцидента, чтобы открыть его сводную страницу.</span><span class="sxs-lookup"><span data-stu-id="aa455-124">Select an incident name to open its summary page.</span></span>
4. <span data-ttu-id="aa455-125">Выберите **вкладку Evidence and Response.**</span><span class="sxs-lookup"><span data-stu-id="aa455-125">Select the **Evidence and Response** tab.</span></span>
5. <span data-ttu-id="aa455-126">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="aa455-126">Select an item in the list.</span></span> <span data-ttu-id="aa455-127">Откроется его боковое окно.</span><span class="sxs-lookup"><span data-stu-id="aa455-127">Its side pane opens.</span></span>
6. <span data-ttu-id="aa455-128">В боковой области примите утверждение или отклонение действий.</span><span class="sxs-lookup"><span data-stu-id="aa455-128">In the side pane, take approve or reject actions.</span></span>

## <a name="investigation-queue"></a><span data-ttu-id="aa455-129">Очередь расследования</span><span class="sxs-lookup"><span data-stu-id="aa455-129">Investigation queue</span></span>

1. <span data-ttu-id="aa455-130">Откройте портал Microsoft 365 Defender <https://security.microsoft.com> () и впишитесь.</span><span class="sxs-lookup"><span data-stu-id="aa455-130">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="aa455-131">Перейдите со страницы оповещений и инцидентов.</span><span class="sxs-lookup"><span data-stu-id="aa455-131">Navigate from the alerts/incident page.</span></span>
3. <span data-ttu-id="aa455-132">На странице Исследование перейдите на вкладку **ожидающих действий.**</span><span class="sxs-lookup"><span data-stu-id="aa455-132">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="aa455-133">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="aa455-133">Select an item in the list.</span></span> <span data-ttu-id="aa455-134">Откроется его боковое окно.</span><span class="sxs-lookup"><span data-stu-id="aa455-134">Its side pane opens.</span></span>
5. <span data-ttu-id="aa455-135">В боковой области примите утверждение или отклонение действий.</span><span class="sxs-lookup"><span data-stu-id="aa455-135">In the side pane, take approve or reject actions.</span></span>

## <a name="action-center"></a><span data-ttu-id="aa455-136">Центр уведомлений</span><span class="sxs-lookup"><span data-stu-id="aa455-136">Action center</span></span>

1. <span data-ttu-id="aa455-137">Откройте портал Microsoft 365 Defender <https://security.microsoft.com> () и впишитесь.</span><span class="sxs-lookup"><span data-stu-id="aa455-137">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="aa455-138">В области навигации выберите **Центр действий.**</span><span class="sxs-lookup"><span data-stu-id="aa455-138">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="aa455-139">На **вкладке Ожидание** просмотрите список действий, ожидающих утверждения.</span><span class="sxs-lookup"><span data-stu-id="aa455-139">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
   - <span data-ttu-id="aa455-140">Выберите **страницу Open investigation,** чтобы просмотреть дополнительные сведения о расследовании.</span><span class="sxs-lookup"><span data-stu-id="aa455-140">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="aa455-141">Выберите **Утверждение,** чтобы инициировать ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="aa455-141">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="aa455-142">Выберите **Отклонение,** чтобы предотвратить ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="aa455-142">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="investigation-and-remediation-investigations-queue"></a><span data-ttu-id="aa455-143">Очередь расследований и исправлений</span><span class="sxs-lookup"><span data-stu-id="aa455-143">Investigation and remediation investigations queue</span></span>

1. <span data-ttu-id="aa455-144">Откройте портал Microsoft 365 Defender <https://security.microsoft.com> () и впишитесь.</span><span class="sxs-lookup"><span data-stu-id="aa455-144">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="aa455-145">Откройте ожидающих расследований.</span><span class="sxs-lookup"><span data-stu-id="aa455-145">Open pending investigations.</span></span>
3. <span data-ttu-id="aa455-146">На странице Исследование перейдите на вкладку **ожидающих действий.**</span><span class="sxs-lookup"><span data-stu-id="aa455-146">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="aa455-147">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="aa455-147">Select an item in the list.</span></span> <span data-ttu-id="aa455-148">Откроется его боковое окно.</span><span class="sxs-lookup"><span data-stu-id="aa455-148">Its side pane opens.</span></span>
5. <span data-ttu-id="aa455-149">В боковой области примите утверждение или отклонение действий.</span><span class="sxs-lookup"><span data-stu-id="aa455-149">In the side pane, take approve or reject actions.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="aa455-150">Изменение или отмена одного действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="aa455-150">Change or undo one remediation action</span></span>

<span data-ttu-id="aa455-151">Существует два различных способа пересмотра представленных действий:</span><span class="sxs-lookup"><span data-stu-id="aa455-151">There are two different ways to reconsider submitted actions:</span></span>

- <span data-ttu-id="aa455-152">Через [единый центр действий](https://security.microsoft.com/action-center).</span><span class="sxs-lookup"><span data-stu-id="aa455-152">Through the [unified action center](https://security.microsoft.com/action-center).</span></span>
- <span data-ttu-id="aa455-153">Хотя центр [Office действий](https://security.microsoft.com/threatincidents).</span><span class="sxs-lookup"><span data-stu-id="aa455-153">Though the [Office action center](https://security.microsoft.com/threatincidents).</span></span>

## <a name="change-or-undo-through-the-unified-action-center"></a><span data-ttu-id="aa455-154">Изменение или отмена с помощью единого центра действий</span><span class="sxs-lookup"><span data-stu-id="aa455-154">Change or undo through the unified action center</span></span>

1. <span data-ttu-id="aa455-155">Перейдите в [единый центр действий и](https://security.microsoft.com/action-center) войдите.</span><span class="sxs-lookup"><span data-stu-id="aa455-155">Go to the [unified action center](https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="aa455-156">На **вкладке История** выберите действие, которое необходимо изменить или отменить.</span><span class="sxs-lookup"><span data-stu-id="aa455-156">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="aa455-157">В области на правой стороне экрана выберите соответствующеедействие (переходить в почтовый **ящик,** перейти к нежелательной, перейти к удаленным элементов, мягкое удаление или жесткое **удаление).**</span><span class="sxs-lookup"><span data-stu-id="aa455-157">In the pane on the right side of the screen, select the appropriate action (**move to inbox**, **move to junk**, **move to deleted items**, **soft delete**, or **hard delete**).</span></span>

## <a name="change-or-undo-through-the-office-action-center"></a><span data-ttu-id="aa455-158">Изменение или отмена через центр Office действий</span><span class="sxs-lookup"><span data-stu-id="aa455-158">Change or undo through the Office action center</span></span>

1. <span data-ttu-id="aa455-159">Перейдите в [центр Office действий и](https://security.microsoft.com/threatincidents) войдите.</span><span class="sxs-lookup"><span data-stu-id="aa455-159">Go to the [Office action center](https://security.microsoft.com/threatincidents) and sign in.</span></span>
2. <span data-ttu-id="aa455-160">Выберите соответствующее исправление.</span><span class="sxs-lookup"><span data-stu-id="aa455-160">Select the appropriate remediation.</span></span>
3. <span data-ttu-id="aa455-161">В боковой области щелкните запись отправки почты и дождись загрузки списка.</span><span class="sxs-lookup"><span data-stu-id="aa455-161">In the side pane, click on the mail submissions entry and wait for the list to load.</span></span>
4. <span data-ttu-id="aa455-162">Подождите кнопку Действие в верхней части, чтобы включить и выбрать кнопку Действие, чтобы изменить тип действия.</span><span class="sxs-lookup"><span data-stu-id="aa455-162">Wait for the Action button at the top to enable and select the Action button to change the action type.</span></span>
5. <span data-ttu-id="aa455-163">Это создаст соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="aa455-163">This will create the appropriate actions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aa455-164">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="aa455-164">Next steps</span></span>

- [<span data-ttu-id="aa455-165">Использование обозревателя угроз</span><span class="sxs-lookup"><span data-stu-id="aa455-165">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="aa455-166">Действия администратора и вручную</span><span class="sxs-lookup"><span data-stu-id="aa455-166">Admin /Manual Actions</span></span>](remediate-malicious-email-delivered-office-365.md)
- [<span data-ttu-id="aa455-167">Как сообщать о ложных срабатывах и отрицательных результатах в возможностях автоматического расследования и ответа</span><span class="sxs-lookup"><span data-stu-id="aa455-167">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="aa455-168">См. также</span><span class="sxs-lookup"><span data-stu-id="aa455-168">See also</span></span>

- [<span data-ttu-id="aa455-169">Просмотр сведений и результатов автоматического расследования в Office 365</span><span class="sxs-lookup"><span data-stu-id="aa455-169">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
