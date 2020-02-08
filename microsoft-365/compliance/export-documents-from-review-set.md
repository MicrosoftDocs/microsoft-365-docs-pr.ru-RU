---
title: Экспорт документов из набора для проверки
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
description: ''
ms.openlocfilehash: b6f467f938ce14aacb9553b11d51dc63431ab409
ms.sourcegitcommit: 570ad1c7c334476ecec00dc355dfe52e8c2bb87b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862079"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="7e0e0-102">Экспорт документов из набора для проверки</span><span class="sxs-lookup"><span data-stu-id="7e0e0-102">Export documents from a review set</span></span>

<span data-ttu-id="7e0e0-103">Вы можете экспортировать контент для представления или внешнего анализа из проверки, заданной одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="7e0e0-103">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="7e0e0-104">Загрузка документов</span><span class="sxs-lookup"><span data-stu-id="7e0e0-104">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="7e0e0-105">Экспорт документов</span><span class="sxs-lookup"><span data-stu-id="7e0e0-105">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="7e0e0-106">Загрузка документов из набора рецензирования</span><span class="sxs-lookup"><span data-stu-id="7e0e0-106">Download documents from a review set</span></span>

<span data-ttu-id="7e0e0-107">Загрузка предлагает простой способ загрузки контента из набора проверки в собственном формате.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-107">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="7e0e0-108">Он использует функции передачи данных в браузере, поэтому приглашение браузера появится после того, как загрузка будет завершена.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-108">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="7e0e0-109">Файлы, загруженные с помощью этого метода, будут архивированы в файл контейнера и будут файлами уровня элемента.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-109">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="7e0e0-110">Это означает, что если вы выбрали вложение, вы автоматически получите сообщение электронной почты с включенным вложением.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-110">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="7e0e0-111">Аналогично, если выбрать электронную таблицу Excel, внедренную в документ Word, вы получите документ Word с внедренной таблицей Excel.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-111">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="7e0e0-112">Скачанные элементы сохраняют дату последнего изменения, которую можно просмотреть в виде свойства файла.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-112">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="7e0e0-113">Чтобы скачать контент из набора рецензирования, сначала выберите файлы, которые нужно скачать, а затем в меню действия выберите команду "Загрузить".</span><span class="sxs-lookup"><span data-stu-id="7e0e0-113">To download content from a review set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![Снимок экрана с автоматически созданным описанием компьютера](media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="7e0e0-115">Экспорт документов из набора для проверки</span><span class="sxs-lookup"><span data-stu-id="7e0e0-115">Export documents from a review set</span></span>

<span data-ttu-id="7e0e0-116">Экспорт позволяет пользователям настраивать контент, включенный в загружаемый пакет.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-116">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="7e0e0-117">Она предоставляет страницу конфигурации со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="7e0e0-117">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="7e0e0-118">Файл метаданных</span><span class="sxs-lookup"><span data-stu-id="7e0e0-118">Metadata file</span></span>

<span data-ttu-id="7e0e0-119">Это можно считать "Загрузка файла", которая содержит метаданные, связанные с экспортируемыми файлами.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-119">This can be considered your "load file" that contains metadata associated with the files you export.</span></span> <span data-ttu-id="7e0e0-120">Список экспортируемых полей, доступных в файле метаданных, представлен в статье [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="7e0e0-120">For a list of exported fields available in the metadata file, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="7e0e0-121">Этот файл обычно можно использовать с помощью сторонних средств.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-121">This file can typically be ingested by third-party tools.</span></span>

### <a name="tag-data"></a><span data-ttu-id="7e0e0-122">Данные тегов</span><span class="sxs-lookup"><span data-stu-id="7e0e0-122">Tag data</span></span>

<span data-ttu-id="7e0e0-123">Этот контент будет добавлен в виде полей в файле метаданных.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-123">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="7e0e0-124">Он содержит все сведения о тегах, применяемые в наборах рецензирования.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-124">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="7e0e0-125">Текстовые файлы</span><span class="sxs-lookup"><span data-stu-id="7e0e0-125">Text files</span></span>

<span data-ttu-id="7e0e0-126">Для каждого файла, экспортированного из набора проверки, можно создать текстовые файлы.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-126">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="7e0e0-127">Часто эти файлы являются обязательными для партнеров служб в процессе их приема в сторонние средства.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-127">Often times these files are required by service partners as part of ingesting data into third-party tools.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="7e0e0-128">Файлы отредактировал</span><span class="sxs-lookup"><span data-stu-id="7e0e0-128">Redacted files</span></span>

<span data-ttu-id="7e0e0-129">Если во время проверки создаются PDF-файлы отредактировал, эти файлы доступны во время экспорта.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-129">If redacted PDF files are generated during review, these files are available during export.</span></span> <span data-ttu-id="7e0e0-130">Вы можете выбрать, следует ли экспортировать только собственные файлы или заменить собственные файлы, которые требовали исправления, с PDF-файлами, которые содержат реальные исправления.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-130">You can decide whether to export native files only or to replace the native files that required redaction with the PDF files that contain the actual redactions.</span></span>

### <a name="export-location"></a><span data-ttu-id="7e0e0-131">Папка для экспорта</span><span class="sxs-lookup"><span data-stu-id="7e0e0-131">Export location</span></span>

<span data-ttu-id="7e0e0-132">Экспортированное содержимое доставляется либо в предоставленный Майкрософт большой двоичный объект Azure, либо на большой двоичный объект клиента, если сведения предоставлены при экспорте.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-132">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="7e0e0-133">Экспорт структуры</span><span class="sxs-lookup"><span data-stu-id="7e0e0-133">Export structure</span></span>

<span data-ttu-id="7e0e0-134">При экспорте контента из набора проверки его содержимое организуется в следующей структуре.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-134">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="7e0e0-135">Корневая папка — код скачивания</span><span class="sxs-lookup"><span data-stu-id="7e0e0-135">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="7e0e0-136">Export\_файл\_Load. CSV = файл метаданных</span><span class="sxs-lookup"><span data-stu-id="7e0e0-136">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="7e0e0-137">Summary. txt = файл сводки со статистикой по экспорту</span><span class="sxs-lookup"><span data-stu-id="7e0e0-137">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="7e0e0-138">Входные\_или\_собственные файлы = содержит все собственные файлы</span><span class="sxs-lookup"><span data-stu-id="7e0e0-138">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="7e0e0-139">Файлы\_ошибок = содержит все файлы ошибок, включенные в экспорт</span><span class="sxs-lookup"><span data-stu-id="7e0e0-139">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="7e0e0-140">Екстрактионеррор — CSV-файл, который содержит все доступные метаданные файлов, которые не были должным образом извлечены из родительских файлов</span><span class="sxs-lookup"><span data-stu-id="7e0e0-140">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="7e0e0-141">Процессинжеррор — контент с ошибками обработки.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-141">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="7e0e0-142">Это содержимое имеет уровень элемента. Если во вложении возникла ошибка обработки, в эту папку будут включены сообщения электронной почты, содержащие вложение.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-142">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="7e0e0-143">\_Извлеченные\_текстовые файлы = содержит все извлеченные текстовые файлы, созданные при обработке.</span><span class="sxs-lookup"><span data-stu-id="7e0e0-143">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>