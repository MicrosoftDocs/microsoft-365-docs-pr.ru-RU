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
description: Узнайте, как выбрать и экспортировать контент из набора Advanced eDiscovery для презентаций или внешних обзоров.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a174c147da6e424891508bad484f45f4a5d308b6
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461403"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="de210-103">Экспорт документов из набора обзоров в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="de210-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="de210-104">Экспорт позволяет пользователям настраивать контент, включенный в пакет загрузки при экспорте документа из набора отзывов в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="de210-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="de210-105">Экспорт документов из набора обзоров:</span><span class="sxs-lookup"><span data-stu-id="de210-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="de210-106">В Центр соответствия требованиям Microsoft 365 откройте Advanced eDiscovery, выберите вкладку **Наборы** обзоров и выберите набор отзывов, который необходимо экспортировать.</span><span class="sxs-lookup"><span data-stu-id="de210-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="de210-107">В наборе обзоров щелкните **Действие**  >  **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="de210-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="de210-108">Средство Экспорт отображает страницу вылетов с настройками экспорта.</span><span class="sxs-lookup"><span data-stu-id="de210-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="de210-109">Некоторые параметры выбираются по умолчанию, но их можно изменить.</span><span class="sxs-lookup"><span data-stu-id="de210-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="de210-110">В следующем разделе описаны параметры экспорта, которые можно настроить.</span><span class="sxs-lookup"><span data-stu-id="de210-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![Параметры конфигурации для экспорта элементов из набора отзывов](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="de210-112">После настройки экспорта щелкните **Экспорт,** чтобы запустить процесс экспорта.</span><span class="sxs-lookup"><span data-stu-id="de210-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="de210-113">В зависимости от выбранного в разделе **Параметры** вывода параметры, вы можете получить доступ к файлам экспорта путем прямой загрузки или в служба хранилища Azure учетной записи организации.</span><span class="sxs-lookup"><span data-stu-id="de210-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="de210-114">Рабочие места экспорта сохраняются в течение всего дела.</span><span class="sxs-lookup"><span data-stu-id="de210-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="de210-115">Однако необходимо скачать содержимое из задания экспорта в течение 30 дней после завершения задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="de210-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="de210-116">Параметры экспорта</span><span class="sxs-lookup"><span data-stu-id="de210-116">Export options</span></span>

<span data-ttu-id="de210-117">Чтобы настроить экспорт, используйте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="de210-117">Use the following options to configure the export.</span></span> <span data-ttu-id="de210-118">Не все параметры разрешены для некоторых выходных параметров, в частности, экспорт текстовых файлов и отредактировали PDF не допускается при экспорте в формат PST.</span><span class="sxs-lookup"><span data-stu-id="de210-118">Not all options are allowed for some output options, most notably, export of text files and redacted PDFs are not allowed when exporting to the PST format.</span></span>

- <span data-ttu-id="de210-119">**Имя экспорта.** Имя задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="de210-119">**Export name**: Name of the export job.</span></span> <span data-ttu-id="de210-120">Это будет использоваться для имени файлов ZIP, которые будут загружены.</span><span class="sxs-lookup"><span data-stu-id="de210-120">This will be used to name the ZIP files that will be downloaded.</span></span>

- <span data-ttu-id="de210-121">**Описание.** Поле для свободного текста для добавления описания.</span><span class="sxs-lookup"><span data-stu-id="de210-121">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="de210-122">**Экспорт этих документов**</span><span class="sxs-lookup"><span data-stu-id="de210-122">**Export these documents**</span></span>

  - <span data-ttu-id="de210-123">Только выбранные документы. Этот параметр экспортирует только выбранные документы.</span><span class="sxs-lookup"><span data-stu-id="de210-123">Selected documents only: This option exports only the documents that are currently selected.</span></span> <span data-ttu-id="de210-124">Этот параметр доступен только при выборе элементов в наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="de210-124">This option is only available when items are selected in a review set.</span></span>
  
  - <span data-ttu-id="de210-125">Все отфильтрованные документы. Этот параметр экспортирует документы в активном фильтре.</span><span class="sxs-lookup"><span data-stu-id="de210-125">All filtered documents: This option exports the documents in an active filter.</span></span> <span data-ttu-id="de210-126">Этот параметр доступен только при применении фильтра к набору отзывов.</span><span class="sxs-lookup"><span data-stu-id="de210-126">This option is only available when a filter is applied to the review set.</span></span>
  
  - <span data-ttu-id="de210-127">Все документы в наборе обзоров. Этот параметр экспортирует все документы в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="de210-127">All documents in the review set: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="de210-128">**Параметры** вывода. Экспортируемая информация доступна для скачивания непосредственно через веб-браузер или может быть отправлена в служба хранилища Azure учетную запись.</span><span class="sxs-lookup"><span data-stu-id="de210-128">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="de210-129">Первые два варианта позволяют напрямую скачивать.</span><span class="sxs-lookup"><span data-stu-id="de210-129">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="de210-130">Только отчеты. Создается только сводка и файл нагрузки.</span><span class="sxs-lookup"><span data-stu-id="de210-130">Reports only: Only the summary and load file are created.</span></span>
  
  - <span data-ttu-id="de210-131">Свободные файлы и PSTs (по возможности электронная почта добавляется в PSTs): Файлы экспортируются в формате, напоминаемом исходной структуре каталогов, которую пользователи видели в своих родных приложениях.</span><span class="sxs-lookup"><span data-stu-id="de210-131">Loose files and PSTs (email is added to PSTs when possible): Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="de210-132">Дополнительные сведения см. в разделе [Loose files and PST export structure.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="de210-132">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="de210-133">Структура сжатого каталога. Файлы экспортируются и включаются в загрузку.</span><span class="sxs-lookup"><span data-stu-id="de210-133">Condensed directory structure: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="de210-134">Структура сжатого каталога, экспортируемая в служба хранилища Azure учетную запись: файлы экспортируются в служба хранилища Azure учетную запись организации.</span><span class="sxs-lookup"><span data-stu-id="de210-134">Condensed directory structure exported to your Azure Storage account: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="de210-135">Для этого параметра необходимо предоставить URL-адрес контейнера в служба хранилища Azure учетной записи для экспорта файлов.</span><span class="sxs-lookup"><span data-stu-id="de210-135">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="de210-136">Вы также должны предоставить маркер подписи общего доступа (SAS) для служба хранилища Azure учетной записи.</span><span class="sxs-lookup"><span data-stu-id="de210-136">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="de210-137">Дополнительные сведения см. [в статью Экспорт документов в наборе отзывов к служба хранилища Azure учетной записи.](download-export-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="de210-137">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

- <span data-ttu-id="de210-138">**Include**</span><span class="sxs-lookup"><span data-stu-id="de210-138">**Include**</span></span>
  
  - <span data-ttu-id="de210-139">Теги. При выборе в файл нагрузки включаются сведения о тегах.</span><span class="sxs-lookup"><span data-stu-id="de210-139">Tags: When selected, tagging information is included in the load file.</span></span>
  
  - <span data-ttu-id="de210-140">Текстовые файлы. Этот параметр включает извлеченные текстовые версии родных файлов в экспорте.</span><span class="sxs-lookup"><span data-stu-id="de210-140">Text files: This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="de210-141">Замените отредактируемые туземцы преобразованными файлами PDF. Если во время проверки создаются отредактируемые ФАЙЛЫ PDF, эти файлы доступны для экспорта.</span><span class="sxs-lookup"><span data-stu-id="de210-141">Replace redacted natives with converted PDFs: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="de210-142">Вы можете экспортировать только личные файлы, которые были отредактировали (не выбрав этот параметр), или вы можете выбрать этот параметр для экспорта pdf-файлов, содержащих фактические отредактации.</span><span class="sxs-lookup"><span data-stu-id="de210-142">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

<span data-ttu-id="de210-143">В следующих разделах описывается структура папок для свободных файлов и параметры структуры каталогов.</span><span class="sxs-lookup"><span data-stu-id="de210-143">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span> <span data-ttu-id="de210-144">Экспорт разделяется на почтовые файлы с максимальным размером некомпрессируемого контента в 75 ГБ.</span><span class="sxs-lookup"><span data-stu-id="de210-144">Exports are partitioned into ZIP files with a maximum size of uncompressed content of 75 GB.</span></span> <span data-ttu-id="de210-145">Если размер экспорта меньше 75 ГБ, экспорт будет состоять из сводного файла и одного zip-файла.</span><span class="sxs-lookup"><span data-stu-id="de210-145">If the export size is less than 75 GB, the export will consist of a summary file and a single ZIP file.</span></span> <span data-ttu-id="de210-146">Для экспорта, объемом более 75 ГБ некомпрессивных данных, будет создано несколько почтовых файлов.</span><span class="sxs-lookup"><span data-stu-id="de210-146">For exports larger than 75 GB of uncompressed data, multiple ZIP files will be created.</span></span> <span data-ttu-id="de210-147">После загрузки zip-файлы можно отпечатать в одном расположении, чтобы воссоздать полный экспорт.</span><span class="sxs-lookup"><span data-stu-id="de210-147">Once downloaded, the ZIP files can be uncompressed into a single location to recreate the full export.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="de210-148">Свободные файлы и структура экспорта PST</span><span class="sxs-lookup"><span data-stu-id="de210-148">Loose files and PST export structure</span></span>

<span data-ttu-id="de210-149">При выборе этого варианта экспорта экспортируемого контента организовано в следующей структуре:</span><span class="sxs-lookup"><span data-stu-id="de210-149">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="de210-150">Summary.csv: включает сводку контента, экспортируемого из набора отзывов</span><span class="sxs-lookup"><span data-stu-id="de210-150">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="de210-151">Корневая папка. Эта папка с именем [Экспортное имя] x z.zip и будет повторяться для каждого раздела файла ZIP.</span><span class="sxs-lookup"><span data-stu-id="de210-151">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="de210-152">Export_load_file_x z.csv: файл метаданных.</span><span class="sxs-lookup"><span data-stu-id="de210-152">Export_load_file_x of z.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="de210-153">Предупреждения и ошибки x из z.csv. Этот файл содержит сведения об ошибках, с которыми сталкиваются при попытке экспорта из набора отзывов.</span><span class="sxs-lookup"><span data-stu-id="de210-153">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>
  
  - <span data-ttu-id="de210-154">Exchange. Эта папка содержит все содержимое из Exchange, хранимые в PST-файлах.</span><span class="sxs-lookup"><span data-stu-id="de210-154">Exchange: This folder contains all content from Exchange stored in PST files.</span></span> <span data-ttu-id="de210-155">Отредактировали PDF-файлы не могут быть включены в этот параметр.</span><span class="sxs-lookup"><span data-stu-id="de210-155">Redacted PDF files cannot be included with this option.</span></span> <span data-ttu-id="de210-156">Если в наборе отзывов выбрано вложение, родительское письмо будет экспортироваться с присоединенным вложением.</span><span class="sxs-lookup"><span data-stu-id="de210-156">If an attachment is selected in the review set, the parent email will be exported with the attachment attached.</span></span>
  
  - <span data-ttu-id="de210-157">SharePoint. Эта папка содержит все родной контент из SharePoint в формате родного файла.</span><span class="sxs-lookup"><span data-stu-id="de210-157">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="de210-158">Отредактировали PDF-файлы не могут быть включены в этот параметр.</span><span class="sxs-lookup"><span data-stu-id="de210-158">Redacted PDF files cannot be included with this option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="de210-159">Структура сжатого каталога</span><span class="sxs-lookup"><span data-stu-id="de210-159">Condensed directory structure</span></span>

- <span data-ttu-id="de210-160">Summary.csv: включает сводку контента, экспортируемого из набора отзывов</span><span class="sxs-lookup"><span data-stu-id="de210-160">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="de210-161">Корневая папка. Эта папка с именем [Экспортное имя] x z.zip и будет повторяться для каждого раздела файла ZIP.</span><span class="sxs-lookup"><span data-stu-id="de210-161">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="de210-162">Export_load_file_x z.csv: файл метаданных, а также расположение каждого файла, хранимого в файле ZIP.</span><span class="sxs-lookup"><span data-stu-id="de210-162">Export_load_file_x of z.csv: The metadata file and also includes the location of each file that is stored in the ZIP file.</span></span>
  
  - <span data-ttu-id="de210-163">Предупреждения и ошибки x из z.csv. Этот файл содержит сведения об ошибках, с которыми сталкиваются при попытке экспорта из набора отзывов.</span><span class="sxs-lookup"><span data-stu-id="de210-163">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>

  - <span data-ttu-id="de210-164">NativeFiles. Эта папка содержит все личные файлы, которые были экспортируются.</span><span class="sxs-lookup"><span data-stu-id="de210-164">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="de210-165">Файлы natives заменяются отредактируемыми PDF, если выбран параметр *Replace redacted natives с преобразованным вариантом PDFs.*</span><span class="sxs-lookup"><span data-stu-id="de210-165">Natives files are replaced with redacted PDFs if you selected the *Replace redacted natives with converted PDFs* option.</span></span>
  
  - <span data-ttu-id="de210-166">Error_files. Эта папка содержит файлы, которые имели либо извлечение, либо другую ошибку обработки.</span><span class="sxs-lookup"><span data-stu-id="de210-166">Error_files: This folder contains files that had either extraction or other processing error.</span></span> <span data-ttu-id="de210-167">Файлы будут помещаются в отдельные папки, как ExtractionError, так и ProcessingError.</span><span class="sxs-lookup"><span data-stu-id="de210-167">The files will be placed into separate folders, either ExtractionError or ProcessingError.</span></span> <span data-ttu-id="de210-168">Эти файлы перечислены в файле нагрузки.</span><span class="sxs-lookup"><span data-stu-id="de210-168">These files are listed in the load file.</span></span>

  - <span data-ttu-id="de210-169">Extracted_text_files. Эта папка содержит все извлеченные текстовые файлы, созданные при обработке.</span><span class="sxs-lookup"><span data-stu-id="de210-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a><span data-ttu-id="de210-170">Структура сжатого каталога, экспортируемая в служба хранилища Azure учетную запись</span><span class="sxs-lookup"><span data-stu-id="de210-170">Condensed directory structure exported to your Azure Storage Account</span></span>

<span data-ttu-id="de210-171">Этот параметр использует ту же общую структуру, что и структура сжатых каталогов, однако содержимое не зажато и данные сохраняются в вашей служба хранилища Azure учетной записи.</span><span class="sxs-lookup"><span data-stu-id="de210-171">This option uses the same general structure as the *Condensed directory structure*, however the contents is not zipped and the data is saved to your Azure Storage account.</span></span> <span data-ttu-id="de210-172">Этот параметр обычно используется при работе с сторонним поставщиком электронных данных.</span><span class="sxs-lookup"><span data-stu-id="de210-172">This option is generally used when working with a third-party eDiscovery provider.</span></span> <span data-ttu-id="de210-173">Дополнительные сведения об использовании этого параметра см. в материале [Export documents in a review set to an служба хранилища Azure account.](download-export-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="de210-173">For details about how to use this option, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>
