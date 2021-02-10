---
title: Просмотр действий по исправлению и управление ими в Microsoft Defender для Office 365
keywords: AIR, autoIR, ATP, автоматизированный, исследование, ответ, исправление, угрозы, расширенные, угроза, защита
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
description: Узнайте о действиях по исправлению в автоматизированном расследовании и реагировании на них в Microsoft Defender для Office 365 (план 2).
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 3fb77fa41ff3e9af995cf80b9f4024aa92a51212
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176019"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="785e4-104">Просмотр действий по исправлению и управление ими в Office 365</span><span class="sxs-lookup"><span data-stu-id="785e4-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="785e4-105">Так как автоматизированные исследования электронной почты & совместной  работы выдают решения, такие как вредоносные или подозрительные, создаются определенные действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="785e4-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="785e4-106">В Microsoft Defender для Office 365 действия по исправлению могут включать:</span><span class="sxs-lookup"><span data-stu-id="785e4-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="785e4-107">Блокировка URL-адреса (время щелчка)</span><span class="sxs-lookup"><span data-stu-id="785e4-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="785e4-108">Мягкое удаление сообщений электронной почты или кластеров</span><span class="sxs-lookup"><span data-stu-id="785e4-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="785e4-109">Карантин электронной почты или вложений электронной почты</span><span class="sxs-lookup"><span data-stu-id="785e4-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="785e4-110">Отключение внешней пересылки почты</span><span class="sxs-lookup"><span data-stu-id="785e4-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="785e4-111">Эти действия по исправлению не будут предприняты до тех пор, пока группа безопасности не утвердит их.</span><span class="sxs-lookup"><span data-stu-id="785e4-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="785e4-112">Мы рекомендуем как можно скорее просмотреть и утвердить все ожидающие действия, чтобы автоматические расследования были завершены своевременно.</span><span class="sxs-lookup"><span data-stu-id="785e4-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="785e4-113">В некоторых случаях можно отменить действие по исправлению.</span><span class="sxs-lookup"><span data-stu-id="785e4-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="785e4-114">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="785e4-114">**Applies to**</span></span>
- [<span data-ttu-id="785e4-115">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="785e4-115">Microsoft Defender for Office 365 plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="785e4-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="785e4-116">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="785e4-117">Утверждение (или отклонение) ожидающих действий</span><span class="sxs-lookup"><span data-stu-id="785e4-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="785e4-118">Перейдите в Центр безопасности Microsoft 365) [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="785e4-118">Go to the Microsoft 365 security center [https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="785e4-119">В области навигации выберите **"Центр действий".**</span><span class="sxs-lookup"><span data-stu-id="785e4-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="785e4-120">На **вкладке** "Ожидание" просмотрите список действий, ожидающих утверждения.</span><span class="sxs-lookup"><span data-stu-id="785e4-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="785e4-121">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="785e4-121">Select an item in the list.</span></span> <span data-ttu-id="785e4-122">Откроется его вылетная области.</span><span class="sxs-lookup"><span data-stu-id="785e4-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="785e4-123">Просмотрите сведения во flyout pane и с последующим одним из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="785e4-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="785e4-124">Выберите **страницу "Открыть исследование",** чтобы просмотреть дополнительные сведения об этом расследовании.</span><span class="sxs-lookup"><span data-stu-id="785e4-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="785e4-125">Выберите **"Утвердить",** чтобы инициировать ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="785e4-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="785e4-126">Выберите  "Отклонить", чтобы предотвратить ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="785e4-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="785e4-127">Отмена одного действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="785e4-127">Undo one remediation action</span></span>

1. <span data-ttu-id="785e4-128">Перейдите в центр действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="785e4-128">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="785e4-129">На **вкладке "История"** выберите действие, которое нужно отменить.</span><span class="sxs-lookup"><span data-stu-id="785e4-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="785e4-130">В области в правой части экрана выберите **"Отменить".**</span><span class="sxs-lookup"><span data-stu-id="785e4-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="785e4-131">Отмена нескольких действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="785e4-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="785e4-132">Перейдите в центр действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="785e4-132">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="785e4-133">На **вкладке "История"** выберите действия, которые нужно отменить.</span><span class="sxs-lookup"><span data-stu-id="785e4-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="785e4-134">Убедитесь, что выбраны элементы с одинаковым типом действия.</span><span class="sxs-lookup"><span data-stu-id="785e4-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="785e4-135">Откроется открываемая окно.</span><span class="sxs-lookup"><span data-stu-id="785e4-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="785e4-136">На flyout pane, select Undo.</span><span class="sxs-lookup"><span data-stu-id="785e4-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="785e4-137">Удаление файла из карантина на нескольких устройствах</span><span class="sxs-lookup"><span data-stu-id="785e4-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="785e4-138">Перейдите в центр действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="785e4-138">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="785e4-139">На **вкладке "История"** выберите файл с типом действия **"Карантин".**</span><span class="sxs-lookup"><span data-stu-id="785e4-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="785e4-140">В области в правой части экрана выберите "Применить к **X"** дополнительных экземпляров этого файла, а затем выберите **"Отменить".**</span><span class="sxs-lookup"><span data-stu-id="785e4-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="785e4-141">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="785e4-141">Next steps</span></span>

- [<span data-ttu-id="785e4-142">Использование обозревателя угроз</span><span class="sxs-lookup"><span data-stu-id="785e4-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="785e4-143">Как сообщать о ложных срабатываах и отрицательных результатах в автоматизированном расследовании и реагировании на них</span><span class="sxs-lookup"><span data-stu-id="785e4-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="785e4-144">См. также</span><span class="sxs-lookup"><span data-stu-id="785e4-144">See also</span></span>

- [<span data-ttu-id="785e4-145">Просмотр сведений и результатов автоматического исследования в Office 365</span><span class="sxs-lookup"><span data-stu-id="785e4-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
