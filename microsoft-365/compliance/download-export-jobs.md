---
title: Загрузка заданий по экспорту для дела advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: Установите и используйте Проводник хранения Azure для скачивания документов, экспортируемого из набора обзоров в advanced eDiscovery.
ms.openlocfilehash: 0a73d157b2661202507883dd6542cdf6c6b482f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926625"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a><span data-ttu-id="c1e2b-103">Загрузка рабочих мест экспорта в случае с расширенным электронным открытием</span><span class="sxs-lookup"><span data-stu-id="c1e2b-103">Download export jobs in an Advanced eDiscovery case</span></span>

<span data-ttu-id="c1e2b-104">При экспорте документов из набора отзывов в случае с расширенным открытием электронных данных эти документы загружаются в расположение Хранилища Azure, предоставленное Майкрософт, или в хранилище Azure, управляемое вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="c1e2b-105">Тип используемого расположения хранилища Azure зависит от того, какой параметр был выбран при экспорте документов.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span>

<span data-ttu-id="c1e2b-106">В этой статье указаны инструкции по использованию проводника хранения Microsoft Azure для подключения к расположению Хранилища Azure для просмотра и загрузки экспортных документов.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="c1e2b-107">Дополнительные сведения о Azure Storage Explorer см. в [обзоре Quickstart: Use Azure Storage Explorer.](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="c1e2b-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="c1e2b-108">Шаг 1. Установка проводника хранения Azure</span><span class="sxs-lookup"><span data-stu-id="c1e2b-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="c1e2b-109">Первым шагом является загрузка и установка Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="c1e2b-110">Инструкции см. в [средстве Azure Storage Explorer.](https://go.microsoft.com/fwlink/p/?LinkId=544842)</span><span class="sxs-lookup"><span data-stu-id="c1e2b-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="c1e2b-111">Этот инструмент используется для подключения и загрузки экспортируемой документации в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="c1e2b-112">Шаг 2. Получение URL-адреса SAS из задания экспорта</span><span class="sxs-lookup"><span data-stu-id="c1e2b-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="c1e2b-113">Следующий шаг — получение URL-адреса подписи общего доступа (SAS), который создается при работе по экспорту для экспорта документов из [набора отзывов.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="c1e2b-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="c1e2b-114">Вы можете скопировать URL-адрес SAS для документов, загруженных в хранилище Azure, предоставленное Майкрософт, или в хранилище Azure, управляемое вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="c1e2b-115">В любом случае URL-адрес SAS используется для подключения к расположению Azure Storage в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="c1e2b-116">На странице **Advanced eDiscovery** перейдите к делу, а затем щелкните вкладку **Экспорт.**</span><span class="sxs-lookup"><span data-stu-id="c1e2b-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="c1e2b-117">На **вкладке Экспорт** щелкните задание экспорта, которое необходимо скачать.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="c1e2b-118">На странице вылет, в **статье Locations,** скопируйте URL-адрес SAS, отображаемый.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="c1e2b-119">При необходимости можно сохранить его в файле, чтобы получить к нему доступ на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![Скопируйте URL-адрес SAS, отображаемый в "Расположениях"](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="c1e2b-121">Шаг 3. Подключение к расположению хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="c1e2b-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="c1e2b-122">На заключительном этапе необходимо использовать Azure Storage Explorer и URL-адрес SAS для подключения к расположению Хранилища Azure и загрузки документов, экспортируемого на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1. <span data-ttu-id="c1e2b-123">Откройте azure Storage Explorer, установленный в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="c1e2b-124">Щелкните **значок Добавить учетную запись.**</span><span class="sxs-lookup"><span data-stu-id="c1e2b-124">Click the **Add account** icon.</span></span> <span data-ttu-id="c1e2b-125">Кроме того, вы можете щелкнуть правой кнопкой мыши **учетные записи хранения**.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![Щелкните значок Добавить учетную запись](../media/AzureStorageConnect.png)

3. <span data-ttu-id="c1e2b-127">На странице **Подключение к Azure Storage** нажмите кнопку Использование URI подписи общего доступа **(SAS)** и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![Нажмите кнопку Использование URI подписи общего доступа (SAS) и нажмите кнопку Далее](../media/AzureStorageConnect2.png)

4. <span data-ttu-id="c1e2b-129">На странице **Attach with SAS URI** щелкните поле URI и вложите URL-адрес SAS, полученный в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![Вклеить URL-адрес SAS в поле URI](../media/AzureStorageConnect3.png)

    <span data-ttu-id="c1e2b-131">Обратите внимание, что часть URL-адреса SAS отображается в поле **Имя отображения.**</span><span class="sxs-lookup"><span data-stu-id="c1e2b-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="c1e2b-132">Это будет использоваться в качестве отображаемого имени контейнера, созданного в учетных записях **хранилища** после подключения к расположению хранилища.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="c1e2b-133">Это имя состоит из идентификатора дела advanced eDiscovery и уникального идентификатора.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="c1e2b-134">Вы можете сохранить имя отображения по умолчанию или изменить его.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="c1e2b-135">Если вы измените его, имя отображения должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-135">If you change it, the display name must be unique.</span></span>

5. <span data-ttu-id="c1e2b-136">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-136">Click **Next**.</span></span>

    <span data-ttu-id="c1e2b-137">Отображается **страница сводки** подключения.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-137">The **Connection summary** page is displayed.</span></span>

    ![Нажмите кнопку Подключение на странице Сводка подключения, чтобы подключиться к расположению хранилища Azure](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="c1e2b-139">На странице **Сводка подключения** просмотрите сведения о подключении и нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span>

    <span data-ttu-id="c1e2b-140">Открывается **узел контейнеров Blob** (под **учетными** записями хранилища  >  **(Присоединенные** \> контейнеры).</span><span class="sxs-lookup"><span data-stu-id="c1e2b-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Экспорт заданий в узле контейнеров Blobs](../media/AzureStorageConnect5.png)

    <span data-ttu-id="c1e2b-142">Он содержит контейнер с именем отображения с шага 4.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="c1e2b-143">Этот контейнер содержит папку для каждой созданной вами экспортной работы.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="c1e2b-144">Эти папки называются с ИД, соответствующий ID задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="c1e2b-145">Эти экспортные документы (и имя экспорта) можно  найти на странице поддержки для  каждого задания по подготовке данных для экспорта, перечисленных на вкладке **Jobs.**</span><span class="sxs-lookup"><span data-stu-id="c1e2b-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="c1e2b-146">Дважды щелкните папку задания экспорта, чтобы открыть ее.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="c1e2b-147">Отображается список папок и отчетов об экспорте.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-147">A list of folders and export reports is displayed.</span></span>
   
    ![Папка экспорта содержит экспортные файлы и отчеты об экспорте](../media/AzureStorageConnect6.png)

   <span data-ttu-id="c1e2b-149">Папка задания экспорта содержит следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-149">The export job folder contains the following items.</span></span> <span data-ttu-id="c1e2b-150">Фактические элементы в папке экспорта определяются вариантами экспорта, настроенными при создания задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="c1e2b-151">Дополнительные сведения см. [в документе Export documents from a review set.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="c1e2b-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="c1e2b-152">Export_load_file.csv. Этот CSV-файл — это отчет о экспорте подробных сведений, содержащий сведения о каждом экспортируемом документе.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="c1e2b-153">Файл состоит из столбца для каждого свойства метаданных для документа.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="c1e2b-154">Список и описание метаданных, включенных в этот отчет, см. в статье Столбец имя экспортируемого поля в таблице в полях метаданных документов в [области advanced eDiscovery.](document-metadata-fields-in-advanced-ediscovery.md) </span><span class="sxs-lookup"><span data-stu-id="c1e2b-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
    
    - <span data-ttu-id="c1e2b-155">Summary.txt: текстовый файл, содержащий сводку экспорта, включая статистику экспорта.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="c1e2b-156">Extracted_text_files. Эта папка содержит текстовую версию каждого экспортируемого документа.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="c1e2b-157">NativeFiles. Эта папка содержит родную версию файла каждого экспортируемого документа.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="c1e2b-158">Error_files: Эта папка включает следующие элементы, когда в экспортной работе содержатся файлы ошибок:</span><span class="sxs-lookup"><span data-stu-id="c1e2b-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="c1e2b-159">ExtractionError.csv. Этот CSV-файл содержит доступные метаданные для файлов, которые не были должным образом извлечены из родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="c1e2b-160">ProcessingError. Эта папка содержит документы с ошибками обработки.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="c1e2b-161">Это содержимое находится на уровне элемента, что означает, что если у вложения была ошибка обработки, документ, содержащий вложение, также будет включен в эту папку.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="c1e2b-162">Чтобы экспортировать все содержимое в экспорте, выберите папку экспорта и нажмите кнопку **Скачать**.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="c1e2b-163">Укажите расположение, в котором необходимо скачать экспортируемую папку, а затем нажмите кнопку Выберите папку.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="c1e2b-164">Проводник хранения Azure запускает процесс экспорта.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="c1e2b-165">Состояние загрузки экспортных элементов отображается в области **Действия.**</span><span class="sxs-lookup"><span data-stu-id="c1e2b-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="c1e2b-166">Сообщение отображается по завершению загрузки.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-166">A message is displayed when the download is finished.</span></span>

    ![Сообщение отображается по завершению загрузки](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="c1e2b-168">Вместо загрузки всей экспортной работы можно выбрать конкретные элементы для скачивания.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="c1e2b-169">Вместо загрузки элементов можно дважды щелкнуть элемент, чтобы просмотреть его.</span><span class="sxs-lookup"><span data-stu-id="c1e2b-169">And instead of downloading items, you can double-click an item to view it.</span></span>