---
title: Решение на основе результатов в Advanced eDiscovery
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
description: Узнайте, как вкладка "Принять решение" в Advanced eDiscovery предоставляет данные, которые помогут определить правильный размер набора файлов дела для проверки.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0423a21520375f1d9de8e2eaeca142b979ff1883
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759871"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="37761-103">Решение на основе результатов в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="37761-103">Decision based on the results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="37761-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="37761-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="37761-106">В Advanced eDiscovery вкладка "Принятие решения" предоставляет дополнительные сведения для просмотра и использования статистики поддержки решений для определения размера проверяемого набора файлов дел.</span><span class="sxs-lookup"><span data-stu-id="37761-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="37761-107">Использование вкладки "Принять решение"</span><span class="sxs-lookup"><span data-stu-id="37761-107">Using the Decide tab</span></span>

!["Релевантность" > "Решение"](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="37761-109">Эта вкладка содержит следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="37761-109">This tab includes the following components:</span></span>
  
- <span data-ttu-id="37761-110">**Проблема:** здесь можно выбрать интересуую проблему из списка.</span><span class="sxs-lookup"><span data-stu-id="37761-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="37761-111">**Соотношение отзывов и отзывов:** сравнение проверки Advanced eDiscovery в соответствии с результатами релевантности.</span><span class="sxs-lookup"><span data-stu-id="37761-111">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="37761-112">Точка "Вырезание" на диаграмме представляет процент проверяемого файла, со карте со значением релевантности.</span><span class="sxs-lookup"><span data-stu-id="37761-112">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="37761-113">Это используется на этапе проверки релевантности и в качестве порогового значения экспорта для вычислений.</span><span class="sxs-lookup"><span data-stu-id="37761-113">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="37761-114">Точка вырезания по умолчанию для количества проверяемого количества файлов находится на том этапе, в котором оптимальный баланс между отзывом и точностью.</span><span class="sxs-lookup"><span data-stu-id="37761-114">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="37761-115">Фактическая точка вырезания должна определяться пользователем в зависимости от целей и компромисса затрат (%review) и риска (%recall).</span><span class="sxs-lookup"><span data-stu-id="37761-115">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="37761-116">С помощью ползунок можно настроить точку вырезания и увидеть влияние на график и параметры, при корректировке процента извлекаемого релевантного файла и перед проверкой решения.</span><span class="sxs-lookup"><span data-stu-id="37761-116">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="37761-117">**Параметры**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics relevant to the review set in relation to the collection for the entire case.</span><span class="sxs-lookup"><span data-stu-id="37761-117">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="37761-118">Определения для этих параметров:</span><span class="sxs-lookup"><span data-stu-id="37761-118">Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="37761-119">**Review**: Percentage of files to review based on this cutoff.</span><span class="sxs-lookup"><span data-stu-id="37761-119">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="37761-120">**Отзыв:** процент релевантного файла в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="37761-120">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="37761-121">**Далее :** затраты на проверку и определение дополнительного соответствующего файла, который в настоящее время не находится в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="37761-121">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="37761-122">**Общая стоимость**: затраты на просмотр этого процента файлов дел.</span><span class="sxs-lookup"><span data-stu-id="37761-122">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="37761-123">Параметры затрат могут быть заданы диспетчером дела.</span><span class="sxs-lookup"><span data-stu-id="37761-123">Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="37761-124">**Распределение по оценке релевантности:** файлы на темно-сером дисплее слева находятся ниже оценки вырезания.</span><span class="sxs-lookup"><span data-stu-id="37761-124">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="37761-125">Подсказка отображает показатель релевантности и соответствующий процент файлов в наборе файлов для проверки по отношению к общему объему файлов.</span><span class="sxs-lookup"><span data-stu-id="37761-125">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="37761-126">В расширенной области сведений отображаются дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="37761-126">The expanded Details pane displays additional details.</span></span> <span data-ttu-id="37761-127">Файлы на рисунках коллекции не включают пустые или неблокличные файлы.</span><span class="sxs-lookup"><span data-stu-id="37761-127">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="37761-128">Рисунки файлов семейства представляют файлы, которые не загружаются в релевантности, но по-прежнему считаются частью семейства.</span><span class="sxs-lookup"><span data-stu-id="37761-128">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
