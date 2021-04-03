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
description: Узнайте, как выбрать и экспортировать контент из набора обзоров advanced eDiscovery для презентаций или внешних обзоров.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581025"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="bc9df-103">Экспорт документов из набора обзоров в advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bc9df-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="bc9df-104">Экспорт позволяет пользователям настраивать контент, включенный в пакет загрузки при экспорте документа из набора обзоров в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="bc9df-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="bc9df-105">Экспорт документов из набора обзоров:</span><span class="sxs-lookup"><span data-stu-id="bc9df-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="bc9df-106">В центре соответствия требованиям Microsoft 365 откройте дело Advanced  eDiscovery, выберите вкладку Наборы отзывов и выберите набор отзывов, который необходимо экспортировать.</span><span class="sxs-lookup"><span data-stu-id="bc9df-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="bc9df-107">В наборе обзоров щелкните **Действие**  >  **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="bc9df-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="bc9df-108">Средство Экспорт отображает страницу вылетов с настройками экспорта.</span><span class="sxs-lookup"><span data-stu-id="bc9df-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="bc9df-109">Некоторые параметры выбираются по умолчанию, но их можно изменить.</span><span class="sxs-lookup"><span data-stu-id="bc9df-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="bc9df-110">В следующем разделе описаны параметры экспорта, которые можно настроить.</span><span class="sxs-lookup"><span data-stu-id="bc9df-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![Параметры конфигурации для экспорта элементов из набора отзывов](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="bc9df-112">После настройки экспорта щелкните **Экспорт,** чтобы запустить процесс экспорта.</span><span class="sxs-lookup"><span data-stu-id="bc9df-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="bc9df-113">В зависимости от параметра, выбранного в разделе **Выходные** параметры, вы можете получить доступ к файлам экспорта путем прямой загрузки или в учетной записи Azure Storage организации.</span><span class="sxs-lookup"><span data-stu-id="bc9df-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="bc9df-114">Рабочие места экспорта сохраняются в течение всего дела.</span><span class="sxs-lookup"><span data-stu-id="bc9df-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="bc9df-115">Однако необходимо скачать содержимое из задания экспорта в течение 30 дней после завершения задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="bc9df-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="bc9df-116">Параметры экспорта</span><span class="sxs-lookup"><span data-stu-id="bc9df-116">Export options</span></span>

<span data-ttu-id="bc9df-117">Чтобы настроить экспорт, используйте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="bc9df-117">Use the following options to configure the export.</span></span>

- <span data-ttu-id="bc9df-118">**Имя экспорта.** Имя задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="bc9df-118">**Export name**: Name of the export job.</span></span>

- <span data-ttu-id="bc9df-119">**Описание.** Поле для свободного текста для добавления описания.</span><span class="sxs-lookup"><span data-stu-id="bc9df-119">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="bc9df-120">**Экспорт этих документов**</span><span class="sxs-lookup"><span data-stu-id="bc9df-120">**Export these documents**</span></span>

  - <span data-ttu-id="bc9df-121">**Только выбранные документы.** Этот параметр экспортирует только те документы, которые в настоящее время выбраны.</span><span class="sxs-lookup"><span data-stu-id="bc9df-121">**Selected documents only**: This option exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="bc9df-122">**Все документы в наборе** обзоров. Этот параметр экспортирует все документы в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="bc9df-122">**All documents in the review set**: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="bc9df-123">**Метаданные**</span><span class="sxs-lookup"><span data-stu-id="bc9df-123">**Metadata**</span></span>
  
  - <span data-ttu-id="bc9df-124">**Файл нагрузки.** Этот файл содержит метаданные для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="bc9df-124">**Load file**: This file contains metadata for each file.</span></span> <span data-ttu-id="bc9df-125">Этот файл обычно может быть ведом сторонними средствами электронного разобнаружия.</span><span class="sxs-lookup"><span data-stu-id="bc9df-125">This file can typically be ingested by third-party eDiscovery tools.</span></span> <span data-ttu-id="bc9df-126">Дополнительные сведения о том, какие поля включены, см. в поле метаданных документа [в advanced eDiscovery.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="bc9df-126">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>
  
  - <span data-ttu-id="bc9df-127">**Теги.** При выборе в файл нагрузки включаются сведения о тегах.</span><span class="sxs-lookup"><span data-stu-id="bc9df-127">**Tags**: When selected, tagging information is included in the load file.</span></span>

- <span data-ttu-id="bc9df-128">**Контент**</span><span class="sxs-lookup"><span data-stu-id="bc9df-128">**Content**</span></span>
  
  - <span data-ttu-id="bc9df-129">**Личные** файлы. Выберите этот почтовый ящик, чтобы включить в набор отзывов личные файлы документов.</span><span class="sxs-lookup"><span data-stu-id="bc9df-129">**Native files**: Select this checkbox to include the native files of the documents in the review set.</span></span> <span data-ttu-id="bc9df-130">Если вы решите экспортировать личные файлы, у вас есть следующие параметры, как экспортировать беседы чата.</span><span class="sxs-lookup"><span data-stu-id="bc9df-130">If you choose to export native files, you have the following options for how export chat conversations.</span></span>
  
  - <span data-ttu-id="bc9df-131">**Параметры беседы**</span><span class="sxs-lookup"><span data-stu-id="bc9df-131">**Conversation options**</span></span>

    - <span data-ttu-id="bc9df-132">**Файлы бесед.** Этот параметр экспортирует восстановленные беседы чата.</span><span class="sxs-lookup"><span data-stu-id="bc9df-132">**Conversation files**: This option exports reconstructed chat conversations.</span></span> <span data-ttu-id="bc9df-133">Этот формат представляет беседы в форме, которая похожа на то, что пользователи видят в родном приложении.</span><span class="sxs-lookup"><span data-stu-id="bc9df-133">This format presents conversations in a form that resembles what users see in the native application.</span></span>

    - <span data-ttu-id="bc9df-134">**Отдельные сообщения чата.** Этот параметр экспортирует исходные файлы беседы, хранимые в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bc9df-134">**Individual chat messages**: This option exports the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="bc9df-135">**Options**</span><span class="sxs-lookup"><span data-stu-id="bc9df-135">**Options**</span></span>

  - <span data-ttu-id="bc9df-136">**Текстовые** файлы. — Этот параметр включает извлеченные текстовые версии родных файлов в экспорте.</span><span class="sxs-lookup"><span data-stu-id="bc9df-136">**Text files**: - This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="bc9df-137">Замените отредактируемые туземцы преобразованными **файлами PDF:** Если во время проверки создаются отредактируемые PDF-файлы, эти файлы доступны для экспорта.</span><span class="sxs-lookup"><span data-stu-id="bc9df-137">**Replace redacted natives with converted PDFs**: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="bc9df-138">Вы можете экспортировать только личные файлы, которые были отредактировали (не выбрав этот параметр), или вы можете выбрать этот параметр для экспорта pdf-файлов, содержащих фактические отредактации.</span><span class="sxs-lookup"><span data-stu-id="bc9df-138">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="bc9df-139">**Варианты вывода.** Экспортируемая информация доступна для скачивания непосредственно через веб-браузер или может быть отправлена в учетную запись Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="bc9df-139">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="bc9df-140">Первые два варианта позволяют напрямую скачивать.</span><span class="sxs-lookup"><span data-stu-id="bc9df-140">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="bc9df-141">Свободные файлы и **PSTs (по** возможности электронная почта добавляется в PSTs) : Файлы экспортируются в формате, напоминаемом исходной структуре каталогов, которую пользователи видели в своих родных приложениях.</span><span class="sxs-lookup"><span data-stu-id="bc9df-141">**Loose files and PSTs (email is added to PSTs when possible)**: Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="bc9df-142">Дополнительные сведения см. в разделе [Loose files and PST export structure.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="bc9df-142">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="bc9df-143">**Структура сжатого каталога.** Файлы экспортируются и включаются в загрузку.</span><span class="sxs-lookup"><span data-stu-id="bc9df-143">**Condensed directory structure**: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="bc9df-144">**Структура сжатого каталога, экспортируемая** в учетную запись Azure Storage: Файлы экспортируются в учетную запись Azure Storage организации.</span><span class="sxs-lookup"><span data-stu-id="bc9df-144">**Condensed directory structure exported to your Azure Storage account**: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="bc9df-145">Для этого параметра необходимо предоставить URL-адрес контейнера в учетной записи Azure Storage для экспорта файлов.</span><span class="sxs-lookup"><span data-stu-id="bc9df-145">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="bc9df-146">Кроме того, необходимо предоставить маркер подписи общего доступа (SAS) для учетной записи Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="bc9df-146">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="bc9df-147">Дополнительные сведения см. в [статью Экспорт документов в наборе отзывов к учетной записи Azure Storage.](download-export-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="bc9df-147">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

<span data-ttu-id="bc9df-148">В следующих разделах описывается структура папок для свободных файлов и параметры структуры каталогов.</span><span class="sxs-lookup"><span data-stu-id="bc9df-148">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="bc9df-149">Свободные файлы и структура экспорта PST</span><span class="sxs-lookup"><span data-stu-id="bc9df-149">Loose files and PST export structure</span></span>

<span data-ttu-id="bc9df-150">При выборе этого варианта экспорта экспортируемого контента организовано в следующей структуре:</span><span class="sxs-lookup"><span data-stu-id="bc9df-150">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="bc9df-151">Корневая папка: эта папка с именем ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="bc9df-151">Root folder: This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="bc9df-152">Export_load_file.csv: файл метаданных.</span><span class="sxs-lookup"><span data-stu-id="bc9df-152">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="bc9df-153">Summary.csv: сводный файл, который также содержит статистику экспорта.</span><span class="sxs-lookup"><span data-stu-id="bc9df-153">Summary.csv: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="bc9df-154">Exchange. Эта папка содержит все содержимое из Exchange в формате родного файла.</span><span class="sxs-lookup"><span data-stu-id="bc9df-154">Exchange: This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="bc9df-155">Файлы natives заменяются отредактируемыми PDF, если выбран параметр **Replace redacted natives с преобразованным вариантом PDFs.**</span><span class="sxs-lookup"><span data-stu-id="bc9df-155">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="bc9df-156">SharePoint. Эта папка содержит все родной контент из SharePoint в формате родного файла.</span><span class="sxs-lookup"><span data-stu-id="bc9df-156">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="bc9df-157">Файлы natives заменяются отредактируемыми PDF, если выбран параметр **Replace redacted natives с преобразованным вариантом PDFs.**</span><span class="sxs-lookup"><span data-stu-id="bc9df-157">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="bc9df-158">Структура сжатого каталога</span><span class="sxs-lookup"><span data-stu-id="bc9df-158">Condensed directory structure</span></span>

- <span data-ttu-id="bc9df-159">Корневая папка. Эта папка называется ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="bc9df-159">Root folder: This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="bc9df-160">Export_load_file.csv: файл метаданных.</span><span class="sxs-lookup"><span data-stu-id="bc9df-160">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="bc9df-161">Summary.txt: сводный файл, который также содержит статистику экспорта.</span><span class="sxs-lookup"><span data-stu-id="bc9df-161">Summary.txt: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="bc9df-162">NativeFiles. Эта папка содержит все личные файлы, которые были экспортируются.</span><span class="sxs-lookup"><span data-stu-id="bc9df-162">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="bc9df-163">Если вы экспортируете отредактные PDF-файлы, они не помещались в PST-файлы.</span><span class="sxs-lookup"><span data-stu-id="bc9df-163">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="bc9df-164">Вместо этого они добавляются в разделенную папку.</span><span class="sxs-lookup"><span data-stu-id="bc9df-164">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="bc9df-165">Error_files: Эта папка содержит следующие файлы ошибок, если они включены в экспорт:</span><span class="sxs-lookup"><span data-stu-id="bc9df-165">Error_files: This folder contains the following error files, if they are included in the export:</span></span>

    - <span data-ttu-id="bc9df-166">ExtractionError: CSV-файл, содержащий все доступные метаданные файлов, которые не были должным образом извлечены из родительских файлов.</span><span class="sxs-lookup"><span data-stu-id="bc9df-166">ExtractionError: A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>

    - <span data-ttu-id="bc9df-167">ProcessingError. Этот файл содержит список документов с ошибками обработки.</span><span class="sxs-lookup"><span data-stu-id="bc9df-167">ProcessingError: This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="bc9df-168">Это содержимое на уровне элементов, то есть если вложение привело к ошибке обработки, сообщение электронной почты, содержающее вложение, включено в эту папку.</span><span class="sxs-lookup"><span data-stu-id="bc9df-168">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="bc9df-169">Extracted_text_files. Эта папка содержит все извлеченные текстовые файлы, созданные при обработке.</span><span class="sxs-lookup"><span data-stu-id="bc9df-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>
