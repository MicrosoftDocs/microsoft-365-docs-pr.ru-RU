---
title: Утверждение или отклонение ожидающих действий после автоматического исследования
description: Используйте центр уведомлений для управления действиями, связанными с автоматизированным анализом угроз и реакцией на угрозы
keywords: действие, центр, автоматизированный анализ угроз и реакция на угрозы, автоматизированный, анализ угроз, реакция на угрозы, исправление
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: b34f4a532571d6215500ab2bec022489fd462d0f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683371"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="56921-104">Утверждение или отклонение ожидающих действий после автоматического исследования</span><span class="sxs-lookup"><span data-stu-id="56921-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="56921-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="56921-105">**Applies to:**</span></span>
- <span data-ttu-id="56921-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56921-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="56921-107">При выполнении автоматического анализа угроз может возникать одно или несколько [действий по исправлению](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions), для которых требуется утверждение.</span><span class="sxs-lookup"><span data-stu-id="56921-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="56921-108">Например, может потребоваться удалить кластер сообщений электронной почты или файл из карантина.</span><span class="sxs-lookup"><span data-stu-id="56921-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="56921-109">Необходимо как можно скорее утвердить (или отклонить) ожидающие выполнения действия, чтобы автоматизированный анализ угроз мог продолжить работу и своевременно завершить ее.</span><span class="sxs-lookup"><span data-stu-id="56921-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="56921-110">Если вы считаете, что функции автоматического исследования и реагирования в Защитнике Microsoft 365 что-то было пропущено или неправильно обнаружено, дайте нам знать!</span><span class="sxs-lookup"><span data-stu-id="56921-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="56921-111">Узнайте, как сообщать о ложных срабатываах и отрицательных результатах в автоматизированных исследованиях и [ответах (AIR) в Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="56921-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="56921-112">Ожидающих действий можно просмотреть и утвердить с помощью Центра действий [или](#review-a-pending-action-in-the-action-center) представления [сведений об анализе.](#review-a-pending-action-in-the-investigation-details-view)</span><span class="sxs-lookup"><span data-stu-id="56921-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="56921-113">Чтобы утвердить или отклонить действия по исправлению, необходимы [соответствующие разрешения](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="56921-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="56921-114">Дополнительные сведения см. в предварительных условия для автоматического исследования и реагирования [в Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="56921-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="56921-115">Просмотр ожидающего действия в центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="56921-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="56921-116">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="56921-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="56921-117">В панели навигации щелкните **Центр уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="56921-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="56921-118">В центре уведомлений на вкладке **Ожидание** выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="56921-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="56921-119">При выборе элемента в столбце **Номер анализа** откроется страница сведений об анализе угроз.</span><span class="sxs-lookup"><span data-stu-id="56921-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="56921-120">На ней вы можете просмотреть результаты анализа угроз и утвердить или отклонить рекомендуемое действие.</span><span class="sxs-lookup"><span data-stu-id="56921-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="56921-121">При выборе строки в списке откроется всплывающее окно, в котором можно просмотреть сведения об этом элементе.</span><span class="sxs-lookup"><span data-stu-id="56921-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Утверждение или отклонение действия](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="56921-123">Используйте ссылки для просмотра связанного предупреждения или анализа, а также для утверждения или отклонения действия.</span><span class="sxs-lookup"><span data-stu-id="56921-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="56921-124">Просмотр ожидающего действия в представлении со сведениями об анализе угроз</span><span class="sxs-lookup"><span data-stu-id="56921-124">Review a pending action in the investigation details view</span></span>

![Сведения об анализе](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="56921-126">На странице [сведений анализа](mtp-autoir-results.md) выберите вкладку **Ожидающие действия** (или **Действия**). Здесь перечислены элементы, ожидающие утверждения.</span><span class="sxs-lookup"><span data-stu-id="56921-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="56921-127">Выберите элемент в списке, а затем выберите **утвердить** или **отклонить**.</span><span class="sxs-lookup"><span data-stu-id="56921-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="56921-128">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="56921-128">Next steps</span></span>

- [<span data-ttu-id="56921-129">Просмотр сведений и результатов автоматического исследования</span><span class="sxs-lookup"><span data-stu-id="56921-129">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="56921-130">Обработка ложных срабатывавай и отрицательных результатов в автоматизированном расследовании и реагировании на них</span><span class="sxs-lookup"><span data-stu-id="56921-130">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
