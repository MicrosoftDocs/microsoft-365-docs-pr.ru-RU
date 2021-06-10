---
title: Применение фильтра оценки прогноза к пунктам в наборе обзоров
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: С помощью фильтра оценки прогноза отображаются элементы, которые модель прогностического кодирования предсказывается как релевантные или не релевантные.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822593"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a><span data-ttu-id="5552d-103">Применение фильтра оценки прогноза к набору обзоров (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="5552d-103">Apply a prediction score filter to a review set (preview)</span></span>

<span data-ttu-id="5552d-104">После создания модели прогностического кодирования в Advanced eDiscovery и ее подготовки до точки, где она стабильна, можно применить фильтр оценки прогноза, чтобы отобразить установленные моделью элементы, соответствующие (или не соответствующие).</span><span class="sxs-lookup"><span data-stu-id="5552d-104">After you create a predictive coding model in Advanced eDiscovery and train it to the point where it's stable, you can apply the prediction score filter to display review set items that the model has determined are relevant (or not relevant).</span></span> <span data-ttu-id="5552d-105">При создании модели также создается соответствующий фильтр оценки прогноза.</span><span class="sxs-lookup"><span data-stu-id="5552d-105">When you create a model, a corresponding prediction score filter is also created.</span></span> <span data-ttu-id="5552d-106">Этот фильтр можно использовать для отображения элементов, заданных в указанном диапазоне.</span><span class="sxs-lookup"><span data-stu-id="5552d-106">You can use this filter to display items assigned a prediction score within a specified range.</span></span> <span data-ttu-id="5552d-107">Как правило, оценки прогноза от 0 до **0,5** назначены для элементов, которые предсказала модель, не являются релевантными. </span><span class="sxs-lookup"><span data-stu-id="5552d-107">In general, prediction scores between **0** and **.5** are assigned to items that model has predicted are not relevant.</span></span> <span data-ttu-id="5552d-108">Элементы, заданная для оценки прогноза **от 0,5** до **1,0,** являются элементами, которые модель предсказала, являются релевантными.</span><span class="sxs-lookup"><span data-stu-id="5552d-108">Items assigned prediction scores between **.5** and **1.0** are items the model has predicted are relevant.</span></span>

<span data-ttu-id="5552d-109">Вот два способа использования фильтра оценки прогноза:</span><span class="sxs-lookup"><span data-stu-id="5552d-109">Here are two ways you can use the prediction score filter:</span></span>

- <span data-ttu-id="5552d-110">Уделяем приоритетное внимание обзору элементов в наборе обзоров, который предсказала модель.</span><span class="sxs-lookup"><span data-stu-id="5552d-110">Prioritize the review of items in a review set that the model has predicted are relevant.</span></span>

- <span data-ttu-id="5552d-111">Элементы cull из набора обзоров, прогнозируемые моделью, не являются релевантными.</span><span class="sxs-lookup"><span data-stu-id="5552d-111">Cull items from the review set that the model has predicted are not relevant.</span></span> <span data-ttu-id="5552d-112">В качестве альтернативы можно использовать фильтр оценки прогноза, чтобы расставить приоритеты при просмотре не соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="5552d-112">Alternative, you can use the prediction score filter to de-prioritize the review of non-relevant items.</span></span>

## <a name="before-you-apply-a-prediction-score-filter"></a><span data-ttu-id="5552d-113">Перед применением фильтра оценки прогноза</span><span class="sxs-lookup"><span data-stu-id="5552d-113">Before you apply a prediction score filter</span></span>

- <span data-ttu-id="5552d-114">Создайте модель прогностического кодирования, чтобы создать соответствующий фильтр оценки прогноза.</span><span class="sxs-lookup"><span data-stu-id="5552d-114">Create a predictive coding model so that a corresponding prediction score filter is created.</span></span>

- <span data-ttu-id="5552d-115">Фильтр оценки прогноза можно применить после любого из учебных раундов.</span><span class="sxs-lookup"><span data-stu-id="5552d-115">You can apply a prediction score filter after any of the training rounds.</span></span> <span data-ttu-id="5552d-116">Но перед использованием фильтра показателей прогнозирования может потребоваться подождать после выполнения нескольких раундов или до тех пор, пока модель не будет стабильной.</span><span class="sxs-lookup"><span data-stu-id="5552d-116">But you may want to wait after performing several rounds or until the model is stable before using the prediction score filter.</span></span>

## <a name="apply-a-prediction-score-filter"></a><span data-ttu-id="5552d-117">Применение фильтра оценки прогноза</span><span class="sxs-lookup"><span data-stu-id="5552d-117">Apply a prediction score filter</span></span>

1. <span data-ttu-id="5552d-118">В центре Microsoft 365 откройте Advanced eDiscovery, выберите вкладку **Наборы** обзоров и откройте набор обзоров.</span><span class="sxs-lookup"><span data-stu-id="5552d-118">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then open the review set.</span></span>

   ![Щелкните Фильтры, чтобы отобразить страницу вылетов фильтров](..\media\PredictionScoreFilter0.png)   

   <span data-ttu-id="5552d-120">Предварительно загруженные фильтры по умолчанию отображаются в верхней части страницы набора обзоров.</span><span class="sxs-lookup"><span data-stu-id="5552d-120">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="5552d-121">Эти наборы можно оставить **в Любом**.</span><span class="sxs-lookup"><span data-stu-id="5552d-121">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="5552d-122">Щелкните **Фильтры,** чтобы **отобразить страницу вылетов** фильтров.</span><span class="sxs-lookup"><span data-stu-id="5552d-122">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="5552d-123">**Расширь раздел & аналитики,** чтобы отобразить набор фильтров.</span><span class="sxs-lookup"><span data-stu-id="5552d-123">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Фильтр оценки прогнозирования в разделе & прогнозирования](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="5552d-125">Конвенция именования для фильтров оценки прогноза — **оценка прогноза (имя модели).**</span><span class="sxs-lookup"><span data-stu-id="5552d-125">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="5552d-126">Например, имя фильтра оценки прогноза для модели с именем **Model A** — **оценка прогнозирования (Модель A).**</span><span class="sxs-lookup"><span data-stu-id="5552d-126">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="5552d-127">Выберите фильтр оценки прогноза, который необходимо использовать, а затем нажмите кнопку **Готово.**</span><span class="sxs-lookup"><span data-stu-id="5552d-127">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="5552d-128">На странице набора обзоров нажмите кнопку dropdown для фильтра оценки прогноза и введите минимальные и максимальные значения для диапазона показателей прогноза.</span><span class="sxs-lookup"><span data-stu-id="5552d-128">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="5552d-129">Например, на следующем скриншоте показан диапазон показателей прогнозирования **между .5** и **1.0**.</span><span class="sxs-lookup"><span data-stu-id="5552d-129">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Минимальные и максимальные значения для фильтра показателей прогнозирования](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="5552d-131">Щелкните вне фильтра, чтобы автоматически применить фильтр к набору отзывов.</span><span class="sxs-lookup"><span data-stu-id="5552d-131">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="5552d-132">Список документов с показателем прогноза в указанном диапазоне отображается на странице заданного обзора.</span><span class="sxs-lookup"><span data-stu-id="5552d-132">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span> 

  > [!TIP]
  > <span data-ttu-id="5552d-133">Чтобы просмотреть фактическую оценку прогноза, присвоенную документу, можно щелкнуть вкладку **Метаданные** в области чтения.</span><span class="sxs-lookup"><span data-stu-id="5552d-133">To view the actual prediction score assign to a document, you can click the **Metadata** tab in the reading pane.</span></span> <span data-ttu-id="5552d-134">Оценки прогноза для всех моделей в наборе обзоров отображаются в свойстве метаданных **RelevanceScores.**</span><span class="sxs-lookup"><span data-stu-id="5552d-134">The prediction scores for all models in the review set are displayed in the **RelevanceScores** metadata property.</span></span>

## <a name="more-information"></a><span data-ttu-id="5552d-135">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="5552d-135">More information</span></span>

- <span data-ttu-id="5552d-136">Дополнительные сведения об использовании фильтров см. в обзоре ["Запрос и фильтрация контента".](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="5552d-136">For more information about using filters, see [Query and filter content in a review set](review-set-search.md).</span></span>
