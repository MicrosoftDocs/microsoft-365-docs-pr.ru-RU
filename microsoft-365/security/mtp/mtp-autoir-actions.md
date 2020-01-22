---
title: Примите или отклоните запрос на ожидающие действия после автоматизированного анализа угроз
description: Используйте центр уведомлений для управления действиями, связанными с автоматизированным анализом угроз и реакцией на угрозы
keywords: действие, центр, автоматизированный анализ угроз и реакция на угрозы, автоматизированный, анализ угроз, реакция на угрозы, исправление
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 35433eccf93c56a8f8bf66b50fa6728ff7585d8e
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260207"
---
# <a name="approve-or-reject-pending-actions-from-automated-investigations"></a><span data-ttu-id="27fd1-104">Примите или отклоните запрос на ожидающие действия от автоматизированных анализов угроз</span><span class="sxs-lookup"><span data-stu-id="27fd1-104">Approve or reject pending actions from automated investigations</span></span>

<span data-ttu-id="27fd1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="27fd1-105">**Applies to:**</span></span>
- <span data-ttu-id="27fd1-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="27fd1-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="27fd1-107">При выполнении автоматического анализа угроз может возникать одно или несколько [действий по исправлению](mtp-action-center.md#remediation-actions), для которых требуется утверждение.</span><span class="sxs-lookup"><span data-stu-id="27fd1-107">When an automated investigation runs, it can result in one or more [remediation actions](mtp-action-center.md#remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="27fd1-108">Например, может потребоваться удалить кластер сообщений электронной почты или файл из карантина.</span><span class="sxs-lookup"><span data-stu-id="27fd1-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="27fd1-109">Необходимо как можно скорее утвердить (или отклонить) ожидающие выполнения действия, чтобы автоматизированный анализ угроз мог продолжить работу и своевременно завершить ее.</span><span class="sxs-lookup"><span data-stu-id="27fd1-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="27fd1-110">Если вы считаете, что что-то пошло не так или неправильно, с помощью автоматизированного расследования и функции ответа в Microsoft Threat Protection, сообщите нам о!</span><span class="sxs-lookup"><span data-stu-id="27fd1-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="27fd1-111">Сведения о [том, как сообщить о ложных положительных и отрицательных значениях при автоматическом расследовании и возможностях реагирования (AIR) в защите от угроз Майкрософт](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="27fd1-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="27fd1-112">Ожидающие выполнения действия могут быть проверены и утверждены с помощью одного из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="27fd1-112">Pending actions can be reviewed and approved by using one of several methods:</span></span>
- [<span data-ttu-id="27fd1-113">через центр уведомлений</span><span class="sxs-lookup"><span data-stu-id="27fd1-113">Use the Action center</span></span>](#review-a-pending-action-in-the-action-center)
- [<span data-ttu-id="27fd1-114">через представление со сведениями об анализе угроз</span><span class="sxs-lookup"><span data-stu-id="27fd1-114">Use the investigation details view</span></span>](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> <span data-ttu-id="27fd1-115">Чтобы утвердить или отклонить действия по исправлению, необходимы [соответствующие разрешения](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="27fd1-115">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="27fd1-116">Просмотр ожидающего действия в центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="27fd1-116">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="27fd1-117">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="27fd1-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="27fd1-118">В панели навигации щелкните **Центр уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="27fd1-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="27fd1-119">В центре уведомлений на вкладке **Ожидание** выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="27fd1-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="27fd1-120">При выборе элемента в столбце **Номер анализа** откроется страница сведений об анализе угроз.</span><span class="sxs-lookup"><span data-stu-id="27fd1-120">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="27fd1-121">На ней вы можете просмотреть результаты анализа угроз и утвердить или отклонить рекомендуемое действие.</span><span class="sxs-lookup"><span data-stu-id="27fd1-121">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="27fd1-122">При выборе строки в списке откроется всплывающее окно, в котором можно просмотреть сведения об этом элементе.</span><span class="sxs-lookup"><span data-stu-id="27fd1-122">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Утверждение или отклонение действия](../images/air-actioncenter-itemselected.png)<br/><span data-ttu-id="27fd1-124">Используйте ссылки для просмотра связанного предупреждения или анализа, а также для утверждения или отклонения действия.</span><span class="sxs-lookup"><span data-stu-id="27fd1-124">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="27fd1-125">Просмотр ожидающего действия в представлении со сведениями об анализе угроз</span><span class="sxs-lookup"><span data-stu-id="27fd1-125">Review a pending action in the investigation details view</span></span>

![Сведения об анализе](../images/mtp-air-investdetails.png)

1. <span data-ttu-id="27fd1-127">На странице [сведений анализа](mtp-autoir-results.md) выберите вкладку **Ожидающие действия** (или **Действия**). Здесь перечислены элементы, ожидающие утверждения.</span><span class="sxs-lookup"><span data-stu-id="27fd1-127">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="27fd1-128">Выберите элемент в списке, а затем выберите **утвердить** или **отклонить**.</span><span class="sxs-lookup"><span data-stu-id="27fd1-128">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="27fd1-129">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="27fd1-129">Next steps</span></span>

- [<span data-ttu-id="27fd1-130">Дополнительные сведения о центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="27fd1-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="27fd1-131">Дополнительные сведения об инцидентах</span><span class="sxs-lookup"><span data-stu-id="27fd1-131">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="27fd1-132">Сведения об охоте на угрозы</span><span class="sxs-lookup"><span data-stu-id="27fd1-132">Learn about hunting</span></span>](advanced-hunting-overview.md)
