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
ms.date: 01/29/2021
ms.openlocfilehash: f0c42bef1b090412a7a6422fe029323b645e90df
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275076"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="67534-104">Просмотр и управление действиями по исправлению в Office 365</span><span class="sxs-lookup"><span data-stu-id="67534-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="67534-105">По мере автоматического расследования & контента совместной работы создаются определенные действия по исправлению, например вредоносные или подозрительные. </span><span class="sxs-lookup"><span data-stu-id="67534-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="67534-106">В Microsoft Defender для Office 365 действий по исправлению можно включить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="67534-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="67534-107">Блокировка URL-адреса (время щелчка мыши)</span><span class="sxs-lookup"><span data-stu-id="67534-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="67534-108">Мягкое удаление сообщений электронной почты или кластеров</span><span class="sxs-lookup"><span data-stu-id="67534-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="67534-109">Карантин вложения электронной почты или электронной почты</span><span class="sxs-lookup"><span data-stu-id="67534-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="67534-110">Отключение внешней пересылаемой почты</span><span class="sxs-lookup"><span data-stu-id="67534-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="67534-111">Эти действия по исправлению не принимаются до тех пор, пока их не утвердит группа операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="67534-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="67534-112">Мы рекомендуем как можно скорее просмотреть и утвердить все ожидающие действия, чтобы автоматические расследования были завершены своевременно.</span><span class="sxs-lookup"><span data-stu-id="67534-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="67534-113">В некоторых случаях можно отменить действие по исправлению.</span><span class="sxs-lookup"><span data-stu-id="67534-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="67534-114">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="67534-114">**Applies to**</span></span>
- [<span data-ttu-id="67534-115">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="67534-115">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="67534-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67534-116">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="67534-117">Утверждение (или отклонение) ожидающих действий</span><span class="sxs-lookup"><span data-stu-id="67534-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="67534-118">Перейдите в центр Microsoft 365 безопасности <https://security.microsoft.com> () и войдите.</span><span class="sxs-lookup"><span data-stu-id="67534-118">Go to the Microsoft 365 security center (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="67534-119">В области навигации выберите **Центр действий.**</span><span class="sxs-lookup"><span data-stu-id="67534-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="67534-120">На **вкладке Ожидание** просмотрите список действий, ожидающих утверждения.</span><span class="sxs-lookup"><span data-stu-id="67534-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="67534-121">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="67534-121">Select an item in the list.</span></span> <span data-ttu-id="67534-122">Откроется его поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="67534-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="67534-123">Просмотрите сведения в области вылетов и примите один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="67534-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="67534-124">Выберите **страницу Open investigation,** чтобы просмотреть дополнительные сведения о расследовании.</span><span class="sxs-lookup"><span data-stu-id="67534-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="67534-125">Выберите **Утверждение,** чтобы инициировать ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="67534-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="67534-126">Выберите **Отклонение,** чтобы предотвратить ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="67534-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="67534-127">Отмена одного действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="67534-127">Undo one remediation action</span></span>

1. <span data-ttu-id="67534-128">Перейдите в центр действий <https://security.microsoft.com/action-center> () и войдите.</span><span class="sxs-lookup"><span data-stu-id="67534-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="67534-129">На **вкладке История** выберите действие, которое необходимо отменить.</span><span class="sxs-lookup"><span data-stu-id="67534-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="67534-130">В области справа от экрана выберите **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="67534-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="67534-131">Отмена нескольких действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="67534-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="67534-132">Перейдите в центр действий <https://security.microsoft.com/action-center> () и войдите.</span><span class="sxs-lookup"><span data-stu-id="67534-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="67534-133">На **вкладке История** выберите действия, которые необходимо отменить.</span><span class="sxs-lookup"><span data-stu-id="67534-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="67534-134">Убедитесь, что выберите элементы с одинаковым типом действия.</span><span class="sxs-lookup"><span data-stu-id="67534-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="67534-135">Открывается поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="67534-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="67534-136">В области вылетов выберите Отмена.</span><span class="sxs-lookup"><span data-stu-id="67534-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="67534-137">Удаление файла из карантина на нескольких устройствах</span><span class="sxs-lookup"><span data-stu-id="67534-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="67534-138">Перейдите в центр действий <https://security.microsoft.com/action-center> () и войдите.</span><span class="sxs-lookup"><span data-stu-id="67534-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="67534-139">На **вкладке История** выберите файл с карантиным файлом типа **Action.**</span><span class="sxs-lookup"><span data-stu-id="67534-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="67534-140">В области справа от экрана выберите **Применить** к X дополнительные экземпляры этого файла, а затем **отменить**.</span><span class="sxs-lookup"><span data-stu-id="67534-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="67534-141">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="67534-141">Next steps</span></span>

- [<span data-ttu-id="67534-142">Использование обозревателя угроз</span><span class="sxs-lookup"><span data-stu-id="67534-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="67534-143">Как сообщать о ложных срабатывах и отрицательных результатах в возможностях автоматического расследования и ответа</span><span class="sxs-lookup"><span data-stu-id="67534-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="67534-144">См. также</span><span class="sxs-lookup"><span data-stu-id="67534-144">See also</span></span>

- [<span data-ttu-id="67534-145">Просмотр сведений и результатов автоматического расследования в Office 365</span><span class="sxs-lookup"><span data-stu-id="67534-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
