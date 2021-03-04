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
description: Узнайте, как выбрать и экспортировать контент из набора обзоров для презентаций или внешних обзоров.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a2ca8e2f400d9f257549e59305d1fd56586185e2
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423650"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="02a4c-103">Экспорт документов из набора обзоров в advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="02a4c-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="02a4c-104">Экспорт позволяет пользователям настраивать контент, включенный в пакет загрузки.</span><span class="sxs-lookup"><span data-stu-id="02a4c-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="02a4c-105">Средство Export предоставляет страницу конфигурации со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="02a4c-105">The Export tool provides a configuration page with the following settings:</span></span>

![Параметры экспорта элементов из набора отзывов](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="02a4c-107">Параметры экспорта</span><span class="sxs-lookup"><span data-stu-id="02a4c-107">Export options</span></span>

- <span data-ttu-id="02a4c-108">Имя экспорта. Имя задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="02a4c-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="02a4c-109">Описание. Поле для свободного текста для добавления описания.</span><span class="sxs-lookup"><span data-stu-id="02a4c-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="02a4c-110">Экспорт этих документов:</span><span class="sxs-lookup"><span data-stu-id="02a4c-110">Export these documents:</span></span>

  - <span data-ttu-id="02a4c-111">Только выбранные документы экспортируют только те документы, которые в настоящее время выбраны.</span><span class="sxs-lookup"><span data-stu-id="02a4c-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="02a4c-112">Все документы в наборе обзоров — экспортируют все документы в наборе обзоров</span><span class="sxs-lookup"><span data-stu-id="02a4c-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="02a4c-113">Metadata</span><span class="sxs-lookup"><span data-stu-id="02a4c-113">Metadata</span></span>
  
  - <span data-ttu-id="02a4c-114">Файл нагрузки . Этот файл содержит метаданные для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="02a4c-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="02a4c-115">Дополнительные сведения о том, какие поля включены, см. в поле метаданных документа [в advanced eDiscovery.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="02a4c-115">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="02a4c-116">Этот файл обычно может быть ведом сторонними средствами электронного разобнаружия.</span><span class="sxs-lookup"><span data-stu-id="02a4c-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="02a4c-117">Теги . При выборе в файл нагрузки будут включены сведения о тегах.</span><span class="sxs-lookup"><span data-stu-id="02a4c-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="02a4c-118">Контент</span><span class="sxs-lookup"><span data-stu-id="02a4c-118">Content</span></span>
  
  - <span data-ttu-id="02a4c-119">Личные файлы . Выберите этот почтовый ящик, чтобы включить личные файлы.</span><span class="sxs-lookup"><span data-stu-id="02a4c-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="02a4c-120">Параметры беседы</span><span class="sxs-lookup"><span data-stu-id="02a4c-120">Conversation options</span></span>
    
    - <span data-ttu-id="02a4c-121">Файлы беседы — экспорт восстановленных сообщений чата.</span><span class="sxs-lookup"><span data-stu-id="02a4c-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="02a4c-122">Этот формат представляет беседы в форме, которая похожа на то, что пользователи видят в родном приложении.</span><span class="sxs-lookup"><span data-stu-id="02a4c-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="02a4c-123">Отдельные сообщения чата — экспорт исходных файлов беседы, хранимые в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02a4c-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="02a4c-124">Параметры</span><span class="sxs-lookup"><span data-stu-id="02a4c-124">Options</span></span>

  - <span data-ttu-id="02a4c-125">Текстовые файлы — включаем извлеченные текстовые версии родных файлов.</span><span class="sxs-lookup"><span data-stu-id="02a4c-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="02a4c-126">Замените отредактируемые туземцы преобразованными PDF-файлами . Если во время проверки создаются отредактируемые PDF-файлы, эти файлы доступны для экспорта.</span><span class="sxs-lookup"><span data-stu-id="02a4c-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="02a4c-127">Вы можете экспортировать только личные файлы, которые были отредактировали (не выбрав этот параметр), или вы можете выбрать этот параметр для экспорта pdf-файлов, содержащих фактические отредактации.</span><span class="sxs-lookup"><span data-stu-id="02a4c-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="02a4c-128">Параметры вывода (экспортируемого контента можно скачать непосредственно через веб-браузер или можно отправить в учетную запись Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="02a4c-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="02a4c-129">Первые два варианта позволяют напрямую скачать.)</span><span class="sxs-lookup"><span data-stu-id="02a4c-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="02a4c-130">Свободные файлы и PSTs (по возможности электронная почта добавляется в PSTs) — файлы экспортируются в формате, напоминаемом исходной структуре каталогов, которую пользователи видели в своих родных приложениях.</span><span class="sxs-lookup"><span data-stu-id="02a4c-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="02a4c-131">Дополнительные сведения см. в разделе [Loose files and PST export structure.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="02a4c-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="02a4c-132">Структура сжатого каталога — файлы экспортируются и включаются в загрузку.</span><span class="sxs-lookup"><span data-stu-id="02a4c-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="02a4c-133">Структура сжатого каталога, экспортируемая в учетную запись Azure Storage. Файлы экспортируются в учетную запись Azure Storage организации.</span><span class="sxs-lookup"><span data-stu-id="02a4c-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage account.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="02a4c-134">Свободные файлы и структура экспорта PST</span><span class="sxs-lookup"><span data-stu-id="02a4c-134">Loose files and PST export structure</span></span>

<span data-ttu-id="02a4c-135">При выборе этого варианта экспорта экспортируемого контента организовано в следующей структуре:</span><span class="sxs-lookup"><span data-stu-id="02a4c-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="02a4c-136">Корневая папка — эта папка с именем ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="02a4c-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="02a4c-137">Export_load_file.csv — файл метаданных.</span><span class="sxs-lookup"><span data-stu-id="02a4c-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="02a4c-138">Summary.csv - сводный файл, который также содержит статистику экспорта.</span><span class="sxs-lookup"><span data-stu-id="02a4c-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="02a4c-139">Exchange . Эта папка содержит все содержимое из Exchange в формате родного файла.</span><span class="sxs-lookup"><span data-stu-id="02a4c-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="02a4c-140">Файлы natives заменяются отредактируемыми PDF, если выбран параметр **Replace redacted natives с преобразованным вариантом PDFs.**</span><span class="sxs-lookup"><span data-stu-id="02a4c-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="02a4c-141">SharePoint = Эта папка содержит все родной контент из SharePoint в формате родного файла.</span><span class="sxs-lookup"><span data-stu-id="02a4c-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="02a4c-142">Файлы natives заменяются отредактируемыми PDF, если выбран параметр **Replace redacted natives с преобразованным вариантом PDFs.**</span><span class="sxs-lookup"><span data-stu-id="02a4c-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="02a4c-143">Структура сжатого каталога</span><span class="sxs-lookup"><span data-stu-id="02a4c-143">Condensed directory structure</span></span>

- <span data-ttu-id="02a4c-144">Корневая папка — эта папка называется ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="02a4c-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="02a4c-145">Export_load_file.csv — файл метаданных.</span><span class="sxs-lookup"><span data-stu-id="02a4c-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="02a4c-146">Summary.txt - сводный файл, который также содержит статистику экспорта.</span><span class="sxs-lookup"><span data-stu-id="02a4c-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="02a4c-147">Input_or_native_files — эта папка содержит все личные файлы, которые были экспортируются.</span><span class="sxs-lookup"><span data-stu-id="02a4c-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="02a4c-148">Если вы экспортируете отредактные PDF-файлы, они не помещались в PST-файлы.</span><span class="sxs-lookup"><span data-stu-id="02a4c-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="02a4c-149">Вместо этого они добавляются в разделенную папку.</span><span class="sxs-lookup"><span data-stu-id="02a4c-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="02a4c-150">Error_files - Эта папка содержит следующие файлы ошибок, если они включены в экспорт:</span><span class="sxs-lookup"><span data-stu-id="02a4c-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="02a4c-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="02a4c-151">ExtractionError.</span></span> <span data-ttu-id="02a4c-152">CSV-файл, содержащий все доступные метаданные файлов, которые не были должным образом извлечены из родительских файлов.</span><span class="sxs-lookup"><span data-stu-id="02a4c-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="02a4c-153">ProcessingError . Этот файл содержит список документов с ошибками обработки.</span><span class="sxs-lookup"><span data-stu-id="02a4c-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="02a4c-154">Это содержимое на уровне элементов, то есть если вложение привело к ошибке обработки, сообщение электронной почты, содержающее вложение, включено в эту папку.</span><span class="sxs-lookup"><span data-stu-id="02a4c-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="02a4c-155">Extracted_text_files — эта папка содержит все извлеченные текстовые файлы, созданные при обработке.</span><span class="sxs-lookup"><span data-stu-id="02a4c-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="02a4c-156">Рабочие места экспорта сохраняются в течение всего дела.</span><span class="sxs-lookup"><span data-stu-id="02a4c-156">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="02a4c-157">Однако необходимо скачать содержимое из задания экспорта в течение 30 дней после завершения задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="02a4c-157">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>
