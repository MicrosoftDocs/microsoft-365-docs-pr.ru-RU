---
title: Использование модуля релевантности для анализа данных в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как модуль релевантности анализирует данные в свидетельстве с описанием рабочего процесса релевантности и учебных шагов в Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286065"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="5f844-103">Использование модуля релевантности для анализа данных в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5f844-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="5f844-104">В Advanced eDiscovery модуль релевантности включает обучение релевантности и просмотр файлов, связанных с делом.</span><span class="sxs-lookup"><span data-stu-id="5f844-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="5f844-105">Чтобы использовать рабочий процесс релевантности, перейдите в "Управление набором проверки" в наборе для проверки и нажмите кнопку "Показать релевантность".</span><span class="sxs-lookup"><span data-stu-id="5f844-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="5f844-106">Перед запуском рабочего процесса необходимо выполнить несколько действий.</span><span class="sxs-lookup"><span data-stu-id="5f844-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="5f844-107">Процесс: каждый набор нагрузки, добавленный в набор для проверки, будет отозжен в качестве "контейнера" здесь.</span><span class="sxs-lookup"><span data-stu-id="5f844-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="5f844-108">Необходимо обработать эти документы, прежде чем добавлять их в модуль релевантности; Здесь также можно пометить их как seed или предварительно помеченные для определенной проблемы.</span><span class="sxs-lookup"><span data-stu-id="5f844-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="5f844-109">Добавление к релевантности. При загрузках релевантности можно добавлять документы, которые были обработаны, в релевантность, чтобы сделать их \> доступными для обучения.</span><span class="sxs-lookup"><span data-stu-id="5f844-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="5f844-110">Рабочий процесс релевантности показан и описан следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5f844-110">The Relevance workflow is shown and described as follows:</span></span>
  
![Рабочий процесс определения релевантности](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="5f844-112">**Циклы оценки и отслеживания:**</span><span class="sxs-lookup"><span data-stu-id="5f844-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="5f844-113">**Оценка**: включает ранняя оценка на основе случайного примера файлов и использует эту оценку для применения решений для определения производительности процесса прогнозирования кодирования.</span><span class="sxs-lookup"><span data-stu-id="5f844-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="5f844-114">**Отслеживание:** вычисляйте и отображайте промежуточные результаты оценки, отслеживая статистическую действительность процесса.</span><span class="sxs-lookup"><span data-stu-id="5f844-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="5f844-115">**Циклы обучения и отслеживания**</span><span class="sxs-lookup"><span data-stu-id="5f844-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="5f844-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span><span class="sxs-lookup"><span data-stu-id="5f844-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="5f844-117">**Отслеживание:** расчет и отображение промежуточных результатов обучения релевантности при мониторинге статистической действительности процесса.</span><span class="sxs-lookup"><span data-stu-id="5f844-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="5f844-118">**Пакетное вычисление:** собранные и полученные критерии релевантности применяются во всей коллекции файлов, и для каждого файла создается оценка релевантности.</span><span class="sxs-lookup"><span data-stu-id="5f844-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="5f844-119">**Решите:** результаты анализа, примененного для всего дела, отображаются после пакетного вычисления, а также отображаются данные, используемые для принятия решений о проверке документов.</span><span class="sxs-lookup"><span data-stu-id="5f844-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="5f844-120">**Тест:** результаты можно протестировать, чтобы проверить правильность и эффективность обработки Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="5f844-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="5f844-121">**Поиск:** после завершения рабочего процесса релевантности можно использовать выходные данные, такие как процентиль чтения документа для вашей проблемы при запуске запроса в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="5f844-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="5f844-122">Руководство по обучению и анализу релевантности</span><span class="sxs-lookup"><span data-stu-id="5f844-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="5f844-123">Ниже представлен обзор рекомендаций по обучению релевантности и проверке.</span><span class="sxs-lookup"><span data-stu-id="5f844-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="5f844-124">**Ошибки и несоответствия:** если во время обучения произошли ошибки тегирования, вернись к предыдущим примерам файлов, чтобы исправить их.</span><span class="sxs-lookup"><span data-stu-id="5f844-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="5f844-125">Если имеется слишком много ошибок для исправления или имеется новая перспектива по делу или проблеме, критерии релевантности должны быть переопределяться администратором, а обучение релевантности перезапущено.</span><span class="sxs-lookup"><span data-stu-id="5f844-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="5f844-126">**Добавление тегов и обучение:**</span><span class="sxs-lookup"><span data-stu-id="5f844-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="5f844-127">Файлы должны быть помечены только на основе контента.</span><span class="sxs-lookup"><span data-stu-id="5f844-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="5f844-128">Не учитывайте метаданные, такие как хранители, дата или путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="5f844-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="5f844-129">Не учитывайте индикации диапазона дат в тексте при маркировке файлов.</span><span class="sxs-lookup"><span data-stu-id="5f844-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="5f844-130">Не учитывайте внедренные графические изображения при маркировке файлов.</span><span class="sxs-lookup"><span data-stu-id="5f844-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="5f844-131">Текст, примененный к релевантности, будет удален в отображаемом содержимом файла в текстовом представлении "Релевантность".</span><span class="sxs-lookup"><span data-stu-id="5f844-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="5f844-132">Если значения для текста Ignore были определены после того, как обучение релевантности уже запущено, новый игнорируемый текст будет применяться к примерам файлов, созданных с того момента, в котором он был определен.</span><span class="sxs-lookup"><span data-stu-id="5f844-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="5f844-133">Функцию "Игнорировать текст" следует использовать с осторожностью, так как ее использование может снизить производительность анализа файлов</span><span class="sxs-lookup"><span data-stu-id="5f844-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="5f844-134">Используйте параметр **пропуска тегов** только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="5f844-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="5f844-135">Advanced eDiscovery не обучается на основе пропущенных файлов.</span><span class="sxs-lookup"><span data-stu-id="5f844-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="5f844-136">В оценке, если сложно определить, является ли файл релевантной, лучше пометить как релевантный (R) или "Не релевантный" (NR), когда это возможно, а не выбирать **"Пропустить".**</span><span class="sxs-lookup"><span data-stu-id="5f844-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="5f844-137">Когда Advanced eDiscovery оценивает обучение, можно увидеть, насколько хорошо эти типы файлов были обработаны.</span><span class="sxs-lookup"><span data-stu-id="5f844-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="5f844-138">Даже файлы с очень небольшим количеством извлеченного текста следует пометить при обучении как R/NR, а не как "Пропустить", когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="5f844-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="5f844-139">Добавление тегов может повлиять на классификатор, если файл является читаемым и может быть помечен как R/NR.</span><span class="sxs-lookup"><span data-stu-id="5f844-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="5f844-140">Номер последовательности файлов в отображаемом  списке примеров файлов на вкладке "Тег" позволяет пользователю вернуться в исходный порядок отображения файлов.</span><span class="sxs-lookup"><span data-stu-id="5f844-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="5f844-141">Вы можете вернуться к любому примеру и изменить маркировку файлов набора для оценки и обучения.</span><span class="sxs-lookup"><span data-stu-id="5f844-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="5f844-142">Изменения будут применены при создании следующего примера.</span><span class="sxs-lookup"><span data-stu-id="5f844-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="5f844-143">Отсканированные файлы Excel в формате PDF должны рассматриваться так же, как и встроенные файлы Excel при маркировке файлов.</span><span class="sxs-lookup"><span data-stu-id="5f844-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="5f844-144">Если есть сомнения относительно тегов релевантности файла, обратитесь к эксперту.</span><span class="sxs-lookup"><span data-stu-id="5f844-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="5f844-145">Неправильное добавление тегов во время обучения релевантности может привести к потерям времени в процессе и также негативно повлиять на качество общих результатов.</span><span class="sxs-lookup"><span data-stu-id="5f844-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="5f844-146">Ключевые слова, определенные в списках ключевых слов, будут отображаться в цветах, чтобы помочь пользователю определить соответствующие файлы при маркировке.</span><span class="sxs-lookup"><span data-stu-id="5f844-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="5f844-147">**Пакетное** вычисление: файлы, помеченные экспертом как R/NR, получат оценку 0 или 100.</span><span class="sxs-lookup"><span data-stu-id="5f844-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="5f844-148">Это относится к тегированию, выполненной до вычисления пакета.</span><span class="sxs-lookup"><span data-stu-id="5f844-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="5f844-149">Если эксперт переключил проблему на "Бездействие" после пакетного вычисления и продолжал помечать эту проблему, новые помеченные оценки будут не 100/0, а исходный показатель.</span><span class="sxs-lookup"><span data-stu-id="5f844-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="5f844-150">**Проблемы** и режим выборки: проблемы обычно отключаются, когда работа над ними завершена (обучение релевантности стабилизируется и выполняется пакетное вычисление), отмена проблем или когда другой пользователь работает над ошибками.</span><span class="sxs-lookup"><span data-stu-id="5f844-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="5f844-151">Этапы обучения релевантности</span><span class="sxs-lookup"><span data-stu-id="5f844-151">Steps in Relevance training</span></span>

<span data-ttu-id="5f844-152">На **вкладке \> "Отслеживание** релевантности" advanced eDiscovery предоставляет рекомендации о том, как перейти к обработке, а также следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5f844-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="5f844-153">Последствия описаны ниже, когда в процессе обучения релевантности рекомендуется каждый из следующих этапов.</span><span class="sxs-lookup"><span data-stu-id="5f844-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="5f844-154">Добавление тегов и продолжение тегов: анализ файлов и добавление тегов релевантности, выполняемые экспертом для каждого файла и проблемы в примере.</span><span class="sxs-lookup"><span data-stu-id="5f844-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="5f844-155">Последствие: существующий пример необходимо пометить.</span><span class="sxs-lookup"><span data-stu-id="5f844-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="5f844-156">Оценка и продолжение оценки: позволяет на ранних стадиях проверки релевантности вопросов дела и предварительного представления релевантности импортируемого для текущего случая файла.</span><span class="sxs-lookup"><span data-stu-id="5f844-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="5f844-157">Последствие. Требуется или рекомендуется больше оценки.</span><span class="sxs-lookup"><span data-stu-id="5f844-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="5f844-158">Обучение и продолжение обучения: процесс, в ходе которого Advanced eDiscovery узнает от эксперта, который помечает образцы файлов и получает возможность определять критерии релевантности, которые соответствуют каждой проблеме в контексте каждого дела.</span><span class="sxs-lookup"><span data-stu-id="5f844-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="5f844-159">Последствие: вопрос требует дополнительной подготовки; Следующий пример должен быть создан и помечен.</span><span class="sxs-lookup"><span data-stu-id="5f844-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="5f844-160">Пакетное вычисление: процесс релевантности, в ходе которого Advanced eDiscovery принимает знания, полученные на этапе обучения, и применяет их ко всем файлам.</span><span class="sxs-lookup"><span data-stu-id="5f844-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="5f844-161">Все файлы в соответствующие группы файлов оцениваются на релевантность и присвоены оценки релевантности.</span><span class="sxs-lookup"><span data-stu-id="5f844-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="5f844-162">Последствие: проблема стабилизируется, и можно выполнить пакетное вычисление.</span><span class="sxs-lookup"><span data-stu-id="5f844-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="5f844-163">Дополнительная информация: релевантность указывает, когда эксперт проверяет и помечает пример файлов, выбранных из дополнительной нагрузки файла во время сценария rolling Loads.</span><span class="sxs-lookup"><span data-stu-id="5f844-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="5f844-164">Последствие: добавлена новая нагрузка, и для продолжения работы требуется дополнительное время.</span><span class="sxs-lookup"><span data-stu-id="5f844-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="5f844-165">Несоответствия тегов: процесс определяет с помощью алгоритма Advanced eDiscovery несоответствия в процессе маркировки файлов, которые могут отрицательно повлиять на анализ.</span><span class="sxs-lookup"><span data-stu-id="5f844-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="5f844-166">Последствие: следующий пример будет включать файлы, помеченные в предыдущих примерах, и их теги должны быть перео присвоены.</span><span class="sxs-lookup"><span data-stu-id="5f844-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="5f844-167">Классификатор обновления: позволяет пользователю применять изменения тегов или занесения.</span><span class="sxs-lookup"><span data-stu-id="5f844-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="5f844-168">Последствие. Изменения тегов и занесения можно применить без необходимости запускать вручную другой пример релевантности.</span><span class="sxs-lookup"><span data-stu-id="5f844-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="5f844-169">На удержании: процесс обучения релевантности завершен.</span><span class="sxs-lookup"><span data-stu-id="5f844-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="5f844-170">Последствие. На этом этапе обучение релевантности не требуется.</span><span class="sxs-lookup"><span data-stu-id="5f844-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="5f844-171">Несмотря на то что Advanced eDiscovery позволяет вам пройти этот процесс, с рекомендуемой следующей процедурой на разных этапах, она также позволяет переходить между вкладками и страницами, а также принимать решения для решения ситуаций, которые могут быть убытны в вашем отдельном случае, проблеме или процессе проверки документов.</span><span class="sxs-lookup"><span data-stu-id="5f844-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="5f844-172">Можно принять или переопредить варианты обработки шага Advanced eDiscovery Next.</span><span class="sxs-lookup"><span data-stu-id="5f844-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="5f844-173">Если вы хотите выполнить не рекомендуемый следующий шаг, нажмите кнопку "Далее", указанную  в расширенном отображите проблему, нажмите кнопку "Изменить" рядом с шагом "Далее" и выберите другой параметр "Далее". </span><span class="sxs-lookup"><span data-stu-id="5f844-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5f844-174">Некоторые параметры могут оставаться отключенными после разблокировки, так как они не поддерживаются на этом этапе процесса.</span><span class="sxs-lookup"><span data-stu-id="5f844-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="5f844-175">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="5f844-175">More information</span></span>

[<span data-ttu-id="5f844-176">Оценка релевантности</span><span class="sxs-lookup"><span data-stu-id="5f844-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5f844-177">Добавление тегов и оценка</span><span class="sxs-lookup"><span data-stu-id="5f844-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5f844-178">Обучение тегам и релевантности</span><span class="sxs-lookup"><span data-stu-id="5f844-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5f844-179">Отслеживание анализа релевантности</span><span class="sxs-lookup"><span data-stu-id="5f844-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5f844-180">Выбор на основе результатов</span><span class="sxs-lookup"><span data-stu-id="5f844-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5f844-181">Тестирование анализа релевантности</span><span class="sxs-lookup"><span data-stu-id="5f844-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="5f844-182">Запрос данных в наборе для проверки</span><span class="sxs-lookup"><span data-stu-id="5f844-182">Query the data in a review set</span></span>](review-set-search.md)
