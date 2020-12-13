---
title: Просмотр результатов модуля процесса в Advanced eDiscovery
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: Узнайте, как найти результаты запуска модуля процесса в Advanced eDiscovery, включая состояние задачи и сводку по процессам.
ms.openlocfilehash: 73699d77e305055f6c2dc444fff00fb714b458cd
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663268"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="60e4d-103">Просмотр результатов модуля процесса в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="60e4d-103">View Process module results in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="60e4d-104">После  \> **инициации** процесса подготовки можно просмотреть ход выполнения и результаты.</span><span class="sxs-lookup"><span data-stu-id="60e4d-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="60e4d-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="60e4d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="60e4d-107">Состояние задачи обработки</span><span class="sxs-lookup"><span data-stu-id="60e4d-107">Process task status</span></span>

<span data-ttu-id="60e4d-108">В **области** \> **"Подготовка результатов** процесса" на странице отображается текущее состояние (если процесс запущен) или последнее состояние задачи состояния процесса, как показано в \> следующем примере.</span><span class="sxs-lookup"><span data-stu-id="60e4d-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![Состояние задач для модуля обработки](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="60e4d-110">Отображаемая задача может отличаться в зависимости от выбранных параметров процесса.</span><span class="sxs-lookup"><span data-stu-id="60e4d-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="60e4d-111">**Inventory**: Advanced eDiscovery выполняет итерации по всем файлам, выбранным для процесса, и выполняет базовое сбор данных.</span><span class="sxs-lookup"><span data-stu-id="60e4d-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="60e4d-112">**Расчет подписей:** вычисляет цифровые подписи MD5.</span><span class="sxs-lookup"><span data-stu-id="60e4d-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="60e4d-113">**Извлечение составных** данных: рекурсивно извлекает внутренние или содержащиеся файлы из составных файлов (например, PST, ZIP, MSG).</span><span class="sxs-lookup"><span data-stu-id="60e4d-113">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG).</span></span> <span data-ttu-id="60e4d-114">Извлеченные файлы хранятся в папке дела.</span><span class="sxs-lookup"><span data-stu-id="60e4d-114">Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="60e4d-115">**Синхронизация базы данных**: внутренний процесс базы данных.</span><span class="sxs-lookup"><span data-stu-id="60e4d-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="60e4d-116">**Копирование файлов:** копирует файлы процесса.</span><span class="sxs-lookup"><span data-stu-id="60e4d-116">**File copy**: Copies Process files.</span></span> <span data-ttu-id="60e4d-117">Эта задача всегда отображается, даже если выбран параметр "Расширенные файлы копирования".</span><span class="sxs-lookup"><span data-stu-id="60e4d-117">This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="60e4d-118">**Извлечение** текста: при нативных файлах Advanced eDiscovery извлекает текст из этих файлов с помощью DTSearch.</span><span class="sxs-lookup"><span data-stu-id="60e4d-118">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch.</span></span> <span data-ttu-id="60e4d-119">Извлеченный текст этих файлов хранится в виде текстовых файлов в папке дела.</span><span class="sxs-lookup"><span data-stu-id="60e4d-119">The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="60e4d-120">**Обновление метаданных:** обрабатывает загруженные метаданные.</span><span class="sxs-lookup"><span data-stu-id="60e4d-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="60e4d-121">**Завершение:** внутренняя обработка, которая завершает данные загруженных файлов дел (например, определение ошибок и файлов успешного завершения).</span><span class="sxs-lookup"><span data-stu-id="60e4d-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="60e4d-122">Состояние задачи: отображается после завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="60e4d-122">Task status: Displayed after task completion.</span></span> <span data-ttu-id="60e4d-123">Во время выполнения задач отображается продолжительность выполнения.</span><span class="sxs-lookup"><span data-stu-id="60e4d-123">While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60e4d-124">Завершенные задачи также могут включать итоги для файлов, которые завершили обработку, или файлы с ошибками.</span><span class="sxs-lookup"><span data-stu-id="60e4d-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="60e4d-125">«Отмена» предоставляет возможность отката, чтобы остановить выполнение процесса, а затем откатить к предыдущему набору данных или сохраненным обработанным данным.</span><span class="sxs-lookup"><span data-stu-id="60e4d-125">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data.</span></span> <span data-ttu-id="60e4d-126">Откат очищает все обработанные данные.</span><span class="sxs-lookup"><span data-stu-id="60e4d-126">Rollback clears all processed data.</span></span> <span data-ttu-id="60e4d-127">Если вы не хотите, чтобы обработанные данные были потеряны (например, вы планируете перезагрузить эти файлы), выберите в этом окне параметр "Отмена", чтобы не откатываться.</span><span class="sxs-lookup"><span data-stu-id="60e4d-127">If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="60e4d-128">Сводка по процессам</span><span class="sxs-lookup"><span data-stu-id="60e4d-128">Process summary</span></span>

<span data-ttu-id="60e4d-129">В сводке "Подготовка процесса результатов процесса" отображается разбивка результатов загруженных файлов в соответствии с результатами успешной обработки файлов и \> \> \> ошибками.</span><span class="sxs-lookup"><span data-stu-id="60e4d-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="60e4d-130">Области отображают графику импортируемой статистики файлов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="60e4d-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="60e4d-131">**Сводка процесса накапливает** d: все файлы в данном случае.</span><span class="sxs-lookup"><span data-stu-id="60e4d-131">**Process summary accumulate** d: All files in the case.</span></span>
    
- <span data-ttu-id="60e4d-132">**Сводка последнего процесса:** файлы, загруженные из последнего сеанса или действия.</span><span class="sxs-lookup"><span data-stu-id="60e4d-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="60e4d-133">**Фамилия**: сведения о фамилии в случае (если таковые есть).</span><span class="sxs-lookup"><span data-stu-id="60e4d-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="60e4d-134">Если **были** добавлены файлы seed, количество файлов с заданным количеством файлов будет указано для каждого вопроса.</span><span class="sxs-lookup"><span data-stu-id="60e4d-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="60e4d-135">Если не удалось **пометить файлы seed,** это также отмечено.</span><span class="sxs-lookup"><span data-stu-id="60e4d-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="60e4d-136">Если **добавлены предварительно** помеченные файлы, количество предварительно помеченных файлов будет указано для каждого вопроса, определенного для файлов.</span><span class="sxs-lookup"><span data-stu-id="60e4d-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="60e4d-137">Если не удалось  пометить предварительно помеченные файлы, это также отмечено.</span><span class="sxs-lookup"><span data-stu-id="60e4d-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![Сводка по модулю обработки](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="60e4d-139">Сводные сведения о процессах, собранные и последние диаграммы</span><span class="sxs-lookup"><span data-stu-id="60e4d-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="60e4d-140">На левой панели находятся исходные и извлеченные файлы— все найденные файлы.</span><span class="sxs-lookup"><span data-stu-id="60e4d-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="60e4d-141">Правая г., обработанная, включает:</span><span class="sxs-lookup"><span data-stu-id="60e4d-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="60e4d-142">Файлы с ошибками загрузки</span><span class="sxs-lookup"><span data-stu-id="60e4d-142">Files with load errors</span></span>
    
- <span data-ttu-id="60e4d-143">Успешно загруженные файлы, которые могут включать:</span><span class="sxs-lookup"><span data-stu-id="60e4d-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="60e4d-144">**Существующие**: файлы, которые были загружены до и теперь снова загружены (включая дубликаты).</span><span class="sxs-lookup"><span data-stu-id="60e4d-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="60e4d-145">**Текст:** уникальные файлы с текстом.</span><span class="sxs-lookup"><span data-stu-id="60e4d-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="60e4d-146">**Нетектовые:** пустые текстовые файлы, пустые текстовые файлы, нетексовые файлы.</span><span class="sxs-lookup"><span data-stu-id="60e4d-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="60e4d-147">**Дублирующиеся** файлы: дублирующиеся файлы с текстом.</span><span class="sxs-lookup"><span data-stu-id="60e4d-147">**Duplicate** s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="60e4d-148">Ошибки последнего процесса</span><span class="sxs-lookup"><span data-stu-id="60e4d-148">Last process errors</span></span>

<span data-ttu-id="60e4d-149">В области "Подготовка ошибок последнего процесса" отображаются сведения об ошибках последнего сеанса или \> \> \> выполненного действия.</span><span class="sxs-lookup"><span data-stu-id="60e4d-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![Ошибки модуля обработки](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="60e4d-151">См. также</span><span class="sxs-lookup"><span data-stu-id="60e4d-151">See also</span></span>

[<span data-ttu-id="60e4d-152">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="60e4d-152">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="60e4d-153">Запуск модуля процесса и загрузка данных</span><span class="sxs-lookup"><span data-stu-id="60e4d-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

