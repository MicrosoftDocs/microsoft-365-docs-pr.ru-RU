---
title: Экспорт документов из набора для проверки
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
ms.openlocfilehash: cf8b11fa82398ab8cfa3981064741d0dbf349f71
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090238"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="ef122-102">Экспорт документов из набора для проверки</span><span class="sxs-lookup"><span data-stu-id="ef122-102">Export documents from a review set</span></span>

<span data-ttu-id="ef122-103">Вы можете экспортировать контент для представления или внешнего анализа из проверки, заданной одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="ef122-103">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="ef122-104">Загрузка документов</span><span class="sxs-lookup"><span data-stu-id="ef122-104">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="ef122-105">Экспорт документов</span><span class="sxs-lookup"><span data-stu-id="ef122-105">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="ef122-106">Загрузка документов из набора рецензирования</span><span class="sxs-lookup"><span data-stu-id="ef122-106">Download documents from a review set</span></span>

<span data-ttu-id="ef122-107">Загрузка предлагает простой способ загрузки контента из набора проверки в собственном формате.</span><span class="sxs-lookup"><span data-stu-id="ef122-107">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="ef122-108">Он использует функции передачи данных в браузере, поэтому приглашение браузера появится после того, как загрузка будет завершена.</span><span class="sxs-lookup"><span data-stu-id="ef122-108">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="ef122-109">Файлы, загруженные с помощью этого метода, будут архивированы в файл контейнера и будут файлами уровня элемента.</span><span class="sxs-lookup"><span data-stu-id="ef122-109">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="ef122-110">Это означает, что если вы выбрали вложение, вы автоматически получите сообщение электронной почты с включенным вложением.</span><span class="sxs-lookup"><span data-stu-id="ef122-110">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="ef122-111">Аналогично, если выбрать электронную таблицу Excel, внедренную в документ Word, вы получите документ Word с внедренной таблицей Excel.</span><span class="sxs-lookup"><span data-stu-id="ef122-111">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="ef122-112">Скачанные элементы сохраняют дату последнего изменения, которую можно просмотреть в виде свойства файла.</span><span class="sxs-lookup"><span data-stu-id="ef122-112">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="ef122-113">Чтобы скачать контент из набора рецензирования, сначала выберите файлы, которые нужно скачать, а затем в меню действия выберите команду "Загрузить".</span><span class="sxs-lookup"><span data-stu-id="ef122-113">To download content from a review set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![Снимок экрана с автоматически созданным описанием компьютера](media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="ef122-115">Экспорт документов из набора для проверки</span><span class="sxs-lookup"><span data-stu-id="ef122-115">Export documents from a review set</span></span>

<span data-ttu-id="ef122-116">Экспорт позволяет пользователям настраивать контент, включенный в загружаемый пакет.</span><span class="sxs-lookup"><span data-stu-id="ef122-116">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="ef122-117">Она предоставляет страницу конфигурации со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="ef122-117">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="ef122-118">Файл метаданных</span><span class="sxs-lookup"><span data-stu-id="ef122-118">Metadata file</span></span>

<span data-ttu-id="ef122-119">Это можно считать "Загрузка файла", которая содержит метаданные, связанные с экспортированными файлами.</span><span class="sxs-lookup"><span data-stu-id="ef122-119">This can be considered your “load file” that contains metadata associated with the files you exported.</span></span> <span data-ttu-id="ef122-120">Список полей, доступных в файле метаданных, приведен в разделе \[Link.\]</span><span class="sxs-lookup"><span data-stu-id="ef122-120">For a list of fields available in the metadata file, see \[link\].</span></span> <span data-ttu-id="ef122-121">Этот файл, как правило, может быть вызван тремя средствами субъектов<sup>удаленных рабочих столов</sup> .</span><span class="sxs-lookup"><span data-stu-id="ef122-121">This file can typically be ingested by 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="tag-data"></a><span data-ttu-id="ef122-122">Данные тегов</span><span class="sxs-lookup"><span data-stu-id="ef122-122">Tag data</span></span>

<span data-ttu-id="ef122-123">Этот контент будет добавлен в виде полей в файле метаданных.</span><span class="sxs-lookup"><span data-stu-id="ef122-123">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="ef122-124">Он содержит все сведения о тегах, применяемые в наборах рецензирования.</span><span class="sxs-lookup"><span data-stu-id="ef122-124">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="ef122-125">Текстовые файлы</span><span class="sxs-lookup"><span data-stu-id="ef122-125">Text files</span></span>

<span data-ttu-id="ef122-126">Для каждого файла, экспортированного из набора проверки, можно создать текстовые файлы.</span><span class="sxs-lookup"><span data-stu-id="ef122-126">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="ef122-127">Часто эти файлы необходимы партнерам по службам в процессе приема данных в 3 средства субъектов<sup>удаленных рабочих столов</sup> .</span><span class="sxs-lookup"><span data-stu-id="ef122-127">Often times these files are required by service partners as part of ingesting data into 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="ef122-128">Файлы отредактировал</span><span class="sxs-lookup"><span data-stu-id="ef122-128">Redacted files</span></span>

<span data-ttu-id="ef122-129">Если во время проверки создаются отредактировал PDF, эти файлы доступны во время экспорта.</span><span class="sxs-lookup"><span data-stu-id="ef122-129">If redacted PDFs are generated during review, these files are available during export.</span></span> <span data-ttu-id="ef122-130">Пользователи могут выбрать, следует ли экспортировать только собственные файлы или заменить собственные файлы с исправлениями, записанными в PDF-файлах.</span><span class="sxs-lookup"><span data-stu-id="ef122-130">Users can decide whether to export native files only or to replace natives that have redactions with the burned in PDFs.</span></span>

### <a name="export-location"></a><span data-ttu-id="ef122-131">Папка для экспорта</span><span class="sxs-lookup"><span data-stu-id="ef122-131">Export Location</span></span>

<span data-ttu-id="ef122-132">Экспортированное содержимое доставляется либо в предоставленный Майкрософт большой двоичный объект Azure, либо на большой двоичный объект клиента, если сведения предоставлены при экспорте.</span><span class="sxs-lookup"><span data-stu-id="ef122-132">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="ef122-133">Экспорт структуры</span><span class="sxs-lookup"><span data-stu-id="ef122-133">Export Structure</span></span>

<span data-ttu-id="ef122-134">При экспорте контента из набора проверки его содержимое организуется в следующей структуре.</span><span class="sxs-lookup"><span data-stu-id="ef122-134">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="ef122-135">Корневая папка — код скачивания</span><span class="sxs-lookup"><span data-stu-id="ef122-135">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="ef122-136">Export\_файл\_Load. CSV = файл метаданных</span><span class="sxs-lookup"><span data-stu-id="ef122-136">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="ef122-137">Summary. txt = файл сводки со статистикой по экспорту</span><span class="sxs-lookup"><span data-stu-id="ef122-137">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="ef122-138">Входные\_или\_собственные файлы = содержит все собственные файлы</span><span class="sxs-lookup"><span data-stu-id="ef122-138">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="ef122-139">Файлы\_ошибок = содержит все файлы ошибок, включенные в экспорт</span><span class="sxs-lookup"><span data-stu-id="ef122-139">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="ef122-140">Екстрактионеррор — CSV-файл, который содержит все доступные метаданные файлов, которые не были должным образом извлечены из родительских файлов</span><span class="sxs-lookup"><span data-stu-id="ef122-140">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="ef122-141">Процессинжеррор — контент с ошибками обработки.</span><span class="sxs-lookup"><span data-stu-id="ef122-141">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="ef122-142">Это содержимое имеет уровень элемента. Если во вложении возникла ошибка обработки, в эту папку будут включены сообщения электронной почты, содержащие вложение.</span><span class="sxs-lookup"><span data-stu-id="ef122-142">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="ef122-143">\_Извлеченные\_текстовые файлы = содержит все извлеченные текстовые файлы, созданные при обработке.</span><span class="sxs-lookup"><span data-stu-id="ef122-143">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>