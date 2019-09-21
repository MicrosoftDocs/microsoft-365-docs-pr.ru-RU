---
title: Использование модуля релевантности для анализа данных в свидетельствах
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: adb807dc2f0ca7440b4d7c1405c0f8e15d346c10
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091490"
---
# <a name="use-the-relevance-module-to-analyze-data-in-evidence"></a><span data-ttu-id="814d1-102">Использование модуля релевантности для анализа данных в свидетельствах</span><span class="sxs-lookup"><span data-stu-id="814d1-102">Use the Relevance module to analyze data in evidence</span></span>

<span data-ttu-id="814d1-103">При расследовании данных (Предварительная версия) модуль релевантности включает обучение и обзор файлов, относящихся к расследованию.</span><span class="sxs-lookup"><span data-stu-id="814d1-103">In Data Investigations (Preview), the Relevance module includes the Relevance training and review of files related to an investigation.</span></span> <span data-ttu-id="814d1-104">Рабочий процесс релевантности отображается и описывается следующим образом:</span><span class="sxs-lookup"><span data-stu-id="814d1-104">The Relevance workflow is shown and described as follows:</span></span>
  
![Рабочий процесс определения релевантности](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="814d1-106">**Циклы оценки и отслеживания**:</span><span class="sxs-lookup"><span data-stu-id="814d1-106">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="814d1-107">**Оценка**: включает ранние оценки на основе случайного примера файлов и использует эту оценку для определения производительности процесса прогнозирующих кодов.</span><span class="sxs-lookup"><span data-stu-id="814d1-107">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="814d1-108">**Track**: вычисление и отображение промежуточных результатов оценки при наблюдении за статистическим действием процесса.</span><span class="sxs-lookup"><span data-stu-id="814d1-108">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="814d1-109">**Циклы обучения и отслеживания**</span><span class="sxs-lookup"><span data-stu-id="814d1-109">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="814d1-110">**Тег**: расследования данных (Предварительная версия) сведения об условиях релевантности, относящихся к каждой из выпусков, на основе последовательного рассмотрения и маркировки отдельных файлов экспертом.</span><span class="sxs-lookup"><span data-stu-id="814d1-110">**Tag**: Data Investigations (Preview) learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="814d1-111">**Track**: вычисляет и отображает промежуточные результаты обучения релевантности при наблюдении за статистическим действием процесса.</span><span class="sxs-lookup"><span data-stu-id="814d1-111">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="814d1-112">**Вычисление пакетов**: критерии накопленного и полученного соответствия применяются ко всей коллекции файлов, а показатель релевантности создается для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="814d1-112">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="814d1-113">**Выбор**: результаты анализа, примененного ко всему случаю, отображаются после вычисления, и отображаются данные, используемые для принятия решений по рецензированию документов.</span><span class="sxs-lookup"><span data-stu-id="814d1-113">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="814d1-114">**Тест**: результаты можно проверить, чтобы проверить допустимость и эффективность обработки данных расследования (Preview).</span><span class="sxs-lookup"><span data-stu-id="814d1-114">**Test**: Results can be tested to verify the validity and effectiveness of the Data Investigations (Preview) processing.</span></span>

- <span data-ttu-id="814d1-115">**Поиск**: после завершения рабочего процесса релевантности вы можете использовать выходные данные, такие как Read персентиль документа для вашего вопроса при выполнении запроса в рабочем наборе.</span><span class="sxs-lookup"><span data-stu-id="814d1-115">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="814d1-116">Рекомендации по изучению и обзору релевантности</span><span class="sxs-lookup"><span data-stu-id="814d1-116">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="814d1-117">Ниже представлен обзор рекомендаций по изучению и проверке релевантности.</span><span class="sxs-lookup"><span data-stu-id="814d1-117">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="814d1-118">**Ошибки и несоответствия**. при возникновении ошибок тегирования в ходе обучения вернитесь к предыдущим примерам файлов, чтобы исправить их.</span><span class="sxs-lookup"><span data-stu-id="814d1-118">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="814d1-119">Если вы намерены слишком много ошибок или если у вас есть новая перспектива или ситуация, условия релевантности должны быть переопределены администратором и перезапущено обучение по релевантности.</span><span class="sxs-lookup"><span data-stu-id="814d1-119">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="814d1-120">**Маркировка и обучение**:</span><span class="sxs-lookup"><span data-stu-id="814d1-120">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="814d1-121">Файлы следует размечать только на основе контента.</span><span class="sxs-lookup"><span data-stu-id="814d1-121">Files should be tagged based on content only.</span></span> <span data-ttu-id="814d1-122">Не учитывайте метаданные, такие как хранитель, дата или путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="814d1-122">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="814d1-123">Не учитывайте указания диапазона дат в тексте при разметке тегами файлов.</span><span class="sxs-lookup"><span data-stu-id="814d1-123">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="814d1-124">Не учитывайте внедренные графические изображения при разметке тегами файлов.</span><span class="sxs-lookup"><span data-stu-id="814d1-124">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="814d1-125">Игнорировать текст, примененный к релевантности, будет удален в отображаемом содержимом файла в текстовом представлении релевантность.</span><span class="sxs-lookup"><span data-stu-id="814d1-125">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="814d1-126">Если значения для параметра Ignore Text были определены после начала обучения соответствия, новый пропущенный текст будет применен к образцам файлов, созданным на основе точки, в которой он был определен.</span><span class="sxs-lookup"><span data-stu-id="814d1-126">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="814d1-127">Функция ignore Text должна использоваться с осторожностью, так как ее использование может привести к снижению производительности анализа файлов.</span><span class="sxs-lookup"><span data-stu-id="814d1-127">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="814d1-128">Используйте параметр **пропускать маркировку** , только если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="814d1-128">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="814d1-129">Исследования данных (Предварительная версия) не обучены на основе пропущенных файлов.</span><span class="sxs-lookup"><span data-stu-id="814d1-129">Data Investigations (Preview) does not train based on skipped files.</span></span> <span data-ttu-id="814d1-130">В процессе оценки, если трудно определить, является ли файл релевантным, лучше помечаться как соответствующий (R) или нет (НР), если это возможно, а не выбирать **пропустить**.</span><span class="sxs-lookup"><span data-stu-id="814d1-130">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="814d1-131">При оценке обучающих данных (предварительной версии) можно увидеть, как хорошо обрабатывались эти типы файлов.</span><span class="sxs-lookup"><span data-stu-id="814d1-131">When Data Investigations (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="814d1-132">Даже файлы с очень небольшим объемом извлеченного текста должны быть помечены как R/НР, а не как "Skip", когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="814d1-132">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="814d1-133">Расстановка тегов может повлиять на классификатор до тех пор, пока файл доступен для чтения и его можно пометить как R/НР.</span><span class="sxs-lookup"><span data-stu-id="814d1-133">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="814d1-134">Порядковый номер файла в списке отображаемых файлов на вкладке **тег** позволяет пользователю вернуться к исходному отображаемому порядку файлов.</span><span class="sxs-lookup"><span data-stu-id="814d1-134">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="814d1-135">Вы можете вернуться к любому примеру и изменить маркировку файлов оценки и учебного набора.</span><span class="sxs-lookup"><span data-stu-id="814d1-135">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="814d1-136">Изменения будут применены при создании следующего примера.</span><span class="sxs-lookup"><span data-stu-id="814d1-136">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="814d1-137">Отсканированные файлы Excel в формате PDF должны рассматриваться как собственные файлы Excel при разметке тегами файлов.</span><span class="sxs-lookup"><span data-stu-id="814d1-137">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="814d1-138">Если у вас есть сомнения относительно тегов релевантности файла, ознакомьтесь со статьей эксперта.</span><span class="sxs-lookup"><span data-stu-id="814d1-138">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="814d1-139">Неправильное расстановка тегов во время обучения несоответствия может привести к потере времени в процессе, а также может негативно повлиять на качество общих результатов.</span><span class="sxs-lookup"><span data-stu-id="814d1-139">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="814d1-140">Ключевые слова, определенные в списках ключевых слов, будут отображаться в цветах, чтобы помочь пользователю определить релевантные файлы при разметке тегами.</span><span class="sxs-lookup"><span data-stu-id="814d1-140">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="814d1-141">**Вычисление пакетов**: файлы, помеченные экспертом как R/НР, получат значение 0 или 100.</span><span class="sxs-lookup"><span data-stu-id="814d1-141">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="814d1-142">Это относится к разметке, выполненным перед вычислением пакетов.</span><span class="sxs-lookup"><span data-stu-id="814d1-142">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="814d1-143">Если эксперт переключился на неактивное после выполнения пакетного вычисления и размечает маркировку этой ситуации, то новые баллы не будут 100/0ся, а исходнее.</span><span class="sxs-lookup"><span data-stu-id="814d1-143">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="814d1-144">**Проблемы и режим выборки**: проблемы обычно отключаются при завершении работы над ними (проведено обучение по релевантности и выполнен пакетный пересчет), когда проблемы отменяются или когда другой пользователь работает над проблемами.</span><span class="sxs-lookup"><span data-stu-id="814d1-144">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="814d1-145">Этапы обучения</span><span class="sxs-lookup"><span data-stu-id="814d1-145">Steps in Relevance training</span></span>

<span data-ttu-id="814d1-146">На вкладке **Отслеживание \> релевантности** данные изученны в статье сведения о том, как продолжить обработку, со следующими дальнейшими действиями.</span><span class="sxs-lookup"><span data-stu-id="814d1-146">In the **Relevance \> Track** tab, Data investigations provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="814d1-147">Эти следствия описаны ниже, когда рекомендуется выполнить каждое из следующих действий в процессе обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="814d1-147">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="814d1-148">Маркировка и продолжение маркировки: Проверка файлов и маркировка релевантности, выполненные экспертом для каждого файла и выпуска в рамках примера.</span><span class="sxs-lookup"><span data-stu-id="814d1-148">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="814d1-149">Результат: существующий пример должен быть помечен.</span><span class="sxs-lookup"><span data-stu-id="814d1-149">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="814d1-150">Оценка/продолжение оценки: включает начальную проверку релевантности с учетом регистра и предварительное представление релевантности заполнения файла, импортированного для текущего случая.</span><span class="sxs-lookup"><span data-stu-id="814d1-150">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="814d1-151">Результат: необходима дополнительная оценка или рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="814d1-151">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="814d1-152">Training/Continue Training: процесс, в ходе которого расследования данных изучены от эксперта, который размечает образцы файлов и получает возможность определять условия релевантности, относящиеся к каждой из них в контексте каждого случая.</span><span class="sxs-lookup"><span data-stu-id="814d1-152">Training / Continue training: Process during which Data investigations learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="814d1-153">Результат: для этой задачи требуется дополнительное обучение; Следующий пример следует создать и пометить тегами.</span><span class="sxs-lookup"><span data-stu-id="814d1-153">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="814d1-154">Вычисление пакетов: процесс релевантности, в котором расследования данных берет на себя знания, полученные на этапе обучения, и применяет его ко всему заполнению файла.</span><span class="sxs-lookup"><span data-stu-id="814d1-154">Batch calculation: Relevance process in which Data investigations takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="814d1-155">Все файлы в релевантной группе файлов оцениваются по релевантности и имеют показатель релевантности.</span><span class="sxs-lookup"><span data-stu-id="814d1-155">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="814d1-156">Результат: Эта ошибка вызвана, и можно выполнить пакетный пересчет.</span><span class="sxs-lookup"><span data-stu-id="814d1-156">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="814d1-157">При сопоставлении: релевантность указывает, что экспертная проверка и теги получит пример файлов, выбранных из дополнительной загрузки файлов во время поэтапной загрузки.</span><span class="sxs-lookup"><span data-stu-id="814d1-157">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="814d1-158">Результат: была добавлена новая нагрузка, и для продолжения работы требуется дополнительное обновление.</span><span class="sxs-lookup"><span data-stu-id="814d1-158">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="814d1-159">Несогласованности тегов: процесс идентифицирует, с помощью алгоритма расследования данных, несоответствия в процессе тегирования файлов, которые могут негативно повлиять на анализ.</span><span class="sxs-lookup"><span data-stu-id="814d1-159">Tag inconsistencies: Process identifies, via an Data investigations algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="814d1-160">Результат: в следующем примере будут содержаться файлы, помеченные в предыдущих примерах, и их маркировку необходимо выполнить повторно.</span><span class="sxs-lookup"><span data-stu-id="814d1-160">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="814d1-161">Классификатор обновлений: позволяет пользователю применять теги и изменения заполнения.</span><span class="sxs-lookup"><span data-stu-id="814d1-161">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="814d1-162">Результат: изменения тегов и заполнения могут быть применены без необходимости вручную запускать еще один пример.</span><span class="sxs-lookup"><span data-stu-id="814d1-162">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="814d1-163">На удержании: процесс обучения соответствия завершен.</span><span class="sxs-lookup"><span data-stu-id="814d1-163">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="814d1-164">Результат: в этой точке не обязательно должно быть обучение по релевантности.</span><span class="sxs-lookup"><span data-stu-id="814d1-164">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="814d1-165">Несмотря на то, что при расследовании данных мы рекомендуем выполнить следующие действия на разных стадиях, он также позволяет переходить между вкладками и страницами, а также предоставлять варианты для обращения к ситуациям, которые могут относиться к конкретному случаю, выпуску или процесс рецензирования документа.</span><span class="sxs-lookup"><span data-stu-id="814d1-165">Although Data investigations guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="814d1-166">Можно принимать или переопределять параметры обработки следующего этапа обработки данных.</span><span class="sxs-lookup"><span data-stu-id="814d1-166">It is possible to accept or override Data investigations Next step processing choices.</span></span> <span data-ttu-id="814d1-167">Если вы хотите выполнить шаг, отличный от рекомендуемого, щелкните **следующий шаг** , приведенный в разделе Расширенная ошибка в диалоговом окне, нажмите кнопку **изменить** рядом с следующим шагом, а затем выберите другой параметр следующего шага.</span><span class="sxs-lookup"><span data-stu-id="814d1-167">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="814d1-168">Некоторые параметры могут быть отключены после снятия блокировки, так как они не поддерживаются в этой точке процесса.</span><span class="sxs-lookup"><span data-stu-id="814d1-168">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="814d1-169">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="814d1-169">More information</span></span>

[<span data-ttu-id="814d1-170">Понимание оценки релевантности</span><span class="sxs-lookup"><span data-stu-id="814d1-170">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="814d1-171">Маркировка и оценка</span><span class="sxs-lookup"><span data-stu-id="814d1-171">Tagging and assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="814d1-172">Расстановка тегов и релевантности</span><span class="sxs-lookup"><span data-stu-id="814d1-172">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="814d1-173">Анализ релевантности отслеживания</span><span class="sxs-lookup"><span data-stu-id="814d1-173">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="814d1-174">Выбор на основе результатов</span><span class="sxs-lookup"><span data-stu-id="814d1-174">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="814d1-175">Анализ релевантности тестирования</span><span class="sxs-lookup"><span data-stu-id="814d1-175">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="814d1-176">Запрос данных в доказательстве</span><span class="sxs-lookup"><span data-stu-id="814d1-176">Query the data in evidence</span></span>](evidence-query.md)
