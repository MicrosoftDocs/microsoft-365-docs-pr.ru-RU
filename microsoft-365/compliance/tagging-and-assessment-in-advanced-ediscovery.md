---
title: Маркировка и оценка в Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: 'Изучите шаги, необходимые для проведения обучения, в том числе файлов тегирования, и просмотра результатов оценки в Office 365 Advanced eDiscovery. '
ms.openlocfilehash: 067f8933bd7fc1286e468d664bf4dbd754e64f00
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090694"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a><span data-ttu-id="96509-103">Маркировка и оценка в Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="96509-103">Tagging and Assessment in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="96509-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="96509-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="96509-106">В этом разделе описывается процедура для расширенного модуля оценки соответствия eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="96509-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="96509-107">Проведение обучения и анализ</span><span class="sxs-lookup"><span data-stu-id="96509-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="96509-108">На вкладке **Отслеживание \> релевантности** нажмите кнопку **Оценка** , чтобы начать оценку.</span><span class="sxs-lookup"><span data-stu-id="96509-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="96509-109">Например, в этой процедуре создается пример оценочного набора данных 500, и отображается вкладка **тега** , содержащая панель маркировки, содержимое файла и другие параметры тегирования.</span><span class="sxs-lookup"><span data-stu-id="96509-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![Вкладка "Релевантность" > "Добавление тегов" для оценки](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="96509-111">Просмотрите каждый файл в этом примере, определите релевантность файла для каждой из них и пометьте файл, используя кнопки релевантность (R), не релевантные (НР) и Skip ( **панель маркировки** ).</span><span class="sxs-lookup"><span data-stu-id="96509-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="96509-112">Для оценки требуется 500 файлов с тегами.</span><span class="sxs-lookup"><span data-stu-id="96509-112">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="96509-113">Если файлы "пропущены", вы получите дополнительные файлы для тегов.</span><span class="sxs-lookup"><span data-stu-id="96509-113">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="96509-114">После маркировки всех файлов в примере нажмите кнопку **Calculate (вычислить**).</span><span class="sxs-lookup"><span data-stu-id="96509-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="96509-115">На вкладке Отслеживание релевантности вычисляются и отображаются сведения о текущей и расширенной оценке, а также на вкладке **Отслеживание релевантности** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="96509-115">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="96509-116">Дополнительные сведения об этом диалоговом окне описаны в разделе "Просмотр результатов оценки".</span><span class="sxs-lookup"><span data-stu-id="96509-116">More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![Оценка на вкладке "Релевантность" > "Отслеживание"](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="96509-118">По умолчанию мы рекомендуем переходить к следующему шагу, когда индикатор выполнения оценки для этой ошибки был выполнен, указывая на то, что образец оценки проверен, и что отмечено достаточное количество релевантных файлов.</span><span class="sxs-lookup"><span data-stu-id="96509-118">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="96509-119">> в противном случае, если вы хотите просмотреть результаты вкладки **отслеживания** и управлять полями ошибки и следующим шагом, щелкните **изменить** смежные на **следующий шаг**, выберите пункт **продолжить оценку**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="96509-119">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="96509-120">Нажмите кнопку **изменить** справа от поля **Оценка** , чтобы просмотреть и указать параметры оценки для каждого вопроса.</span><span class="sxs-lookup"><span data-stu-id="96509-120">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="96509-121">Отображается диалоговое окно **уровня оценки** для каждой из выпусков, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="96509-121">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![Уровень оценки: элемент для оценивания при выполнении задания](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="96509-123">Следующие параметры для этой задачи рассчитываются и отображаются в диалоговом окне **уровень оценки** :</span><span class="sxs-lookup"><span data-stu-id="96509-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="96509-124">**Целевое поле ошибки для оценок отзыва**: на основе этого значения вычисляется предполагаемое количество дополнительных файлов, необходимых для проверки.</span><span class="sxs-lookup"><span data-stu-id="96509-124">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="96509-125">Маржа, используемая для отзыва, превышает 75% и степень вероятности 95%.</span><span class="sxs-lookup"><span data-stu-id="96509-125">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="96509-126">**Требуются дополнительные файлы оценки**: указывает, сколько дополнительных файлов требуется, если не выполнены требования к текущему полю ошибки.</span><span class="sxs-lookup"><span data-stu-id="96509-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="96509-127">Чтобы скорректировать текущее поле ошибки и увидеть результаты различных полей ошибок (по вопросу), выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="96509-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="96509-128">В списке **выберите вопрос** выберите вопрос.</span><span class="sxs-lookup"><span data-stu-id="96509-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="96509-129">В **поле Целевая ошибка для оценки отзыва**введите новое значение.</span><span class="sxs-lookup"><span data-stu-id="96509-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="96509-130">Нажмите кнопку **обновить значения** , чтобы увидеть влияние корректировок.</span><span class="sxs-lookup"><span data-stu-id="96509-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="96509-131">В диалоговом окне **уровень оценки** нажмите кнопку **Дополнительно** , чтобы просмотреть следующие дополнительные параметры и сведения:</span><span class="sxs-lookup"><span data-stu-id="96509-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![Расширенное представление "Уровень оценки: элемент для оценивания при выполнении задания"](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="96509-133">**Оценка полноты**оценки в соответствии с текущими результатами оценки</span><span class="sxs-lookup"><span data-stu-id="96509-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="96509-134">**Для предполагаемого отзыва**: по умолчанию целевое поле ошибки применяется к предыдущему вызываемому пользователю 75%.</span><span class="sxs-lookup"><span data-stu-id="96509-134">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="96509-135">Нажмите кнопку **изменить** , чтобы изменить этот параметр и управлять полем ошибки для другого диапазона значений отзыва.</span><span class="sxs-lookup"><span data-stu-id="96509-135">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="96509-136">**Уровень вероятности**: по умолчанию рекомендуемое поле ошибки для достоверности составляет 95%.</span><span class="sxs-lookup"><span data-stu-id="96509-136">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="96509-137">Если вы хотите изменить этот параметр, нажмите кнопку **изменить** .</span><span class="sxs-lookup"><span data-stu-id="96509-137">Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="96509-138">**Ожидалось поле расширенной проверки погрешностей**: при наличии обновленных значений это предполагаемое поле ошибки полноты, после рассмотрения всех дополнительных файлов оценки.</span><span class="sxs-lookup"><span data-stu-id="96509-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="96509-139">**Требуются дополнительные файлы оценки**: с учетом обновленных значений, количества дополнительных файлов оценки, которые необходимо проверить для достижения целевого значения.</span><span class="sxs-lookup"><span data-stu-id="96509-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="96509-140">**Общие требуемые файлы оценки**: при наличии обновленных значений все файлы оценки, необходимые для проверки.</span><span class="sxs-lookup"><span data-stu-id="96509-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="96509-141">**Ожидаемое количество релевантных файлов в ходе оценки**: с учетом обновленных значений — предполагаемое число релевантных файлов во всей оценке после рассмотрения всех дополнительных файлов оценки.</span><span class="sxs-lookup"><span data-stu-id="96509-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="96509-142">Нажмите кнопку **пересчитать значения**, если параметры изменены.</span><span class="sxs-lookup"><span data-stu-id="96509-142">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="96509-143">Если проблема не устранена, нажмите кнопку **ОК** , чтобы сохранить изменения **(или,** если имеется несколько проблем, которые необходимо просмотреть или изменить, а затем **завершить**).</span><span class="sxs-lookup"><span data-stu-id="96509-143">When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="96509-144">При возникновении нескольких проблем после того как все проблемы были проверены или скорректированы, отображается **уровень оценки:** отображается диалоговое окно сводки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="96509-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Уровень оценки: сводка](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="96509-146">После успешного завершения оценки переходите к следующему этапу обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="96509-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="96509-147">Просмотр результатов оценки</span><span class="sxs-lookup"><span data-stu-id="96509-147">Reviewing assessment results</span></span>

<span data-ttu-id="96509-148">После того как отмечен пример оценки, результаты оценки рассчитываются и отображаются на вкладке Отслеживание релевантности.</span><span class="sxs-lookup"><span data-stu-id="96509-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="96509-149">На дисплее расширенной записи отображаются следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="96509-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="96509-150">Оценка текущих полей ошибок для оценок отзыва</span><span class="sxs-lookup"><span data-stu-id="96509-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="96509-151">Оценка возможностей</span><span class="sxs-lookup"><span data-stu-id="96509-151">Estimated richness</span></span>
    
- <span data-ttu-id="96509-152">Требуются дополнительные файлы оценки (для проверки)</span><span class="sxs-lookup"><span data-stu-id="96509-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="96509-153">Поле Оценка текущей ошибки — это поле ошибки, рекомендованное расширенным обнаружением электронных данных.</span><span class="sxs-lookup"><span data-stu-id="96509-153">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="96509-154">Число, отображаемое для "дополнительных необходимых файлов оценки", соответствует этой рекомендации.</span><span class="sxs-lookup"><span data-stu-id="96509-154">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="96509-155">Индикатор хода оценки показывает уровень завершения оценки с учетом текущего поля ошибки.</span><span class="sxs-lookup"><span data-stu-id="96509-155">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="96509-156">После выполнения оценки пользователь помечает другой пример оценки.</span><span class="sxs-lookup"><span data-stu-id="96509-156">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="96509-157">Когда индикатор выполнения оценки выводит оценку как завершенный, это означает, что проверка выполнена успешно, а помечены соответствующие файлы.</span><span class="sxs-lookup"><span data-stu-id="96509-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="96509-158">На развернутом дисплее показан рекомендуемый следующий шаг, статистика оценки и доступ к подробным результатам.</span><span class="sxs-lookup"><span data-stu-id="96509-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="96509-159">Если насыщенность очень мала, количество дополнительных файлов оценки, необходимых для достижения минимального количества релевантных файлов для получения полезной статистики, очень высокое.</span><span class="sxs-lookup"><span data-stu-id="96509-159">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="96509-160">После этого Расширенное обнаружение электронных данных будет рекомендовано переходить на обучающий курс.</span><span class="sxs-lookup"><span data-stu-id="96509-160">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="96509-161">Индикатор хода оценки будет затенен, а статистика будет недоступна.</span><span class="sxs-lookup"><span data-stu-id="96509-161">The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="96509-162">В случае отсутствия на основе статистики стабилизатион результаты будут иметь более низкий уровень точности и вероятности.</span><span class="sxs-lookup"><span data-stu-id="96509-162">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="96509-163">Тем не менее, эти результаты можно использовать для поиска релевантных файлов, если вам не нужно знать процент релевантных файлов.</span><span class="sxs-lookup"><span data-stu-id="96509-163">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="96509-164">Аналогично, это состояние можно использовать для обучения проблем с небольшим богатыми возможностями, где показатели релевантности могут ускорить доступ к файлам, связанным с определенной ошибкой.</span><span class="sxs-lookup"><span data-stu-id="96509-164">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="96509-165">На вкладке **Отслеживание \> релевантности** отображается развернутая ошибка, доступны следующие параметры просмотра: > рекомендуемый следующий шаг, например **следующий шаг: пропускать маркировку** (на вопрос), нажав кнопку **Modify (изменить** ) справа , а затем выберите другой шаг на **следующем шаге**.</span><span class="sxs-lookup"><span data-stu-id="96509-165">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="96509-166">Когда индикатор выполнения оценки не закончится, будет использоваться следующий рекомендуемый вариант, чтобы отметить дополнительные файлы оценки и повысить точность статистики.</span><span class="sxs-lookup"><span data-stu-id="96509-166">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> <span data-ttu-id="96509-167">> вы можете изменить поле ошибки и оценить его влияние, нажав кнопку **изменить**, а затем в **диалоговом окне уровень оценки**измените **целевое поле ошибки для оценок отзыва**и нажмите кнопку **обновить значения**.</span><span class="sxs-lookup"><span data-stu-id="96509-167">> You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="96509-168">Кроме того, в этом диалоговом окне можно просмотреть дополнительные параметры, нажав кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="96509-168">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> <span data-ttu-id="96509-169">> вы можете просмотреть дополнительную статистику по уровню оценки и их влияние, нажав кнопку **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="96509-169">> You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="96509-170">В диалоговом окне Отображение подробных результатов статистические данные доступны для каждой задачи, при наличии по крайней мере 500 файлов оценки с тегами и по крайней мере 18 файлов помечаются как имеющие отношение к этой ошибке.</span><span class="sxs-lookup"><span data-stu-id="96509-170">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="96509-171">См. также</span><span class="sxs-lookup"><span data-stu-id="96509-171">See also</span></span>

[<span data-ttu-id="96509-172">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="96509-172">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="96509-173">Понимание оценки релевантности</span><span class="sxs-lookup"><span data-stu-id="96509-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="96509-174">Расстановка тегов и релевантности</span><span class="sxs-lookup"><span data-stu-id="96509-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="96509-175">Анализ релевантности отслеживания</span><span class="sxs-lookup"><span data-stu-id="96509-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="96509-176">Выбор на основе результатов</span><span class="sxs-lookup"><span data-stu-id="96509-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="96509-177">Анализ релевантности тестирования</span><span class="sxs-lookup"><span data-stu-id="96509-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

