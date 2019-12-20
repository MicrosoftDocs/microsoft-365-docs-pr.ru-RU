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
ms.openlocfilehash: edc952a0361ee8cfa6ed3df2eaf80f0fc4bf7fd5
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808464"
---
# <a name="approve-or-reject-pending-actions-from-automated-investigations"></a><span data-ttu-id="0dfd7-104">Примите или отклоните запрос на ожидающие действия от автоматизированных анализов угроз</span><span class="sxs-lookup"><span data-stu-id="0dfd7-104">Approve or reject pending actions from automated investigations</span></span>

<span data-ttu-id="0dfd7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0dfd7-105">**Applies to:**</span></span>
- <span data-ttu-id="0dfd7-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="0dfd7-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="0dfd7-107">При выполнении автоматического анализа угроз может возникать одно или несколько [действий по исправлению](mtp-action-center.md#remediation-actions), для которых требуется утверждение.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-107">When an automated investigation runs, it can result in one or more [remediation actions](mtp-action-center.md#remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="0dfd7-108">Например, может потребоваться удалить кластер сообщений электронной почты или файл из карантина.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="0dfd7-109">Необходимо как можно скорее утвердить (или отклонить) ожидающие выполнения действия, чтобы автоматизированный анализ угроз мог продолжить работу и своевременно завершить ее.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

<span data-ttu-id="0dfd7-110">Ожидающие выполнения действия могут быть проверены и утверждены с помощью одного из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="0dfd7-110">Pending actions can be reviewed and approved by using one of several methods:</span></span>
- [<span data-ttu-id="0dfd7-111">через центр уведомлений</span><span class="sxs-lookup"><span data-stu-id="0dfd7-111">Use the Action center</span></span>](#review-a-pending-action-in-the-action-center)
- [<span data-ttu-id="0dfd7-112">через представление со сведениями об анализе угроз</span><span class="sxs-lookup"><span data-stu-id="0dfd7-112">Use the investigation details view</span></span>](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> <span data-ttu-id="0dfd7-113">Чтобы утвердить или отклонить действия по исправлению, необходимы [соответствующие разрешения](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="0dfd7-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="0dfd7-114">Просмотр ожидающего действия в центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="0dfd7-114">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="0dfd7-115">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-115">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="0dfd7-116">В панели навигации щелкните **Центр уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-116">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="0dfd7-117">В центре уведомлений на вкладке **Ожидание** выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-117">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="0dfd7-118">При выборе элемента в столбце **Номер анализа** откроется страница сведений об анализе угроз.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-118">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="0dfd7-119">На ней вы можете просмотреть результаты анализа угроз и утвердить или отклонить рекомендуемое действие.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-119">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="0dfd7-120">При выборе строки в списке откроется всплывающее окно, в котором можно просмотреть сведения об этом элементе.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-120">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Утверждение или отклонение действия](../images/air-actioncenter-itemselected.png)<br/><span data-ttu-id="0dfd7-122">Используйте ссылки для просмотра связанного предупреждения или анализа, а также для утверждения или отклонения действия.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-122">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="0dfd7-123">Просмотр ожидающего действия в представлении со сведениями об анализе угроз</span><span class="sxs-lookup"><span data-stu-id="0dfd7-123">Review a pending action in the investigation details view</span></span>

![Сведения об анализе](../images/mtp-air-investdetails.png)

1. <span data-ttu-id="0dfd7-125">На странице [сведений анализа](mtp-autoir-results.md) выберите вкладку **Ожидающие действия** (или **Действия**). Здесь перечислены элементы, ожидающие утверждения.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-125">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="0dfd7-126">Выберите элемент в списке, а затем выберите **утвердить** или **отклонить**.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-126">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0dfd7-127">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="0dfd7-127">Next steps</span></span>

- [<span data-ttu-id="0dfd7-128">Дополнительные сведения о центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="0dfd7-128">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="0dfd7-129">Дополнительные сведения об инцидентах</span><span class="sxs-lookup"><span data-stu-id="0dfd7-129">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="0dfd7-130">Сведения об охоте на угрозы</span><span class="sxs-lookup"><span data-stu-id="0dfd7-130">Learn about hunting</span></span>](advanced-hunting-overview.md)
