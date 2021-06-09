---
title: Отслеживание анализа релевантности в Advanced eDiscovery
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как просматривать и интерпретировать состояние подготовки релевантности и результаты для проблем с Advanced eDiscovery.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769184"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="33321-103">Отслеживание анализа релевантности в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="33321-103">Track Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="33321-104">В Advanced eDiscovery на вкладке "Отслеживание релевантности" отображается вычисляемая действительность учебного процесса Релевантность, выполняемого на вкладке Tag, и указывается следующий шаг, который необходимо выполнить в процессе итерации обучения в Релевантность.</span><span class="sxs-lookup"><span data-stu-id="33321-104">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="33321-105">Отслеживание состояния подготовки релевантности</span><span class="sxs-lookup"><span data-stu-id="33321-105">Tracking Relevance training status</span></span>

1. <span data-ttu-id="33321-106">Просмотр следующих сведений в отслеживании релевантности для проблем, как показано в следующем примере диалоговое окно **имя** проблемы ниже.</span><span class="sxs-lookup"><span data-stu-id="33321-106">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span>

   - <span data-ttu-id="33321-107">**Оценка.** Этот индикатор прогресса показывает, в какой степени выполненная к этому моменту подготовка релевантности достигла цели оценки с точки зрения погрешности.</span><span class="sxs-lookup"><span data-stu-id="33321-107">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="33321-108">Также отображается богатство результатов обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="33321-108">The richness of the Relevance training results is also displayed.</span></span>

   - <span data-ttu-id="33321-109">**Обучение.** Этот индикатор прогресса с кодом цвета и подсказка инструментов указывает на стабильность результатов обучения релевантности и цифровую шкалу, показывающая количество примеров подготовки релевантности, помеченных для каждой проблемы.</span><span class="sxs-lookup"><span data-stu-id="33321-109">**Training**: This color-coded progress indicator and tool-tip indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="33321-110">Эксперт отслеживает ход итеративного учебного процесса релевантности.</span><span class="sxs-lookup"><span data-stu-id="33321-110">The expert monitors the progress of the iterative Relevance training process.</span></span> 
  
   - <span data-ttu-id="33321-111">**Пакетный** расчет. Этот индикатор прогресса предоставляет сведения о завершении вычисления пакета.</span><span class="sxs-lookup"><span data-stu-id="33321-111">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
  
   - <span data-ttu-id="33321-112">**Следующий шаг.** Отображается рекомендация для следующего шага, который будет выполнен.</span><span class="sxs-lookup"><span data-stu-id="33321-112">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
  
    <span data-ttu-id="33321-113">В примере показана успешно выполненная оценка проблемы, указанная индикатором выполнения цвета и задаткой.</span><span class="sxs-lookup"><span data-stu-id="33321-113">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="33321-114">Пометка ведется, но случай по-прежнему считается неустойчивым (состояние стабильности также отображается в подсказке инструмента).</span><span class="sxs-lookup"><span data-stu-id="33321-114">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="33321-115">Следующая рекомендация шага — "Обучение".</span><span class="sxs-lookup"><span data-stu-id="33321-115">The next step recommendation is "Training".</span></span> 
  
    ![Данные об обучении на вкладке "Релевантность" > "Отслеживание" (этап 1)](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="33321-117">В расширенном представлении отображаются дополнительные сведения и параметры.</span><span class="sxs-lookup"><span data-stu-id="33321-117">The expanded view displays additional information and options.</span></span> <span data-ttu-id="33321-118">Отображаемая текущая погрешность — это погрешность отзыва в текущем состоянии оценки, учитывая существующие (уже помеченные) файлы оценки.</span><span class="sxs-lookup"><span data-stu-id="33321-118">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="33321-119">Этап оценки можно обойти путем очистки контрольного окна **оценки** за одну проблему, а затем для "всех проблем".</span><span class="sxs-lookup"><span data-stu-id="33321-119">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="33321-120">Однако в результате статистики по этому вопросу не будет.</span><span class="sxs-lookup"><span data-stu-id="33321-120">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="33321-121">> очистку контрольного окна **оценки** можно выполнить только до выполнения оценки.</span><span class="sxs-lookup"><span data-stu-id="33321-121">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="33321-122">Если в деле существует несколько проблем, оценка обходится без проверки только в том случае, если для каждой проблемы будет очищено поле</span><span class="sxs-lookup"><span data-stu-id="33321-122">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="33321-123">Если оценка не завершена с первым набором примеров файлов, оценка может быть следующим шагом для тегов дополнительных файлов.</span><span class="sxs-lookup"><span data-stu-id="33321-123">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span>
  
    <span data-ttu-id="33321-124">В **"Отслеживание** релевантности" индикатор хода обучения и подсказка по инструментам указывают предполагаемое количество дополнительных образцов, необходимых для \> достижения стабильности.</span><span class="sxs-lookup"><span data-stu-id="33321-124">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="33321-125">В этой оценке содержится руководство по дополнительному обучению, необходимому.</span><span class="sxs-lookup"><span data-stu-id="33321-125">This estimate provides a guideline for the additional training needed.</span></span>
  
    ![Данные об обучении на вкладке "Релевантность" > "Отслеживание"](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="33321-127">Когда вы закончили теги и если вам необходимо продолжить обучение, нажмите кнопку **Обучение**.</span><span class="sxs-lookup"><span data-stu-id="33321-127">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="33321-128">Другой пример набора файлов создается из загружаемого набора файлов для дополнительного обучения.</span><span class="sxs-lookup"><span data-stu-id="33321-128">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="33321-129">Затем вы возвращается на вкладку Tag для тегов и подготовки дополнительных файлов.</span><span class="sxs-lookup"><span data-stu-id="33321-129">You are then returned to the Tag tab to tag and train more files.</span></span>

### <a name="reaching-stable-training-levels"></a><span data-ttu-id="33321-130">Достижение стабильного уровня подготовки</span><span class="sxs-lookup"><span data-stu-id="33321-130">Reaching stable training levels</span></span>

<span data-ttu-id="33321-131">После того, как файлы оценки достигнут стабильного уровня подготовки, Advanced eDiscovery готовы к вычислению Batch.</span><span class="sxs-lookup"><span data-stu-id="33321-131">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="33321-132">Обычно после трех стабильных образцов обучения следующим шагом является "Пакетный расчет".</span><span class="sxs-lookup"><span data-stu-id="33321-132">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="33321-133">Могут быть исключения, например, при внесении изменений в теги файлов из более ранних образцов или при добавлении файлов семян.</span><span class="sxs-lookup"><span data-stu-id="33321-133">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="33321-134">Выполнение вычисления пакета</span><span class="sxs-lookup"><span data-stu-id="33321-134">Performing Batch calculation</span></span>

<span data-ttu-id="33321-135">Пакетный расчет выполняется по мере успешного завершения обучения на следующем этапе (когда в панели прогресса отображается стабильный учебный статус, контрольный знак и стабильный статус в подсказке инструмента).) Пакетный расчет применяет знания, полученные во время обучения релевантности для всего населения файлов, для оценки релевантности файлов и назначения баллов релевантности.</span><span class="sxs-lookup"><span data-stu-id="33321-135">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="33321-136">Если существует несколько проблем, для каждой проблемы делается пакетный расчет.</span><span class="sxs-lookup"><span data-stu-id="33321-136">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="33321-137">Во время вычислений batch отслеживается прогресс при обработке всех файлов.</span><span class="sxs-lookup"><span data-stu-id="33321-137">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="33321-138">Здесь рекомендуется следующий шаг "Нет", что указывает на то, что дополнительные итеративные учебные курсы релевантности не требуются на данном этапе.</span><span class="sxs-lookup"><span data-stu-id="33321-138">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="33321-139">Следующий этап — **вкладка \> Релевантность Решите.**</span><span class="sxs-lookup"><span data-stu-id="33321-139">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="33321-140">Если после вычисления пакета необходимо импортировать новые файлы, администратор может добавить импортируемые файлы в новую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="33321-140">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="33321-141">Если вы **нажмете Отмена** во время вычисления пакета, процесс сохранит то, что уже выполнено.</span><span class="sxs-lookup"><span data-stu-id="33321-141">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="33321-142">При повторном выполнении вычисления пакетов процесс будет продолжаться с последней выполненной точки.</span><span class="sxs-lookup"><span data-stu-id="33321-142">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="33321-143">Оценка согласованности тегов</span><span class="sxs-lookup"><span data-stu-id="33321-143">Assessing tagging consistency</span></span>

<span data-ttu-id="33321-144">Если в тегах файлов есть несоответствия, это может повлиять на анализ.</span><span class="sxs-lookup"><span data-stu-id="33321-144">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="33321-145">Процесс Advanced eDiscovery пометок можно использовать, если результаты не являются оптимальными или под вопросом согласованность.</span><span class="sxs-lookup"><span data-stu-id="33321-145">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="33321-146">Возвращается список возможных непоследовательных помеченных файлов, которые при необходимости можно просмотреть и повторно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="33321-146">A list of possible inconsistently tagged files is returned, and they can be reviewed and retagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="33321-147">После семи или более учебных раундов после оценки  можно просмотреть последовательность тегов в выпуске подробных результатов обучения \>  \>  \>  \> релевантности.</span><span class="sxs-lookup"><span data-stu-id="33321-147">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="33321-148">Этот обзор делается по одной проблеме одновременно.</span><span class="sxs-lookup"><span data-stu-id="33321-148">This review is done for one issue at a time.</span></span>
  
1. <span data-ttu-id="33321-149">В **\> отслеживании релевантности** разо расширении строки проблемы.</span><span class="sxs-lookup"><span data-stu-id="33321-149">In **Relevance \> Track**, expand an issue's row.</span></span>
  
2. <span data-ttu-id="33321-150">Справа от следующего **шага** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="33321-150">To the right of **Next step**, click **Modify**.</span></span>
  
3. <span data-ttu-id="33321-151">Выберите **несоответствия тегов** в качестве **параметра Следующий** шаг после семи примеров обучения и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="33321-151">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
  
4. <span data-ttu-id="33321-152">Выберите **несоответствия тегов.**</span><span class="sxs-lookup"><span data-stu-id="33321-152">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="33321-153">Вкладка **Tag** открывает список несоответствий, которые необходимо переоценить.</span><span class="sxs-lookup"><span data-stu-id="33321-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span></span>
  
5. <span data-ttu-id="33321-154">Щелкните **Вычислять,** чтобы отправить изменения.</span><span class="sxs-lookup"><span data-stu-id="33321-154">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="33321-155">Следующим шагом после пометки несоответствий является "Обучение".</span><span class="sxs-lookup"><span data-stu-id="33321-155">The next step after tagging inconsistencies is "Training".</span></span> 
  
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="33321-156">Просмотр и использование результатов релевантности</span><span class="sxs-lookup"><span data-stu-id="33321-156">Viewing and using Relevance results</span></span>

<span data-ttu-id="33321-157">На **вкладке Отслеживание \>** релевантности разойдите строку проблемы, а рядом с подробными результатами **щелкните** **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="33321-157">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="33321-158">Отображаются области подробных результатов, как показано и описано ниже.</span><span class="sxs-lookup"><span data-stu-id="33321-158">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Подробные результаты обучения для определения релевантности](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="33321-160">Сводка тегов</span><span class="sxs-lookup"><span data-stu-id="33321-160">Tagging summary</span></span>

 <span data-ttu-id="33321-161">В приведенной ниже  примере сводка тегов отображает итоги для каждого процесса пометки файлов "Оценка", "Обучение" и "Догонять".</span><span class="sxs-lookup"><span data-stu-id="33321-161">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span>
  
![Сводка по тегам на вкладке "Релевантность" > "Отслеживание"](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="33321-163">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="33321-163">Keywords</span></span>

<span data-ttu-id="33321-164">Ключевое слово — это уникальная строка, слово, фраза или последовательность слов в файле, Advanced eDiscovery в качестве важного индикатора актуальности файла.</span><span class="sxs-lookup"><span data-stu-id="33321-164">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="33321-165">В списке столбцов "Включить" ключевые слова и весы в файлах с тегами "Релевантные", а в столбцах "Исключить" перечислены ключевые слова и весы в файлах, помеченных как Не релевантные.</span><span class="sxs-lookup"><span data-stu-id="33321-165">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="33321-166">Advanced eDiscovery назначает отрицательные или положительные значения веса ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="33321-166">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="33321-167">Чем больше вес, тем выше вероятность того, что файлу, в котором появится ключевое слово, назначена более высокая оценка релевантности при вычислении пакета.</span><span class="sxs-lookup"><span data-stu-id="33321-167">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span>
  
<span data-ttu-id="33321-168">Список Advanced eDiscovery ключевых слов можно использовать для дополнения списка, построенного экспертом, или в качестве косвенной проверки вменяемости в любой момент процесса проверки файлов.</span><span class="sxs-lookup"><span data-stu-id="33321-168">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="33321-169">Ход обучения</span><span class="sxs-lookup"><span data-stu-id="33321-169">Training progress</span></span>

<span data-ttu-id="33321-170">В **области "Прогресс** обучения" содержится график прогресса подготовки и отображение индикатора качества, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="33321-170">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span>
  
![Индикатор выполнения обучения на вкладке "Релевантность" > "Отслеживание"](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
<span data-ttu-id="33321-172">**Индикатор качества подготовки:** отображает рейтинг согласованности тегов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="33321-172">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="33321-173">**Хорошо:** файлы помечены последовательно.</span><span class="sxs-lookup"><span data-stu-id="33321-173">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="33321-174">(Отображается зеленый свет)</span><span class="sxs-lookup"><span data-stu-id="33321-174">(Green light displayed)</span></span>
  
- <span data-ttu-id="33321-175">**Medium.** Некоторые файлы могут быть помечены несогласованно.</span><span class="sxs-lookup"><span data-stu-id="33321-175">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="33321-176">(Отображается желтый свет)</span><span class="sxs-lookup"><span data-stu-id="33321-176">(Yellow light displayed)</span></span>

- <span data-ttu-id="33321-177">**Предупреждение.** Многие файлы могут быть помечены несогласованно.</span><span class="sxs-lookup"><span data-stu-id="33321-177">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="33321-178">(Отображается красный свет)</span><span class="sxs-lookup"><span data-stu-id="33321-178">(Red light displayed)</span></span>

<span data-ttu-id="33321-179">**График хода обучения:** показывает степень устойчивости подготовки релевантности после многих циклов подготовки релевантности по сравнению со значением F-measure.</span><span class="sxs-lookup"><span data-stu-id="33321-179">**Training progress graph**: Shows the degree of Relevance training stability after many Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="33321-180">При переходе слева направо по графику интервал доверия сужается и, наряду с F-мерой, используется Advanced eDiscovery Релевантность для определения стабильности при оптимизации результатов обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="33321-180">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="33321-181">Релевантность использует F2, метрику F-measure, в которой recall получает в два раза больше веса, чем Точность.</span><span class="sxs-lookup"><span data-stu-id="33321-181">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="33321-182">Для случаев с высоким уровнем насыщенности (более 25%) релевантность использует коэффициент F1 (1:1).</span><span class="sxs-lookup"><span data-stu-id="33321-182">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="33321-183">Коэффициент F-measure можно настроить в настройках **релевантности** \> **Advanced.**</span><span class="sxs-lookup"><span data-stu-id="33321-183">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span>
  
### <a name="batch-calculation-results"></a><span data-ttu-id="33321-184">Результаты вычислений пакетов</span><span class="sxs-lookup"><span data-stu-id="33321-184">Batch calculation results</span></span>

<span data-ttu-id="33321-185">В **области результатов** пакетных вычислений содержится количество файлов, которые были забиты для релевантности:</span><span class="sxs-lookup"><span data-stu-id="33321-185">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="33321-186">**Success**</span><span class="sxs-lookup"><span data-stu-id="33321-186">**Success**</span></span>
  
- <span data-ttu-id="33321-187">**Empty:** Не содержит текста, например, только пробелы/вкладки</span><span class="sxs-lookup"><span data-stu-id="33321-187">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
  
- <span data-ttu-id="33321-188">**Failed:** Due to excessive size or could not be read</span><span class="sxs-lookup"><span data-stu-id="33321-188">**Failed**: Due to excessive size or could not be read</span></span>
  
- <span data-ttu-id="33321-189">**Игнорируется:** Из-за чрезмерного размера</span><span class="sxs-lookup"><span data-stu-id="33321-189">**Ignored**: Due to excessive size</span></span>
  
- <span data-ttu-id="33321-190">**Туманность:** содержит бессмысленным текстом или не содержит функций, соответствующих проблеме</span><span class="sxs-lookup"><span data-stu-id="33321-190">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
  
> [!NOTE]
> <span data-ttu-id="33321-191">Пустой, неудачный, проигнорированный или туманный получит значение релевантности -1.</span><span class="sxs-lookup"><span data-stu-id="33321-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span>
  
### <a name="training-statistics"></a><span data-ttu-id="33321-192">Статистика подготовки</span><span class="sxs-lookup"><span data-stu-id="33321-192">Training statistics</span></span>

<span data-ttu-id="33321-193">В **области статистики подготовки** отображаются статистические данные и графики, основанные на результатах Advanced eDiscovery релевантности.</span><span class="sxs-lookup"><span data-stu-id="33321-193">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Статистика обучения на вкладке "Релевантность" > "Отслеживание"](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="33321-195">В этом представлении показано следующее:</span><span class="sxs-lookup"><span data-stu-id="33321-195">This view shows the following:</span></span>
  
- <span data-ttu-id="33321-196">**Отношение review-recall**: Сравнение результатов в соответствии с баллами релевантности в гипотетическом линейном обзоре.</span><span class="sxs-lookup"><span data-stu-id="33321-196">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="33321-197">Recall is estimated given the review set size set.</span><span class="sxs-lookup"><span data-stu-id="33321-197">Recall is estimated given the review set size set.</span></span>
  
- <span data-ttu-id="33321-198">**Параметры.** Совокупная вычисляемая статистика, относящуюся к набору отзывов по отношению к популяции файлов для всего случая.</span><span class="sxs-lookup"><span data-stu-id="33321-198">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
  
- <span data-ttu-id="33321-199">**Обзор.** Процент файлов, которые необходимо просмотреть на основе этого отсека.</span><span class="sxs-lookup"><span data-stu-id="33321-199">**Review**: Percentage of files to review based on this cutoff.</span></span>
  
- <span data-ttu-id="33321-200">**Напомним.** Процент релевантного файла в наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="33321-200">**Recall**: Percentage of Relevant files in the review set.</span></span> 
  
- <span data-ttu-id="33321-201">**Распределение по оценке релевантности.** Файлы в темно-сером дисплее слева находятся ниже оценки отсеки.</span><span class="sxs-lookup"><span data-stu-id="33321-201">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="33321-202">На подсказке инструмента отображается оценка релевантности и соответствующий процент файлов в файле обзора по отношению к общему объему файлов.</span><span class="sxs-lookup"><span data-stu-id="33321-202">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
