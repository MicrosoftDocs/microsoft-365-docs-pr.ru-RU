---
title: Прогностическое кодирование в Advanced eDiscovery - быстрый запуск
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
description: Узнайте, как начать работу с модулем прогностического кодирования в Advanced eDiscovery. В этой статье вы проходите сквозной процесс использования прогностического кодирования для определения контента в наборе отзывов, наиболее релевантном для вашего исследования.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822625"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a><span data-ttu-id="c4d79-104">Быстрый запуск: прогностическое кодирование в Advanced eDiscovery (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="c4d79-104">Quick start: Predictive coding in Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="c4d79-105">В этой статье представлен быстрый запуск для использования прогностического кодирования в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c4d79-105">This article presents a quick start for using predictive coding in Advanced eDiscovery.</span></span> <span data-ttu-id="c4d79-106">Модуль прогностического кодирования в Advanced eDiscovery использует интеллектуальные возможности машинного обучения в Advanced eDiscovery, чтобы уменьшить количество просмотров контента.</span><span class="sxs-lookup"><span data-stu-id="c4d79-106">The predictive coding module in Advanced eDiscovery uses the intelligent, machine learning capabilities in Advanced eDiscovery to help you reduce the amount of content to review.</span></span> <span data-ttu-id="c4d79-107">Прогностическое кодирование позволяет сократить и отоиметь большие объемы контента для дела до соответствующего набора элементов, которые можно расставить приоритеты для проверки.</span><span class="sxs-lookup"><span data-stu-id="c4d79-107">Predictive coding helps you reduce and cull large volumes of case content to a relevant set of items that you can prioritize for review.</span></span> <span data-ttu-id="c4d79-108">Это достигается путем создания и подготовки собственных моделей прогностического кодирования, которые помогут вам расставить приоритеты при просмотре наиболее релевантных элементов в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="c4d79-108">This is accomplished by creating and training your own predictive coding models that help you prioritize the review of the most relevant items in a review set.</span></span>

<span data-ttu-id="c4d79-109">Ниже представлен краткий обзор процесса прогностического кодирования:</span><span class="sxs-lookup"><span data-stu-id="c4d79-109">Here's an a quick overview of the predictive coding process:</span></span>

![Процесс быстрого запуска для кодирования прогнозов](..\media\PredictiveCodingQuickStartProcess.png)

<span data-ttu-id="c4d79-111">Чтобы начать работу, создайте модель, наметив не более 50 элементов как релевантные или не соответствующие.</span><span class="sxs-lookup"><span data-stu-id="c4d79-111">To get started, you create a model, label as few as 50 items as relevant or not relevant.</span></span> <span data-ttu-id="c4d79-112">Затем система использует это обучение для применения баллов прогнозирования к каждому элементу в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="c4d79-112">The system then uses this training to apply prediction scores to every item in the review set.</span></span> <span data-ttu-id="c4d79-113">Это позволяет фильтровать элементы на основе оценки прогноза, что позволяет сначала просмотреть наиболее релевантные (или не соответствующие) элементы.</span><span class="sxs-lookup"><span data-stu-id="c4d79-113">This lets you filter items based on the prediction score, which  allows you to review the most relevant (or non-relevant) items first.</span></span> <span data-ttu-id="c4d79-114">Если вы хотите обучить модели с более высокими уровнями аккуратий и отзывов, вы можете продолжить маркировку элементов в последующих учебных раундах, пока модель не стабилизируется.</span><span class="sxs-lookup"><span data-stu-id="c4d79-114">If you want to train models with higher accuracies and recall rates, you can continue labeling items in subsequent training rounds until the model stabilizes.</span></span> <span data-ttu-id="c4d79-115">После стабилизации модели можно применить конечный фильтр прогнозирования, чтобы приоритизировать элементы для просмотра.</span><span class="sxs-lookup"><span data-stu-id="c4d79-115">Once the model is stabilized, you can apply the final prediction filter to prioritize items to review.</span></span>

<span data-ttu-id="c4d79-116">Подробный обзор прогностического кодирования см. в описании [прогностического кодирования в Advanced eDiscovery.](predictive-coding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c4d79-116">For a detailed overview of predictive coding, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span></span>

## <a name="step-1-create-a-new-predictive-coding-model"></a><span data-ttu-id="c4d79-117">Шаг 1. Создание новой модели прогностического кодирования</span><span class="sxs-lookup"><span data-stu-id="c4d79-117">Step 1: Create a new predictive coding model</span></span>

<span data-ttu-id="c4d79-118">Первым шагом является создание новой модели прогностического кодирования в наборе обзоров</span><span class="sxs-lookup"><span data-stu-id="c4d79-118">The first step is to create a new predictive coding model in the review set</span></span>

1. <span data-ttu-id="c4d79-119">В центре Microsoft 365, откройте Advanced eDiscovery, а затем выберите вкладку **Наборы отзывов.**</span><span class="sxs-lookup"><span data-stu-id="c4d79-119">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="c4d79-120">Откройте набор обзоров и нажмите **кнопку Analytics**  >  **Manage прогностическое кодирование (предварительный просмотр).**</span><span class="sxs-lookup"><span data-stu-id="c4d79-120">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

   ![Щелкните меню Анализ выпадающих данных в наборе обзоров, чтобы перейти на страницу прогностического кодирования](..\media\ManagePredictiveCoding.png)

3. <span data-ttu-id="c4d79-122">На странице **Прогностические модели кодирования (предварительный просмотр)** нажмите **кнопку Новая модель**.</span><span class="sxs-lookup"><span data-stu-id="c4d79-122">On the **Predictive coding models (preview)** page, click **New model**.</span></span>

4. <span data-ttu-id="c4d79-123">На странице вылет введите имя модели и необязательное описание.</span><span class="sxs-lookup"><span data-stu-id="c4d79-123">On the flyout page, type a name for the model and an optional description.</span></span>

5. <span data-ttu-id="c4d79-124">Нажмите **кнопку Сохранить,** чтобы создать модель.</span><span class="sxs-lookup"><span data-stu-id="c4d79-124">Click **Save** to create the model.</span></span>

   <span data-ttu-id="c4d79-125">Подготовка модели для системы займет несколько минут.</span><span class="sxs-lookup"><span data-stu-id="c4d79-125">It will take a couple minutes for the system to prepare your model.</span></span> <span data-ttu-id="c4d79-126">После его готовности можно выполнить первый раунд обучения.</span><span class="sxs-lookup"><span data-stu-id="c4d79-126">After it's ready, you can perform the first round of training.</span></span>

<span data-ttu-id="c4d79-127">Дополнительные инструкции см. в [примере Create a predictive coding model.](predictive-coding-create-model.md)</span><span class="sxs-lookup"><span data-stu-id="c4d79-127">For more detailed instructions, see [Create a predictive coding model](predictive-coding-create-model.md).</span></span>

## <a name="step-2-perform-the-first-training-round"></a><span data-ttu-id="c4d79-128">Шаг 2. Выполнение первого учебного раунда</span><span class="sxs-lookup"><span data-stu-id="c4d79-128">Step 2: Perform the first training round</span></span>

<span data-ttu-id="c4d79-129">После создания модели следующий шаг — завершить первый учебный раунд, наметив элементы как релевантные или не соответствующие.</span><span class="sxs-lookup"><span data-stu-id="c4d79-129">After you create the model, the next step is to complete the first training round by labeling items as relevant or not relevant.</span></span>

1. <span data-ttu-id="c4d79-130">Откройте набор обзоров и нажмите **кнопку Analytics**  >  **Manage прогностическое кодирование (предварительный просмотр).**</span><span class="sxs-lookup"><span data-stu-id="c4d79-130">Open the review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

2. <span data-ttu-id="c4d79-131">На странице **Прогностические модели кодирования (предварительный просмотр)** выберите модель, которую необходимо обучить.</span><span class="sxs-lookup"><span data-stu-id="c4d79-131">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

3. <span data-ttu-id="c4d79-132">На **вкладке Обзор** в **1 раунде** нажмите **кнопку Начните следующий учебный раунд.**</span><span class="sxs-lookup"><span data-stu-id="c4d79-132">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="c4d79-133">Вкладка **Training** отображается и содержит 50 элементов для метки.</span><span class="sxs-lookup"><span data-stu-id="c4d79-133">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

4. <span data-ttu-id="c4d79-134">Просмотрите каждый документ,  а затем выберите **соответствующую** или не соответствующую кнопку в нижней части области чтения, чтобы пометить его.</span><span class="sxs-lookup"><span data-stu-id="c4d79-134">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![Пометить каждый документ как релевантный или не соответствующий](..\media\TrainModel1.png)

5. <span data-ttu-id="c4d79-136">После метки всех 50 элементов нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="c4d79-136">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="c4d79-137">На то, чтобы система "узнала" о маркировке и обновила модель, уйма займет несколько минут.</span><span class="sxs-lookup"><span data-stu-id="c4d79-137">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="c4d79-138">По завершению этого процесса  для модели на странице Предиктивное кодирование **(предварительный просмотр)** отображается состояние Ready.</span><span class="sxs-lookup"><span data-stu-id="c4d79-138">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

<span data-ttu-id="c4d79-139">Дополнительные инструкции см. в [примере Train a predictive coding model.](predictive-coding-train-model.md)</span><span class="sxs-lookup"><span data-stu-id="c4d79-139">For more detailed instructions, see [Train a predictive coding model](predictive-coding-train-model.md).</span></span>

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a><span data-ttu-id="c4d79-140">Шаг 3. Применение фильтра оценки прогноза к пунктам в наборе обзоров</span><span class="sxs-lookup"><span data-stu-id="c4d79-140">Step 3: Apply the prediction score filter to items in review set</span></span>

<span data-ttu-id="c4d79-141">После выполнения в аренде одного учебного раунда можно применить фильтр оценки прогноза к пунктам в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="c4d79-141">After you perform at lease one training round, you can apply the prediction score filter to items in review set.</span></span> <span data-ttu-id="c4d79-142">Это позволяет просмотреть элементы, которые модель предсказала как релевантные или не соответствующие.</span><span class="sxs-lookup"><span data-stu-id="c4d79-142">This lets you review the items the model has predicted as relevant or not relevant.</span></span>   

1. <span data-ttu-id="c4d79-143">Откройте набор отзывов.</span><span class="sxs-lookup"><span data-stu-id="c4d79-143">Open the review set.</span></span>

   ![Щелкните Фильтры, чтобы отобразить страницу вылетов фильтров](..\media\PredictionScoreFilter0.png)

   <span data-ttu-id="c4d79-145">Предварительно загруженные фильтры по умолчанию отображаются в верхней части страницы набора обзоров.</span><span class="sxs-lookup"><span data-stu-id="c4d79-145">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="c4d79-146">Эти наборы можно оставить **в Любом**.</span><span class="sxs-lookup"><span data-stu-id="c4d79-146">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="c4d79-147">Щелкните **Фильтры,** чтобы **отобразить страницу вылетов** фильтров.</span><span class="sxs-lookup"><span data-stu-id="c4d79-147">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="c4d79-148">**Расширь раздел & аналитики,** чтобы отобразить набор фильтров.</span><span class="sxs-lookup"><span data-stu-id="c4d79-148">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Фильтр оценки прогнозирования в разделе & прогнозирования](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="c4d79-150">Конвенция именования для фильтров оценки прогноза — **оценка прогноза (имя модели).**</span><span class="sxs-lookup"><span data-stu-id="c4d79-150">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="c4d79-151">Например, имя фильтра оценки прогноза для модели с именем **Model A** — **оценка прогнозирования (Модель A).**</span><span class="sxs-lookup"><span data-stu-id="c4d79-151">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="c4d79-152">Выберите фильтр оценки прогноза, который необходимо использовать, а затем нажмите кнопку **Готово.**</span><span class="sxs-lookup"><span data-stu-id="c4d79-152">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="c4d79-153">На странице набора обзоров нажмите кнопку dropdown для фильтра оценки прогноза и введите минимальные и максимальные значения для диапазона показателей прогноза.</span><span class="sxs-lookup"><span data-stu-id="c4d79-153">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="c4d79-154">Например, на следующем скриншоте показан диапазон показателей прогнозирования **между .5** и **1.0**.</span><span class="sxs-lookup"><span data-stu-id="c4d79-154">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Минимальные и максимальные значения для фильтра показателей прогнозирования](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="c4d79-156">Щелкните вне фильтра, чтобы автоматически применить фильтр к набору отзывов.</span><span class="sxs-lookup"><span data-stu-id="c4d79-156">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="c4d79-157">Список документов с показателем прогноза в указанном диапазоне отображается на странице заданного обзора.</span><span class="sxs-lookup"><span data-stu-id="c4d79-157">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span>

<span data-ttu-id="c4d79-158">Дополнительные инструкции см. в [описании Применения фильтра прогнозирования к набору обзоров.](predictive-coding-apply-prediction-filter.md)</span><span class="sxs-lookup"><span data-stu-id="c4d79-158">For more detailed instructions, see [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>

## <a name="step-4-perform-more-training-rounds"></a><span data-ttu-id="c4d79-159">Шаг 4. Выполните дополнительные учебные раунды</span><span class="sxs-lookup"><span data-stu-id="c4d79-159">Step 4: Perform more training rounds</span></span>

<span data-ttu-id="c4d79-160">Скорее всего, вам придется выполнить больше учебных раундов, чтобы обучить модуль, чтобы лучше прогнозировать релевантные и не соответствующие элементы в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="c4d79-160">More than likely, you'll have to perform more training rounds to train the module to better predict relevant and non-relevant items in the review set.</span></span> <span data-ttu-id="c4d79-161">В общем, вы будете обучать модель достаточно времени, пока она не стабилизируется достаточно, чтобы соответствовать вашим требованиям.</span><span class="sxs-lookup"><span data-stu-id="c4d79-161">In general, you'll train the model enough times until it stabilizes enough to meet your requirements.</span></span>

<span data-ttu-id="c4d79-162">Дополнительные сведения см. в таблице [Выполнение дополнительных учебных раундов](predictive-coding-train-model.md#perform-additional-training-rounds)</span><span class="sxs-lookup"><span data-stu-id="c4d79-162">For more information, see [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)</span></span>

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a><span data-ttu-id="c4d79-163">Шаг 5. Применение фильтра конечных показателей прогноза для приоритета обзора</span><span class="sxs-lookup"><span data-stu-id="c4d79-163">Step 5: Apply the final prediction score filter to prioritize review</span></span>

<span data-ttu-id="c4d79-164">Повторите инструкции в шаге 3, чтобы применить итоговый показатель прогноза к набору обзоров, чтобы приоритизировать обзор релевантных и не соответствующих элементов после завершения всех учебных раундов и стабилизации модели.</span><span class="sxs-lookup"><span data-stu-id="c4d79-164">Repeat the instructions in Step 3 to apply the final prediction score to the review set to prioritize the review of relevant and non-relevant items after you complete all the training rounds and stabilize the model.</span></span>
