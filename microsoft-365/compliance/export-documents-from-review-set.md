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
description: Узнайте, как выбрать и экспортировать контент из набора для презентаций или внешних отзывов.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285365"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="0a499-103">Экспорт документов из набора для проверки в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0a499-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="0a499-104">Экспорт позволяет пользователям настраивать содержимое, включенное в пакет скачивания.</span><span class="sxs-lookup"><span data-stu-id="0a499-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="0a499-105">Средство экспорта предоставляет страницу конфигурации со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="0a499-105">The Export tool provides a configuration page with the following settings:</span></span>

![Параметры экспорта элементов из набора для проверки](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="0a499-107">Параметры экспорта</span><span class="sxs-lookup"><span data-stu-id="0a499-107">Export options</span></span>

- <span data-ttu-id="0a499-108">Имя экспорта: имя задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="0a499-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="0a499-109">Описание: поле свободного текста для добавления описания.</span><span class="sxs-lookup"><span data-stu-id="0a499-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="0a499-110">Экспортировать эти документы:</span><span class="sxs-lookup"><span data-stu-id="0a499-110">Export these documents:</span></span>

  - <span data-ttu-id="0a499-111">Только выбранные документы — экспортируются только выбранные в данный момент документы.</span><span class="sxs-lookup"><span data-stu-id="0a499-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="0a499-112">Все документы в наборе для проверки — экспорт всех документов в наборе для проверки</span><span class="sxs-lookup"><span data-stu-id="0a499-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="0a499-113">Metadata</span><span class="sxs-lookup"><span data-stu-id="0a499-113">Metadata</span></span>
  
  - <span data-ttu-id="0a499-114">Файл загрузки — этот файл содержит метаданные для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="0a499-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="0a499-115">Дополнительные сведения о включенных полях см. в полях метаданных документа [в Advanced eDiscovery.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="0a499-115">see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) for more information about what fields are included.</span></span> <span data-ttu-id="0a499-116">Как правило, этот файл может быть вмедом сторонними средствами eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0a499-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="0a499-117">Теги . Если этот тег выбран, сведения о тегах будут включены в файл загрузки.</span><span class="sxs-lookup"><span data-stu-id="0a499-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="0a499-118">Контент</span><span class="sxs-lookup"><span data-stu-id="0a499-118">Content</span></span>
  
  - <span data-ttu-id="0a499-119">Native files - Select this checkbox to include the native files.</span><span class="sxs-lookup"><span data-stu-id="0a499-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="0a499-120">Параметры беседы</span><span class="sxs-lookup"><span data-stu-id="0a499-120">Conversation options</span></span>
    
    - <span data-ttu-id="0a499-121">Файлы беседы — экспорт восстановленных сообщений чата.</span><span class="sxs-lookup"><span data-stu-id="0a499-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="0a499-122">Этот формат представляет беседы в форме, похожей на то, что пользователи видят в приложении.</span><span class="sxs-lookup"><span data-stu-id="0a499-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="0a499-123">Отдельные сообщения чата — экспортировать исходные файлы беседы, хранимые в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0a499-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="0a499-124">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a499-124">Options</span></span>

  - <span data-ttu-id="0a499-125">Текстовые файлы — включаем извлеченные текстовые версии файлов.</span><span class="sxs-lookup"><span data-stu-id="0a499-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="0a499-126">Замените отредактируемые встроенные файлы преобразованными файлами PDF. Если во время проверки создаются отредактируемые PDF-файлы, эти файлы доступны для экспорта.</span><span class="sxs-lookup"><span data-stu-id="0a499-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="0a499-127">Вы можете экспортировать только встроенные файлы, которые были отредактировали (не выбрав этот параметр), или выбрать этот параметр для экспорта PDF-файлов, содержащих фактические отредактации.</span><span class="sxs-lookup"><span data-stu-id="0a499-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="0a499-128">Параметры вывода (экспортируемого содержимого доступен для скачивания непосредственно через веб-браузер или может быть отправлен в учетную запись хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="0a499-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="0a499-129">Первые два варианта обеспечивают прямую загрузку.)</span><span class="sxs-lookup"><span data-stu-id="0a499-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="0a499-130">Свободные файлы и PTS (по возможности в PTS добавляется электронная почта) — файлы экспортируются в формате, похожем на исходную структуру каталогов, которая видна пользователям в их собственных приложениях.</span><span class="sxs-lookup"><span data-stu-id="0a499-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="0a499-131">Дополнительные сведения см. в разделе ["Свободные файлы и структура экспорта PST-файлов".](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="0a499-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="0a499-132">Сжатая структура каталогов — файлы экспортируются и включаются в загрузку.</span><span class="sxs-lookup"><span data-stu-id="0a499-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="0a499-133">Сжатая структура каталогов, экспортируемая в учетную запись службы хранилища Azure— файлы экспортируются в обсчет хранилища Azure вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0a499-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage accouunt.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="0a499-134">Свободные файлы и структура экспорта PST-файлов</span><span class="sxs-lookup"><span data-stu-id="0a499-134">Loose files and PST export structure</span></span>

<span data-ttu-id="0a499-135">Если выбран этот вариант экспорта, экспортируемая содержимое будет организована в следующей структуре:</span><span class="sxs-lookup"><span data-stu-id="0a499-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="0a499-136">Корневая папка — эта папка с именем ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="0a499-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="0a499-137">Export_load_file.csv - файл метаданных.</span><span class="sxs-lookup"><span data-stu-id="0a499-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="0a499-138">Summary.csv - сводный файл, который также содержит статистику экспорта.</span><span class="sxs-lookup"><span data-stu-id="0a499-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="0a499-139">Exchange — эта папка содержит все содержимое из Exchange в формате файла.</span><span class="sxs-lookup"><span data-stu-id="0a499-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="0a499-140">Файлы Natives заменяются на отредактируемые PDF, если вы выбрали параметр "Заменить отредактируемые нативные" на преобразованные **PDFs.**</span><span class="sxs-lookup"><span data-stu-id="0a499-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="0a499-141">SharePoint = эта папка содержит все содержимое из SharePoint в формате файла.</span><span class="sxs-lookup"><span data-stu-id="0a499-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="0a499-142">Файлы Natives заменяются на отредактируемые PDF, если вы выбрали параметр "Заменить отредактируемые нативные" на преобразованные **PDFs.**</span><span class="sxs-lookup"><span data-stu-id="0a499-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="0a499-143">Сжатая структура каталогов</span><span class="sxs-lookup"><span data-stu-id="0a499-143">Condensed directory structure</span></span>

- <span data-ttu-id="0a499-144">Корневая папка — эта папка называется ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="0a499-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="0a499-145">Export_load_file.csv - файл метаданных.</span><span class="sxs-lookup"><span data-stu-id="0a499-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="0a499-146">Summary.txt - сводный файл, который также содержит статистику экспорта.</span><span class="sxs-lookup"><span data-stu-id="0a499-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="0a499-147">Input_or_native_files - эта папка содержит все файлы, которые были экспортироваться.</span><span class="sxs-lookup"><span data-stu-id="0a499-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="0a499-148">При экспорте отредактных PDF-файлов они не помещаются в PST-файлы.</span><span class="sxs-lookup"><span data-stu-id="0a499-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="0a499-149">Вместо этого они добавляются в раздельную папку.</span><span class="sxs-lookup"><span data-stu-id="0a499-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="0a499-150">Error_files - эта папка содержит следующие файлы ошибок, если они включены в экспорт:</span><span class="sxs-lookup"><span data-stu-id="0a499-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="0a499-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="0a499-151">ExtractionError.</span></span> <span data-ttu-id="0a499-152">CSV-файл, содержащий любые доступные метаданные файлов, которые не были надлежащим образом извлечены из родительских файлов.</span><span class="sxs-lookup"><span data-stu-id="0a499-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="0a499-153">ProcessingError — этот файл содержит список документов с ошибками обработки.</span><span class="sxs-lookup"><span data-stu-id="0a499-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="0a499-154">Это содержимое на уровне элемента, т. е. если вложение привело к ошибке обработки, сообщение электронной почты, содержающее вложение, будет включено в эту папку.</span><span class="sxs-lookup"><span data-stu-id="0a499-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="0a499-155">Extracted_text_files - эта папка содержит все извлеченные текстовые файлы, созданные при обработке.</span><span class="sxs-lookup"><span data-stu-id="0a499-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="0a499-156">Задания экспорта сохраняются в течение всего жизненного времени дела и могут быть загружены, если дело не удалено.</span><span class="sxs-lookup"><span data-stu-id="0a499-156">Export jobs are retained for the life of the case and can be downloaded as long as the case isn't deleted.</span></span>
