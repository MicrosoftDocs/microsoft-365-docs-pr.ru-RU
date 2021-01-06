---
title: Добавление тегов и оценка в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
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
ms.openlocfilehash: 9f826c836337ecf7a8479e7d824ff8ad9e737e97
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760379"
---
# <a name="tagging-and-assessment-in-advanced-ediscovery-classic"></a><span data-ttu-id="111ce-103">Добавление тегов и оценка в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="111ce-103">Tagging and Assessment in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="111ce-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="111ce-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="111ce-106">В этом разделе описывается процедура модуля оценки релевантности Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="111ce-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="111ce-107">Обучение и анализ оценок</span><span class="sxs-lookup"><span data-stu-id="111ce-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="111ce-108">На **вкладке \> "Отслеживание** релевантности" **щелкните "Оценка",** чтобы начать оценку дела.</span><span class="sxs-lookup"><span data-stu-id="111ce-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="111ce-109">Например, в этой процедуре создается пример набора оценки из  500 файлов и отображается вкладка "Тег", которая содержит панель тегов, отображаемую содержимое файла и другие параметры маркировки.</span><span class="sxs-lookup"><span data-stu-id="111ce-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![Вкладка "Релевантность" > "Добавление тегов" для оценки](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="111ce-111">Просмотрите каждый файл в примере, определите релевантность файла для каждого случая и помечайте файл с помощью  кнопок "Релевантность" (R), "Не релевантно" (NR) и "Пропустить" на панели тегов.</span><span class="sxs-lookup"><span data-stu-id="111ce-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="111ce-112">Для оценки требуется 500 файлов с тегами.</span><span class="sxs-lookup"><span data-stu-id="111ce-112">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="111ce-113">Если файлы "пропущены", вы получите дополнительные файлы для тегов.</span><span class="sxs-lookup"><span data-stu-id="111ce-113">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="111ce-114">После пометки всех файлов в примере нажмите кнопку **"Вычислить".**</span><span class="sxs-lookup"><span data-stu-id="111ce-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="111ce-115">Текущее поле ошибки и насыщенность оценки вычисляются и отображаются на вкладке **"Отслеживание** релевантности" с расширенными сведениями для каждого вопроса, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="111ce-115">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="111ce-116">Дополнительные сведения об этом диалоговом окте описаны в разделе "Оценка результатов оценки".</span><span class="sxs-lookup"><span data-stu-id="111ce-116">More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![Оценка на вкладке "Релевантность" > "Отслеживание"](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="111ce-118">По умолчанию рекомендуется перейти к следующему шагу по умолчанию после завершения индикатора хода выполнения оценки для проблемы, указывающее, что образец оценки был проанализироваен и помечены достаточные релевантные файлы.</span><span class="sxs-lookup"><span data-stu-id="111ce-118">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="111ce-119">> противном случае, если вы  хотите просмотреть результаты вкладки "Отслеживание"  и контролировать поле ошибки и следующий шаг, нажмите кнопку "Изменить рядом с следующим шагом", выберите "Продолжить оценку" **и** нажмите кнопку "ОК". </span><span class="sxs-lookup"><span data-stu-id="111ce-119">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="111ce-120">Щелкните **"Изменить"**  справа от окна оценки, чтобы просмотреть и указать параметры оценки для каждого вопроса.</span><span class="sxs-lookup"><span data-stu-id="111ce-120">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="111ce-121">Отображается **диалоговое окно** уровня оценки для каждой проблемы, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="111ce-121">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![Уровень оценки: элемент для оценивания при выполнении задания](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="111ce-123">Следующие параметры для проблемы вычисляются и отображаются в диалоговом оке **уровня** оценки:</span><span class="sxs-lookup"><span data-stu-id="111ce-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="111ce-124">**Целевое поле ошибки для** оценки отзывов: на основе этого значения вычисляется предполагаемое количество дополнительных файлов, необходимых для проверки.</span><span class="sxs-lookup"><span data-stu-id="111ce-124">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="111ce-125">Поле, используемая для отзыва, превышает 75 % и имеет уровень достоверности 95 %.</span><span class="sxs-lookup"><span data-stu-id="111ce-125">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="111ce-126">**Необходимы дополнительные файлы** оценки: указывает, сколько еще файлов необходимо, если текущие требования к полям ошибок не выполнены.</span><span class="sxs-lookup"><span data-stu-id="111ce-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="111ce-127">Чтобы изменить текущее поле ошибки и увидеть влияние разных полей ошибок (на проблему):</span><span class="sxs-lookup"><span data-stu-id="111ce-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="111ce-128">В **списке "Выбор проблем"** выберите проблему.</span><span class="sxs-lookup"><span data-stu-id="111ce-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="111ce-129">В **поле целевой ошибки для оценок отзыва** введите новое значение.</span><span class="sxs-lookup"><span data-stu-id="111ce-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="111ce-130">Щелкните **"Update values" (Обновить),** чтобы увидеть влияние изменений.</span><span class="sxs-lookup"><span data-stu-id="111ce-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="111ce-131">Щелкните **"Дополнительно"** **в** диалоговом окте "Уровень оценки", чтобы увидеть следующие дополнительные параметры и сведения:</span><span class="sxs-lookup"><span data-stu-id="111ce-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![Расширенное представление "Уровень оценки: элемент для оценивания при выполнении задания"](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="111ce-133">**Примерная насыщенность:** предполагаемый объем в соответствии с текущими результатами оценки</span><span class="sxs-lookup"><span data-stu-id="111ce-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="111ce-134">**Для предполагается, что** отзыв: по умолчанию целевое поле ошибки применяется к отзыву выше 75 %.</span><span class="sxs-lookup"><span data-stu-id="111ce-134">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="111ce-135">Нажмите **кнопку** "Изменить", чтобы изменить этот параметр и управлять полем ошибки для другого диапазона значений отзыва.</span><span class="sxs-lookup"><span data-stu-id="111ce-135">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="111ce-136">**Уровень уверенности:** по умолчанию рекомендуемое поле ошибки для уверенности составляет 95 %.</span><span class="sxs-lookup"><span data-stu-id="111ce-136">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="111ce-137">Если **вы** хотите изменить этот параметр, нажмите кнопку "Изменить".</span><span class="sxs-lookup"><span data-stu-id="111ce-137">Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="111ce-138">**Ожидаемое поле** ошибки "Насыщенность": с учетом обновленных значений это ожидаемая погрешность этого значения после просмотра всех дополнительных файлов оценки.</span><span class="sxs-lookup"><span data-stu-id="111ce-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="111ce-139">**Необходимы дополнительные файлы** оценки: с учетом обновленных значений количество дополнительных файлов оценки, которые необходимо просмотреть для достижения целевого значения.</span><span class="sxs-lookup"><span data-stu-id="111ce-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="111ce-140">**Общее количество необходимых файлов** оценки: с учетом обновленных значений общее количество файлов оценки, необходимых для проверки.</span><span class="sxs-lookup"><span data-stu-id="111ce-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="111ce-141">**Ожидаемое количество соответствующих** файлов в оценке: с учетом обновленных значений ожидаемое количество соответствующих файлов во всей оценке после проверки всех дополнительных файлов оценки.</span><span class="sxs-lookup"><span data-stu-id="111ce-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="111ce-142">Щелкните **"Пересчитать значения",** если параметры изменены.</span><span class="sxs-lookup"><span data-stu-id="111ce-142">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="111ce-143">Когда все будет готово, если есть одна проблема, нажмите  кнопку "ОК", чтобы сохранить изменения (или "Далее" при нескольких проблемах, которые необходимо просмотреть или изменить, а затем **— "Готово").** </span><span class="sxs-lookup"><span data-stu-id="111ce-143">When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="111ce-144">Если имеется несколько проблем, после проверки или корректировки  всех проблем отображается диалоговое окно сводки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="111ce-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Уровень оценки: сводка](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="111ce-146">После успешного завершения оценки переходите к следующему этапу обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="111ce-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="111ce-147">Просмотр результатов оценки</span><span class="sxs-lookup"><span data-stu-id="111ce-147">Reviewing assessment results</span></span>

<span data-ttu-id="111ce-148">После маркировки примера оценки результаты оценки вычисляются и отображаются на вкладке "Отслеживание релевантности".</span><span class="sxs-lookup"><span data-stu-id="111ce-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="111ce-149">На экране расширенной дорожки отображаются следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="111ce-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="111ce-150">Текущая поле ошибки оценки при отзыве</span><span class="sxs-lookup"><span data-stu-id="111ce-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="111ce-151">Примерная насыщенность</span><span class="sxs-lookup"><span data-stu-id="111ce-151">Estimated richness</span></span>
    
- <span data-ttu-id="111ce-152">Необходимы дополнительные файлы оценки (для проверки)</span><span class="sxs-lookup"><span data-stu-id="111ce-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="111ce-153">Поле текущей ошибки оценки — это поле ошибки, рекомендованные Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="111ce-153">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="111ce-154">Число, отображаемого для "Необходимы дополнительных файлов оценки", соответствует этой рекомендации.</span><span class="sxs-lookup"><span data-stu-id="111ce-154">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="111ce-155">Индикатор хода выполнения оценки показывает уровень завершения оценки с учетом текущего поля ошибки.</span><span class="sxs-lookup"><span data-stu-id="111ce-155">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="111ce-156">Когда оценка будет проведена, пользователь помечет еще один пример оценки.</span><span class="sxs-lookup"><span data-stu-id="111ce-156">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="111ce-157">Когда индикатор хода оценки показывает, что оценка завершена, это означает, что образец оценки был завершен и помечены достаточно релевантные файлы.</span><span class="sxs-lookup"><span data-stu-id="111ce-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="111ce-158">На развернутом экране "Track" показаны рекомендуемый следующий шаг, статистика оценки и доступ к подробным результатам.</span><span class="sxs-lookup"><span data-stu-id="111ce-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="111ce-159">Если уровень насыщенности очень низкий, количество дополнительных файлов оценки, необходимых для достижения минимального количества релевантных файлов для получения полезной статистики, очень высок.</span><span class="sxs-lookup"><span data-stu-id="111ce-159">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="111ce-160">Advanced eDiscovery затем рекомендует двигаться к обучению.</span><span class="sxs-lookup"><span data-stu-id="111ce-160">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="111ce-161">Индикатор хода выполнения оценки будет затенен, и статистика не будет доступна.</span><span class="sxs-lookup"><span data-stu-id="111ce-161">The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="111ce-162">В отсутствие статистически основанной на статистике стабилизации будут результаты с более низким уровнем точности и достоверности.</span><span class="sxs-lookup"><span data-stu-id="111ce-162">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="111ce-163">Однако эти результаты можно использовать для поиска соответствующих файлов, если вам не нужно знать процент найденных релевантных файлов.</span><span class="sxs-lookup"><span data-stu-id="111ce-163">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="111ce-164">Аналогичным образом это состояние можно использовать для обучения проблем с низкой насыщенностью, где результаты релевантности могут ускорить доступ к файлам, относячим к определенной проблеме.</span><span class="sxs-lookup"><span data-stu-id="111ce-164">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="111ce-165">На вкладке  **"Отслеживание \>** релевантности" доступны следующие параметры просмотра: > Рекомендуемый следующий шаг, например следующий **шаг:** можно обойти теги (для каждого вопроса), нажав кнопку "Изменить" справа, а затем выбрав другой шаг на следующем шаге. </span><span class="sxs-lookup"><span data-stu-id="111ce-165">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="111ce-166">Когда индикатор хода выполнения оценки не будет завершен, рекомендуется использовать оценку, чтобы пометить дополнительные файлы оценки и повысить точность статистики.</span><span class="sxs-lookup"><span data-stu-id="111ce-166">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> <span data-ttu-id="111ce-167">> Вы можете изменить поле ошибки и оценить ее влияние, нажав кнопку **"Изменить"** и в диалоговом окнах уровня оценки, изменив поле целевой ошибки для оценок отзыва и щелкнув "Обновить **значения".**  </span><span class="sxs-lookup"><span data-stu-id="111ce-167">> You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="111ce-168">Кроме того, в этом диалоговом оке можно просмотреть дополнительные параметры, нажав кнопку **"Дополнительные".**</span><span class="sxs-lookup"><span data-stu-id="111ce-168">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> <span data-ttu-id="111ce-169">> Вы можете просмотреть дополнительную статистику об уровне оценки и их влияние, нажав кнопку **"Просмотреть".**</span><span class="sxs-lookup"><span data-stu-id="111ce-169">> You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="111ce-170">В диалоговом окте "Подробные результаты" статистика доступна по каждой проблеме, если имеется не менее 500 помеченных файлов оценки, а не менее 18 файлов помечены как релевантные для проблемы.</span><span class="sxs-lookup"><span data-stu-id="111ce-170">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  