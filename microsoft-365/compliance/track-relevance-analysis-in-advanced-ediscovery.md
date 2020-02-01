---
title: Отслеживание релевантности в Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: 'Сведения о том, как просматривать и интерпретировать состояние обучения релевантности и результаты для проблем с обращениями в Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 5fa9fe49f1a644f2a64321c1ec106b11c487c885
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601406"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="2a496-103">Отслеживание релевантности в Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2a496-103">Track Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="2a496-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="2a496-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="2a496-106">В разделе Advanced eDiscovery на вкладке "релевантность" отображается рассчитанное действие обучения релевантности, выполненного на вкладке "тег", и указывается следующий шаг, который необходимо выполнить в процессе итеративного обучения по релевантности.</span><span class="sxs-lookup"><span data-stu-id="2a496-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="2a496-107">Отслеживание состояния обучения релевантности</span><span class="sxs-lookup"><span data-stu-id="2a496-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="2a496-108">Ознакомьтесь со следующими сведениями в разделе релевантность для проблем с обращением, как показано в следующем примере диалогового окна " **имя проблемы** " ниже.</span><span class="sxs-lookup"><span data-stu-id="2a496-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="2a496-109">**Оценка**: этот индикатор выполнения показывает, насколько степень релевантности, выполненной на этом шаге, достигла цели оценки в плане Маржи к ошибке.</span><span class="sxs-lookup"><span data-stu-id="2a496-109">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="2a496-110">Также отображается насыщенность результатов обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="2a496-110">The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="2a496-111">**Обучающие материалы**: индикатор хода выполнения и всплывающих подсказок на экране указывает на стабильность результатов обучения и числовой масштаб, отображающий количество образцов обучения релевантности, отмеченных для каждого вопроса.</span><span class="sxs-lookup"><span data-stu-id="2a496-111">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="2a496-112">Эксперт отслеживает ход процесса обучения по итеративной релевантности.</span><span class="sxs-lookup"><span data-stu-id="2a496-112">The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="2a496-113">**Вычисление пакетов**: этот индикатор выполнения содержит сведения о завершении пакетного вычисления.</span><span class="sxs-lookup"><span data-stu-id="2a496-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="2a496-114">**Следующий шаг**: отображает рекомендацию для следующего этапа, который необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="2a496-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="2a496-115">В этом примере показана успешная Оценка вопроса, обозначенная индикатором завершения цветового процесса и галочкой.</span><span class="sxs-lookup"><span data-stu-id="2a496-115">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="2a496-116">Расстановка тегов выполняется, но ситуация все еще считается нестабильной (состояние стабильности также отображается в подсказке средства).</span><span class="sxs-lookup"><span data-stu-id="2a496-116">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="2a496-117">Следующий шаг — "обучение".</span><span class="sxs-lookup"><span data-stu-id="2a496-117">The next step recommendation is "Training".</span></span> 
    
    ![Данные об обучении на вкладке "Релевантность" > "Отслеживание" (этап 1)](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="2a496-119">Расширенное представление отображает дополнительные сведения и параметры.</span><span class="sxs-lookup"><span data-stu-id="2a496-119">The expanded view displays additional information and options.</span></span> <span data-ttu-id="2a496-120">Отображаемая текущая погрешность — это поле ошибки отзыва в текущем состоянии оценки с учетом существующих файлов оценки (уже помеченных).</span><span class="sxs-lookup"><span data-stu-id="2a496-120">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="2a496-121">Этап оценки можно пропустить, сняв флажок **оценки** для каждой проблемы, а затем — "все проблемы".</span><span class="sxs-lookup"><span data-stu-id="2a496-121">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="2a496-122">Тем не менее, в результате этой ситуации будет отсутствовать статистика.</span><span class="sxs-lookup"><span data-stu-id="2a496-122">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="2a496-123">> очистку флажка **оценки** можно выполнить только до выполнения оценки.</span><span class="sxs-lookup"><span data-stu-id="2a496-123">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="2a496-124">Если в случае существует несколько проблем, оценка обходится только в том случае, если этот флажок снят для каждой проблемы</span><span class="sxs-lookup"><span data-stu-id="2a496-124">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="2a496-125">Если не выполнить оценку с первого примера набора файлов, оценка может оказаться следующим шагом для пометки дополнительных файлов.</span><span class="sxs-lookup"><span data-stu-id="2a496-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="2a496-126">В разделе **релевантность** \> \*\*\*\* индикатор хода обучения и инструмент подсказки указывают предполагаемое количество дополнительных примеров, необходимых для достижения стабильности.</span><span class="sxs-lookup"><span data-stu-id="2a496-126">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="2a496-127">Эта оценка содержит рекомендации по дополнительным обучению.</span><span class="sxs-lookup"><span data-stu-id="2a496-127">This estimate provides a guideline for the additional training needed.</span></span>
    
    ![Данные об обучении на вкладке "Релевантность" > "Отслеживание"](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="2a496-129">Когда вы закончите маркировку и вам нужно продолжить обучение, нажмите кнопку **учебные курсы**.</span><span class="sxs-lookup"><span data-stu-id="2a496-129">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="2a496-130">Другой образец набора файлов создается из набора загруженных файлов для дополнительного обучения.</span><span class="sxs-lookup"><span data-stu-id="2a496-130">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="2a496-131">После этого вы вернетесь на вкладку тега, чтобы пометить Теги и научить больше файлов.</span><span class="sxs-lookup"><span data-stu-id="2a496-131">You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="2a496-132">Достижение стабильных уровней обучения</span><span class="sxs-lookup"><span data-stu-id="2a496-132">Reaching stable training levels</span></span>

<span data-ttu-id="2a496-133">После того как файлы оценки пристигают стабильного уровня обучения, Расширенное обнаружение электронных данных готово для пакетного вычисления.</span><span class="sxs-lookup"><span data-stu-id="2a496-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a496-134">Как правило, после трех стабильных образцов обучения следующим шагом является "пакетное вычисление".</span><span class="sxs-lookup"><span data-stu-id="2a496-134">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="2a496-135">Возможны исключения, например, при изменении тегов файлов из предыдущих образцов или при добавлении начальных файлов.</span><span class="sxs-lookup"><span data-stu-id="2a496-135">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="2a496-136">Выполнение пакетного вычисления</span><span class="sxs-lookup"><span data-stu-id="2a496-136">Performing Batch calculation</span></span>

<span data-ttu-id="2a496-137">Вычисление пакетов выполняется в следующий шаг после успешного завершения обучения (при отображении индикатора выполнения — Пометка и стабильное состояние в подсказке подсказки). При выполнении пакетного вычисления информация, полученная во время изучения релевантности, применяется ко всему заполнению файла, чтобы оценить релевантность файлов и присвоить показатели релевантности.</span><span class="sxs-lookup"><span data-stu-id="2a496-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="2a496-138">При наличии нескольких ошибок в пакетном расчете выполняется по каждой из выпусков.</span><span class="sxs-lookup"><span data-stu-id="2a496-138">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="2a496-139">Во время пакетного вычисления отслеживается ход выполнения при обработке всех файлов.</span><span class="sxs-lookup"><span data-stu-id="2a496-139">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="2a496-140">Здесь рекомендуемый следующий шаг — "None", что означает, что на этом этапе не нужно выполнять дополнительное обучение по итеративной релевантности.</span><span class="sxs-lookup"><span data-stu-id="2a496-140">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="2a496-141">Следующим этапом является вкладка \*\*релевантность \> \*\* .</span><span class="sxs-lookup"><span data-stu-id="2a496-141">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="2a496-142">Если вы хотите импортировать новые файлы после пакетного вычисления, администратор может добавить импортированные файлы в новую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="2a496-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a496-143">Если нажать кнопку **Отмена** во время пакетного вычисления, процесс сохранит уже выполненное.</span><span class="sxs-lookup"><span data-stu-id="2a496-143">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="2a496-144">При повторном выполнении пакетного вычисления процесс продолжится с последней точки.</span><span class="sxs-lookup"><span data-stu-id="2a496-144">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="2a496-145">Оценка согласованности тегов</span><span class="sxs-lookup"><span data-stu-id="2a496-145">Assessing tagging consistency</span></span>

<span data-ttu-id="2a496-146">Если маркировка файлов содержит несоответствия, это может повлиять на анализ.</span><span class="sxs-lookup"><span data-stu-id="2a496-146">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="2a496-147">Процесс согласования с расширенной проверкой тегов обнаружения электронных данных можно использовать, если результаты не являются оптимальными или несогласованными.</span><span class="sxs-lookup"><span data-stu-id="2a496-147">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="2a496-148">Возвращается список возможных несогласованных файлов с тегами, которые можно просматривать и повторно помечать при необходимости.</span><span class="sxs-lookup"><span data-stu-id="2a496-148">A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a496-149">После \*\*\*\* \> семи циклов обучения, оценивающих после оценки, можно просмотреть согласованность тегов в **подробных результатах** \> \*\*\*\* **отслеживания** \> **релевантности** \> .</span><span class="sxs-lookup"><span data-stu-id="2a496-149">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="2a496-150">Эта проверка выполняется по одной ошибке за раз.</span><span class="sxs-lookup"><span data-stu-id="2a496-150">This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="2a496-151">В **списке \> релевантность**разверните строку вопроса.</span><span class="sxs-lookup"><span data-stu-id="2a496-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="2a496-152">Щелкните **изменить**, чтобы перейти к **следующему шагу**.</span><span class="sxs-lookup"><span data-stu-id="2a496-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="2a496-153">Выберите параметр **несогласованности тегов** в качестве **следующего шага** , после семи образцов обучения и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2a496-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="2a496-154">Выберите **несоответствия тегов**.</span><span class="sxs-lookup"><span data-stu-id="2a496-154">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="2a496-155">На вкладке **тег** открывается список несоответствий для повторного пометки при необходимости.</span><span class="sxs-lookup"><span data-stu-id="2a496-155">The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="2a496-156">Нажмите кнопку **вычислить** , чтобы отправит изменения.</span><span class="sxs-lookup"><span data-stu-id="2a496-156">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="2a496-157">Следующий шаг после рассогласования тегов — "обучение".</span><span class="sxs-lookup"><span data-stu-id="2a496-157">The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="2a496-158">Просмотр и использование результатов релевантности</span><span class="sxs-lookup"><span data-stu-id="2a496-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="2a496-159">На вкладке **Отслеживание \> релевантности** разверните строку вопроса и рядом с элементом **подробные результаты**нажмите кнопку **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="2a496-159">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="2a496-160">Отображаются области подробных результатов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="2a496-160">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Подробные результаты обучения для определения релевантности](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="2a496-162">Сводка по разметке</span><span class="sxs-lookup"><span data-stu-id="2a496-162">Tagging summary</span></span>

 <span data-ttu-id="2a496-163">В приведенном ниже примере **Сводка тегов** отображает итоговые значения для каждого из процессов оценки, обучения и отслеживания файлов.</span><span class="sxs-lookup"><span data-stu-id="2a496-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![Сводка по тегам на вкладке "Релевантность" > "Отслеживание"](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="2a496-165">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a496-165">Keywords</span></span>

<span data-ttu-id="2a496-166">Ключевое слово — это уникальная строка, слово, фраза или последовательность слов в файле, определяемой расширенным обнаружением электронных данных, как важный индикатор того, является ли файл релевантным.</span><span class="sxs-lookup"><span data-stu-id="2a496-166">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="2a496-167">Ключевое слово "include" содержит список столбцов и весовые значения для файлов, помеченных как имеющие отношение, а в столбцах "исключить" перечислены ключевые слова и веса в файлах, помеченных как несущественные.</span><span class="sxs-lookup"><span data-stu-id="2a496-167">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="2a496-168">Advanced eDiscovery задает отрицательные или положительные значения веса ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="2a496-168">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="2a496-169">Чем выше вес, тем выше вероятность того, что файл, в котором отображается ключевое слово, будет иметь более высокую оценку релевантности во время выполнения пакетного вычисления.</span><span class="sxs-lookup"><span data-stu-id="2a496-169">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="2a496-170">Расширенный список обнаружения электронных данных с ключевыми словами можно использовать для дополнения списка, созданного экспертом, или в качестве косвенной проверки санити в любой момент в процессе проверки файлов.</span><span class="sxs-lookup"><span data-stu-id="2a496-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="2a496-171">Ход обучения</span><span class="sxs-lookup"><span data-stu-id="2a496-171">Training progress</span></span>

<span data-ttu-id="2a496-172">Область " **Ход обучения** " содержит график хода обучения и отображение индикатора качества, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="2a496-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![Индикатор выполнения обучения на вкладке "Релевантность" > "Отслеживание"](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="2a496-174">**Индикатор качества обучения**: отображает оценку согласованности тегов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2a496-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="2a496-175">**Хорошая**: файлы помечаются тегами единообразно.</span><span class="sxs-lookup"><span data-stu-id="2a496-175">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="2a496-176">(Отображается зеленый свет)</span><span class="sxs-lookup"><span data-stu-id="2a496-176">(Green light displayed)</span></span>
    
- <span data-ttu-id="2a496-177">**Medium**: некоторые файлы могут помечаться как несогласованные.</span><span class="sxs-lookup"><span data-stu-id="2a496-177">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="2a496-178">(Желтый индикатор отображается)</span><span class="sxs-lookup"><span data-stu-id="2a496-178">(Yellow light displayed)</span></span>
    
- <span data-ttu-id="2a496-179">**Предупреждение**: многие файлы могут быть отмечены как несогласованные.</span><span class="sxs-lookup"><span data-stu-id="2a496-179">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="2a496-180">(Отображается красный индикатор)</span><span class="sxs-lookup"><span data-stu-id="2a496-180">(Red light displayed)</span></span>
    
 <span data-ttu-id="2a496-181">**График хода обучения**: показывает степень стабильности обучения по релевантности после циклов обучения по сравнению со значением F – Measure.</span><span class="sxs-lookup"><span data-stu-id="2a496-181">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="2a496-182">Когда вы перемещаетесь слева направо на диаграмме, диапазон доверия сужается и используется вместе с F-мерой, а также с помощью расширенной функции обнаружения электронных данных для определения стабильности при оптимизации результатов обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="2a496-182">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a496-183">Релевантность использует клавишу F2, метрику координат F, в которой отзыв получается вдвое как точность.</span><span class="sxs-lookup"><span data-stu-id="2a496-183">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="2a496-184">Для случаев с высоким уровнем насыщенности (более 25%) релевантность использует F1 (соотношение 1:1).</span><span class="sxs-lookup"><span data-stu-id="2a496-184">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="2a496-185">Отношение единицы измерения F можно настроить в \> **дополнительных параметрах** **настройки релевантности** .</span><span class="sxs-lookup"><span data-stu-id="2a496-185">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="2a496-186">Результаты расчетов партий</span><span class="sxs-lookup"><span data-stu-id="2a496-186">Batch calculation results</span></span>

<span data-ttu-id="2a496-187">В области **результатов расчетов пакетов** указывается количество файлов, которые были оценены по релевантности, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="2a496-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="2a496-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="2a496-188">**Success**</span></span>
    
- <span data-ttu-id="2a496-189">**Empty**: не содержит текста (например, только пробелы/знаки табуляции)</span><span class="sxs-lookup"><span data-stu-id="2a496-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="2a496-190">**Сбой**: из-за чрезмерного размера или недоступен для чтения</span><span class="sxs-lookup"><span data-stu-id="2a496-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="2a496-191">**Проигнорировано**: из-за чрезмерного размера</span><span class="sxs-lookup"><span data-stu-id="2a496-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="2a496-192">**Небулаус**: содержит небессмысленный текст или компоненты, не связанные с этой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="2a496-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="2a496-193">"Пустой", "ошибка", "игнорируется" или "Небулаус" получает показатель релевантности, равный – 1.</span><span class="sxs-lookup"><span data-stu-id="2a496-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="2a496-194">Статистика обучения</span><span class="sxs-lookup"><span data-stu-id="2a496-194">Training statistics</span></span>

<span data-ttu-id="2a496-195">В области " **Статистика обучения** " отображаются статистические данные и графики на основе результатов расширенного обучения относительно обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="2a496-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Статистика обучения на вкладке "Релевантность" > "Отслеживание"](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="2a496-197">В этом представлении отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="2a496-197">This view shows the following:</span></span>
  
- <span data-ttu-id="2a496-198">**Коэффициент отзыва**: сравнение результатов в соответствии с оценками релевантности в гипотетической линейной проверке.</span><span class="sxs-lookup"><span data-stu-id="2a496-198">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="2a496-199">Пример отзыва оценивается с учетом установленного размера набора рецензирования.</span><span class="sxs-lookup"><span data-stu-id="2a496-199">Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="2a496-200">**Parameters**: интегральная вычисляемые статистические данные, относящиеся к набору проверки по отношению к совокупности файлов для всего случая.</span><span class="sxs-lookup"><span data-stu-id="2a496-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="2a496-201">**Обзор**: процент файлов для проверки на основе этой отсечки.</span><span class="sxs-lookup"><span data-stu-id="2a496-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="2a496-202">**Отзыв**: процент релевантных файлов в наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="2a496-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="2a496-203">**Распределение по показателю релевантности**: файлы в темно-сером дисплее слева расположены под показателем отсечки.</span><span class="sxs-lookup"><span data-stu-id="2a496-203">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="2a496-204">Всплывающая подсказка отображает показатель релевантности и связанный с ними процент файлов в наборе контрольных файлов по отношению к общему количеству файлов.</span><span class="sxs-lookup"><span data-stu-id="2a496-204">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2a496-205">См. также</span><span class="sxs-lookup"><span data-stu-id="2a496-205">See also</span></span>

[<span data-ttu-id="2a496-206">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2a496-206">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2a496-207">Понимание оценки релевантности</span><span class="sxs-lookup"><span data-stu-id="2a496-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a496-208">Выполнение и Просмотр оценки</span><span class="sxs-lookup"><span data-stu-id="2a496-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a496-209">Обучение по релевантности</span><span class="sxs-lookup"><span data-stu-id="2a496-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a496-210">Принятие решений на основе результатов</span><span class="sxs-lookup"><span data-stu-id="2a496-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a496-211">Анализ релевантности тестирования</span><span class="sxs-lookup"><span data-stu-id="2a496-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

