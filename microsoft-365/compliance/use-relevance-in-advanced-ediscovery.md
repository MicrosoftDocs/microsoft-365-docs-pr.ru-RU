---
title: Использование модуля релевантности в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: Узнайте о модуле релевантности в Advanced eDiscovery, включая рабочий процесс, рекомендации и инструкции по обучению и проверке файлов.
ms.openlocfilehash: 0319ac378fb891d96437f53931213429b111d61d
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663288"
---
# <a name="use-the-relevance-module-in-advanced-ediscovery-classic"></a><span data-ttu-id="ad30c-103">Использование модуля релевантности в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="ad30c-103">Use the Relevance module in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="ad30c-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="ad30c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ad30c-106">В Advanced eDiscovery модуль релевантности включает обучение релевантности и просмотр файлов, связанных с делом.</span><span class="sxs-lookup"><span data-stu-id="ad30c-106">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="ad30c-107">Рабочий процесс релевантности показан и описан следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ad30c-107">The Relevance workflow is shown and described as follows:</span></span>
  
![Рабочий процесс определения релевантности](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="ad30c-109">**Циклы оценки и отслеживания:**</span><span class="sxs-lookup"><span data-stu-id="ad30c-109">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="ad30c-110">**Оценка**: Advanced eDiscovery позволяет ранней оценки на основе случайного примера файлов и использует эту оценку для применения решений для определения производительности процесса прогнозирования кодирования.</span><span class="sxs-lookup"><span data-stu-id="ad30c-110">**Assessment**: Advanced eDiscovery enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="ad30c-111">**Track**: Advanced eDiscovery вычисляет и отображает промежуточные результаты оценки, отслеживая статистическую действительность процесса.</span><span class="sxs-lookup"><span data-stu-id="ad30c-111">**Track**: Advanced eDiscovery calculates and displays interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="ad30c-112">**Циклы обучения и отслеживания:**</span><span class="sxs-lookup"><span data-stu-id="ad30c-112">**Cycles of training and tracking**:</span></span>
    
  - <span data-ttu-id="ad30c-113">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span><span class="sxs-lookup"><span data-stu-id="ad30c-113">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="ad30c-114">**Track**: Advanced eDiscovery вычисляет и отображает промежуточные результаты обучения релевантности, отслеживая статистическую достоверность процесса.</span><span class="sxs-lookup"><span data-stu-id="ad30c-114">**Track**: Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="ad30c-115">**Пакетное** вычисление: Advanced eDiscovery принимает собранные и научившиеся критерии релевантности, применяет его ко всей коллекции файлов и создает оценки релевантности для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="ad30c-115">**Batch calculation**: Advanced eDiscovery takes the accumulated and learned Relevance criteria, applies it to the entire file collection, and generates Relevance scores for each file.</span></span>
    
- <span data-ttu-id="ad30c-116">**Принятие** решения: Advanced eDiscovery отображает результаты анализа, примененного для всего дела после пакетного вычисления, и отображает данные для принятия решений по проверке документов.</span><span class="sxs-lookup"><span data-stu-id="ad30c-116">**Decide**: Advanced eDiscovery displays the results of the analysis applied to the entire case after Batch calculation and displays data for making document review decisions.</span></span>
    
- <span data-ttu-id="ad30c-117">**Тест:** результаты Advanced eDiscovery можно проверить, чтобы проверить правильность и эффективность обработки Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ad30c-117">**Test**: Advanced eDiscovery results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="ad30c-118">Руководство по обучению и анализу релевантности</span><span class="sxs-lookup"><span data-stu-id="ad30c-118">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="ad30c-119">Ниже представлен обзор рекомендаций по обучению релевантности и проверке.</span><span class="sxs-lookup"><span data-stu-id="ad30c-119">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="ad30c-120">**Ошибки и несоответствия:** если во время обучения произошли ошибки тегирования, вернись к предыдущим примерам файлов, чтобы исправить их.</span><span class="sxs-lookup"><span data-stu-id="ad30c-120">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="ad30c-121">Если имеется слишком много ошибок для исправления или имеется новая перспектива по делу или проблеме, критерии релевантности должны быть переопределяться администратором, а обучение релевантности перезапущено.</span><span class="sxs-lookup"><span data-stu-id="ad30c-121">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="ad30c-122">**Добавление тегов и обучение:**</span><span class="sxs-lookup"><span data-stu-id="ad30c-122">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="ad30c-123">Файлы должны быть помечены только на основе контента.</span><span class="sxs-lookup"><span data-stu-id="ad30c-123">Files should be tagged based on content only.</span></span> <span data-ttu-id="ad30c-124">Не учитывайте метаданные, такие как хранители, дата или путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="ad30c-124">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="ad30c-125">Не учитывайте индикации диапазона дат в тексте при маркировке файлов.</span><span class="sxs-lookup"><span data-stu-id="ad30c-125">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="ad30c-126">Не учитывайте внедренные графические изображения при маркировке файлов.</span><span class="sxs-lookup"><span data-stu-id="ad30c-126">Do not consider embedded graphical images when tagging files.</span></span>
    
  - <span data-ttu-id="ad30c-127">При просмотре файла с помощью значка **форматирования** представления текста при маркировке не учитывайте форматирование текста.</span><span class="sxs-lookup"><span data-stu-id="ad30c-127">If viewing a file using the **formatted text view** icon while tagging, do not consider the formatting of text.</span></span> <span data-ttu-id="ad30c-128">Например, слово, отображающееся с зачерком (горизонтальная линия по центру, указывающая на удаление), по-прежнему рассматривается в релевантности как часть анализируемого текста.</span><span class="sxs-lookup"><span data-stu-id="ad30c-128">For example, a word displayed with a strikethrough (a horizontal line through its center indicating deletion) is still considered by Relevance as part of the analyzed text.</span></span> 
    
  - <span data-ttu-id="ad30c-129">Игнорируйте текст, примененный к релевантности (заданной руководителем дела или администратором), который будет удален в отображаемом содержимом файла в текстовом представлении "Релевантность".</span><span class="sxs-lookup"><span data-stu-id="ad30c-129">Ignore text applied to Relevance (as set by the Case Manager or Administrator) will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="ad30c-130">Если значения для текста Ignore были определены после того, как обучение релевантности уже запущено, новый игнорируемый текст будет применяться к примерам файлов, созданных с того момента, в котором он был определен.</span><span class="sxs-lookup"><span data-stu-id="ad30c-130">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="ad30c-131">Функцию "Игнорировать текст" следует использовать с осторожностью, так как ее использование может снизить производительность анализа файлов</span><span class="sxs-lookup"><span data-stu-id="ad30c-131">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="ad30c-132">Используйте параметр **пропуска тегов** только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="ad30c-132">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="ad30c-133">Advanced eDiscovery не обучается на основе пропущенных файлов.</span><span class="sxs-lookup"><span data-stu-id="ad30c-133">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="ad30c-134">В оценке, если сложно определить, является ли файл релевантной, лучше пометить как релевантный (R) или "Не релевантный" (NR), когда это возможно, а не выбирать **"Пропустить".**</span><span class="sxs-lookup"><span data-stu-id="ad30c-134">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="ad30c-135">Когда Advanced eDiscovery оценивает обучение, можно увидеть, насколько хорошо эти типы файлов были обработаны.</span><span class="sxs-lookup"><span data-stu-id="ad30c-135">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="ad30c-136">Даже файлы с очень небольшим количеством извлеченного текста следует пометить при обучении как R/NR, а не как "Пропустить", когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="ad30c-136">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="ad30c-137">Добавление тегов может повлиять на классификатор, если файл является читаемым и может быть помечен как R/NR.</span><span class="sxs-lookup"><span data-stu-id="ad30c-137">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="ad30c-138">Номер последовательности файлов в отображаемом  списке примеров файлов на вкладке "Тег" позволяет пользователю вернуться в исходный порядок отображения файлов.</span><span class="sxs-lookup"><span data-stu-id="ad30c-138">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="ad30c-139">Вы можете вернуться к любому примеру и изменить маркировку файлов набора для оценки и обучения.</span><span class="sxs-lookup"><span data-stu-id="ad30c-139">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="ad30c-140">Изменения будут применены при создании следующего примера.</span><span class="sxs-lookup"><span data-stu-id="ad30c-140">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="ad30c-141">Отсканированные файлы Excel в формате PDF должны рассматриваться так же, как и встроенные файлы Excel при маркировке файлов.</span><span class="sxs-lookup"><span data-stu-id="ad30c-141">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="ad30c-142">Если есть сомнения относительно тегов релевантности файла, обратитесь к эксперту.</span><span class="sxs-lookup"><span data-stu-id="ad30c-142">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="ad30c-143">Неправильное добавление тегов во время обучения релевантности может привести к потерям времени в процессе и также негативно повлиять на качество общих результатов.</span><span class="sxs-lookup"><span data-stu-id="ad30c-143">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="ad30c-144">Ключевые слова, определенные в списках ключевых слов, будут отображаться в цветах, чтобы помочь пользователю определить соответствующие файлы при маркировке.</span><span class="sxs-lookup"><span data-stu-id="ad30c-144">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="ad30c-145">**Пакетное** вычисление: файлы, помеченные экспертом как R/NR, получат оценку 0 или 100.</span><span class="sxs-lookup"><span data-stu-id="ad30c-145">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="ad30c-146">Это относится к тегированию, выполненной до вычисления пакета.</span><span class="sxs-lookup"><span data-stu-id="ad30c-146">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="ad30c-147">Если эксперт переключил проблему на "Бездействие" после пакетного вычисления и продолжал помечать эту проблему, новые помеченные оценки будут не 100/0, а исходный показатель.</span><span class="sxs-lookup"><span data-stu-id="ad30c-147">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="ad30c-148">**Проблемы** и режим выборки: проблемы обычно отключаются, когда работа над ними завершена (обучение релевантности стабилизируется и выполняется пакетное вычисление), отмена проблем или когда другой пользователь работает над ошибками.</span><span class="sxs-lookup"><span data-stu-id="ad30c-148">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="ad30c-149">Этапы обучения релевантности</span><span class="sxs-lookup"><span data-stu-id="ad30c-149">Steps in Relevance training</span></span>

<span data-ttu-id="ad30c-150">На **вкладке \> "Отслеживание** релевантности" advanced eDiscovery предоставляет рекомендации о том, как перейти к обработке, а также следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ad30c-150">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="ad30c-151">Последствия описаны ниже, когда в процессе обучения релевантности рекомендуется каждый из следующих этапов.</span><span class="sxs-lookup"><span data-stu-id="ad30c-151">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="ad30c-152">Добавление тегов и продолжение тегов: анализ файлов и добавление тегов релевантности, выполняемые экспертом для каждого файла и проблемы в примере.</span><span class="sxs-lookup"><span data-stu-id="ad30c-152">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="ad30c-153">Последствие: существующий пример необходимо пометить.</span><span class="sxs-lookup"><span data-stu-id="ad30c-153">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="ad30c-154">Оценка и продолжение оценки: позволяет на ранних стадиях проверки релевантности вопросов дела и предварительного представления релевантности импортируемого для текущего случая файла.</span><span class="sxs-lookup"><span data-stu-id="ad30c-154">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="ad30c-155">Последствие. Требуется или рекомендуется больше оценки.</span><span class="sxs-lookup"><span data-stu-id="ad30c-155">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="ad30c-156">Обучение и продолжение обучения: процесс, в ходе которого Advanced eDiscovery узнает от эксперта, который помечает образцы файлов и получает возможность определять критерии релевантности, которые соответствуют каждой проблеме в контексте каждого случая.</span><span class="sxs-lookup"><span data-stu-id="ad30c-156">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="ad30c-157">Последствие: вопрос требует дополнительной подготовки; Следующий пример должен быть создан и помечен.</span><span class="sxs-lookup"><span data-stu-id="ad30c-157">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="ad30c-158">Пакетное вычисление: процесс релевантности, в ходе которого Advanced eDiscovery принимает знания, полученные на этапе обучения, и применяет их ко всем файлам.</span><span class="sxs-lookup"><span data-stu-id="ad30c-158">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="ad30c-159">Все файлы в релевантной группе файлов оцениваются на релевантность и имеют оценку релевантности.</span><span class="sxs-lookup"><span data-stu-id="ad30c-159">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="ad30c-160">Последствие: проблема стабилизируется, и можно выполнить пакетное вычисление.</span><span class="sxs-lookup"><span data-stu-id="ad30c-160">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="ad30c-161">Дополнительная информация: релевантность указывает, когда эксперт проверяет и помечает пример файлов, выбранных из дополнительной нагрузки файла во время сценария rolling Loads.</span><span class="sxs-lookup"><span data-stu-id="ad30c-161">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="ad30c-162">Последствие: добавлена новая нагрузка, и для продолжения работы требуется дополнительное время.</span><span class="sxs-lookup"><span data-stu-id="ad30c-162">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="ad30c-163">Несоответствия тегов: процесс определяет с помощью алгоритма Advanced eDiscovery несоответствия в процессе маркировки файлов, которые могут отрицательно повлиять на анализ.</span><span class="sxs-lookup"><span data-stu-id="ad30c-163">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="ad30c-164">Последствие: следующий пример будет включать файлы, помеченные в предыдущих примерах, и их теги должны быть перео присвоены.</span><span class="sxs-lookup"><span data-stu-id="ad30c-164">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="ad30c-165">Классификатор обновления: позволяет пользователю применять изменения тегов или занесения.</span><span class="sxs-lookup"><span data-stu-id="ad30c-165">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="ad30c-166">Последствие: изменения тегов и занесения можно применять без необходимости запускать вручную другой пример релевантности.</span><span class="sxs-lookup"><span data-stu-id="ad30c-166">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="ad30c-167">На удержании: процесс обучения релевантности завершен.</span><span class="sxs-lookup"><span data-stu-id="ad30c-167">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="ad30c-168">Последствие. На этом этапе обучение релевантности не требуется.</span><span class="sxs-lookup"><span data-stu-id="ad30c-168">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="ad30c-169">Несмотря на то что Advanced eDiscovery позволяет вам пройти этот процесс, с рекомендуемой следующей процедурой на разных этапах, она также позволяет переходить между вкладками и страницами, а также принимать решения для решения ситуаций, которые могут быть убытны в вашем отдельном случае, проблеме или процессе проверки документов.</span><span class="sxs-lookup"><span data-stu-id="ad30c-169">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="ad30c-170">Можно принимать или переопределять варианты обработки дополнительных этапов eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ad30c-170">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="ad30c-171">Если вы хотите выполнить не рекомендуемый следующий шаг, нажмите кнопку "Далее", указанную  в расширенном отображите проблему, нажмите кнопку "Изменить" рядом с шагом "Далее" и выберите другой параметр "Далее". </span><span class="sxs-lookup"><span data-stu-id="ad30c-171">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ad30c-172">Некоторые параметры могут оставаться отключенными после разблокировки, так как они не поддерживаются на этом этапе процесса.</span><span class="sxs-lookup"><span data-stu-id="ad30c-172">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ad30c-173">См. также</span><span class="sxs-lookup"><span data-stu-id="ad30c-173">See also</span></span>

[<span data-ttu-id="ad30c-174">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="ad30c-174">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ad30c-175">Понимание оценки релевантности</span><span class="sxs-lookup"><span data-stu-id="ad30c-175">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ad30c-176">Добавление тегов и оценка</span><span class="sxs-lookup"><span data-stu-id="ad30c-176">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ad30c-177">Обучение тегам и релевантности</span><span class="sxs-lookup"><span data-stu-id="ad30c-177">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ad30c-178">Отслеживание анализа релевантности</span><span class="sxs-lookup"><span data-stu-id="ad30c-178">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ad30c-179">Выбор на основе результатов</span><span class="sxs-lookup"><span data-stu-id="ad30c-179">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ad30c-180">Тестирование анализа релевантности</span><span class="sxs-lookup"><span data-stu-id="ad30c-180">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

