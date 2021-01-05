---
title: Загрузка заданий экспорта для дела Advanced eDiscovery
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
description: Установите и используйте обозреватель службы хранилища Azure для загрузки документов, которые были экспортируются из набора для проверки в Advanced eDiscovery.
ms.openlocfilehash: 094dcb4ecc8b1ca73a7ec0238ed20b27d4c16e72
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751296"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a><span data-ttu-id="79ff1-103">Загрузка заданий экспорта в случае Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="79ff1-103">Download export jobs in an Advanced eDiscovery case</span></span>

<span data-ttu-id="79ff1-104">При экспорте документов из набора для проверки в случае Advanced eDiscovery документы загружаются в предоставленное корпорацией Майкрософт хранилище Azure или в хранилище Azure, управляемое вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="79ff1-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="79ff1-105">Тип используемого хранилища Azure зависит от того, какой параметр был выбран при экспорте документов.</span><span class="sxs-lookup"><span data-stu-id="79ff1-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span>

<span data-ttu-id="79ff1-106">В этой статье данная статья содержит инструкции по использованию обозревателя хранилища Microsoft Azure для подключения к расположению хранилища Azure для просмотра и загрузки экспортных документов.</span><span class="sxs-lookup"><span data-stu-id="79ff1-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="79ff1-107">Дополнительные сведения о обозревателе службы хранилища Azure см. в [кратком обзоре: использование обозревателя службы хранилища Azure.](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="79ff1-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="79ff1-108">Шаг 1. Установка обозревателя хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="79ff1-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="79ff1-109">Первым шагом является загрузка и установка проводника службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="79ff1-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="79ff1-110">Инструкции см. в [средстве обозревателя службы хранилища Azure.](https://go.microsoft.com/fwlink/p/?LinkId=544842)</span><span class="sxs-lookup"><span data-stu-id="79ff1-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="79ff1-111">Это средство используется для подключения и загрузки экспортных документов в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="79ff1-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="79ff1-112">Шаг 2. Получение URL-адреса SAS из задания экспорта</span><span class="sxs-lookup"><span data-stu-id="79ff1-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="79ff1-113">Далее необходимо получить URL-адрес подписи общего доступа (SAS), который создается при созданном задание экспорта для экспорта документов из [набора для проверки.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="79ff1-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="79ff1-114">ВЫ можете скопировать URL-адрес SAS для документов, которые выложены в предоставленное Майкрософт хранилище Azure или хранилище Azure, управляемое вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="79ff1-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="79ff1-115">В любом случае url-адрес SAS используется для подключения к хранилищу Azure на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="79ff1-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="79ff1-116">На странице **Advanced eDiscovery** перейдите к делу и перейдите на вкладку **"Экспорт".**</span><span class="sxs-lookup"><span data-stu-id="79ff1-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="79ff1-117">На **вкладке "Экспорт"** щелкните задание экспорта, которое нужно скачать.</span><span class="sxs-lookup"><span data-stu-id="79ff1-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="79ff1-118">На странице "Расположения" на странице **"Расположения"** скопируйте url-адрес SAS, который отображается.</span><span class="sxs-lookup"><span data-stu-id="79ff1-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="79ff1-119">При необходимости вы можете сохранить его в файл, чтобы получить к нему доступ на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="79ff1-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![Копирование URL-адреса SAS, отображаемого в расположениях](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="79ff1-121">Шаг 3. Подключение к хранилищу Azure</span><span class="sxs-lookup"><span data-stu-id="79ff1-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="79ff1-122">Последний шаг — использование обозревателя хранилища Azure и URL-адреса SAS для подключения к расположению хранилища Azure и загрузки экспортных документов на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="79ff1-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1. <span data-ttu-id="79ff1-123">Откройте проводник службы хранилища Azure, установленный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="79ff1-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="79ff1-124">Щелкните **значок "Добавить учетную запись".**</span><span class="sxs-lookup"><span data-stu-id="79ff1-124">Click the **Add account** icon.</span></span> <span data-ttu-id="79ff1-125">Кроме того, можно щелкнуть правой кнопкой **мыши "Учетные записи хранения".**</span><span class="sxs-lookup"><span data-stu-id="79ff1-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![Щелкните значок "Добавить учетную запись"](../media/AzureStorageConnect.png)

3. <span data-ttu-id="79ff1-127">На странице **"Подключение к хранилищу Azure"** щелкните **"Использовать URI подписанного SAS"** и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="79ff1-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![Щелкните "Использовать URI подписанного SAS" и нажмите кнопку "Далее"](../media/AzureStorageConnect2.png)

4. <span data-ttu-id="79ff1-129">На странице "Присоединение с **URI SAS"** щелкните поле URI и вложите URL-адрес SAS, полученный на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="79ff1-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![В поле URI в поле "URL-адрес SAS" в поле "URL-адрес SAS"](../media/AzureStorageConnect3.png)

    <span data-ttu-id="79ff1-131">Обратите внимание, что часть URL-адреса SAS отображается в поле **отображаемого** имени.</span><span class="sxs-lookup"><span data-stu-id="79ff1-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="79ff1-132">Он будет использоваться в качестве отображаемого имени контейнера, созданного в учетных записях хранилища после подключения к месту хранения. </span><span class="sxs-lookup"><span data-stu-id="79ff1-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="79ff1-133">Это имя состоит из идентификатора дела Advanced eDiscovery и уникального идентификатора.</span><span class="sxs-lookup"><span data-stu-id="79ff1-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="79ff1-134">Можно сохранить отображаемую именем по умолчанию или изменить его.</span><span class="sxs-lookup"><span data-stu-id="79ff1-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="79ff1-135">Если вы измените его, отображаемое имя должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="79ff1-135">If you change it, the display name must be unique.</span></span>

5. <span data-ttu-id="79ff1-136">Щелкните кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="79ff1-136">Click **Next**.</span></span>

    <span data-ttu-id="79ff1-137">Отображается **страница сводки по** подключению.</span><span class="sxs-lookup"><span data-stu-id="79ff1-137">The **Connection summary** page is displayed.</span></span>

    ![Click Connect on the Connection summary page to connect to the Azure Storage location](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="79ff1-139">На странице **"Сводка по** подключению" просмотрите сведения о подключении и нажмите кнопку **"Подключиться".**</span><span class="sxs-lookup"><span data-stu-id="79ff1-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span>

    <span data-ttu-id="79ff1-140">Откроется **узел контейнеров BLOB** (в узле **"Учетные** записи хранилища  >  **(присоединенные** \> контейнеры").</span><span class="sxs-lookup"><span data-stu-id="79ff1-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Экспорт заданий в узле контейнеров BLOB](../media/AzureStorageConnect5.png)

    <span data-ttu-id="79ff1-142">Он содержит контейнер с отображаемой именем из шага 4.</span><span class="sxs-lookup"><span data-stu-id="79ff1-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="79ff1-143">Этот контейнер содержит папку для каждого созданного задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="79ff1-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="79ff1-144">Имена этих папок соответствуют ИД задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="79ff1-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="79ff1-145">Эти ИД экспорта (и имя экспорта) можно  найти на странице "Поддержка"  для каждого задания подготовки к экспорту, перечисленных на вкладке **"Задания".**</span><span class="sxs-lookup"><span data-stu-id="79ff1-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="79ff1-146">Дважды щелкните папку задания экспорта, чтобы открыть ее.</span><span class="sxs-lookup"><span data-stu-id="79ff1-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="79ff1-147">Отображается список папок и отчетов об экспорте.</span><span class="sxs-lookup"><span data-stu-id="79ff1-147">A list of folders and export reports is displayed.</span></span>
   
    ![Папка экспорта содержит экспортные файлы и отчеты об экспорте](../media/AzureStorageConnect6.png)

   <span data-ttu-id="79ff1-149">Папка задания экспорта содержит следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="79ff1-149">The export job folder contains the following items.</span></span> <span data-ttu-id="79ff1-150">Фактические элементы в папке экспорта определяются с помощью параметров экспорта, настроенных при создания задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="79ff1-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="79ff1-151">Дополнительные сведения см. в документе ["Экспорт документов из набора для проверки".](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="79ff1-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="79ff1-152">Export_load_file.csv: этот CSV-файл является подробным отчетом об экспорте, который содержит сведения о каждом экспортируемом документе.</span><span class="sxs-lookup"><span data-stu-id="79ff1-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="79ff1-153">Файл состоит из столбца для каждого свойства метаданных документа.</span><span class="sxs-lookup"><span data-stu-id="79ff1-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="79ff1-154">Список и описание метаданных, включенных в этот отчет, см. в столбце "Экспортируемое имя поля" таблицы в полях метаданных документа [в Advanced eDiscovery.](document-metadata-fields-in-advanced-ediscovery.md) </span><span class="sxs-lookup"><span data-stu-id="79ff1-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
    
    - <span data-ttu-id="79ff1-155">Summary.txt: текстовый файл, содержащий сводку по экспорту, включая статистику экспорта.</span><span class="sxs-lookup"><span data-stu-id="79ff1-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="79ff1-156">Extracted_text_files: эта папка содержит текстовую версию каждого экспортируемого документа.</span><span class="sxs-lookup"><span data-stu-id="79ff1-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="79ff1-157">NativeFiles: эта папка содержит свою версию файла каждого экспортируемого документа.</span><span class="sxs-lookup"><span data-stu-id="79ff1-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="79ff1-158">Error_files: эта папка содержит следующие элементы, если задание экспорта содержит файлы ошибок:</span><span class="sxs-lookup"><span data-stu-id="79ff1-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="79ff1-159">ExtractionError.csv: этот CSV-файл содержит доступные метаданные для файлов, которые не были надлежащим образом извлечены из родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="79ff1-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="79ff1-160">ProcessingError: эта папка содержит документы с ошибками обработки.</span><span class="sxs-lookup"><span data-stu-id="79ff1-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="79ff1-161">Это содержимое находится на уровне элемента, что означает, что если вложение имеет ошибку обработки, документ, содержащий вложение, также будет включен в эту папку.</span><span class="sxs-lookup"><span data-stu-id="79ff1-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="79ff1-162">Чтобы экспортировать все содержимое в экспорте, выберите папку экспорта и нажмите кнопку **"Скачать".**</span><span class="sxs-lookup"><span data-stu-id="79ff1-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="79ff1-163">Укажите расположение для загрузки экспортных файлов и нажмите кнопку "Выбрать папку".</span><span class="sxs-lookup"><span data-stu-id="79ff1-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="79ff1-164">Процесс экспорта запускается в проводнике службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="79ff1-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="79ff1-165">Состояние загрузки экспортных элементов отображается в **области** действий.</span><span class="sxs-lookup"><span data-stu-id="79ff1-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="79ff1-166">Сообщение отображается после завершения скачивания.</span><span class="sxs-lookup"><span data-stu-id="79ff1-166">A message is displayed when the download is finished.</span></span>

    ![Сообщение отображается после завершения скачивания](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="79ff1-168">Вместо скачивания всего задания экспорта можно выбрать конкретные элементы для скачивания.</span><span class="sxs-lookup"><span data-stu-id="79ff1-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="79ff1-169">Вместо скачивания элементов можно дважды щелкнуть элемент, чтобы просмотреть его.</span><span class="sxs-lookup"><span data-stu-id="79ff1-169">And instead of downloading items, you can double-click an item to view it.</span></span>
