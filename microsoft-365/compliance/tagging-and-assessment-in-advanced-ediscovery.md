---
title: Теги и оценка в Advanced eDiscovery
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
description: Просмотрите действия по выполнению обучения оценке, включая теги файлов, а также результаты оценки в Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769194"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="756f2-103">Теги и оценка в модуле Релевантность в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="756f2-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="756f2-104">В этом разделе описывается процедура оценки в модуле Релевантность в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="756f2-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="756f2-105">Выполнение обучения и анализа оценки</span><span class="sxs-lookup"><span data-stu-id="756f2-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="756f2-106">На **вкладке \> "Отслеживание** релевантности" **щелкните "Оценка",** чтобы начать оценку дела.</span><span class="sxs-lookup"><span data-stu-id="756f2-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="756f2-107">Например, в этой процедуре создается примерный набор оценки из 500 файлов и отображается вкладка **Tag,** содержаная панель Tagging, отображаемая содержимое файла и другие параметры тегов.</span><span class="sxs-lookup"><span data-stu-id="756f2-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![Вкладка "Релевантность" > "Добавление тегов" для оценки](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="756f2-109">Просмотрите каждый файл в примере, определите релевантность файла для каждого случая и пометить файл с помощью кнопок Релевантность (R), Not relevant (NR) и Skip в панели **tagging.**</span><span class="sxs-lookup"><span data-stu-id="756f2-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="756f2-110">Для оценки требуется 500 помеченных файлов.</span><span class="sxs-lookup"><span data-stu-id="756f2-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="756f2-111">Если файлы "пропущены", вы получите дополнительные файлы для тегов.</span><span class="sxs-lookup"><span data-stu-id="756f2-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="756f2-112">После пометки всех файлов в примере щелкните **Calculate**.</span><span class="sxs-lookup"><span data-stu-id="756f2-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="756f2-113">Текущая погрешность и богатство оценки вычисляются и отображаются на вкладке **"Отслеживание** релевантности" с расширенными сведениями на одну проблему, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="756f2-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="756f2-114">Дополнительные сведения об этом диалоговом диалоговом диалоге описаны в разделе [Обзор результатов оценки.](#reviewing-assessment-results)</span><span class="sxs-lookup"><span data-stu-id="756f2-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![Оценка на вкладке "Релевантность" > "Отслеживание"](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="756f2-116">По умолчанию рекомендуется приступить к следующему шагу по умолчанию после завершения индикатора прогресса оценки для проблемы, указав, что образец оценки был рассмотрен и помечены достаточно релевантные файлы.</span><span class="sxs-lookup"><span data-stu-id="756f2-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="756f2-117">> противном случае, если вы хотите просмотреть результаты вкладки **Track** и контролировать маржу ошибки и следующий шаг, нажмите **кнопку Изменить** рядом с **Next Step,** выберите Продолжить оценку, а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="756f2-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="756f2-118">Щелкните **Изменение** вправо от контрольного окна **"Оценка",** чтобы просмотреть и указать параметры оценки по одной проблеме.</span><span class="sxs-lookup"><span data-stu-id="756f2-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="756f2-119">Диалоговое **окно уровня** оценки для каждой проблемы отображается, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="756f2-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![Уровень оценки: элемент для оценивания при выполнении задания](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="756f2-121">В диалоговом окантове Уровня Оценки вычисляются и отображаются следующие параметры проблемы: </span><span class="sxs-lookup"><span data-stu-id="756f2-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="756f2-122">**Целевая маржа** ошибок для оценок отзывов. На основе этого значения вычисляется предполагаемое число дополнительных файлов, необходимых для проверки.</span><span class="sxs-lookup"><span data-stu-id="756f2-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="756f2-123">Маржа, используемая для отзыва, превышает 75% и имеет уровень доверия 95%.</span><span class="sxs-lookup"><span data-stu-id="756f2-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="756f2-124">**Дополнительные файлы оценки:** указывает, сколько еще файлов необходимо, если требования текущей разницы ошибок не выполнены.</span><span class="sxs-lookup"><span data-stu-id="756f2-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="756f2-125">Чтобы настроить текущую маржу ошибок и увидеть эффект различных полей ошибок (по одной проблеме):</span><span class="sxs-lookup"><span data-stu-id="756f2-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="756f2-126">В **списке Выберите** проблему выберите проблему.</span><span class="sxs-lookup"><span data-stu-id="756f2-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="756f2-127">В **поле Целевой погрешности для оценок отзыва** введите новое значение.</span><span class="sxs-lookup"><span data-stu-id="756f2-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="756f2-128">Щелкните **значения Update,** чтобы увидеть влияние корректировок.</span><span class="sxs-lookup"><span data-stu-id="756f2-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="756f2-129">Нажмите **кнопку Advanced** в **диалоговом** окте "Уровень оценки", чтобы увидеть следующие дополнительные параметры и сведения:</span><span class="sxs-lookup"><span data-stu-id="756f2-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![Расширенное представление "Уровень оценки: элемент для оценивания при выполнении задания"](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="756f2-131">**Предполагаемое богатство:** Предполагаемое богатство в соответствии с текущими результатами оценки</span><span class="sxs-lookup"><span data-stu-id="756f2-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="756f2-132">**Для предположенного отзыва.** По умолчанию предел целевой погрешности применяется к отзыву свыше 75%.</span><span class="sxs-lookup"><span data-stu-id="756f2-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="756f2-133">Нажмите **кнопку Изменить,** если вы хотите изменить этот параметр и контролировать погрешность на другом диапазоне значений отзыва.</span><span class="sxs-lookup"><span data-stu-id="756f2-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="756f2-134">**Уровень доверия.** По умолчанию рекомендуемая погрешность для уверенности составляет 95%.</span><span class="sxs-lookup"><span data-stu-id="756f2-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="756f2-135">Нажмите **кнопку Изменить,** если вы хотите изменить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="756f2-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="756f2-136">**Ожидаемая погрешность** богатства. Учитывая обновленные значения, это ожидаемая погрешность погрешности, после того как будут рассмотрены все дополнительные файлы оценки.</span><span class="sxs-lookup"><span data-stu-id="756f2-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="756f2-137">**Дополнительные файлы оценки.** Учитывая обновленные значения, количество дополнительных файлов оценки, которые необходимо просмотреть для достижения цели.</span><span class="sxs-lookup"><span data-stu-id="756f2-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="756f2-138">**Общие файлы оценки:** Учитывая обновленные значения, общие файлы оценки, необходимые для проверки.</span><span class="sxs-lookup"><span data-stu-id="756f2-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="756f2-139">**Ожидаемое количество соответствующих** файлов в оценке. Учитывая обновленные значения, ожидаемое количество соответствующих файлов во всей оценке после просмотра всех дополнительных файлов оценки.</span><span class="sxs-lookup"><span data-stu-id="756f2-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="756f2-140">Щелкните **Перерасчет значений,** если параметры изменены.</span><span class="sxs-lookup"><span data-stu-id="756f2-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="756f2-141">Когда вы закончите, если есть одна проблема, нажмите **кнопку ОК,** чтобы сохранить изменения (или далее, когда есть несколько проблем, чтобы просмотреть или изменить, а затем **закончить**). </span><span class="sxs-lookup"><span data-stu-id="756f2-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="756f2-142">При нескольких проблемах после рассмотрения или корректировки всех проблем отображается уровень **оценки:** отображается диалоговое окно сводки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="756f2-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![Уровень оценки: сводка](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="756f2-144">После успешного завершения оценки переходите к следующему этапу обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="756f2-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="756f2-145">Проверка результатов оценки</span><span class="sxs-lookup"><span data-stu-id="756f2-145">Reviewing assessment results</span></span>

<span data-ttu-id="756f2-146">После метки образца оценки результаты оценки вычисляются и отображаются на вкладке "Отслеживание релевантности".</span><span class="sxs-lookup"><span data-stu-id="756f2-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="756f2-147">В расширенном дисплее Track отображаются следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="756f2-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="756f2-148">Текущая маржа ошибок для оценок отзыва</span><span class="sxs-lookup"><span data-stu-id="756f2-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="756f2-149">Предполагаемое богатство</span><span class="sxs-lookup"><span data-stu-id="756f2-149">Estimated richness</span></span>

- <span data-ttu-id="756f2-150">Дополнительные файлы оценки, необходимые (для проверки)</span><span class="sxs-lookup"><span data-stu-id="756f2-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="756f2-151">Текущая погрешность Оценки — это маржа ошибок, рекомендуемая Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="756f2-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="756f2-152">Номер, отображаемый для "Необходимые дополнительные файлы оценки", соответствует этой рекомендации.</span><span class="sxs-lookup"><span data-stu-id="756f2-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="756f2-153">Индикатор хода оценки показывает уровень завершения оценки с учетом текущей разницы ошибок.</span><span class="sxs-lookup"><span data-stu-id="756f2-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="756f2-154">Когда оценка будет проведена, пользователь будет отмечать другой пример оценки.</span><span class="sxs-lookup"><span data-stu-id="756f2-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="756f2-155">Когда индикатор хода оценки показывает, что оценка завершена, это означает, что проверка образца оценки была завершена и были помечены достаточно релевантные файлы.</span><span class="sxs-lookup"><span data-stu-id="756f2-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="756f2-156">На расширенном экране Track показан рекомендуемый следующий шаг, статистика оценки и доступ к подробным результатам.</span><span class="sxs-lookup"><span data-stu-id="756f2-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="756f2-157">При очень низком уровне богатства количество дополнительных файлов оценки, необходимых для достижения минимального количества релевантных файлов для получения полезной статистики, является очень высоким.</span><span class="sxs-lookup"><span data-stu-id="756f2-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="756f2-158">Advanced eDiscovery рекомендуется двигаться дальше к обучению.</span><span class="sxs-lookup"><span data-stu-id="756f2-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="756f2-159">Индикатор хода оценки будет затеняться, и статистики не будет.</span><span class="sxs-lookup"><span data-stu-id="756f2-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="756f2-160">При отсутствии стабилизации на основе статистических данных результаты будут иметь более низкий уровень точности и уверенности.</span><span class="sxs-lookup"><span data-stu-id="756f2-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="756f2-161">Однако эти результаты можно использовать для поиска соответствующих файлов, если вам не нужно знать процент найденных соответствующих файлов.</span><span class="sxs-lookup"><span data-stu-id="756f2-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="756f2-162">Кроме того, этот статус можно использовать для подготовки проблем с низким уровнем насыщенности, где оценки релевантности могут ускорить доступ к файлам, соответствующим определенной проблеме.</span><span class="sxs-lookup"><span data-stu-id="756f2-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="756f2-163">На **вкладке \> Отслеживание** релевантности, расширенном дисплее проблемы, доступны следующие параметры просмотра:</span><span class="sxs-lookup"><span data-stu-id="756f2-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="756f2-164">Рекомендуемый следующий шаг, например Следующий **шаг:** теги можно обойти (в каждом выпуске), нажав кнопку **Изменение** справа, а затем выбрав другой шаг на следующем **шаге**.</span><span class="sxs-lookup"><span data-stu-id="756f2-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="756f2-165">Когда индикатор прогресса оценки не завершен, оценка будет следующим рекомендуемым вариантом, чтобы тегировать больше файлов оценки и повысить точность статистики.</span><span class="sxs-lookup"><span data-stu-id="756f2-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="756f2-166">Вы можете изменить разницу ошибок и оценить ее влияние, щелкнув Кнопку **Изменить** и в диалоговом окантове уровня оценки, изменяя поле целевой ошибки для оценок отзыва **и** щелкнув значения **Update.**</span><span class="sxs-lookup"><span data-stu-id="756f2-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="756f2-167">Кроме того, в этом диалоговом октаге можно просмотреть расширенные параметры, щелкнув **Расширенный**.</span><span class="sxs-lookup"><span data-stu-id="756f2-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="756f2-168">Дополнительные статистические данные об уровне оценки и их влияние можно просмотреть, нажав **представление**.</span><span class="sxs-lookup"><span data-stu-id="756f2-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="756f2-169">В диалоговом окантове "Результаты детализации" статистика доступна в каждой проблеме, когда имеется по крайней мере 500 помеченных файлов оценки и по крайней мере 18 файлов помечены как релевантные для проблемы.</span><span class="sxs-lookup"><span data-stu-id="756f2-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
