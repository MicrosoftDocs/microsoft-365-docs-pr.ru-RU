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
description: Сведения о том, как выбирать и экспортировать контент из набора для рецензирования для презентаций или внешних просмотров.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285365"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="a2f3c-103">Экспорт документов из набора проверки в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a2f3c-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="a2f3c-104">Экспорт позволяет пользователям настраивать контент, включенный в загружаемый пакет.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="a2f3c-105">Средство экспорта предоставляет страницу конфигурации со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="a2f3c-105">The Export tool provides a configuration page with the following settings:</span></span>

![Параметры для экспорта элементов из набора проверки](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="a2f3c-107">Параметры экспорта</span><span class="sxs-lookup"><span data-stu-id="a2f3c-107">Export options</span></span>

- <span data-ttu-id="a2f3c-108">Имя экспорта: имя задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="a2f3c-109">Описание: свободное текстовое поле для добавления описания.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="a2f3c-110">Экспортируйте эти документы:</span><span class="sxs-lookup"><span data-stu-id="a2f3c-110">Export these documents:</span></span>

  - <span data-ttu-id="a2f3c-111">Только выбранные документы — экспортирует только выбранные в данный момент документы.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="a2f3c-112">Все документы в наборе рецензирования — экспорт всех документов в наборе рецензирования</span><span class="sxs-lookup"><span data-stu-id="a2f3c-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="a2f3c-113">Метаданные</span><span class="sxs-lookup"><span data-stu-id="a2f3c-113">Metadata</span></span>
  
  - <span data-ttu-id="a2f3c-114">Загрузить файл — этот файл содержит метаданные для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="a2f3c-115">Дополнительные сведения о том, какие поля включены, можно посмотреть [в разделе Metadata Document Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) .</span><span class="sxs-lookup"><span data-stu-id="a2f3c-115">see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) for more information about what fields are included.</span></span> <span data-ttu-id="a2f3c-116">Как правило, этот файл можно использовать сторонними средствами обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="a2f3c-117">Теги — Если выбран этот параметр, в файл загрузки будут включены сведения о разметке тегами.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="a2f3c-118">Содержимое</span><span class="sxs-lookup"><span data-stu-id="a2f3c-118">Content</span></span>
  
  - <span data-ttu-id="a2f3c-119">Собственные файлы — установите этот флажок, чтобы включить собственные файлы.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="a2f3c-120">Параметры беседы</span><span class="sxs-lookup"><span data-stu-id="a2f3c-120">Conversation options</span></span>
    
    - <span data-ttu-id="a2f3c-121">Файлы беседы — экспорт перестроенных сообщений чата.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="a2f3c-122">В этом формате отображаются беседы в форме, которые похожи на то, что пользователи видят в собственном приложении.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="a2f3c-123">Отдельные сообщения для разговора — экспорт исходных файлов бесед в том виде, в котором они хранятся в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="a2f3c-124">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2f3c-124">Options</span></span>

  - <span data-ttu-id="a2f3c-125">Текстовые файлы — включить извлеченные текстовые версии исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="a2f3c-126">Замените встроенные файлы отредактировал на преобразованные PDF-файлы (если во время проверки создаются файлы отредактировал PDF) эти файлы доступны для экспорта.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="a2f3c-127">Вы можете экспортировать только собственные файлы, которые были отредактировал (если не выбрать этот параметр), или выбрать этот параметр, чтобы экспортировать PDF-файлы, содержащие фактические исправления.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="a2f3c-128">Параметры вывода (экспортированное содержимое доступно для загрузки непосредственно через веб-браузер или может быть отправлено в учетную запись службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="a2f3c-129">Первые два параметра позволяют выполнить прямую загрузку.)</span><span class="sxs-lookup"><span data-stu-id="a2f3c-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="a2f3c-130">Свободные файлы и PST-файлы (по возможности по возможности добавляются в PST-файлы) — файлы экспортируются в формате, который напоминает исходную структуру каталогов, видимую пользователям в собственных приложениях.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="a2f3c-131">Для получения дополнительных сведений см раздел " [свободные файлы и экспорт PST-структуры](#loose-files-and-pst-export-structure) ".</span><span class="sxs-lookup"><span data-stu-id="a2f3c-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="a2f3c-132">Сжатая структура каталогов — файлы экспортируются и включаются в загрузку.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="a2f3c-133">Сжатая структура каталогов, экспортированная в учетную запись хранения Azure, экспортируется в хранилище Azure аккауунт для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage accouunt.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="a2f3c-134">Структура экспорта свободных файлов и PST</span><span class="sxs-lookup"><span data-stu-id="a2f3c-134">Loose files and PST export structure</span></span>

<span data-ttu-id="a2f3c-135">Если выбран этот параметр экспорта, экспортируемое содержимое организовано в следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="a2f3c-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="a2f3c-136">Корневая папка: папка с именем ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="a2f3c-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="a2f3c-137">Файл метаданных Export_load_file.csv.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="a2f3c-138">Summary.csv — сводный файл, который также содержит статистику экспорта.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="a2f3c-139">Exchange — эта папка содержит весь контент из Exchange в собственном формате файлов.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="a2f3c-140">Собственные файлы заменяются на отредактировал PDF, если вы выбрали параметр **заменить встроенные файлы PDF отредактировал** .</span><span class="sxs-lookup"><span data-stu-id="a2f3c-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="a2f3c-141">SharePoint = Эта папка содержит весь встроенный контент из SharePoint в собственном формате файлов.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="a2f3c-142">Собственные файлы заменяются на отредактировал PDF, если вы выбрали параметр **заменить встроенные файлы PDF отредактировал** .</span><span class="sxs-lookup"><span data-stu-id="a2f3c-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="a2f3c-143">Сжатая структура каталогов</span><span class="sxs-lookup"><span data-stu-id="a2f3c-143">Condensed directory structure</span></span>

- <span data-ttu-id="a2f3c-144">Корневая папка: имя этой папки ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="a2f3c-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="a2f3c-145">Файл метаданных Export_load_file.csv.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="a2f3c-146">Summary.txt — сводный файл, который также содержит статистику экспорта.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="a2f3c-147">Input_or_native_files — в этой папке содержатся все экспортированные файлы машинного кода.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="a2f3c-148">При экспорте PDF-файлов отредактировал они не помещаются в PST-файлы.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="a2f3c-149">Вместо этого они добавляются в отдельную папку.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="a2f3c-150">Error_files — эта папка содержит следующие файлы ошибок, если они включены в экспорт:</span><span class="sxs-lookup"><span data-stu-id="a2f3c-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="a2f3c-151">Екстрактионеррор.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-151">ExtractionError.</span></span> <span data-ttu-id="a2f3c-152">CSV-файл, содержащий все доступные метаданные файлов, которые не были должным образом извлечены из родительских файлов.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="a2f3c-153">Процессинжеррор — этот файл содержит список документов с ошибками обработки.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="a2f3c-154">Этот контент является уровнем элемента, то есть если вложение привело к ошибке обработки, в эту папку включается сообщение электронной почты, содержащее вложение.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="a2f3c-155">Extracted_text_files — в этой папке содержатся все извлеченные текстовые файлы, созданные при обработке.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="a2f3c-156">Задания экспорта сохраняются в течение всего срока существования обращения и могут быть скачаны, пока не будет удалено обращение.</span><span class="sxs-lookup"><span data-stu-id="a2f3c-156">Export jobs are retained for the life of the case and can be downloaded as long as the case isn't deleted.</span></span>
