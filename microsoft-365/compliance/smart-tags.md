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
description: Смарт-теги позволяют применять возможности машинного обучения при просмотре контента в расширенном случае обнаружения электронных данных. Используйте группы смарт-тегов для отображения результатов моделей обнаружения машинного обучения, таких как модель полномочий клиентов с юристами.
ms.openlocfilehash: 9b3e1310baa06f53a3ee1dab5c371fb67d6ab95c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597406"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="cfd0d-104">Настройка смарт-тегов в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="cfd0d-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="cfd0d-105">Возможности машинного обучения (ML) в Advanced eDiscovery могут помочь повысить эффективность процесса принятия решений при просмотре документов с учетом регистра в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="cfd0d-106">Смарт-теги позволяют обеспечить возможности ML, в которые записываются решения: при разметке документов во время рецензирования.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="cfd0d-107">При создании группы смарт-тегов решения, которые являются результатом модели ML, связанной с группой смарт-тегов, отображаются в виде тегов в группе тегов.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="cfd0d-108">Это помогает просмотреть сведения о результатах в ML, когда вы просматриваете конкретные документы.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="cfd0d-109">Настройка группы смарт-тегов</span><span class="sxs-lookup"><span data-stu-id="cfd0d-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="cfd0d-110">В наборе проверки щелкните **Управление набором проверки** , а затем щелкните **Управление тегами**.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="cfd0d-111">Нажмите кнопку **Добавить группу тегов** , а затем выберите пункт **Добавить группу смарт-тегов**.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="cfd0d-112">Выберите модель ML, которую необходимо связать с группой тегов.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="cfd0d-113">При этом создается группа тегов и дочерние теги *n* , где *N* — это количество возможных выходов модели.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="cfd0d-114">Например, [модель обнаружения доверенных прав клиентов](attorney-privilege-detection.md) имеет два возможных выхода:</span><span class="sxs-lookup"><span data-stu-id="cfd0d-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="cfd0d-115">**Положительный** — используется для обозначения документов, содержащих привилегированный контент клиента с ограниченным уровнем доверенности.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="cfd0d-116">**Отрицательные** — используйте для тегов документов, не содержащих привилегированного контента клиента.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="cfd0d-117">Если выбрана эта модель, создается группа тегов с двумя дочерними тегами (один дочерний тег под названием **положительный** и другой с именем **отрицательный**) для набора проверки.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="cfd0d-118">В этом примере каждый дочерний тег соответствует одному из возможных выходных данных из модели обнаружения прав клиентов с юристами.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="cfd0d-119">При необходимости можно переименовать группу тегов и дочерние теги.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="cfd0d-120">Например, вы можете переименовать **положительный** тег в значение **privileged** , а **отрицательный** — на **непривилегированный**.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="cfd0d-121">Использование смарт-тегов</span><span class="sxs-lookup"><span data-stu-id="cfd0d-121">How to use smart tags</span></span>

<span data-ttu-id="cfd0d-122">При просмотре документа результаты модели отображаются рядом с соответствующим дочерним тегом.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="cfd0d-123">Например, если у вас есть группа смарт-тегов для обнаружения доверенных прав клиентов и вы просматриваете потенциально привилегированный документ, то причина этого завершения отображается рядом с соответствующим тегом.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="cfd0d-124">Важно отметить, что тег не применяется автоматически к документу.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="cfd0d-125">Проверяющий принимает решение о том, как отмечать тегами документ.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-125">The reviewer makes the decision about how to tag the document.</span></span>