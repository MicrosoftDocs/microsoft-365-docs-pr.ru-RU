---
title: Добавление тегов и оценка в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: Просмотрите действия, необходимые для обучения оценке, включая файлы тегов и результаты оценки в Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769194"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="04aab-103">Добавление тегов и оценка в модуле релевантности в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="04aab-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="04aab-104">В этом разделе описывается процедура оценки в модуле релевантности в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="04aab-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="04aab-105">Обучение и анализ оценок</span><span class="sxs-lookup"><span data-stu-id="04aab-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="04aab-106">На **вкладке \> "Отслеживание** релевантности" **щелкните "Оценка",** чтобы начать оценку дела.</span><span class="sxs-lookup"><span data-stu-id="04aab-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="04aab-107">Например, в этой процедуре создается пример набора оценки из  500 файлов и отображается вкладка "Тег", которая содержит панель тегов, отображаемую содержимое файла и другие параметры маркировки.</span><span class="sxs-lookup"><span data-stu-id="04aab-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![Вкладка "Релевантность" > "Добавление тегов" для оценки](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="04aab-109">Просмотрите каждый файл в примере, определите релевантность файла для каждого случая и помечайте файл с помощью  кнопок "Релевантность" (R), "Не релевантно" (NR) и "Пропустить" на панели тегов.</span><span class="sxs-lookup"><span data-stu-id="04aab-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="04aab-110">Для оценки требуется 500 файлов с тегами.</span><span class="sxs-lookup"><span data-stu-id="04aab-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="04aab-111">Если файлы "пропущены", вы получите дополнительные файлы для тегов.</span><span class="sxs-lookup"><span data-stu-id="04aab-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="04aab-112">После пометки всех файлов в примере нажмите кнопку **"Вычислить".**</span><span class="sxs-lookup"><span data-stu-id="04aab-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="04aab-113">Текущее поле ошибки и насыщенность оценки вычисляются и отображаются на вкладке **"Отслеживание** релевантности" с расширенными сведениями для каждого вопроса, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="04aab-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="04aab-114">Дополнительные сведения об этом диалоговом оке описаны в разделе ["Оценка результатов](#reviewing-assessment-results) оценки".</span><span class="sxs-lookup"><span data-stu-id="04aab-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![Оценка на вкладке "Релевантность" > "Отслеживание"](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="04aab-116">По умолчанию рекомендуется перейти к следующему шагу по умолчанию после завершения индикатора хода выполнения оценки для проблемы, указывающее, что образец оценки был проанализироваен и помечены достаточные релевантные файлы.</span><span class="sxs-lookup"><span data-stu-id="04aab-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="04aab-117">> противном случае, если вы  хотите просмотреть результаты вкладки "Отслеживание"  и контролировать поле ошибки и следующий шаг, нажмите кнопку "Изменить рядом с следующим шагом", выберите "Продолжить оценку" **и** нажмите кнопку "ОК". </span><span class="sxs-lookup"><span data-stu-id="04aab-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="04aab-118">Щелкните **"Изменить"**  справа от окна оценки, чтобы просмотреть и указать параметры оценки для каждого вопроса.</span><span class="sxs-lookup"><span data-stu-id="04aab-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="04aab-119">Отображается **диалоговое окно** уровня оценки для каждой проблемы, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="04aab-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![Уровень оценки: элемент для оценивания при выполнении задания](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="04aab-121">Следующие параметры для проблемы вычисляются и отображаются в диалоговом **оке уровня** оценки:</span><span class="sxs-lookup"><span data-stu-id="04aab-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="04aab-122">**Целевое поле ошибки для** оценки отзывов: на основе этого значения вычисляется предполагаемое количество дополнительных файлов, необходимых для проверки.</span><span class="sxs-lookup"><span data-stu-id="04aab-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="04aab-123">Поле, используемая для отзыва, превышает 75 % и имеет уровень достоверности 95 %.</span><span class="sxs-lookup"><span data-stu-id="04aab-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="04aab-124">**Необходимы дополнительные файлы** оценки: указывает, сколько еще файлов необходимо, если текущие требования к полям ошибок не выполнены.</span><span class="sxs-lookup"><span data-stu-id="04aab-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="04aab-125">Чтобы изменить текущее поле ошибки и увидеть влияние разных полей ошибок (на проблему):</span><span class="sxs-lookup"><span data-stu-id="04aab-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="04aab-126">В **списке "Выбор проблем"** выберите проблему.</span><span class="sxs-lookup"><span data-stu-id="04aab-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="04aab-127">В **поле целевой ошибки для оценок отзыва** введите новое значение.</span><span class="sxs-lookup"><span data-stu-id="04aab-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="04aab-128">Щелкните **"Update values" (Обновить),** чтобы увидеть влияние изменений.</span><span class="sxs-lookup"><span data-stu-id="04aab-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="04aab-129">Щелкните **"Дополнительно"** в диалоговом окте "Уровень оценки", чтобы увидеть следующие дополнительные параметры и сведения: </span><span class="sxs-lookup"><span data-stu-id="04aab-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![Расширенное представление "Уровень оценки: элемент для оценивания при выполнении задания"](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="04aab-131">**Примерная насыщенность:** предполагаемый объем в соответствии с текущими результатами оценки</span><span class="sxs-lookup"><span data-stu-id="04aab-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="04aab-132">**Для предполагается, что** отзыв: по умолчанию целевое поле ошибки применяется к отзыву выше 75 %.</span><span class="sxs-lookup"><span data-stu-id="04aab-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="04aab-133">Нажмите **кнопку** "Изменить", чтобы изменить этот параметр и управлять полем ошибки для другого диапазона значений отзыва.</span><span class="sxs-lookup"><span data-stu-id="04aab-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="04aab-134">**Уровень уверенности:** по умолчанию рекомендуемое поле ошибки для уверенности составляет 95 %.</span><span class="sxs-lookup"><span data-stu-id="04aab-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="04aab-135">Если **вы** хотите изменить этот параметр, нажмите кнопку "Изменить".</span><span class="sxs-lookup"><span data-stu-id="04aab-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="04aab-136">**Ожидаемое поле** ошибки "Насыщенность": с учетом обновленных значений это ожидаемое поле ошибки разности после проверки всех дополнительных файлов оценки.</span><span class="sxs-lookup"><span data-stu-id="04aab-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="04aab-137">**Необходимы дополнительные файлы** оценки: с учетом обновленных значений, количество дополнительных файлов оценки, которые необходимо просмотреть для достижения целевого значения.</span><span class="sxs-lookup"><span data-stu-id="04aab-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="04aab-138">**Общее количество необходимых файлов** оценки: с учетом обновленных значений общее количество файлов оценки, необходимых для проверки.</span><span class="sxs-lookup"><span data-stu-id="04aab-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="04aab-139">**Ожидаемое количество соответствующих** файлов в оценке: с учетом обновленных значений ожидаемое количество соответствующих файлов во всей оценке после проверки всех дополнительных файлов оценки.</span><span class="sxs-lookup"><span data-stu-id="04aab-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="04aab-140">Щелкните **"Пересчитать значения",** если параметры изменены.</span><span class="sxs-lookup"><span data-stu-id="04aab-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="04aab-141">Когда все будет готово, если есть одна проблема, нажмите  кнопку "ОК", чтобы сохранить изменения (или "Далее", если есть несколько проблем, которые необходимо просмотреть или изменить, а затем **готово).** </span><span class="sxs-lookup"><span data-stu-id="04aab-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="04aab-142">Если имеется несколько проблем, после проверки или корректировки  всех проблем отображается диалоговое окно сводки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="04aab-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![Уровень оценки: сводка](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="04aab-144">После успешного завершения оценки переходите к следующему этапу обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="04aab-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="04aab-145">Просмотр результатов оценки</span><span class="sxs-lookup"><span data-stu-id="04aab-145">Reviewing assessment results</span></span>

<span data-ttu-id="04aab-146">После маркировки примера оценки результаты оценки вычисляются и отображаются на вкладке "Отслеживание релевантности".</span><span class="sxs-lookup"><span data-stu-id="04aab-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="04aab-147">На экране расширенной дорожки отображаются следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="04aab-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="04aab-148">Текущая поле ошибки оценки при отзыве</span><span class="sxs-lookup"><span data-stu-id="04aab-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="04aab-149">Примерная насыщенность</span><span class="sxs-lookup"><span data-stu-id="04aab-149">Estimated richness</span></span>

- <span data-ttu-id="04aab-150">Необходимы дополнительные файлы оценки (для проверки)</span><span class="sxs-lookup"><span data-stu-id="04aab-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="04aab-151">Поле текущей ошибки оценки — это поле ошибки, рекомендованные Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="04aab-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="04aab-152">Число, отображаемого для "Необходимы дополнительных файлов оценки", соответствует этой рекомендации.</span><span class="sxs-lookup"><span data-stu-id="04aab-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="04aab-153">Индикатор хода выполнения оценки показывает уровень завершения оценки с учетом текущего поля ошибки.</span><span class="sxs-lookup"><span data-stu-id="04aab-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="04aab-154">Когда оценка будет проведена, пользователь помечет еще один пример оценки.</span><span class="sxs-lookup"><span data-stu-id="04aab-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="04aab-155">Когда индикатор хода выполнения оценки показывает, что оценка завершена, это означает, что проверка примера оценки завершена, а соответствующие файлы были помечены.</span><span class="sxs-lookup"><span data-stu-id="04aab-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="04aab-156">На развернутом экране "Track" показаны рекомендуемый следующий шаг, статистика оценки и доступ к подробным результатам.</span><span class="sxs-lookup"><span data-stu-id="04aab-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="04aab-157">Если уровень насыщенности очень низкий, количество дополнительных файлов оценки, необходимых для достижения минимального количества релевантных файлов для получения полезной статистики, очень высок.</span><span class="sxs-lookup"><span data-stu-id="04aab-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="04aab-158">Advanced eDiscovery затем рекомендует двигаться к обучению.</span><span class="sxs-lookup"><span data-stu-id="04aab-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="04aab-159">Индикатор хода выполнения оценки будет затенен, и статистика не будет доступна.</span><span class="sxs-lookup"><span data-stu-id="04aab-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="04aab-160">В отсутствие статистически основанной на статистике стабилизации будут результаты с более низким уровнем точности и достоверности.</span><span class="sxs-lookup"><span data-stu-id="04aab-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="04aab-161">Однако эти результаты можно использовать для поиска соответствующих файлов, если вам не нужно знать процент найденных релевантных файлов.</span><span class="sxs-lookup"><span data-stu-id="04aab-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="04aab-162">Аналогичным образом это состояние можно использовать для обучения проблем с низкой насыщенностью, где результаты релевантности могут ускорить доступ к файлам, относячим к определенной проблеме.</span><span class="sxs-lookup"><span data-stu-id="04aab-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="04aab-163">На **вкладке \> "Отслеживание** релевантности" отображаются проблемы, доступные следующие параметры просмотра:</span><span class="sxs-lookup"><span data-stu-id="04aab-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="04aab-164">Рекомендуемый следующий шаг, например следующий **шаг:** добавление тегов можно обойти (для каждого вопроса), нажав кнопку **"Изменить"** справа, а затем выбрав другой шаг на следующем **шаге.**</span><span class="sxs-lookup"><span data-stu-id="04aab-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="04aab-165">Когда индикатор хода выполнения оценки не будет завершен, рекомендуется использовать оценку, чтобы пометить дополнительные файлы оценки и повысить точность статистики.</span><span class="sxs-lookup"><span data-stu-id="04aab-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="04aab-166">Вы можете изменить поле ошибки и оценить ее влияние, нажав кнопку  **"Изменить"** и в диалоговом окнах уровня оценки, изменив поле целевой ошибки для оценок отзыва и щелкнув "Обновить **значения".**</span><span class="sxs-lookup"><span data-stu-id="04aab-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="04aab-167">Кроме того, в этом диалоговом оке можно просмотреть дополнительные параметры, нажав кнопку **"Дополнительные".**</span><span class="sxs-lookup"><span data-stu-id="04aab-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="04aab-168">Вы можете просмотреть дополнительную статистику уровня оценки и ее влияние, нажав кнопку **"Просмотреть".**</span><span class="sxs-lookup"><span data-stu-id="04aab-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="04aab-169">В диалоговом окте "Подробные результаты" статистика доступна по каждой проблеме, если имеется не менее 500 помеченных файлов оценки, а не менее 18 файлов помечены как релевантные для проблемы.</span><span class="sxs-lookup"><span data-stu-id="04aab-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
