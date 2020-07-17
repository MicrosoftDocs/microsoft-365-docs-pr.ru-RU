---
title: Просмотр модуля обработки результатов для расширенного обнаружения электронных данных
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: Узнайте, как найти результаты работы модуля процесса в Advanced eDiscovery, в том числе состояние задачи и сводка по процессу.
ms.openlocfilehash: 26ef87c762fc5c77f2374978bf4a425940dd5f37
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936172"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="f176c-103">Просмотр модуля обработки результатов в Advanced eDiscovery (классический)</span><span class="sxs-lookup"><span data-stu-id="f176c-103">View Process module results in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="f176c-104">После **Prepare** \> запуска **процесса** подготовки можно просмотреть ход выполнения и результаты.</span><span class="sxs-lookup"><span data-stu-id="f176c-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f176c-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="f176c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="f176c-107">Состояние задачи процесса</span><span class="sxs-lookup"><span data-stu-id="f176c-107">Process task status</span></span>

<span data-ttu-id="f176c-108">В окне **Подготовка** \> **Process** \> **результатов**процесса на странице отображается текущее состояние (если процесс в данный момент выполняется) или состояние последней задачи состояния процесса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f176c-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![Состояние задач для модуля обработки](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="f176c-110">Отображаемые задачи могут различаться в зависимости от выбранных параметров процесса.</span><span class="sxs-lookup"><span data-stu-id="f176c-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="f176c-111">**Inventory**: Advanced eDiscovery просматривает все файлы, выбранные для обработки, и выполняет базовую сбор данных.</span><span class="sxs-lookup"><span data-stu-id="f176c-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="f176c-112">**Рассчитать подписи**: вычисляет цифровые подписи MD5.</span><span class="sxs-lookup"><span data-stu-id="f176c-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="f176c-113">**Извлечение**составных элементов: рекурсивно извлекает внутренние или вложенные файлы из составных файлов (например, PST, ZIP, MSG).</span><span class="sxs-lookup"><span data-stu-id="f176c-113">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG).</span></span> <span data-ttu-id="f176c-114">Извлеченные файлы хранятся в папке для случая.</span><span class="sxs-lookup"><span data-stu-id="f176c-114">Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="f176c-115">**Синхронизация базы данных**: внутренний процесс базы данных.</span><span class="sxs-lookup"><span data-stu-id="f176c-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="f176c-116">**Копирование файлов**: копирование файлов процесса.</span><span class="sxs-lookup"><span data-stu-id="f176c-116">**File copy**: Copies Process files.</span></span> <span data-ttu-id="f176c-117">Эта задача всегда отображается, даже если выбран параметр Дополнительные файлы копирования файлов.</span><span class="sxs-lookup"><span data-stu-id="f176c-117">This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="f176c-118">**Извлечение текста**: при наличии собственных файлов Расширенное обнаружение электронных данных извлекает текст из этих файлов с помощью дтсеарч.</span><span class="sxs-lookup"><span data-stu-id="f176c-118">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch.</span></span> <span data-ttu-id="f176c-119">Извлеченный текст этих файлов хранится в виде текстовых файлов в папке "обращение".</span><span class="sxs-lookup"><span data-stu-id="f176c-119">The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="f176c-120">**Обновление метаданных**: обрабатывает загруженные метаданные.</span><span class="sxs-lookup"><span data-stu-id="f176c-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="f176c-121">**Завершение**: Внутренняя обработка, которая завершает данные загруженных файлов (например, выявление файлов ошибок и успехов).</span><span class="sxs-lookup"><span data-stu-id="f176c-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="f176c-122">Состояние задачи: отображается после завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="f176c-122">Task status: Displayed after task completion.</span></span> <span data-ttu-id="f176c-123">Во время выполнения задач отображается длительность выполнения.</span><span class="sxs-lookup"><span data-stu-id="f176c-123">While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f176c-124">Завершенные задачи также могут включать в себя итоговые значения для файлов, которые завершили обработку, или файлы с ошибками.</span><span class="sxs-lookup"><span data-stu-id="f176c-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="f176c-125">"Cancel" предоставляет параметр отката для остановки выполнения процесса, а затем выполняет откат до предыдущего заполнения данных или сохраненных обработанных данных.</span><span class="sxs-lookup"><span data-stu-id="f176c-125">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data.</span></span> <span data-ttu-id="f176c-126">ROLLBACK — удаляет все обработанные данные.</span><span class="sxs-lookup"><span data-stu-id="f176c-126">Rollback clears all processed data.</span></span> <span data-ttu-id="f176c-127">Если вы не хотите, чтобы обработанные данные не были утрачены (например, вы планируете перегрузить эти файлы), выберите пункт "Отмена" в этом окне, чтобы отменить откат.</span><span class="sxs-lookup"><span data-stu-id="f176c-127">If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="f176c-128">Сводка по процессу</span><span class="sxs-lookup"><span data-stu-id="f176c-128">Process summary</span></span>

<span data-ttu-id="f176c-129">В \> \> \> сводке по процессу подготовки результатов процесса подразделение результатов загруженных файлов отображается в соответствии с успешными обработкой файлов и результатами ошибок.</span><span class="sxs-lookup"><span data-stu-id="f176c-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="f176c-130">В областях отображается графическое представление статистики импортированных файлов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f176c-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="f176c-131">**Сводка по процессу накопления**d: все файлы в случае.</span><span class="sxs-lookup"><span data-stu-id="f176c-131">**Process summary accumulate**d: All files in the case.</span></span>
    
- <span data-ttu-id="f176c-132">**Сводка по процессу в последнюю очередь**: файлы, загруженные из последнего сеанса или действия.</span><span class="sxs-lookup"><span data-stu-id="f176c-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="f176c-133">**Последние семейства**: сведения о семье в случае, если они есть.</span><span class="sxs-lookup"><span data-stu-id="f176c-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="f176c-134">Если были добавлены **начальные** файлы, число начальных файлов перечислено для каждого вопроса, определенного для файлов.</span><span class="sxs-lookup"><span data-stu-id="f176c-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="f176c-135">Если не удалось отмечать **начальные** файлы, также указано другое.</span><span class="sxs-lookup"><span data-stu-id="f176c-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="f176c-136">Если **предварительно помеченные** файлы были добавлены, то количество файлов, помеченных до пометки, отображается для каждого вопроса, определенного для файлов.</span><span class="sxs-lookup"><span data-stu-id="f176c-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="f176c-137">Если не удалось отмечать файлы, **помеченные** как отмеченные, это также отмечается.</span><span class="sxs-lookup"><span data-stu-id="f176c-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![Сводка по модулю обработки](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="f176c-139">Сводка по процессу собранные и последние диаграммы</span><span class="sxs-lookup"><span data-stu-id="f176c-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="f176c-140">В левой панели содержатся файлы источник и извлеченные файлы: все найденные файлы.</span><span class="sxs-lookup"><span data-stu-id="f176c-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="f176c-141">Правая черта, которая обрабатывается, включает:</span><span class="sxs-lookup"><span data-stu-id="f176c-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="f176c-142">Файлы с ошибками загрузки</span><span class="sxs-lookup"><span data-stu-id="f176c-142">Files with load errors</span></span>
    
- <span data-ttu-id="f176c-143">Успешно загружены файлы, которые могут включать:</span><span class="sxs-lookup"><span data-stu-id="f176c-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="f176c-144">**Existing**: файлы, которые были загружены ранее и теперь загружаются повторно (в том числе дубликаты).</span><span class="sxs-lookup"><span data-stu-id="f176c-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="f176c-145">**Text**: уникальные файлы с текстом.</span><span class="sxs-lookup"><span data-stu-id="f176c-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="f176c-146">**Нетекст**: пустые текстовые файлы, пустые файлы в машинном коде, а не текстовые файлы.</span><span class="sxs-lookup"><span data-stu-id="f176c-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="f176c-147">**Дубликат**s: повторяющиеся файлы с текстом.</span><span class="sxs-lookup"><span data-stu-id="f176c-147">**Duplicate**s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="f176c-148">Ошибки последней обработки</span><span class="sxs-lookup"><span data-stu-id="f176c-148">Last process errors</span></span>

<span data-ttu-id="f176c-149">В \> процессе подготовки \> процесса \> отображаются ошибки последней обработки, сведения об ошибках в последнем сеансе или выполненных действиях.</span><span class="sxs-lookup"><span data-stu-id="f176c-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![Ошибки модуля обработки](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="f176c-151">См. также</span><span class="sxs-lookup"><span data-stu-id="f176c-151">See also</span></span>

[<span data-ttu-id="f176c-152">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="f176c-152">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f176c-153">Запуск модуля Process и загрузка данных</span><span class="sxs-lookup"><span data-stu-id="f176c-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

