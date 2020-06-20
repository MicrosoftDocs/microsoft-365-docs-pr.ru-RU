---
title: Решение на основе результатов расширенного обнаружения электронных данных
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 'Узнайте, как на вкладке "выбор" в Microsoft 365 Advanced eDiscovery содержатся данные, которые помогут определить правильный размер набора файлов для проверки. '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0139bc0505150a4d27aaca97b9b253f2043d649f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817908"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="9fe1d-103">Решение на основе результатов расширенного обнаружения электронных данных (классический)</span><span class="sxs-lookup"><span data-stu-id="9fe1d-103">Decision based on the results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="9fe1d-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="9fe1d-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="9fe1d-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="9fe1d-106">В Advanced eDiscovery на вкладке "выбор" представлены дополнительные сведения о просмотре и использовании статистики поддержки принятия решений для определения размера набора проверки файлов вариантов.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="9fe1d-107">Использование вкладки "выбор"</span><span class="sxs-lookup"><span data-stu-id="9fe1d-107">Using the Decide tab</span></span>

!["Релевантность" > "Решение"](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="9fe1d-109">Эта вкладка содержит следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="9fe1d-109">This tab includes the following:</span></span>
  
- <span data-ttu-id="9fe1d-110">**Вопрос**: отсюда можно выбрать вопрос из списка.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="9fe1d-111">**Коэффициент отзыва**: сравнение расширенного анализа обнаружения электронных данных в соответствии со степенью релевантности.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-111">**Review-recall ratio**: Comparison of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="9fe1d-112">Точка отсчета на диаграмме указывает процент файлов для проверки, сопоставленных с показателем релевантности.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-112">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="9fe1d-113">Он используется на этапе тестирования релевантности и в качестве порога экспорта для отбора.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-113">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="9fe1d-114">Точка отсчета по умолчанию для числа файлов, которые необходимо проверить, находится в точке, в которой оптимальным считается баланс между отзывами и точностью.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-114">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="9fe1d-115">Фактическая точка отсечки должна быть определена пользователем в зависимости от целей и компромиссных затрат (% пересмотра) и риска (% отозвать). С помощью ползунка вы можете настроить точку отсечки и увидеть, как на диаграмме и в параметрах извлекать процент релевантных файлов и перед проверкой принятия решения.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-115">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="9fe1d-116">**Параметры**: "Проверка", "отозвать", "следующие релевантные" и "Общие затраты" — это совокупная вычисленная статистика, относящаяся к набору проверки по отношению к коллекции для всего случая.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-116">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="9fe1d-117">Для этих параметров определены следующие определения:</span><span class="sxs-lookup"><span data-stu-id="9fe1d-117">Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="9fe1d-118">**Обзор**: процент файлов для проверки на основе этой отсечки.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-118">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="9fe1d-119">**Отзыв**: процент релевантных файлов в наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-119">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="9fe1d-120">**Следующий релевантный**: затраты на проверку и определение дополнительного релевантного файла, который в настоящее время не является набором рецензирования.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-120">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="9fe1d-121">**Общие затраты**: затраты для просмотра этого процента файлов вариантов.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-121">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="9fe1d-122">Настройки параметров затрат можно задать с помощью диспетчера вариантов.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-122">Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="9fe1d-123">**Распределение по показателю релевантности**: файлы в темно-сером дисплее слева расположены под показателем отсечки.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-123">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="9fe1d-124">Всплывающая подсказка отображает показатель релевантности и связанный с ними процент файлов в наборе контрольных файлов по отношению к общему количеству файлов.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-124">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="9fe1d-125">В области расширенных сведений отображаются дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-125">The expanded Details pane displays additional details.</span></span> <span data-ttu-id="9fe1d-126">Файлы в рисунках коллекции не включают пустые или небулаус файлы.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-126">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="9fe1d-127">На рисунках с семейными файлами представлены файлы, которые не загружаются по релевантности, но по-прежнему считаются частью семейства.</span><span class="sxs-lookup"><span data-stu-id="9fe1d-127">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9fe1d-128">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9fe1d-128">Related topics</span></span>

[<span data-ttu-id="9fe1d-129">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="9fe1d-129">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="9fe1d-130">Понимание оценки релевантности</span><span class="sxs-lookup"><span data-stu-id="9fe1d-130">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9fe1d-131">Маркировка и оценка</span><span class="sxs-lookup"><span data-stu-id="9fe1d-131">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9fe1d-132">Обучение по релевантности</span><span class="sxs-lookup"><span data-stu-id="9fe1d-132">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9fe1d-133">Анализ релевантности отслеживания</span><span class="sxs-lookup"><span data-stu-id="9fe1d-133">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9fe1d-134">Анализ релевантности тестирования</span><span class="sxs-lookup"><span data-stu-id="9fe1d-134">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

