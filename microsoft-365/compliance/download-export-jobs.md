---
title: Экспорт документов в учетную запись служба хранилища Azure организации
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
ms.custom: seo-marvel-mar2020
description: Экспорт документов в обзоре, за набором для служба хранилища Azure учетной записи, а затем Обозреватель службы хранилища Azure для их загрузки на локальный компьютер.
ms.openlocfilehash: dfb3892f31e857d4744f6da337c924efaa87ab11
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574731"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a><span data-ttu-id="9fdbe-103">Экспорт документов в наборе отзывов для служба хранилища Azure учетной записи</span><span class="sxs-lookup"><span data-stu-id="9fdbe-103">Export documents in a review set to an Azure Storage account</span></span>

<span data-ttu-id="9fdbe-104">При экспорте документов из набора отзывов в Advanced eDiscovery случае вы можете экспортировать их в учетную запись служба хранилища Azure, управляемой вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-104">When you export documents from a review set in an Advanced eDiscovery case, you have the option to export them to an Azure Storage account managed by your organization.</span></span> <span data-ttu-id="9fdbe-105">Если вы использовали этот параметр, документы загружаются в ваше служба хранилища Azure расположение.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-105">If you used this option, the documents are uploaded to your Azure Storage location.</span></span> <span data-ttu-id="9fdbe-106">После их экспорта можно получить доступ к документам (и загрузить их на локальный компьютер или другое расположение) с помощью Обозреватель службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-106">After they are exported, you can access the documents (and download them to a local computer or other location) by using the Azure Storage Explorer.</span></span> <span data-ttu-id="9fdbe-107">В этой статье данная статья содержит инструкции по экспорту документов на служба хранилища Azure учетной записи и использованию Обозреватель службы хранилища Azure для подключения к служба хранилища Azure для загрузки экспортных документов.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-107">This article provides instructions for how to export documents to your Azure Storage account and the use the Azure Storage Explorer to connect to an Azure Storage location to download the exported documents.</span></span> <span data-ttu-id="9fdbe-108">Дополнительные сведения о Обозреватель службы хранилища Azure см. в [Обозреватель службы хранилища Azure.](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="9fdbe-108">For more information about Azure Storage Explorer, see [Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="before-you-export-documents-from-a-review-set"></a><span data-ttu-id="9fdbe-109">Перед экспортом документов из набора отзывов</span><span class="sxs-lookup"><span data-stu-id="9fdbe-109">Before you export documents from a review set</span></span>

- <span data-ttu-id="9fdbe-110">Для экспорта документов из набора отзывов необходимо предоставить маркер подписи общего доступа (SAS) для учетной записи служба хранилища Azure и URL-адрес определенного контейнера в учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-110">You need to provide a shared access signature (SAS) token for your Azure Storage account and the URL for a specific container in the storage account to export documents from a review set.</span></span> <span data-ttu-id="9fdbe-111">Убедитесь, что они под рукой (например, скопированные в текстовый файл) при выполнении шага 2</span><span class="sxs-lookup"><span data-stu-id="9fdbe-111">Be sure to have these at hand (for example, copied to a text file) when you perform Step 2</span></span>

  - <span data-ttu-id="9fdbe-112">**Маркер SAS.** Не забудьте получить маркер SAS для вашей служба хранилища Azure учетной записи (а не для контейнера).</span><span class="sxs-lookup"><span data-stu-id="9fdbe-112">**SAS token**: Be sure to get the SAS token is for your Azure Storage account (and not for the container).</span></span> <span data-ttu-id="9fdbe-113">Вы можете создать маркер SAS для вашей учетной записи в служба хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-113">You can generate an SAS token for your account in Azure Storage.</span></span> <span data-ttu-id="9fdbe-114">Для этого перейдите служба хранилища Azure учетную запись и  выберите подпись доступа **к share** под Параметры параметров в лезвии учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-114">To do this, go to the Azure Storage account, and select **Share access signature** under the **Settings** settings in the storage account blade.</span></span> <span data-ttu-id="9fdbe-115">Используйте параметры по умолчанию и разрешайте все типы ресурсов при создании маркера SAS.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-115">Use the default settings and allow all resource types when you generate the SAS token.</span></span>

  - <span data-ttu-id="9fdbe-116">**URL-адрес** контейнера. Для загрузки документов набора отзывов необходимо создать контейнер, а затем получить копию URL-адреса для контейнера; например, `https://ediscoverydata.blob.core.windows.net/exportdata` .</span><span class="sxs-lookup"><span data-stu-id="9fdbe-116">**Container URL**: You need to create a container to upload the review set documents to, and then get a copy of the URL for the container; for example, `https://ediscoverydata.blob.core.windows.net/exportdata`.</span></span> <span data-ttu-id="9fdbe-117">Чтобы получить URL-адрес, перейдите в контейнер в  служба хранилища Azure и выберите Свойства в разделе **Параметры** в лезвии контейнера.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-117">To get the URL, go to the container in Azure Storage, and select **Properties** under the **Settings** section in the container blade.</span></span>

- <span data-ttu-id="9fdbe-118">Скачайте и установите Обозреватель службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-118">Download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="9fdbe-119">Инструкции см. [в Обозреватель службы хранилища Azure.](https://go.microsoft.com/fwlink/p/?LinkId=544842)</span><span class="sxs-lookup"><span data-stu-id="9fdbe-119">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="9fdbe-120">Этот инструмент используется для подключения к контейнеру в служба хранилища Azure учетной записи и загрузки документов, экспортируемой в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-120">You use this tool to connect to the container in your Azure Storage account and download the documents that you exported in Step 1.</span></span>

## <a name="step-1-export-the-documents-from-a-review-set"></a><span data-ttu-id="9fdbe-121">Шаг 1. Экспорт документов из набора отзывов</span><span class="sxs-lookup"><span data-stu-id="9fdbe-121">Step 1: Export the documents from a review set</span></span>

<span data-ttu-id="9fdbe-122">Первым шагом является создание задания экспорта для экспорта документов из набора отзывов.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-122">The first step is to create an export job to export documents out of a review set.</span></span> <span data-ttu-id="9fdbe-123">Дополнительные инструкции по всем вариантам экспорта см. в документе [Export documents from a review set.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="9fdbe-123">For more detailed instructions about all the export options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="9fdbe-124">В следующей процедуре выделены параметры экспорта документов в учетную запись служба хранилища Azure организации.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-124">The following procedure highlights the settings to export documents to your organization's Azure Storage account.</span></span>

1. <span data-ttu-id="9fdbe-125">В центре Microsoft 365 откройте Advanced eDiscovery, выберите вкладку **Наборы** отзывов, а затем выберите набор отзывов, который необходимо экспортировать.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-125">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="9fdbe-126">В наборе обзоров щелкните **Действие**  >  **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-126">In the review set, click **Action** > **Export**.</span></span>

3. <span data-ttu-id="9fdbe-127">На странице **флажок** "Параметры экспорта" введите имя (обязательно) и описание (необязательно) для экспорта.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-127">On the **Export options** flyout page, type a name (required) and description (optional) for the export.</span></span>

4. <span data-ttu-id="9fdbe-128">Настройка параметров в разделах документы, метаданные, контент и параметры.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-128">Configure the settings in the documents, metadata, content, and options sections.</span></span> <span data-ttu-id="9fdbe-129">Дополнительные сведения об этих параметрах см. в документе [Export documents from a review set.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="9fdbe-129">For more information about these settings, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

5. <span data-ttu-id="9fdbe-130">В разделе **Параметры вывода** выберите структуру сконденсируемого каталога, экспортируемую в **служба хранилища Azure учетную** запись.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-130">In the **Output options** section, select the **Condensed directory structure exported to your Azure Storage account** option.</span></span>

6. <span data-ttu-id="9fdbe-131">Вклейте URL-адрес контейнера и маркер SAS для учетной записи хранилища в соответствующих полях.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-131">Paste the container URL and the SAS token for your storage account in the corresponding fields.</span></span>

   ![Вклеить URL-адрес подключения и маркер SAS в соответствующих полях](../media/AzureStorageOutputOptions.png)

7. <span data-ttu-id="9fdbe-133">Нажмите **кнопку Экспорт** для создания задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-133">Click **Export** to create the export job.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="9fdbe-134">Шаг 2. Получение URL-адреса SAS из задания экспорта</span><span class="sxs-lookup"><span data-stu-id="9fdbe-134">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="9fdbe-135">Следующий шаг — получение URL-адреса SAS, который создается после создания задания экспорта в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-135">The next step is to obtain the SAS URL that's generated after you create the export job in Step 1.</span></span> <span data-ttu-id="9fdbe-136">URL-адрес SAS используется для подключения к контейнеру в служба хранилища Azure учетной записи, в которую вы экспортировали документы набора отзывов.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-136">You use the SAS URL to connect to the container in your Azure Storage account that you exported the review set documents to.</span></span>

1. <span data-ttu-id="9fdbe-137">На странице **Advanced eDiscovery** перейдите к делу, а затем щелкните вкладку **Экспорт.**</span><span class="sxs-lookup"><span data-stu-id="9fdbe-137">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="9fdbe-138">На вкладке **Экспорт** щелкните задание экспорта, которое необходимо скачать.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-138">On the **Exports** tab, click the export job that you want to download.</span></span> <span data-ttu-id="9fdbe-139">Это задание экспорта, созданное в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-139">This is the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="9fdbe-140">На странице вылет, в **статье Locations,** скопируйте URL-адрес SAS, отображаемый.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-140">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="9fdbe-141">При необходимости можно сохранить его в текстовом файле, чтобы получить к нему доступ на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-141">If necessary, you can save it to a text file so you can access it in Step 3.</span></span>

   ![Скопируйте URL-адрес SAS, отображаемый в "Расположениях"](../media/eDiscoExportJob.png)

   > [!TIP]
   > <span data-ttu-id="9fdbe-143">URL-адрес SAS, отображаемый в экспортной работе, является конкатецией URL-адреса контейнера и маркера SAS для служба хранилища Azure учетной записи.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-143">The SAS URL that's displayed in the export job is a concatenation of the container URL and the SAS token for your Azure Storage account.</span></span> <span data-ttu-id="9fdbe-144">Вы можете скопировать его из задания экспорта или создать его самостоятельно, объединив URL-адрес и маркер SAS.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-144">You can copy it from the export job or create it yourself by combining the URL and the SAS token.</span></span>

## <a name="step-3-connect-to-the-azure-storage-container"></a><span data-ttu-id="9fdbe-145">Шаг 3. Подключение в контейнер служба хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="9fdbe-145">Step 3: Connect to the Azure Storage container</span></span>

<span data-ttu-id="9fdbe-146">Последний шаг — использовать URL Обозреватель службы хранилища Azure и URL-адрес SAS для подключения к контейнеру в служба хранилища Azure учетной записи и загрузки экспортных документов на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-146">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the container in your Azure Storage account and download the exported documents to a local computer.</span></span>

1. <span data-ttu-id="9fdbe-147">Запустите Обозреватель службы хранилища Azure, который вы скачали и установили.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-147">Start the Azure Storage Explorer that you downloaded and installed.</span></span>

2. <span data-ttu-id="9fdbe-148">Щелкните **значок Подключение диалоговое окно.**</span><span class="sxs-lookup"><span data-stu-id="9fdbe-148">Click the **Open Connect Dialog** icon.</span></span>

   ![Щелкните значок Добавить учетную запись](../media/AzureStorageConnect.png)

3. <span data-ttu-id="9fdbe-150">На странице **Подключение служба хранилища Azure** щелкните **контейнер Blob**.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-150">On the **Connect to Azure Storage** page, click **Blob container**.</span></span>

4. <span data-ttu-id="9fdbe-151">На странице **Выбор метода проверки подлинности** выберите параметр Подпись общего доступа **(SAS)** и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-151">On the **Select Authentication Method** page, select the **Shared access signature (SAS)** option and then click **Next**.</span></span>

5. <span data-ttu-id="9fdbe-152">На странице **Enter Connection Info** введите URL-адрес SAS (полученный в экспортной работе в шаге 2) в поле URL-адрес SAS контейнера **Blob.**</span><span class="sxs-lookup"><span data-stu-id="9fdbe-152">On the **Enter Connection Info** page, paste the SAS URL (that you obtained in the export job in Step 2) in the **Blob Container SAS URL** box.</span></span>

    ![Вклеить URL-адрес SAS в поле URI](../media/AzureStorageConnect3.png)

    <span data-ttu-id="9fdbe-154">Обратите внимание, что имя контейнера отображается в поле **Отображения имен.**</span><span class="sxs-lookup"><span data-stu-id="9fdbe-154">Notice that the container name is displayed in the **Display name** box.</span></span> <span data-ttu-id="9fdbe-155">Вы можете изменить это имя.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-155">You can edit this name.</span></span>

6. <span data-ttu-id="9fdbe-156">Нажмите **кнопку Далее,** чтобы **отобразить сводную** страницу, а затем **нажмите кнопку Подключение**.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-156">Click **Next** to display the **summary** page and then click **Connect**.</span></span>

    <span data-ttu-id="9fdbe-157">Открывается **узел контейнеров Blob** **(служба хранилища учетные** записи  >  **(присоединенные** \> контейнеры).</span><span class="sxs-lookup"><span data-stu-id="9fdbe-157">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Экспорт заданий в узле контейнеров Blobs](../media/AzureStorageConnect5.png)

    <span data-ttu-id="9fdbe-159">Он содержит контейнер с именем отображения из шага 5.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-159">It contains a container named with the display name from step 5.</span></span> <span data-ttu-id="9fdbe-160">Этот контейнер содержит папку для каждой экспортной работы, которую вы скачали в контейнер в служба хранилища Azure учетной записи.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-160">This container contains a folder for each export job that you've downloaded to the container in your Azure Storage account.</span></span> <span data-ttu-id="9fdbe-161">Эти папки называются с ИД, соответствующий ID задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-161">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="9fdbe-162">Эти экспортные ID (и имя экспорта) можно  найти на странице поддержки  для каждого задания по подготовке данных для экспорта, перечисленных на вкладке **Jobs** в Advanced eDiscovery случае.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-162">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab in the Advanced eDiscovery case.</span></span>

7. <span data-ttu-id="9fdbe-163">Дважды щелкните папку задания экспорта, чтобы открыть ее.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-163">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="9fdbe-164">Отображается список папок и отчетов об экспорте.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-164">A list of folders and export reports is displayed.</span></span>

    ![Папка экспорта содержит экспортные файлы и отчеты об экспорте](../media/AzureStorageConnect6.png)

8. <span data-ttu-id="9fdbe-166">Чтобы экспортировать все содержимое из задания экспорта, щелкните стрелку **Up,** чтобы вернуться в папку задания экспорта, а затем нажмите кнопку **Скачать**.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-166">To export all contents from the export job, click the **Up** arrow to go back to the export job folder, and then click **Download**.</span></span>

9. <span data-ttu-id="9fdbe-167">Укажите расположение для скачивания экспортируемых файлов и нажмите кнопку Выбрать папку.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-167">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="9fdbe-168">В Обозреватель службы хранилища Azure запускается процесс загрузки.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-168">The Azure Storage Explorer starts the download process.</span></span> <span data-ttu-id="9fdbe-169">Состояние загрузки экспортных элементов отображается в области **Действия.**</span><span class="sxs-lookup"><span data-stu-id="9fdbe-169">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="9fdbe-170">Сообщение отображается после завершения загрузки.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-170">A message is displayed when the download is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="9fdbe-171">Вместо загрузки всей экспортной работы в Обозреватель службы хранилища Azure можно выбрать определенные элементы для скачивания и просмотра.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-171">Instead of downloading the entire export job in Azure Storage Explorer, you can select specific items to download and view.</span></span>

## <a name="more-information"></a><span data-ttu-id="9fdbe-172">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="9fdbe-172">More information</span></span>

- <span data-ttu-id="9fdbe-173">Папка задания экспорта содержит следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-173">The export job folder contains the following items.</span></span> <span data-ttu-id="9fdbe-174">Фактические элементы в папке экспорта определяются вариантами экспорта, настроенными при создания задания экспорта.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-174">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="9fdbe-175">Дополнительные сведения об этих параметрах см. в [документе Export documents from a review set.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="9fdbe-175">For more information about these options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

  - <span data-ttu-id="9fdbe-176">Export_load_file.csv. Этот CSV-файл — это отчет о экспорте подробных сведений, содержащий сведения о каждом экспортируемом документе.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-176">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="9fdbe-177">Файл состоит из столбца для каждого свойства метаданных для документа.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-177">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="9fdbe-178">Список и описание метаданных, включенных в этот отчет, см. в столбце Имя экспортируемого поля в таблице в полях метаданных документов в [Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md). </span><span class="sxs-lookup"><span data-stu-id="9fdbe-178">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>

  - <span data-ttu-id="9fdbe-179">Summary.txt: текстовый файл, содержащий сводку экспорта, включая статистику экспорта.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-179">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>

  - <span data-ttu-id="9fdbe-180">Extracted_text_files. Эта папка содержит текстовую версию каждого экспортируемого документа.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-180">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>

  - <span data-ttu-id="9fdbe-181">NativeFiles. Эта папка содержит родную версию файла каждого экспортируемого документа.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-181">NativeFiles: This folder contains a native file version of each exported document.</span></span>

  - <span data-ttu-id="9fdbe-182">Error_files: Эта папка включает следующие элементы, когда в экспортной работе содержатся файлы ошибок:</span><span class="sxs-lookup"><span data-stu-id="9fdbe-182">Error_files: This folder includes the following items when the export job contains any error files:</span></span>

    - <span data-ttu-id="9fdbe-183">ExtractionError.csv. Этот CSV-файл содержит доступные метаданные для файлов, которые не были должным образом извлечены из родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-183">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>

    - <span data-ttu-id="9fdbe-184">ProcessingError. Эта папка содержит документы с ошибками обработки.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-184">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="9fdbe-185">Это содержимое находится на уровне элемента, что означает, что если у вложения была ошибка обработки, документ, содержащий вложение, также будет включен в эту папку.</span><span class="sxs-lookup"><span data-stu-id="9fdbe-185">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
