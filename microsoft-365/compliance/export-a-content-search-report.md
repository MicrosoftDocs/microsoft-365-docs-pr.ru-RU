---
title: Экспорт отчета о поиске контента
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Вместо экспорта фактических результатов поиска контента в Центре & безопасности в Office 365 можно экспортировать отчет о результатах поиска. Отчет содержит сводку результатов поиска и документ с подробными сведениями о каждом экспортируемом элементе.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311577"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="b0b15-104">Экспорт отчета о поиске контента</span><span class="sxs-lookup"><span data-stu-id="b0b15-104">Export a Content search report</span></span>

<span data-ttu-id="b0b15-105">Вместо экспорта полного набора результатов поиска из поиска контента в центре соответствия требованиям Microsoft 365 (или из поиска, связанного с делом об обнаружении основных данных), можно экспортировать те же отчеты, которые создаются при экспорте фактических результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="b0b15-105">Instead of exporting the full set of search results from a Content search in the Microsoft 365 compliance Center (or from a search that's associated with a Core eDiscovery case), you can export the same reports that are generated when you export the actual search results.</span></span>
  
<span data-ttu-id="b0b15-106">При экспорте отчета файлы отчетов загружаются в папку на локальном компьютере с тем же именем, что и поиск контента, но приложенные _ReportsOnly *.*</span><span class="sxs-lookup"><span data-stu-id="b0b15-106">When you export a report, the report files are downloaded to a folder on your local computer that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="b0b15-107">Например, если поиск контента называется  *ContosoCase0815,* отчет загружается в папку с именем *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="b0b15-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="b0b15-108">Список документов, включенных в отчет, см. в документе [What's included in the report.](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="b0b15-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-export-a-search-report"></a><span data-ttu-id="b0b15-109">Перед экспортом отчета о поиске</span><span class="sxs-lookup"><span data-stu-id="b0b15-109">Before you export a search report</span></span>

- <span data-ttu-id="b0b15-110">Чтобы экспортировать отчет о поиске, необходимо навести роль управления поиском соответствия требованиям в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b0b15-110">To export a search report, you have to be assigned the Compliance Search management role in Security & Compliance Center.</span></span> <span data-ttu-id="b0b15-111">Эта роль по умолчанию назначена встроенным группам управления электронными данными и группами ролей управления организацией.</span><span class="sxs-lookup"><span data-stu-id="b0b15-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="b0b15-112">Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b0b15-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="b0b15-113">При экспорте отчета данные временно хранятся в локальном служба хранилища Azure в облаке Майкрософт перед его загрузкой на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="b0b15-113">When you export a report, the data is temporarily stored in an Azure Storage location in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="b0b15-114">Убедитесь, что ваша организация может подключиться к конечной точке Azure, которая **\* является .blob.core.windows.net** (подмывка представляет уникальный идентификатор для экспорта).</span><span class="sxs-lookup"><span data-stu-id="b0b15-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="b0b15-115">Данные результатов поиска удаляются из служба хранилища Azure через две недели после создания.</span><span class="sxs-lookup"><span data-stu-id="b0b15-115">The search results data is deleted from the Azure Storage location two weeks after it's created.</span></span>

- <span data-ttu-id="b0b15-116">Компьютер, используемый для экспорта результатов поиска, должен соответствовать указанным ниже требованиям к системе.</span><span class="sxs-lookup"><span data-stu-id="b0b15-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="b0b15-117">Последняя версия Windows (32-битная или 64-битная)</span><span class="sxs-lookup"><span data-stu-id="b0b15-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="b0b15-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="b0b15-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="b0b15-119">Для запуска экспортного средства eDiscovery 1 необходимо использовать один из следующих поддерживаемых<sup>браузеров.</sup></span><span class="sxs-lookup"><span data-stu-id="b0b15-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="b0b15-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b0b15-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="b0b15-121">OR</span><span class="sxs-lookup"><span data-stu-id="b0b15-121">OR</span></span>

  - <span data-ttu-id="b0b15-122">Microsoft Internet Explorer 10 и более поздних версиях</span><span class="sxs-lookup"><span data-stu-id="b0b15-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="b0b15-123"><sup>1</sup> Корпорация Майкрософт не производит сторонние расширения или надстройки для ClickOnce приложений.</span><span class="sxs-lookup"><span data-stu-id="b0b15-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="b0b15-124">Экспорт результатов поиска с помощью неподдермеченного браузера с сторонними расширениями или надстройки не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b0b15-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="b0b15-125"><sup>2</sup> В результате недавних изменений Microsoft Edge ClickOnce по умолчанию поддержка больше не включена.</span><span class="sxs-lookup"><span data-stu-id="b0b15-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="b0b15-126">Инструкции по включению ClickOnce поддержки в Edge см. в инструкции [Use the eDiscovery Export Tool in Microsoft Edge.](configure-edge-to-export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="b0b15-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="b0b15-127">Если предполагаемый общий размер результатов, возвращенных в результате поиска, превышает 2 ТБ, экспорт отчетов не удается.</span><span class="sxs-lookup"><span data-stu-id="b0b15-127">If the estimated total size of the results returned by search exceeds 2 TB, exporting the reports fails.</span></span> <span data-ttu-id="b0b15-128">Чтобы успешно экспортировать отчеты, попробуйте сузить область поиска и перезахоранить поиск, чтобы предполагаемый размер результатов не превышает 2 ТБ.</span><span class="sxs-lookup"><span data-stu-id="b0b15-128">To successfully export the reports, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="b0b15-129">Если результаты поиска старше 7 дней и вы представляете задание отчета об экспорте, отображается сообщение об ошибке, в результате которое будет отображаться повторное повторение поиска для обновления результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="b0b15-129">If the results of a search are older than 7 days and you submit an export report job, an error message is displayed prompting you to rerun the search to update the search results.</span></span> <span data-ttu-id="b0b15-130">Если это произойдет, отмените экспорт, повторно запустите поиск и снова запустите экспорт.</span><span class="sxs-lookup"><span data-stu-id="b0b15-130">If this happens, cancel the export, rerun the search, and then start the export again.</span></span>

- <span data-ttu-id="b0b15-131">Экспорт отчетов о поиске учитывает максимальное количество экспортов, запущенных одновременно, и максимальное число экспортов, которые может выполнить один пользователь.</span><span class="sxs-lookup"><span data-stu-id="b0b15-131">Exporting search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="b0b15-132">Дополнительные сведения об ограничениях экспорта см. в результатах [поиска по экспорту контента.](export-search-results.md#export-limits)</span><span class="sxs-lookup"><span data-stu-id="b0b15-132">For more information about export limits, see [Export Content search results](export-search-results.md#export-limits).</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="b0b15-133">Шаг 1. Создание отчета для экспорта</span><span class="sxs-lookup"><span data-stu-id="b0b15-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="b0b15-134">Первый шаг — подготовка отчета для загрузки на экспорт компьютера.</span><span class="sxs-lookup"><span data-stu-id="b0b15-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="b0b15-135">При экспорте отчета документы отчета загружаются в область служба хранилища Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b0b15-135">When you export the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="b0b15-136">В центре Microsoft 365 выберите поиск контента, из который необходимо экспортировать отчет.</span><span class="sxs-lookup"><span data-stu-id="b0b15-136">In the Microsoft 365 compliance center, select the Content search that you want to export the report from.</span></span>
  
2. <span data-ttu-id="b0b15-137">В меню **Действия** в нижней части страницы вылетов поиска щелкните **Отчет о экспорте**.</span><span class="sxs-lookup"><span data-stu-id="b0b15-137">On the **Actions** menu at the bottom of the search flyout page, click **Export report**.</span></span>

   ![Вариант экспортируемого отчета в меню Действия](../media/ActionMenuExportReport.png)

   <span data-ttu-id="b0b15-139">Отображается **страница вылетов** отчетов о экспорте.</span><span class="sxs-lookup"><span data-stu-id="b0b15-139">The **Export report** flyout page is displayed.</span></span> <span data-ttu-id="b0b15-140">Параметры экспортного отчета, доступные для экспорта сведений о поиске, зависят от того, находятся ли результаты поиска в почтовых ящиках или на сайтах или в сочетании обоих.</span><span class="sxs-lookup"><span data-stu-id="b0b15-140">The export report options available to export information about the search depend on whether search results are located in mailboxes or sites or a combination of both.</span></span>
  
3. <span data-ttu-id="b0b15-141">В **параметрах Output** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="b0b15-141">Under **Output options**, choose one of the following options:</span></span>
  
   ![Параметры вывода экспорта](../media/ExportOutputOptions.png)

    - <span data-ttu-id="b0b15-143">**Все элементы, за исключением** элементов непризнаного формата, шифруются или не индексируются по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="b0b15-143">**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="b0b15-144">Этот параметр экспортирует только сведения об индексируемом элементе.</span><span class="sxs-lookup"><span data-stu-id="b0b15-144">This option only exports information about indexed items.</span></span>
  
    - <span data-ttu-id="b0b15-145">**Все элементы, в** том числе непризнаваемого формата, шифруются или не индексируются по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="b0b15-145">**All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="b0b15-146">Этот параметр экспортирует сведения об индексных и неиндексуальных элементов.</span><span class="sxs-lookup"><span data-stu-id="b0b15-146">This option exports information about indexed and unindexed items.</span></span>
  
    - <span data-ttu-id="b0b15-147">**Шифруются** только элементы, которые имеют непризнаненный формат или не индексируются по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="b0b15-147">**Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="b0b15-148">Этот параметр экспортирует только сведения о неиндексуальных элементов.</span><span class="sxs-lookup"><span data-stu-id="b0b15-148">This option only exports information about unindexed items.</span></span>

4. <span data-ttu-id="b0b15-149">Настройка **параметра Enable de-duplication для Exchange** контента.</span><span class="sxs-lookup"><span data-stu-id="b0b15-149">Configure the **Enable de-duplication for Exchange content** option.</span></span>
  
   - <span data-ttu-id="b0b15-150">При выборе этого параметра в сводный отчет об экспорте включается количество дублирующих сообщений (перед де дубликатированием и после дублирования).</span><span class="sxs-lookup"><span data-stu-id="b0b15-150">If you select this option, the count of duplicate messages (before de-duplication and after de-duplication) is included in the export summary report.</span></span> <span data-ttu-id="b0b15-151">Кроме того, в файл manifest.xml будет включена только одна копия сообщения.</span><span class="sxs-lookup"><span data-stu-id="b0b15-151">Also, only one copy of a message will be included in the manifest.xml file.</span></span> <span data-ttu-id="b0b15-152">Но отчет о результатах экспорта будет содержать строку для каждой копии дублируемого сообщения, чтобы можно было определить почтовые ящики, содержащие копию дубликатного сообщения.</span><span class="sxs-lookup"><span data-stu-id="b0b15-152">But the export results report will contain a row for every copy of a duplicate message so that you can identify the mailboxes that contain a copy of the duplicate message.</span></span> <span data-ttu-id="b0b15-153">Дополнительные сведения об экспортируемом отчете см. в дополнительных сведениях о том, [что включено в отчет.](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="b0b15-153">For more information about the exported reports, see [What's included in the report](#whats-included-in-the-report).</span></span>

   - <span data-ttu-id="b0b15-154">Если этот параметр не выбран, отчеты об экспорте будут содержать сведения обо всех сообщениях, возвращаемом поиском, включая дубликаты.</span><span class="sxs-lookup"><span data-stu-id="b0b15-154">If you don't select this option, the export reports will contain information about all messages returned by the search, including duplicates.</span></span>

     <span data-ttu-id="b0b15-155">Дополнительные сведения о де-дублировании и выявлении дублирующих элементов см. в статьи [De-duplication in eDiscovery search results.](de-duplication-in-ediscovery-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="b0b15-155">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

5. <span data-ttu-id="b0b15-156">Щелкните **Создать отчет**.</span><span class="sxs-lookup"><span data-stu-id="b0b15-156">Click **Generate report**.</span></span>

   <span data-ttu-id="b0b15-157">Отчеты о поиске подготовлены для скачивания, что означает, что документы отчета загружаются в служба хранилища Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b0b15-157">The search reports are prepared for downloading, which means the report documents are uploaded to an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="b0b15-158">Это может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="b0b15-158">This may take several minutes.</span></span>

<span data-ttu-id="b0b15-159">В следующем разделе указаны инструкции по загрузке экспортных отчетов о поиске.</span><span class="sxs-lookup"><span data-stu-id="b0b15-159">See the next section for instructions to download the exported search reports.</span></span>
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="b0b15-160">Шаг 2. Скачайте отчет</span><span class="sxs-lookup"><span data-stu-id="b0b15-160">Step 2: Download the report</span></span>

<span data-ttu-id="b0b15-161">Следующий шаг — скачивание отчета из области служба хранилища Azure на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="b0b15-161">The next step is to download the report from the Azure Storage area to your local computer.</span></span>

1. <span data-ttu-id="b0b15-162">На странице **поиска контента** в центре Microsoft 365 выберите вкладку **Exports**</span><span class="sxs-lookup"><span data-stu-id="b0b15-162">On the **Content search** page in the Microsoft 365 compliance center, select the **Exports** tab</span></span>
  
   <span data-ttu-id="b0b15-163">Возможно, вам придется нажать **кнопку Обновить,** чтобы обновить список рабочих мест экспорта, чтобы он отображал созданное задание экспорта.</span><span class="sxs-lookup"><span data-stu-id="b0b15-163">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="b0b15-164">Задания отчета экспорта имеют то же имя, что и соответствующий поиск с _ReportsOnly **к** имени поиска.</span><span class="sxs-lookup"><span data-stu-id="b0b15-164">Export report jobs have the same name as the corresponding search with **_ReportsOnly** appended to the search name.</span></span>
  
2. <span data-ttu-id="b0b15-165">Выберите задание экспорта, созданное в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="b0b15-165">Select the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="b0b15-166">На странице **вылет отчет экспорт** в статье **Экспорт ключ**, нажмите **Копировать в буфер обмена**.</span><span class="sxs-lookup"><span data-stu-id="b0b15-166">On the **Export report** flyout page under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="b0b15-167">Этот ключ используется в шаге 6 для скачивания результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="b0b15-167">You use this key in step 6 to download the search results.</span></span>
  
   > [!IMPORTANT]
   > <span data-ttu-id="b0b15-168">Поскольку любой человек может установить и запустить средство экспорта электронных данных, а затем использовать этот ключ для загрузки отчета о поиске, не забудьте принять меры предосторожности для защиты этого ключа так же, как вы бы защитить пароли или другую информацию, связанную с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="b0b15-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span>

4. <span data-ttu-id="b0b15-169">В верхней части страницы вылет нажмите кнопку **Скачать результаты**.</span><span class="sxs-lookup"><span data-stu-id="b0b15-169">At the top of the flyout page, click **Download results**.</span></span>

5. <span data-ttu-id="b0b15-170">Если вам предложено установить средство экспорта **электронных** обнаружений, нажмите кнопку **Установите**.</span><span class="sxs-lookup"><span data-stu-id="b0b15-170">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>

6. <span data-ttu-id="b0b15-171">В **средстве экспорта электронных открытий** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="b0b15-171">In the **eDiscovery Export Tool**, do the following:</span></span>

   ![Средство экспорта электронных открытий](../media/eDiscoveryExportTool.png)

   1. <span data-ttu-id="b0b15-173">Вклеить клавишу экспорта, скопированную на шаге 3, в соответствующем поле.</span><span class="sxs-lookup"><span data-stu-id="b0b15-173">Paste the export key that you copied in step 3 in the appropriate box.</span></span>
  
   2. <span data-ttu-id="b0b15-174">Щелкните **Обзор,** чтобы указать расположение, в котором необходимо скачать файлы отчетов о поиске.</span><span class="sxs-lookup"><span data-stu-id="b0b15-174">Click **Browse** to specify the location where you want to download the search report files.</span></span>

7. <span data-ttu-id="b0b15-175">Нажмите кнопку **Пуск**, чтобы скачать результаты поиска на свой компьютер.</span><span class="sxs-lookup"><span data-stu-id="b0b15-175">Click **Start** to download the search results to your computer.</span></span>
  
    <span data-ttu-id="b0b15-176">**Средство экспорта службы обнаружения электронных данных** отображает сведения о состоянии процесса экспорта, в том числе о предполагаемом количестве (и размере) элементов, которые осталось скачать.</span><span class="sxs-lookup"><span data-stu-id="b0b15-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="b0b15-177">По завершению процесса экспорта можно получить доступ к файлам в том месте, где они были загружены.</span><span class="sxs-lookup"><span data-stu-id="b0b15-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span>
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="b0b15-178">Что включено в отчет</span><span class="sxs-lookup"><span data-stu-id="b0b15-178">What's included in the report</span></span>

<span data-ttu-id="b0b15-179">При генерации и экспорте отчета о результатах поиска контента загружаются следующие документы:</span><span class="sxs-lookup"><span data-stu-id="b0b15-179">When you generate and export a report about the results of a Content search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="b0b15-180">**Сводка экспорта:** Документ Excel, содержащий сводку экспорта.</span><span class="sxs-lookup"><span data-stu-id="b0b15-180">**Export summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="b0b15-181">К ним относятся такие сведения, как количество поисковых источников контента, количество результатов поиска из каждого расположения контента, предполагаемое количество элементов, фактическое число экспортируемого товара, а также предполагаемый и фактический размер экспортируемого товара.</span><span class="sxs-lookup"><span data-stu-id="b0b15-181">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span>

   <span data-ttu-id="b0b15-182">Если при экспорте отчета включены неиндексуалные элементы, количество неиндексуальных элементов включается в общее число предполагаемых результатов поиска и общее число скачанных результатов поиска (если необходимо экспортировать результаты поиска), перечисленных в сводном отчете об экспорте.</span><span class="sxs-lookup"><span data-stu-id="b0b15-182">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the export summary report.</span></span> <span data-ttu-id="b0b15-183">Другими словами, общее число скачанных элементов равно общему числу оценных результатов и общему числу неиндексуальных элементов.</span><span class="sxs-lookup"><span data-stu-id="b0b15-183">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span>
  
- <span data-ttu-id="b0b15-184">**Манифест:** Файл манифеста (в формате XML), содержащий сведения о каждом элементе, включенном в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="b0b15-184">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="b0b15-185">Если включен параметр de-duplication, дублирующие сообщения не включаются в файл манифеста.</span><span class="sxs-lookup"><span data-stu-id="b0b15-185">If you enabled the de-duplication option, duplicate message are not included in the manifest file.</span></span>

- <span data-ttu-id="b0b15-186">**Результаты:** Документ Excel, содержащий строку с информацией о каждом индексируемом элементе, который будет экспортироваться с результатами поиска.</span><span class="sxs-lookup"><span data-stu-id="b0b15-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="b0b15-187">При выполнении поиска в почте журнал результатов содержит сведения о каждом сообщении, включая указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="b0b15-187">For email, the result log contains information about each message, including:</span></span> 

  - <span data-ttu-id="b0b15-188">Расположение сообщения в исходном почтовом ящике (включая сведения о том, в каком почтовом ящике находится сообщение, в основном или в архивном).</span><span class="sxs-lookup"><span data-stu-id="b0b15-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>

  - <span data-ttu-id="b0b15-189">Дата отправки или получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="b0b15-189">The date the message was sent or received.</span></span>

  - <span data-ttu-id="b0b15-190">Тема сообщения.</span><span class="sxs-lookup"><span data-stu-id="b0b15-190">The Subject line from the message.</span></span>

  - <span data-ttu-id="b0b15-191">Отправитель и получатели сообщения.</span><span class="sxs-lookup"><span data-stu-id="b0b15-191">The sender and recipients of the message.</span></span>

  <span data-ttu-id="b0b15-192">Для документов с SharePoint OneDrive для бизнеса сайтов журнал результатов содержит сведения о каждом документе, в том числе:</span><span class="sxs-lookup"><span data-stu-id="b0b15-192">For documents from SharePoint and OneDrive for Business sites, the results log contains information about each document, including:</span></span>

  - <span data-ttu-id="b0b15-193">URL-адрес документа.</span><span class="sxs-lookup"><span data-stu-id="b0b15-193">The URL for the document.</span></span>

  - <span data-ttu-id="b0b15-194">URL-адрес семейства веб-сайтов, в котором расположен документ.</span><span class="sxs-lookup"><span data-stu-id="b0b15-194">The URL for the site collection where the document is located.</span></span>

  - <span data-ttu-id="b0b15-195">Дата последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="b0b15-195">The date that the document was last modified.</span></span>

  - <span data-ttu-id="b0b15-196">Имя документа (которое указано в столбце "Тема" журнала результатов).</span><span class="sxs-lookup"><span data-stu-id="b0b15-196">The name of the document (which is located in the Subject column in the result log).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b0b15-197">Количество строк в отчете **"Результаты"** должно быть равно общему числу результатов поиска за вычетом общего числа элементов, перечисленных в отчете Об элементах **Unindexed.**</span><span class="sxs-lookup"><span data-stu-id="b0b15-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span>
  
- <span data-ttu-id="b0b15-198">**Trace.log:** журнал трассировки, содержащий подробные сведения о процессе экспорта и который может помочь в обнаружении проблем при экспорте.</span><span class="sxs-lookup"><span data-stu-id="b0b15-198">**Trace.log**: A trace log that contains detailed logging information about the export process and can help uncover issues during export.</span></span> <span data-ttu-id="b0b15-199">Если вы откроете билет в Службе поддержки Майкрософт по поводу проблемы, связанной с экспортом отчетов о поиске, вам может потребоваться предоставить этот журнал трассировки.</span><span class="sxs-lookup"><span data-stu-id="b0b15-199">If you open a ticket with Microsoft Support about an issue related to exporting search reports, you may be asked to provide this trace log.</span></span>

- <span data-ttu-id="b0b15-200">**Элементы unindexed:** Документ Excel, содержащий сведения о любых неиндексуальных элементов, включенных в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="b0b15-200">**Unindexed items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="b0b15-201">Если при генерации отчета о результатах поиска не будут включены неидексные элементы, этот отчет будет по-прежнему загружен, но будет пустым.</span><span class="sxs-lookup"><span data-stu-id="b0b15-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
