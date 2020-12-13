---
title: Запуск модуля "Процесс" в Advanced eDiscovery
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
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: Рекомендации по подготовке файлов дел данных для анализа с помощью Advanced eDiscovery.
ms.openlocfilehash: 3773833d9d0af993b4ccb35bcd18276800c4081f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662814"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a><span data-ttu-id="eb2ef-103">Запуск модуля "Процесс" в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="eb2ef-103">Run the Process module in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="eb2ef-104">Файлы дела загружаются в Advanced eDiscovery во время  \> **подготовки процесса.**</span><span class="sxs-lookup"><span data-stu-id="eb2ef-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="eb2ef-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="eb2ef-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="eb2ef-107">Руководство: подготовка данных для Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="eb2ef-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="eb2ef-108">**Качество**: четко определите, что файл дела является наиболее убытным.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="eb2ef-109">**Loads**: Loads files into a location that is accessible to Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="eb2ef-110">**Идентификатор файла:** уникальный идентификатор файла в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-110">**File ID**: A unique file identifier in Advanced eDiscovery.</span></span> <span data-ttu-id="eb2ef-111">Если идентификатор файла не импортируется, Advanced eDiscovery автоматически создает идентификатор.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-111">If no file identifier is imported, Advanced eDiscovery automatically generates the ID.</span></span> <span data-ttu-id="eb2ef-112">Если вы сопозначили этот ИД в последующей загрузке процесса и настроили путь, который отличается от начальной нагрузки процесса, Advanced eDiscovery заменит путь (вместо добавления новой записи файла).</span><span class="sxs-lookup"><span data-stu-id="eb2ef-112">If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry).</span></span> <span data-ttu-id="eb2ef-113">Этот ИД можно использовать в качестве ссылки в процессе экспорта.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-113">The ID can be used as a reference in the Export process.</span></span> <span data-ttu-id="eb2ef-114">Значение ID не должно быть "-1".</span><span class="sxs-lookup"><span data-stu-id="eb2ef-114">The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="eb2ef-115">**MD5**: эта подпись используется для различения файлов (два файла не считаются точными дубликатами, если они не имеют одинаковый MD5).</span><span class="sxs-lookup"><span data-stu-id="eb2ef-115">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5).</span></span> <span data-ttu-id="eb2ef-116">По умолчанию Advanced eDiscovery вычисляет MD5 файлов.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-116">By default, Advanced eDiscovery calculates the MD5 of files.</span></span> <span data-ttu-id="eb2ef-117">Если загруженные файлы являются текстовыми файлами, рекомендуется загружать и сопоывать исходное значение MD5, а не вычислять его в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-117">When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="eb2ef-118">**Тип и имя файла:**</span><span class="sxs-lookup"><span data-stu-id="eb2ef-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="eb2ef-119">Advanced eDiscovery может обрабатывать файлы различных форматов и извлекать загруженные файлы в стандартный формат, например \* . TXT, HTML или . XML.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-119">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML.</span></span> <span data-ttu-id="eb2ef-120">Обработка текстовых файлов быстрее, чем обработка файлов из нативных файлов.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-120">Processing of text files is faster than native files.</span></span> <span data-ttu-id="eb2ef-121">Извлеченные текстовые файлы хранятся в папке дела.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-121">Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="eb2ef-122">Не загружать файлы, которые невозможно извлечь, например системные файлы или графические изображения.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-122">Do not load files that cannot be extracted, such as system files or graphic images.</span></span> <span data-ttu-id="eb2ef-123">Эти файлы могут задержать обработку.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-123">These files may delay processing.</span></span>
    
  - <span data-ttu-id="eb2ef-124">Убедитесь, что имена файлов имеют значительные имена, а пути верны.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="eb2ef-125">**Путь к** файлу: Advanced eDiscovery может загружать файлы длиной до 400 символов.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="eb2ef-126">Извлечение **текста:** при извлечении текста из встроенных файлов помимо обычного текста также извлекаются следующие данные: скрытый текст (Excel и DOC), скрытые столбцы (Excel), отслеживание изменений (DOC), заметки динамика (PPT), внедренные объекты (например, объекты Excel в PPT).</span><span class="sxs-lookup"><span data-stu-id="eb2ef-126">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt).</span></span> <span data-ttu-id="eb2ef-127">Их можно просмотреть в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-127">These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="eb2ef-128">**Ignore Text**: this optional feature is defined after Process is run and before Analyze.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-128">**Ignore Text**: This optional feature is defined after Process is run and before Analyze.</span></span> <span data-ttu-id="eb2ef-129">Игнорируйте текст с осторожностью, так как его использование может снизить производительность анализа файлов.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-129">Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="eb2ef-130">**Многоязычный текст:** Advanced eDiscovery в настоящее время не обрабатывает многоязычные имена тегов, хранителя и проблем.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="eb2ef-131">**Метаданные:** определите, есть ли метаданные, которые нужно сохранить в базе данных дел для дальнейшей ссылки, например диапазон дат, размер файла, тип файла, хранителя и тема.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-131">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject.</span></span> <span data-ttu-id="eb2ef-132">Метаданные можно загрузить после загрузки файлов без повторного перезапись инвентаризации или добавления дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-132">Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="eb2ef-133">Если файлы изначально загружались по пути, созначим столбец пути при последующих импорте метаданных.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-133">If the files were originally loaded by path, map the path column when later importing metadata.</span></span> <span data-ttu-id="eb2ef-134">Можно сослаться на файл по его ид и сослаться на другой путь.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-134">It is possible to refer to the file by ID and to map a different path.</span></span> <span data-ttu-id="eb2ef-135">Это полезный сценарий при изменении путей к файлу.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-135">This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="eb2ef-136">Если файлы изначально загружались с помощью ИД файла, созначим столбец "ИД" при загрузке метаданных.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-136">If the files were originally loaded by File ID, map the ID column when loading metadata.</span></span> <span data-ttu-id="eb2ef-137">Ссылка на файл по пути (а не по ИД) приведет к повторной загрузке файлов с другим ИД.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-137">Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID.</span></span> <span data-ttu-id="eb2ef-138">Advanced eDiscovery создает копии файлов, а не загружает метаданные существующих файлов.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-138">Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="eb2ef-139">**Семейства:** невозможно загрузить семейство без родительского (глава семейства).</span><span class="sxs-lookup"><span data-stu-id="eb2ef-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="eb2ef-140">**Размер файла:** размер файлов, загруженных в Advanced eDiscovery, не существует ограничений.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-140">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery.</span></span> <span data-ttu-id="eb2ef-141">Для анализа (анализ, релевантность и т. д.) ограничение составляет 5 242 880 символов извлеченного текста.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-141">For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text.</span></span> <span data-ttu-id="eb2ef-142">Большие файлы игнорируются (например, в релевантности файлы не участвуют в процессе обучения релевантности и не получают оценку релевантности после пакетного вычисления).</span><span class="sxs-lookup"><span data-stu-id="eb2ef-142">Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="eb2ef-143">**Количество файлов:** не рекомендуется ограничивать количество файлов, которые можно обработать в одном случае.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-143">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case.</span></span> <span data-ttu-id="eb2ef-144">Производительность зависит от ресурсов системы.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-144">Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="eb2ef-145">Фильтрация файлов</span><span class="sxs-lookup"><span data-stu-id="eb2ef-145">Filtering files</span></span>

<span data-ttu-id="eb2ef-146">Определяемая пользователем метка может быть связана с набором файлов, чтобы исключить их из процесса или других задач.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-146">A user-defined label can be associated with a set of files to exclude them from Process or other tasks.</span></span> <span data-ttu-id="eb2ef-147">Каждый сеанс процесса связан с пакетным ИД.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-147">Each Process session is associated with a batch ID.</span></span> <span data-ttu-id="eb2ef-148">Несмотря на то, что пакетный ИД не виден эксперту по релевантности, это можно сделать с помощью с помощью с помощью с помощью поисковой функции, добавив фильтр для текущего пакета и помечая все соответствующие файлы с помощью пользовательской метки.</span><span class="sxs-lookup"><span data-stu-id="eb2ef-148">Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="eb2ef-149">См. также</span><span class="sxs-lookup"><span data-stu-id="eb2ef-149">See also</span></span>

[<span data-ttu-id="eb2ef-150">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="eb2ef-150">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="eb2ef-151">Запуск модуля процесса и загрузка данных</span><span class="sxs-lookup"><span data-stu-id="eb2ef-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="eb2ef-152">Просмотр результатов модуля процесса</span><span class="sxs-lookup"><span data-stu-id="eb2ef-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

