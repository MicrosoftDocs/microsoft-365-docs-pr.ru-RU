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
description: Узнайте, как просматривать и интерпретировать состояние обучения релевантности и результаты для проблем с делом в Advanced eDiscovery.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769184"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="e763e-103">Отслеживание анализа релевантности в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e763e-103">Track Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="e763e-104">В Advanced eDiscovery вкладка "Отслеживание релевантности" отображает вычисляемую действительность обучения релевантности, выполненного на вкладке "Тег", и указывает на следующий шаг, выполняемый в процессе итеративного обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="e763e-104">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="e763e-105">Отслеживание состояния обучения релевантности</span><span class="sxs-lookup"><span data-stu-id="e763e-105">Tracking Relevance training status</span></span>

1. <span data-ttu-id="e763e-106">Просмотреть следующие сведения в отслеживании релевантности для проблем с делом, как показано в следующем примере диалоговое окно **"Имя** проблемы" ниже.</span><span class="sxs-lookup"><span data-stu-id="e763e-106">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span>

   - <span data-ttu-id="e763e-107">**Оценка**: этот индикатор хода выполнения показывает, в какой степени обучение релевантности, выполненного до этого момента, достигло целевого показателя оценки с точки зрения полей ошибок.</span><span class="sxs-lookup"><span data-stu-id="e763e-107">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="e763e-108">Также отображаются результаты обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="e763e-108">The richness of the Relevance training results is also displayed.</span></span>

   - <span data-ttu-id="e763e-109">**Обучение**: этот индикатор хода выполнения с цветом и подсказка для средства указывает стабильность результатов обучения релевантности и числовую шкалу, показывающая количество примеров обучения релевантности, помеченных для каждой проблемы.</span><span class="sxs-lookup"><span data-stu-id="e763e-109">**Training**: This color-coded progress indicator and tool-tip indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="e763e-110">Эксперт отслеживает ход выполнения итеративного процесса обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="e763e-110">The expert monitors the progress of the iterative Relevance training process.</span></span> 
  
   - <span data-ttu-id="e763e-111">**Пакетное вычисление**: этот индикатор хода выполнения предоставляет сведения о завершении пакетного вычисления.</span><span class="sxs-lookup"><span data-stu-id="e763e-111">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
  
   - <span data-ttu-id="e763e-112">**Следующий шаг:** отображает рекомендации по следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="e763e-112">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
  
    <span data-ttu-id="e763e-113">В этом примере показана успешно завершенная оценка проблемы, обозначенная индикатором хода выполнения цвета и закладкой.</span><span class="sxs-lookup"><span data-stu-id="e763e-113">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="e763e-114">Маркировка уже ведется, но этот случай по-прежнему считается нестабильным (состояние стабильности также отображается в подсказке).</span><span class="sxs-lookup"><span data-stu-id="e763e-114">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="e763e-115">Следующий шаг — "Обучение".</span><span class="sxs-lookup"><span data-stu-id="e763e-115">The next step recommendation is "Training".</span></span> 
  
    ![Данные об обучении на вкладке "Релевантность" > "Отслеживание" (этап 1)](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="e763e-117">В расширенном представлении отображаются дополнительные сведения и параметры.</span><span class="sxs-lookup"><span data-stu-id="e763e-117">The expanded view displays additional information and options.</span></span> <span data-ttu-id="e763e-118">Отображаемая текущая поле ошибки — это поле ошибки отзыва в текущем состоянии оценки с учетом существующих (уже помеченных) файлов оценки.</span><span class="sxs-lookup"><span data-stu-id="e763e-118">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="e763e-119">Этап оценки можно обойти, с  помощью каждого вопроса с помощью каждого из них, а затем для всех проблем.</span><span class="sxs-lookup"><span data-stu-id="e763e-119">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="e763e-120">Однако в результате статистика по этой проблеме не будет.</span><span class="sxs-lookup"><span data-stu-id="e763e-120">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="e763e-121">> проверку **можно** выполнить только перед ее выполнением.</span><span class="sxs-lookup"><span data-stu-id="e763e-121">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="e763e-122">Если в ситуации имеется несколько проблем, оценка пропускается только в том случае, если для каждой проблемы не задан этот контроль</span><span class="sxs-lookup"><span data-stu-id="e763e-122">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="e763e-123">Если оценка не завершена с помощью первого примера набора файлов, оценка может быть следующим шагом для маркировки дополнительных файлов.</span><span class="sxs-lookup"><span data-stu-id="e763e-123">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span>
  
    <span data-ttu-id="e763e-124">В  \> **средстве "Отслеживание** релевантности" индикатор хода обучения и подсказка указывают предполагаемое количество дополнительных примеров, необходимых для достижения стабильности.</span><span class="sxs-lookup"><span data-stu-id="e763e-124">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="e763e-125">В этой оценке содержится руководство по дополнительному обучению.</span><span class="sxs-lookup"><span data-stu-id="e763e-125">This estimate provides a guideline for the additional training needed.</span></span>
  
    ![Данные об обучении на вкладке "Релевантность" > "Отслеживание"](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="e763e-127">Когда вы пометите теги и, если вам нужно продолжить обучение, щелкните **"Обучение".**</span><span class="sxs-lookup"><span data-stu-id="e763e-127">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="e763e-128">Другой пример набора файлов создается из загруженного набора файлов для дополнительного обучения.</span><span class="sxs-lookup"><span data-stu-id="e763e-128">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="e763e-129">Затем вы вернетесь на вкладку "Тег", чтобы пометить и обучить дополнительные файлы.</span><span class="sxs-lookup"><span data-stu-id="e763e-129">You are then returned to the Tag tab to tag and train more files.</span></span>

### <a name="reaching-stable-training-levels"></a><span data-ttu-id="e763e-130">Достижение стабильных уровней обучения</span><span class="sxs-lookup"><span data-stu-id="e763e-130">Reaching stable training levels</span></span>

<span data-ttu-id="e763e-131">После того как файлы оценки пройдют стабильный уровень обучения, Advanced eDiscovery будет готов к пакетным вычислениям.</span><span class="sxs-lookup"><span data-stu-id="e763e-131">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e763e-132">Обычно после трех стабильных учебных примеров следующим шагом является "Пакетное вычисление".</span><span class="sxs-lookup"><span data-stu-id="e763e-132">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="e763e-133">Могут быть исключения, например, при внесении изменений в маркировку файлов из предыдущих примеров или при добавлении файлов с заполнениями.</span><span class="sxs-lookup"><span data-stu-id="e763e-133">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="e763e-134">Выполнение пакетных вычислений</span><span class="sxs-lookup"><span data-stu-id="e763e-134">Performing Batch calculation</span></span>

<span data-ttu-id="e763e-135">Пакетное вычисление выполняется в качестве следующего шага после успешного завершения обучения (когда на панели хода выполнения отображается стабильное состояние обучения, в подсказке инструмента отображается контрольный знак и стабильное состояние).) Пакетное вычисление применяет знания, полученные во время обучения релевантности, ко всем файлам, чтобы оценить релевантность файлов и назначить оценки релевантности.</span><span class="sxs-lookup"><span data-stu-id="e763e-135">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="e763e-136">Если имеется несколько проблем, для каждой проблемы делается пакетное вычисление.</span><span class="sxs-lookup"><span data-stu-id="e763e-136">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="e763e-137">Во время пакетного вычисления ход выполнения отслеживается при обработке всех файлов.</span><span class="sxs-lookup"><span data-stu-id="e763e-137">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="e763e-138">Далее рекомендуется использовать значение "None", которое указывает на то, что на данном этапе не требуется дополнительное обучение релевантности.</span><span class="sxs-lookup"><span data-stu-id="e763e-138">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="e763e-139">Следующий этап — вкладка **"Выбор \> релевантности".**</span><span class="sxs-lookup"><span data-stu-id="e763e-139">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="e763e-140">Если после пакетного вычисления необходимо импортировать новые файлы, администратор может добавить импортируемые файлы в новую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="e763e-140">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e763e-141">Если вы **нажмете** кнопку "Отмена" во время пакетного вычисления, процесс сохранит выполненные.</span><span class="sxs-lookup"><span data-stu-id="e763e-141">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="e763e-142">Если вы снова запустите пакетное вычисление, процесс продолжится с последней выполненной точки.</span><span class="sxs-lookup"><span data-stu-id="e763e-142">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="e763e-143">Оценка согласованности тегов</span><span class="sxs-lookup"><span data-stu-id="e763e-143">Assessing tagging consistency</span></span>

<span data-ttu-id="e763e-144">Если в тегах файлов имеются несоответствия, это может повлиять на анализ.</span><span class="sxs-lookup"><span data-stu-id="e763e-144">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="e763e-145">Процесс согласованности тегов Advanced eDiscovery можно использовать, если результаты не являются оптимальными или не уверены в согласованности.</span><span class="sxs-lookup"><span data-stu-id="e763e-145">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="e763e-146">Возвращается список возможных файлов с несогласованными тегами, которые при необходимости можно просмотреть и повторно использовать.</span><span class="sxs-lookup"><span data-stu-id="e763e-146">A list of possible inconsistently tagged files is returned, and they can be reviewed and retagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e763e-147">После семи или более учебных кругов после оценки  можно просмотреть согласованность тегов в ходе обучения релевантности отслеживания вопросов с \>  \>  \>  \> **подробными результатами.**</span><span class="sxs-lookup"><span data-stu-id="e763e-147">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="e763e-148">Этот обзор делается по одной проблеме за раз.</span><span class="sxs-lookup"><span data-stu-id="e763e-148">This review is done for one issue at a time.</span></span>
  
1. <span data-ttu-id="e763e-149">В **\> отслеживании релевантности** разоширйте строку проблемы.</span><span class="sxs-lookup"><span data-stu-id="e763e-149">In **Relevance \> Track**, expand an issue's row.</span></span>
  
2. <span data-ttu-id="e763e-150">Справа от следующего **шага нажмите** кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="e763e-150">To the right of **Next step**, click **Modify**.</span></span>
  
3. <span data-ttu-id="e763e-151">Выберите **несоответствия тегов** в качестве следующего **шага** после семи учебных примеров и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="e763e-151">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
  
4. <span data-ttu-id="e763e-152">Выберите **несоответствия тегов.**</span><span class="sxs-lookup"><span data-stu-id="e763e-152">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="e763e-153">На **вкладке** "Тег" откроется список несоответствий, которые необходимо переустановить при необходимости.</span><span class="sxs-lookup"><span data-stu-id="e763e-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span></span>
  
5. <span data-ttu-id="e763e-154">Нажмите **кнопку "Расчет",** чтобы отправить изменения.</span><span class="sxs-lookup"><span data-stu-id="e763e-154">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="e763e-155">Следующий шаг после разметки несоответствий — "Обучение".</span><span class="sxs-lookup"><span data-stu-id="e763e-155">The next step after tagging inconsistencies is "Training".</span></span> 
  
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="e763e-156">Просмотр и использование результатов релевантности</span><span class="sxs-lookup"><span data-stu-id="e763e-156">Viewing and using Relevance results</span></span>

<span data-ttu-id="e763e-157">На **вкладке \> "Отслеживание** релевантности" разйдите по строке проблемы и нажмите кнопку "Просмотреть" рядом с подробными **результатами.**</span><span class="sxs-lookup"><span data-stu-id="e763e-157">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="e763e-158">Отображаются области подробных результатов, как показано и описано ниже.</span><span class="sxs-lookup"><span data-stu-id="e763e-158">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Подробные результаты обучения для определения релевантности](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="e763e-160">Сводка по тегам</span><span class="sxs-lookup"><span data-stu-id="e763e-160">Tagging summary</span></span>

 <span data-ttu-id="e763e-161">В приведенной ниже  примере сводка по тегам отображает итоги для каждого процесса маркировки файлов оценки, обучения и перенаверки.</span><span class="sxs-lookup"><span data-stu-id="e763e-161">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span>
  
![Сводка по тегам на вкладке "Релевантность" > "Отслеживание"](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="e763e-163">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e763e-163">Keywords</span></span>

<span data-ttu-id="e763e-164">Ключевое слово — это уникальная строка, слово, фраза или последовательность слов в файле, идентифицированных Advanced eDiscovery как важный индикатор релевантнсти файла.</span><span class="sxs-lookup"><span data-stu-id="e763e-164">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="e763e-165">В столбцах "Включить" перечислены ключевые слова и веса в файлах, помеченных как релевантные, а в столбцах "Исключить" перечислены ключевые слова и веса в файлах, помеченных как не релевантные.</span><span class="sxs-lookup"><span data-stu-id="e763e-165">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="e763e-166">Advanced eDiscovery назначает отрицательные или положительные значения веса ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="e763e-166">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="e763e-167">Чем выше вес, тем выше вероятность того, что файлу, в котором отображается ключевое слово, будет присвоена более высокая релевантность во время пакетного вычисления.</span><span class="sxs-lookup"><span data-stu-id="e763e-167">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span>
  
<span data-ttu-id="e763e-168">Список ключевых слов Advanced eDiscovery можно использовать для дополнения списка, составленного экспертом, или в качестве косвенной проверки на санацию в любой момент процесса проверки файлов.</span><span class="sxs-lookup"><span data-stu-id="e763e-168">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="e763e-169">Ход обучения</span><span class="sxs-lookup"><span data-stu-id="e763e-169">Training progress</span></span>

<span data-ttu-id="e763e-170">В **области "Ход** обучения" содержится график хода обучения и индикатор качества, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="e763e-170">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span>
  
![Индикатор выполнения обучения на вкладке "Релевантность" > "Отслеживание"](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
<span data-ttu-id="e763e-172">**Индикатор качества обучения:** отображает оценку согласованности тегов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e763e-172">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="e763e-173">**Хороший:** файлы помечены согласованно.</span><span class="sxs-lookup"><span data-stu-id="e763e-173">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="e763e-174">(Отображается зеленый свет)</span><span class="sxs-lookup"><span data-stu-id="e763e-174">(Green light displayed)</span></span>
  
- <span data-ttu-id="e763e-175">**Средний:** некоторые файлы могут быть помечены несогласованно.</span><span class="sxs-lookup"><span data-stu-id="e763e-175">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="e763e-176">(Отображается желтый свет)</span><span class="sxs-lookup"><span data-stu-id="e763e-176">(Yellow light displayed)</span></span>

- <span data-ttu-id="e763e-177">**Предупреждение:** многие файлы могут быть помечены несогласованно.</span><span class="sxs-lookup"><span data-stu-id="e763e-177">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="e763e-178">(Отображается красный свет)</span><span class="sxs-lookup"><span data-stu-id="e763e-178">(Red light displayed)</span></span>

<span data-ttu-id="e763e-179">**График хода обучения:** показывает степень стабильности обучения релевантности после многих циклов обучения релевантности по сравнению со значением F-measure.</span><span class="sxs-lookup"><span data-stu-id="e763e-179">**Training progress graph**: Shows the degree of Relevance training stability after many Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="e763e-180">По мере перемещения слева направо по графику интервал уверенности сужается и используется наряду с F-мерой с помощью релевантности Advanced eDiscovery для определения стабильности при оптимизации результатов обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="e763e-180">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e763e-181">Релевантность использует F2, метрику F-measure, в которой при отзыве вес в два раза превышает точность.</span><span class="sxs-lookup"><span data-stu-id="e763e-181">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="e763e-182">Для случаев с высоким уровнем насыщенности (более 25 %) релевантность использует F1 (соотношение 1:1).</span><span class="sxs-lookup"><span data-stu-id="e763e-182">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="e763e-183">Коэффициент F-мер можно настроить в **дополнительных** параметрах настройки \> **релевантности.**</span><span class="sxs-lookup"><span data-stu-id="e763e-183">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span>
  
### <a name="batch-calculation-results"></a><span data-ttu-id="e763e-184">Результаты пакетного вычисления</span><span class="sxs-lookup"><span data-stu-id="e763e-184">Batch calculation results</span></span>

<span data-ttu-id="e763e-185">В **области результатов** пакетного вычисления содержится количество файлов, которые были очислены за релевантность следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e763e-185">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="e763e-186">**Success**</span><span class="sxs-lookup"><span data-stu-id="e763e-186">**Success**</span></span>
  
- <span data-ttu-id="e763e-187">**Пустой:** не содержит текста, например, только пробелы/вкладки</span><span class="sxs-lookup"><span data-stu-id="e763e-187">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
  
- <span data-ttu-id="e763e-188">**Failed**: Due to excessive size or could not be read</span><span class="sxs-lookup"><span data-stu-id="e763e-188">**Failed**: Due to excessive size or could not be read</span></span>
  
- <span data-ttu-id="e763e-189">**Ignored**: Due to excessive size</span><span class="sxs-lookup"><span data-stu-id="e763e-189">**Ignored**: Due to excessive size</span></span>
  
- <span data-ttu-id="e763e-190">**Nebulous**: содержит бессмысленный текст или функции, релевантные для проблемы</span><span class="sxs-lookup"><span data-stu-id="e763e-190">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
  
> [!NOTE]
> <span data-ttu-id="e763e-191">Пустой, неудачный, игнорируемый или неблоковый будет иметь значение релевантности -1.</span><span class="sxs-lookup"><span data-stu-id="e763e-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span>
  
### <a name="training-statistics"></a><span data-ttu-id="e763e-192">Статистика обучения</span><span class="sxs-lookup"><span data-stu-id="e763e-192">Training statistics</span></span>

<span data-ttu-id="e763e-193">В **области статистики** "Обучение" отображаются статистика и графики, основанные на результатах обучения релевантности advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="e763e-193">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Статистика обучения на вкладке "Релевантность" > "Отслеживание"](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="e763e-195">В этом представлении показано следующее:</span><span class="sxs-lookup"><span data-stu-id="e763e-195">This view shows the following:</span></span>
  
- <span data-ttu-id="e763e-196">**Соотношение отзывов и** отзывов: сравнение результатов в соответствии с результатами релевантности в гипотетически линейном обзоре.</span><span class="sxs-lookup"><span data-stu-id="e763e-196">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="e763e-197">Отзыв оценивается с учетом набора размеров набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="e763e-197">Recall is estimated given the review set size set.</span></span>
  
- <span data-ttu-id="e763e-198">**Параметры:** накопительная вычисляемая статистика, относящуюся к набору проверки по отношению к совокупности файлов для всего дела.</span><span class="sxs-lookup"><span data-stu-id="e763e-198">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
  
- <span data-ttu-id="e763e-199">**Review**: Percentage of files to review based on this cutoff.</span><span class="sxs-lookup"><span data-stu-id="e763e-199">**Review**: Percentage of files to review based on this cutoff.</span></span>
  
- <span data-ttu-id="e763e-200">**Отзыв:** процент релевантного файла в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="e763e-200">**Recall**: Percentage of Relevant files in the review set.</span></span> 
  
- <span data-ttu-id="e763e-201">**Распределение по оценке релевантности:** файлы на темно-сером дисплее слева находятся ниже оценки вырезания.</span><span class="sxs-lookup"><span data-stu-id="e763e-201">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="e763e-202">Подсказка отображает показатель релевантности и соответствующий процент файлов в наборе файлов для проверки по отношению к общему объему файлов.</span><span class="sxs-lookup"><span data-stu-id="e763e-202">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
