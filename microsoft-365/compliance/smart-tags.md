---
title: Настройка смарт-тегов в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Смарт-теги могут применять возможности машинного обучения при просмотре контента в случае Advanced eDiscovery. Используйте группы смарт-тегов для отображения результатов моделей обнаружения машинного обучения, таких как модель привилегий клиента.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081086"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="8a5de-104">Настройка смарт-тегов в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8a5de-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="8a5de-105">Возможности машинного обучения (ML) в Advanced eDiscovery помогут вам сделать процесс принятия решений более эффективным при просмотре документов дела в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="8a5de-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="8a5de-106">Смарт-теги — это способ принятия решений с учетом возможностей ML: при пометке документов во время проверки.</span><span class="sxs-lookup"><span data-stu-id="8a5de-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="8a5de-107">При создании группы смарт-тегов решения, которые являются результатом модели ML, связанной с группой смарт-тегов, отображаются вместе с тегами в группе тегов.</span><span class="sxs-lookup"><span data-stu-id="8a5de-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="8a5de-108">Это помогает просмотреть сведения о результатах ML в строке при просмотре определенных документов.</span><span class="sxs-lookup"><span data-stu-id="8a5de-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="8a5de-109">Настройка группы смарт-тегов</span><span class="sxs-lookup"><span data-stu-id="8a5de-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="8a5de-110">В наборе для проверки **щелкните "Управление набором** для проверки" и выберите **"Управление тегами".**</span><span class="sxs-lookup"><span data-stu-id="8a5de-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="8a5de-111">Нажмите **кнопку "Добавить группу тегов"** и выберите **"Добавить группу смарт-тегов".**</span><span class="sxs-lookup"><span data-stu-id="8a5de-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="8a5de-112">Выберите модель ML, которую необходимо связать с группой тегов.</span><span class="sxs-lookup"><span data-stu-id="8a5de-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="8a5de-113">При этом создается группа тегов и N-потомки, где *N* — это число возможных выходных данных модели. </span><span class="sxs-lookup"><span data-stu-id="8a5de-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="8a5de-114">Например, модель [обнаружения адвокатских привилегий](attorney-privilege-detection.md) имеет два возможных выходных результата:</span><span class="sxs-lookup"><span data-stu-id="8a5de-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="8a5de-115">**Положительное** — используется для пометки документов, содержащих привилегированное содержимое адвокатского клиента.</span><span class="sxs-lookup"><span data-stu-id="8a5de-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="8a5de-116">**Отрицательный** — используется для пометки документов, которые не содержат привилегированного содержимого адвокатского клиента.</span><span class="sxs-lookup"><span data-stu-id="8a5de-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="8a5de-117">При выборе этой модели создается группа тегов с двумя потомков (один потомок с именем **Positive,** а другой отрицательный) для набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="8a5de-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="8a5de-118">В этом примере каждый из этих тегов соответствует одному из возможных результатов из модели обнаружения адвокатских привилегий.</span><span class="sxs-lookup"><span data-stu-id="8a5de-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="8a5de-119">При желании можно переименовать группу тегов и их потомки.</span><span class="sxs-lookup"><span data-stu-id="8a5de-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="8a5de-120">Например, можно переименовать тег Positive в  **Privileged,** а отрицательный — на  **"Не привилегированный".**</span><span class="sxs-lookup"><span data-stu-id="8a5de-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="8a5de-121">Использование смарт-тегов</span><span class="sxs-lookup"><span data-stu-id="8a5de-121">How to use smart tags</span></span>

<span data-ttu-id="8a5de-122">При просмотре документа результаты модели отображаются рядом с соответствующим тегом потомка.</span><span class="sxs-lookup"><span data-stu-id="8a5de-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="8a5de-123">Например, если у вас есть смарт-группа тегов для обнаружения адвокатских привилегий и вы просматриваете документ, который потенциально привилегированный, причина такого вывода отображается рядом с соответствующим тегом.</span><span class="sxs-lookup"><span data-stu-id="8a5de-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="8a5de-124">Важно отметить, что тег не применяется к документу автоматически.</span><span class="sxs-lookup"><span data-stu-id="8a5de-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="8a5de-125">Рецензент принимает решение о том, как пометить документ.</span><span class="sxs-lookup"><span data-stu-id="8a5de-125">The reviewer makes the decision about how to tag the document.</span></span>
