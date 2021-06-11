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
ms.openlocfilehash: 7894a9aa38239bf661c809cce96ea2a2a96c3725
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904132"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="ac90f-104">Просмотр и управление действиями по исправлению в Office 365</span><span class="sxs-lookup"><span data-stu-id="ac90f-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="ac90f-105">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="ac90f-105">**Applies to**</span></span>
- [<span data-ttu-id="ac90f-106">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="ac90f-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ac90f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac90f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ac90f-108">По мере автоматического расследования & контента совместной работы создаются определенные действия по исправлению, например вредоносные или подозрительные. </span><span class="sxs-lookup"><span data-stu-id="ac90f-108">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="ac90f-109">В Microsoft Defender для Office 365 действий по исправлению можно включить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ac90f-109">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="ac90f-110">Блокировка URL-адреса (время щелчка мыши)</span><span class="sxs-lookup"><span data-stu-id="ac90f-110">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="ac90f-111">Мягкое удаление сообщений электронной почты или кластеров</span><span class="sxs-lookup"><span data-stu-id="ac90f-111">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="ac90f-112">Карантин вложения электронной почты или электронной почты</span><span class="sxs-lookup"><span data-stu-id="ac90f-112">Quarantining email or email attachments</span></span>
- <span data-ttu-id="ac90f-113">Отключение внешней пересылаемой почты</span><span class="sxs-lookup"><span data-stu-id="ac90f-113">Turning off external mail forwarding</span></span>

<span data-ttu-id="ac90f-114">Эти действия по исправлению не принимаются до тех пор, пока их не утвердит группа операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="ac90f-114">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="ac90f-115">Мы рекомендуем как можно скорее просмотреть и утвердить все ожидающие действия, чтобы автоматические расследования были завершены своевременно.</span><span class="sxs-lookup"><span data-stu-id="ac90f-115">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="ac90f-116">В некоторых случаях можно отменить действие по исправлению.</span><span class="sxs-lookup"><span data-stu-id="ac90f-116">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="ac90f-117">Утверждение (или отклонение) ожидающих действий</span><span class="sxs-lookup"><span data-stu-id="ac90f-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="ac90f-118">Перейдите на портал Microsoft 365 Defender <https://security.microsoft.com> () и войдите.</span><span class="sxs-lookup"><span data-stu-id="ac90f-118">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="ac90f-119">В области навигации выберите **Центр действий.**</span><span class="sxs-lookup"><span data-stu-id="ac90f-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="ac90f-120">На **вкладке Ожидание** просмотрите список действий, ожидающих утверждения.</span><span class="sxs-lookup"><span data-stu-id="ac90f-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="ac90f-121">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="ac90f-121">Select an item in the list.</span></span> <span data-ttu-id="ac90f-122">Откроется его поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="ac90f-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="ac90f-123">Просмотрите сведения в области вылетов и примите один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="ac90f-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="ac90f-124">Выберите **страницу Open investigation,** чтобы просмотреть дополнительные сведения о расследовании.</span><span class="sxs-lookup"><span data-stu-id="ac90f-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="ac90f-125">Выберите **Утверждение,** чтобы инициировать ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="ac90f-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="ac90f-126">Выберите **Отклонение,** чтобы предотвратить ожидающих действий.</span><span class="sxs-lookup"><span data-stu-id="ac90f-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="ac90f-127">Изменение или отмена одного действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="ac90f-127">Change or undo one remediation action</span></span>

1. <span data-ttu-id="ac90f-128">Перейдите в центр действий <https://security.microsoft.com/action-center> () и войдите.</span><span class="sxs-lookup"><span data-stu-id="ac90f-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="ac90f-129">На **вкладке История** выберите действие, которое необходимо изменить или отменить.</span><span class="sxs-lookup"><span data-stu-id="ac90f-129">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="ac90f-130">В области справа от экрана выберите **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="ac90f-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="change-or-undo-multiple-remediation-actions"></a><span data-ttu-id="ac90f-131">Изменение или отмена нескольких действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="ac90f-131">Change or undo multiple remediation actions</span></span>

1. <span data-ttu-id="ac90f-132">Перейдите в центр действий <https://security.microsoft.com/action-center> () и войдите.</span><span class="sxs-lookup"><span data-stu-id="ac90f-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="ac90f-133">На **вкладке История** выберите действия, которые необходимо изменить или отменить.</span><span class="sxs-lookup"><span data-stu-id="ac90f-133">On the **History** tab, select the actions that you want to change or undo.</span></span> <span data-ttu-id="ac90f-134">Убедитесь, что выберите элементы с одинаковым типом действия.</span><span class="sxs-lookup"><span data-stu-id="ac90f-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="ac90f-135">Открывается поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="ac90f-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="ac90f-136">В области вылетов выберите Отмена.</span><span class="sxs-lookup"><span data-stu-id="ac90f-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="ac90f-137">Удаление файла из карантина на нескольких устройствах</span><span class="sxs-lookup"><span data-stu-id="ac90f-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="ac90f-138">Перейдите в центр действий <https://security.microsoft.com/action-center> () и войдите.</span><span class="sxs-lookup"><span data-stu-id="ac90f-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="ac90f-139">На **вкладке История** выберите файл с карантиным файлом типа **Action.**</span><span class="sxs-lookup"><span data-stu-id="ac90f-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="ac90f-140">В области справа от экрана выберите **Применить** к X дополнительные экземпляры этого файла, а затем **отменить**.</span><span class="sxs-lookup"><span data-stu-id="ac90f-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ac90f-141">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ac90f-141">Next steps</span></span>

- [<span data-ttu-id="ac90f-142">Использование обозревателя угроз</span><span class="sxs-lookup"><span data-stu-id="ac90f-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="ac90f-143">Как сообщать о ложных срабатывах и отрицательных результатах в возможностях автоматического расследования и ответа</span><span class="sxs-lookup"><span data-stu-id="ac90f-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="ac90f-144">См. также</span><span class="sxs-lookup"><span data-stu-id="ac90f-144">See also</span></span>

- [<span data-ttu-id="ac90f-145">Просмотр сведений и результатов автоматического расследования в Office 365</span><span class="sxs-lookup"><span data-stu-id="ac90f-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
