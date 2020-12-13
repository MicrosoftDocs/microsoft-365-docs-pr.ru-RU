---
title: Оценка релевантности в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Получите обзор этапа оценки и его роли в определении разности проблем во время обучения релевантности в Microsoft 365 Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28bbe15a6e3f5611041cf446bd053f59de395d54
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663084"
---
# <a name="understand-assessment-in-relevance-in-advanced-ediscovery-classic"></a><span data-ttu-id="07769-103">Оценка релевантности в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="07769-103">Understand Assessment in Relevance in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="07769-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="07769-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="07769-106">Advanced eDiscovery позволяет ранней оценки, например, для определенных проблем и данных, импортируемых для дела.</span><span class="sxs-lookup"><span data-stu-id="07769-106">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case.</span></span> <span data-ttu-id="07769-107">Advanced eDiscovery позволяет эксперту принимать решения о принятом подходе и применять эти решения к проекту проверки документов.</span><span class="sxs-lookup"><span data-stu-id="07769-107">Advanced eDiscovery lets the expert make decisions about an adopted approach and to apply these decisions to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="07769-108">Общее представление об оценке</span><span class="sxs-lookup"><span data-stu-id="07769-108">Understanding assessment</span></span>

<span data-ttu-id="07769-109">В оценке эксперт просматривает случайный набор не менее 500 файлов, которые используются для определения статистности проблем и получения статистики, отражающих результаты обучения.</span><span class="sxs-lookup"><span data-stu-id="07769-109">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results.</span></span> <span data-ttu-id="07769-110">Оценка прошла успешно, если обнаружено достаточное количество соответствующих файлов для достижения статистического уровня, который поможет advanced eDiscovery Релевантность предоставлять точную статистику и эффективно определять точку стабилизации в процессе обучения.</span><span class="sxs-lookup"><span data-stu-id="07769-110">Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="07769-111">Чем больше релевантные файлы в наборе оценок, тем точнее статистика и эффективность алгоритма стабильности.</span><span class="sxs-lookup"><span data-stu-id="07769-111">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm.</span></span> <span data-ttu-id="07769-112">Количество соответствующих файлов в файлах оценки зависит от большого значения проблемы.</span><span class="sxs-lookup"><span data-stu-id="07769-112">The number of relevant files within the assessment files depends on the richness of the issue.</span></span> <span data-ttu-id="07769-113">Насыщенность — это предполагаемый процент релевантности файлов в наборе, релевантном для проблемы.</span><span class="sxs-lookup"><span data-stu-id="07769-113">Richness is the estimated percent of relevant files in the set relevant to an issue.</span></span> <span data-ttu-id="07769-114">Проблемы с более высокой насыщенностью будут достигать большего количества релевантных файлов быстрее, чем проблемы с более низкой насыщенностью.</span><span class="sxs-lookup"><span data-stu-id="07769-114">Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness.</span></span> <span data-ttu-id="07769-115">Для проблем с очень низким уровнем насыщенности (например, 2% или меньше) потребуется очень большой набор оценок, чтобы получить значительное количество релевантных файлов.</span><span class="sxs-lookup"><span data-stu-id="07769-115">Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="07769-116">Статистика, представленная на вкладке "Отслеживание" и "Решение" во время обучения и после пакетного вычисления, включает оценки отзывов для разных наборов проверки.</span><span class="sxs-lookup"><span data-stu-id="07769-116">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets.</span></span> <span data-ttu-id="07769-117">В статистике оценки, основанные на примере набора (в данном случае это файлы оценки), включают поле ошибки и уровень вероятности этого поля ошибки.</span><span class="sxs-lookup"><span data-stu-id="07769-117">In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin.</span></span> <span data-ttu-id="07769-118">Например, при примерном отзыве 80 % может быть поле ошибки плюс или минус 5 % с уровнем достоверности 95 %.</span><span class="sxs-lookup"><span data-stu-id="07769-118">For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%.</span></span> <span data-ttu-id="07769-119">Это означает, что приблизительным отзывом фактически является 75%-85 %, и эта оценка имеет 95 % уверенности.</span><span class="sxs-lookup"><span data-stu-id="07769-119">This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence.</span></span> <span data-ttu-id="07769-120">Чем больше набор оценок, тем меньше поле ошибки, а статистика более точна.</span><span class="sxs-lookup"><span data-stu-id="07769-120">The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="07769-121">После того как эксперт проверит исходный набор из 500 файлов, релевантность может определить текущее поле ошибки значений отзыва.</span><span class="sxs-lookup"><span data-stu-id="07769-121">After the expert reviews an initial assessment set of 500 files, Relevance can determine the current margin of error of the recall values.</span></span> <span data-ttu-id="07769-122">Релевантность также рекомендует использовать поле ошибки по умолчанию для оптимизации набора оценок.</span><span class="sxs-lookup"><span data-stu-id="07769-122">Relevance will also recommend a default margin of error to reach to optimize the assessment set.</span></span> <span data-ttu-id="07769-123">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="07769-123">Here are some examples:</span></span>
  
- <span data-ttu-id="07769-124">Если набор оценки уже дает поле ошибки плюс или минус 10 %, релевантность будет рекомендовать двигаться к обучению (дополнительная проверка оценки не требуется).</span><span class="sxs-lookup"><span data-stu-id="07769-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend moving on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="07769-125">Если набор оценок дает поле ошибки плюс или минус 13 %, релевантность может порекомендовать просмотреть другой набор файлов оценки, чтобы достичь меньшего поля.</span><span class="sxs-lookup"><span data-stu-id="07769-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="07769-126">Если уровень насыщенности очень низкий, релевантность может порекомендовать остановить оценку, даже если поле ошибки слишком большое (что делает статистику непрактичной), так как набор оценки, необходимый для достижения полезного поля ошибки, слишком велик.</span><span class="sxs-lookup"><span data-stu-id="07769-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="07769-127">Каждая проблема имеет собственный объем, текущее поле ошибки и, как следствие, предполагаемое количество дополнительных файлов оценки.</span><span class="sxs-lookup"><span data-stu-id="07769-127">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files.</span></span> <span data-ttu-id="07769-128">Следующий набор оценок создается в соответствии с максимальным количеством файлов (до 1000 в одном наборе).</span><span class="sxs-lookup"><span data-stu-id="07769-128">The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="07769-129">Вы можете принять рекомендации по релевантности или изменить текущее поле ошибки в соответствии со своими потребностями.</span><span class="sxs-lookup"><span data-stu-id="07769-129">You can accept the Relevance recommendations or adjust the current margin of error according to your needs.</span></span> <span data-ttu-id="07769-130">Текущее поле ошибки по умолчанию определяется для отзыва равным или более 75%.</span><span class="sxs-lookup"><span data-stu-id="07769-130">The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="07769-131">Этап оценки можно обойти на вкладке  **"Отслеживание \>** релевантности" в расширенном представлении для проблемы, с помощью с помощью каждого из них с помощью каждого из них с помощью каждого из них с помощью каждого из них.</span><span class="sxs-lookup"><span data-stu-id="07769-131">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="07769-132">Однако в результате статистики по этой проблеме не будет.</span><span class="sxs-lookup"><span data-stu-id="07769-132">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="07769-133">> можно **только** перед выполнением оценки.</span><span class="sxs-lookup"><span data-stu-id="07769-133">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="07769-134">Если в ситуации имеется несколько проблем, оценка пропускается только в том случае, если для каждой проблемы был сдан этот контроль</span><span class="sxs-lookup"><span data-stu-id="07769-134">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="07769-135">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="07769-135">Related topics</span></span>

[<span data-ttu-id="07769-136">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="07769-136">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="07769-137">Добавление тегов и оценка</span><span class="sxs-lookup"><span data-stu-id="07769-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="07769-138">Обучение тегам и релевантности</span><span class="sxs-lookup"><span data-stu-id="07769-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="07769-139">Отслеживание анализа релевантности</span><span class="sxs-lookup"><span data-stu-id="07769-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="07769-140">Выбор на основе результатов</span><span class="sxs-lookup"><span data-stu-id="07769-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="07769-141">Тестирование анализа релевантности</span><span class="sxs-lookup"><span data-stu-id="07769-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

