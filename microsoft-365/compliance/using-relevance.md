---
title: Использование модуля релевантности для анализа данных в Advanced eDiscovery
f1.keywords:
- NOCSH
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
description: Сведения о том, как модуль релевантности анализирует данные в свидетельствах с описанием рабочих процессов релевантности и обучающих действий в Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4babb0aa7693bc1107cc7594da967bca2d307228
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034471"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="89ac3-103">Использование модуля релевантности для анализа данных в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="89ac3-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="89ac3-104">В Advanced eDiscovery модуль релевантности включает обучение релевантности и обзор файлов, связанных с обращением.</span><span class="sxs-lookup"><span data-stu-id="89ac3-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="89ac3-105">Чтобы использовать рабочий процесс релевантности, перейдите к разделу Управление набором проверки в наборе проверки и нажмите кнопку Показать релевантность.</span><span class="sxs-lookup"><span data-stu-id="89ac3-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="89ac3-106">Для запуска рабочего процесса необходимо выполнить несколько действий.</span><span class="sxs-lookup"><span data-stu-id="89ac3-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="89ac3-107">Процесс: каждый набор нагрузок, добавленный в набор проверки, будет отображаться как "контейнер".</span><span class="sxs-lookup"><span data-stu-id="89ac3-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="89ac3-108">Эти документы необходимо обработать, прежде чем их можно будет добавить в модуль релевантности; Кроме того, вы можете пометить их как заполненные или предварительно помеченные для конкретной ситуации.</span><span class="sxs-lookup"><span data-stu-id="89ac3-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="89ac3-109">Добавить в соответствие: под загрузкой релевантности \> вы можете добавлять документы, которые были обработаны, чтобы сделать их доступными для обучения.</span><span class="sxs-lookup"><span data-stu-id="89ac3-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="89ac3-110">Рабочий процесс релевантности отображается и описывается следующим образом:</span><span class="sxs-lookup"><span data-stu-id="89ac3-110">The Relevance workflow is shown and described as follows:</span></span>
  
![Рабочий процесс определения релевантности](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="89ac3-112">**Циклы оценки и отслеживания**:</span><span class="sxs-lookup"><span data-stu-id="89ac3-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="89ac3-113">**Оценка**: включает ранние оценки на основе случайного примера файлов и использует эту оценку для определения производительности процесса прогнозирующих кодов.</span><span class="sxs-lookup"><span data-stu-id="89ac3-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="89ac3-114">**Track**: вычисление и отображение промежуточных результатов оценки при наблюдении за статистическим действием процесса.</span><span class="sxs-lookup"><span data-stu-id="89ac3-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="89ac3-115">**Циклы обучения и отслеживания**</span><span class="sxs-lookup"><span data-stu-id="89ac3-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="89ac3-116">**Тег**: Advanced eDiscovery сведения об условиях релевантности для каждой из них, основанных на итеративной проверке и разметке отдельных файлов экспертом.</span><span class="sxs-lookup"><span data-stu-id="89ac3-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="89ac3-117">**Track**: вычисляет и отображает промежуточные результаты обучения релевантности при наблюдении за статистическим действием процесса.</span><span class="sxs-lookup"><span data-stu-id="89ac3-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="89ac3-118">**Вычисление пакетов**: критерии накопленного и полученного соответствия применяются ко всей коллекции файлов, а показатель релевантности создается для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="89ac3-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="89ac3-119">**Выбор**: результаты анализа, примененного ко всему случаю, отображаются после вычисления, и отображаются данные, используемые для принятия решений по рецензированию документов.</span><span class="sxs-lookup"><span data-stu-id="89ac3-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="89ac3-120">**Тест**: результаты можно проверить, чтобы проверить правильность и эффективность расширенной обработки обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="89ac3-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="89ac3-121">**Поиск**: после завершения рабочего процесса релевантности вы можете использовать такие выходные данные, как Read персентиль документа для вашего вопроса при выполнении запроса в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="89ac3-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="89ac3-122">Рекомендации по изучению и обзору релевантности</span><span class="sxs-lookup"><span data-stu-id="89ac3-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="89ac3-123">Ниже представлен обзор рекомендаций по изучению и проверке релевантности.</span><span class="sxs-lookup"><span data-stu-id="89ac3-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="89ac3-124">**Ошибки и несоответствия**. при возникновении ошибок тегирования в ходе обучения вернитесь к предыдущим примерам файлов, чтобы исправить их.</span><span class="sxs-lookup"><span data-stu-id="89ac3-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="89ac3-125">Если вы намерены слишком много ошибок или если у вас есть новая перспектива или ситуация, условия релевантности должны быть переопределены администратором и перезапущено обучение по релевантности.</span><span class="sxs-lookup"><span data-stu-id="89ac3-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="89ac3-126">**Маркировка и обучение**:</span><span class="sxs-lookup"><span data-stu-id="89ac3-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="89ac3-127">Файлы следует размечать только на основе контента.</span><span class="sxs-lookup"><span data-stu-id="89ac3-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="89ac3-128">Не учитывайте метаданные, такие как хранитель, дата или путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="89ac3-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="89ac3-129">Не учитывайте указания диапазона дат в тексте при разметке тегами файлов.</span><span class="sxs-lookup"><span data-stu-id="89ac3-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="89ac3-130">Не учитывайте внедренные графические изображения при разметке тегами файлов.</span><span class="sxs-lookup"><span data-stu-id="89ac3-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="89ac3-131">Игнорировать текст, примененный к релевантности, будет удален в отображаемом содержимом файла в текстовом представлении релевантность.</span><span class="sxs-lookup"><span data-stu-id="89ac3-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="89ac3-132">Если значения для параметра Ignore Text были определены после начала обучения соответствия, новый пропущенный текст будет применен к образцам файлов, созданным на основе точки, в которой он был определен.</span><span class="sxs-lookup"><span data-stu-id="89ac3-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="89ac3-133">Функция ignore Text должна использоваться с осторожностью, так как ее использование может привести к снижению производительности анализа файлов.</span><span class="sxs-lookup"><span data-stu-id="89ac3-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="89ac3-134">Используйте параметр **пропускать маркировку** , только если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="89ac3-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="89ac3-135">Расширенные функции обнаружения электронных данных не обучены на основе пропущенных файлов.</span><span class="sxs-lookup"><span data-stu-id="89ac3-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="89ac3-136">В процессе оценки, если трудно определить, является ли файл релевантным, лучше помечаться как соответствующий (R) или нет (НР), если это возможно, а не выбирать **пропустить**.</span><span class="sxs-lookup"><span data-stu-id="89ac3-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="89ac3-137">Когда Расширенное обнаружение электронных данных оценивает обучение, можно увидеть, насколько хорошо обрабатывались эти типы файлов.</span><span class="sxs-lookup"><span data-stu-id="89ac3-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="89ac3-138">Даже файлы с очень небольшим объемом извлеченного текста должны быть помечены как R/НР, а не как "Skip", когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="89ac3-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="89ac3-139">Расстановка тегов может повлиять на классификатор до тех пор, пока файл доступен для чтения и его можно пометить как R/НР.</span><span class="sxs-lookup"><span data-stu-id="89ac3-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="89ac3-140">Порядковый номер файла в списке отображаемых файлов на вкладке **тег** позволяет пользователю вернуться к исходному отображаемому порядку файлов.</span><span class="sxs-lookup"><span data-stu-id="89ac3-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="89ac3-141">Вы можете вернуться к любому примеру и изменить маркировку файлов оценки и учебного набора.</span><span class="sxs-lookup"><span data-stu-id="89ac3-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="89ac3-142">Изменения будут применены при создании следующего примера.</span><span class="sxs-lookup"><span data-stu-id="89ac3-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="89ac3-143">Отсканированные файлы Excel в формате PDF должны рассматриваться как собственные файлы Excel при разметке тегами файлов.</span><span class="sxs-lookup"><span data-stu-id="89ac3-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="89ac3-144">Если у вас есть сомнения относительно тегов релевантности файла, ознакомьтесь со статьей эксперта.</span><span class="sxs-lookup"><span data-stu-id="89ac3-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="89ac3-145">Неправильное расстановка тегов во время обучения несоответствия может привести к потере времени в процессе, а также может негативно повлиять на качество общих результатов.</span><span class="sxs-lookup"><span data-stu-id="89ac3-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="89ac3-146">Ключевые слова, определенные в списках ключевых слов, будут отображаться в цветах, чтобы помочь пользователю определить релевантные файлы при разметке тегами.</span><span class="sxs-lookup"><span data-stu-id="89ac3-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="89ac3-147">**Вычисление пакетов**: файлы, помеченные экспертом как R/НР, получат значение 0 или 100.</span><span class="sxs-lookup"><span data-stu-id="89ac3-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="89ac3-148">Это относится к разметке, выполненным перед вычислением пакетов.</span><span class="sxs-lookup"><span data-stu-id="89ac3-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="89ac3-149">Если эксперт переключился на неактивное после выполнения пакетного вычисления и размечает маркировку этой ситуации, то новые баллы не будут 100/0ся, а исходнее.</span><span class="sxs-lookup"><span data-stu-id="89ac3-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="89ac3-150">**Проблемы и режим выборки**: проблемы обычно отключаются при завершении работы над ними (проведено обучение по релевантности и выполнен пакетный пересчет), когда проблемы отменяются или когда другой пользователь работает над проблемами.</span><span class="sxs-lookup"><span data-stu-id="89ac3-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="89ac3-151">Этапы обучения</span><span class="sxs-lookup"><span data-stu-id="89ac3-151">Steps in Relevance training</span></span>

<span data-ttu-id="89ac3-152">На вкладке **Отслеживание \> релевантности** Расширенное обнаружение электронных данных содержит рекомендации относительно того, как продолжить обработку, со следующими действиями.</span><span class="sxs-lookup"><span data-stu-id="89ac3-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="89ac3-153">Эти следствия описаны ниже, когда рекомендуется выполнить каждое из следующих действий в процессе обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="89ac3-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="89ac3-154">Маркировка и продолжение маркировки: Проверка файлов и маркировка релевантности, выполненные экспертом для каждого файла и выпуска в рамках примера.</span><span class="sxs-lookup"><span data-stu-id="89ac3-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="89ac3-155">Результат: существующий пример должен быть помечен.</span><span class="sxs-lookup"><span data-stu-id="89ac3-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="89ac3-156">Оценка/продолжение оценки: включает начальную проверку релевантности с учетом регистра и предварительное представление релевантности заполнения файла, импортированного для текущего случая.</span><span class="sxs-lookup"><span data-stu-id="89ac3-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="89ac3-157">Результат: необходима дополнительная оценка или рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="89ac3-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="89ac3-158">Обучение и продолжение обучения: процесс, в ходе которого расширенные функции обнаружения электронных данных изучены от эксперта, который размечает образцы файлов и получает возможность определять условия релевантности, относящиеся к каждой из них в контексте каждого случая.</span><span class="sxs-lookup"><span data-stu-id="89ac3-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="89ac3-159">Результат: для этой задачи требуется дополнительное обучение; Следующий пример следует создать и пометить тегами.</span><span class="sxs-lookup"><span data-stu-id="89ac3-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="89ac3-160">Вычисление пакетов: процесс релевантности, в котором расширенные функции обнаружения электронных данных принимаются на этапе обучения и применяют его ко всему заполнению файла.</span><span class="sxs-lookup"><span data-stu-id="89ac3-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="89ac3-161">Все файлы в релевантной группе файлов оцениваются по релевантности и имеют показатель релевантности.</span><span class="sxs-lookup"><span data-stu-id="89ac3-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="89ac3-162">Результат: Эта ошибка вызвана, и можно выполнить пакетный пересчет.</span><span class="sxs-lookup"><span data-stu-id="89ac3-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="89ac3-163">При сопоставлении: релевантность указывает, что экспертная проверка и теги получит пример файлов, выбранных из дополнительной загрузки файлов во время поэтапной загрузки.</span><span class="sxs-lookup"><span data-stu-id="89ac3-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="89ac3-164">Результат: была добавлена новая нагрузка, и для продолжения работы требуется дополнительное обновление.</span><span class="sxs-lookup"><span data-stu-id="89ac3-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="89ac3-165">Несогласованности тегов: процесс идентифицирует, с помощью расширенного алгоритма обнаружения электронных данных, несогласованности в процессе тегирования файлов, которые могут негативно повлиять на анализ.</span><span class="sxs-lookup"><span data-stu-id="89ac3-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="89ac3-166">Результат: в следующем примере будут содержаться файлы, помеченные в предыдущих примерах, и их маркировку необходимо выполнить повторно.</span><span class="sxs-lookup"><span data-stu-id="89ac3-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="89ac3-167">Классификатор обновлений: позволяет пользователю применять теги и изменения заполнения.</span><span class="sxs-lookup"><span data-stu-id="89ac3-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="89ac3-168">Результат: изменения тегов и заполнения могут быть применены без необходимости вручную запускать еще один пример.</span><span class="sxs-lookup"><span data-stu-id="89ac3-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="89ac3-169">На удержании: процесс обучения соответствия завершен.</span><span class="sxs-lookup"><span data-stu-id="89ac3-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="89ac3-170">Результат: в этой точке не обязательно должно быть обучение по релевантности.</span><span class="sxs-lookup"><span data-stu-id="89ac3-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="89ac3-171">Несмотря на то, что Расширенное обнаружение электронных данных рассказывает о рекомендуемых дальнейших действиях на разных стадиях, она также позволяет переходить между вкладками и страницами, а также делать варианты для решения конкретных ситуаций, проблем или процессов рецензирования документов.</span><span class="sxs-lookup"><span data-stu-id="89ac3-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="89ac3-172">Можно принимать или переопределять дополнительные параметры обработки следующего этапа обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="89ac3-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="89ac3-173">Если вы хотите выполнить шаг, отличный от рекомендуемого, щелкните **следующий шаг** , приведенный в разделе Расширенная ошибка в диалоговом окне, нажмите кнопку **изменить** рядом с следующим шагом, а затем выберите другой параметр следующего шага.</span><span class="sxs-lookup"><span data-stu-id="89ac3-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="89ac3-174">Некоторые параметры могут быть отключены после снятия блокировки, так как они не поддерживаются в этой точке процесса.</span><span class="sxs-lookup"><span data-stu-id="89ac3-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="89ac3-175">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="89ac3-175">More information</span></span>

[<span data-ttu-id="89ac3-176">Понимание оценки релевантности</span><span class="sxs-lookup"><span data-stu-id="89ac3-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="89ac3-177">Маркировка и оценка</span><span class="sxs-lookup"><span data-stu-id="89ac3-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="89ac3-178">Расстановка тегов и релевантности</span><span class="sxs-lookup"><span data-stu-id="89ac3-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="89ac3-179">Анализ релевантности отслеживания</span><span class="sxs-lookup"><span data-stu-id="89ac3-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="89ac3-180">Выбор на основе результатов</span><span class="sxs-lookup"><span data-stu-id="89ac3-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="89ac3-181">Анализ релевантности тестирования</span><span class="sxs-lookup"><span data-stu-id="89ac3-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="89ac3-182">Запрос данных в наборе для проверки</span><span class="sxs-lookup"><span data-stu-id="89ac3-182">Query the data in a review set</span></span>](review-set-search.md)
