---
title: Решение основано на результатах Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: Узнайте, как вкладка Decide в Advanced eDiscovery предоставляет данные, которые помогут определить правильный размер набора файлов дел для проверки.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769154"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="fb557-103">Решения, основанные на релевантности, Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fb557-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="fb557-104">В модуле Релевантность в Advanced eDiscovery вкладка Decide предоставляет дополнительные сведения для просмотра и использования статистики поддержки принятия решений для определения размера набора рассмотренных файлов.</span><span class="sxs-lookup"><span data-stu-id="fb557-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="fb557-105">Использование вкладки "Решение"</span><span class="sxs-lookup"><span data-stu-id="fb557-105">Using the Decide tab</span></span>

!["Релевантность" > "Решение"](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="fb557-107">Эта вкладка содержит следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="fb557-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="fb557-108">**Вопрос.** Здесь вы можете выбрать интересуемую проблему из списка.</span><span class="sxs-lookup"><span data-stu-id="fb557-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="fb557-109">**Соотношение отзывов** и отзывов: сравнение Advanced eDiscovery в соответствии с баллами релевантности.</span><span class="sxs-lookup"><span data-stu-id="fb557-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="fb557-110">Точка отсечь на диаграмме представляет процент просмотров файлов, относясь к оценке релевантности.</span><span class="sxs-lookup"><span data-stu-id="fb557-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="fb557-111">Это используется на этапе Тестирования релевантности и в качестве порогового значения экспорта для выкаповки.</span><span class="sxs-lookup"><span data-stu-id="fb557-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="fb557-112">Точка отсека по умолчанию, так как количество файлов, которые необходимо просмотреть, находится в точке оптимального баланса между Отзывом и точностью.</span><span class="sxs-lookup"><span data-stu-id="fb557-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="fb557-113">Фактическая точка отсеки должна определяться пользователем в зависимости от целей и компромисса затрат (%review) и риска (%recall).</span><span class="sxs-lookup"><span data-stu-id="fb557-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="fb557-114">С помощью ползунок можно настроить точку отсежения и увидеть влияние на график и параметры, при корректировке процентов соответствующих файлов, которые будут извлечены, и перед проверкой решения.</span><span class="sxs-lookup"><span data-stu-id="fb557-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="fb557-115">**Параметры:** Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span><span class="sxs-lookup"><span data-stu-id="fb557-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="fb557-116">Определения для этих параметров следуют следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fb557-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="fb557-117">**Обзор.** Процент файлов, которые необходимо просмотреть на основе этого отсека.</span><span class="sxs-lookup"><span data-stu-id="fb557-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="fb557-118">**Напомним.** Процент релевантного файла в наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="fb557-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="fb557-119">**Далее** релевантные: Стоимость проверки и определения другого соответствующего файла, который в настоящее время не находится в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="fb557-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="fb557-120">**Общие затраты.** Затраты на просмотр этого процента файлов дел.</span><span class="sxs-lookup"><span data-stu-id="fb557-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="fb557-121">Параметры затрат могут быть заданы менеджером case.</span><span class="sxs-lookup"><span data-stu-id="fb557-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="fb557-122">**Распределение по оценке релевантности.** Файлы в темно-сером дисплее слева находятся ниже оценки отсеки.</span><span class="sxs-lookup"><span data-stu-id="fb557-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="fb557-123">На подсказке инструмента отображается оценка релевантности и соответствующий процент файлов в файле обзора по отношению к общему объему файлов.</span><span class="sxs-lookup"><span data-stu-id="fb557-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="fb557-124">В расширенной **области Details** отображаются дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="fb557-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="fb557-125">Файлы в фигурах коллекции не включают пустые или туманные файлы.</span><span class="sxs-lookup"><span data-stu-id="fb557-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="fb557-126">Фигуры семейных файлов представляют файлы, которые не загружаются в Релевантность, но по-прежнему считаются частью семейства.</span><span class="sxs-lookup"><span data-stu-id="fb557-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
