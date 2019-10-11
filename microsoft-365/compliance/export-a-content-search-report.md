---
title: Экспорт отчета о поиске контента
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
description: Вместо того чтобы экспортировать фактические результаты поиска контента в центре безопасности & соответствия требованиям в Office 365, можно экспортировать отчет о результатах поиска. Отчет содержит сводку результатов поиска и документ с подробными сведениями о каждом экспортируемом элементе.
ms.openlocfilehash: 9fe006ba595920f938a4d070eb87987137d73f7e
ms.sourcegitcommit: db580dc2626328d324f65c7380a5816a500688a7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2019
ms.locfileid: "37437789"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="0e937-104">Экспорт отчета о поиске контента</span><span class="sxs-lookup"><span data-stu-id="0e937-104">Export a Content Search report</span></span>

<span data-ttu-id="0e937-105">Вместо того чтобы экспортировать полный набор результатов поиска из поиска контента в центре безопасности & соответствия требованиям (и из поиска контента, связанного с вариантом обнаружения электронных данных), можно экспортировать те же отчеты, которые создаются при экспорте результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="0e937-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="0e937-106">При экспорте отчета он загружается в папку с таким же именем, что и для поиска контента, но добавляется с помощью *_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="0e937-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="0e937-107">Например, если поиск контента имеет имя *ContosoCase0815*, то отчет загружается в папку с именем *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="0e937-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="0e937-108">Список документов, включенных в отчет, приведен в разделе сведения, [включенные в отчет](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="0e937-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0e937-109">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="0e937-109">Before you begin</span></span>

- <span data-ttu-id="0e937-110">Для экспорта отчета о поиске контента необходимо назначить роль управления поиском соответствия требованиям в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="0e937-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="0e937-111">Эта роль назначена встроенному Диспетчеру обнаружения электронных данных и группам ролей управления Организацией.</span><span class="sxs-lookup"><span data-stu-id="0e937-111">This role is assigned to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="0e937-112">По умолчанию эта роль не назначена группе ролей "Управление организацией".</span><span class="sxs-lookup"><span data-stu-id="0e937-112">It isn't assigned by default to the Organization Management role group.</span></span> <span data-ttu-id="0e937-113">Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0e937-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="0e937-114">При экспорте отчета данные временно хранятся в уникальной области хранилища Azure в облаке Майкрософт, прежде чем она будет загружена на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="0e937-114">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="0e937-115">Убедитесь, что ваша организация может подключаться к конечной точке в Azure, т \*\* \*. е. BLOB.Core.Windows.NET\*\* (подстановочный знак представляет уникальный идентификатор для экспорта).</span><span class="sxs-lookup"><span data-stu-id="0e937-115">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="0e937-116">Данные результатов поиска удаляются из области хранилища Azure две недели после ее создания.</span><span class="sxs-lookup"><span data-stu-id="0e937-116">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="0e937-117">Компьютер, используемый для экспорта результатов поиска, должен соответствовать указанным ниже требованиям к системе.</span><span class="sxs-lookup"><span data-stu-id="0e937-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="0e937-118">32 — разрядная или 64 – разрядная версия Windows 7 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="0e937-118">32-bit or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="0e937-119">Microsoft .NET Framework 4,7</span><span class="sxs-lookup"><span data-stu-id="0e937-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="0e937-120">Поддерживаемый браузер:</span><span class="sxs-lookup"><span data-stu-id="0e937-120">A supported browser:</span></span>
    
    - <span data-ttu-id="0e937-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0e937-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="0e937-122">Кроме того:</span><span class="sxs-lookup"><span data-stu-id="0e937-122">or</span></span>
    
    - <span data-ttu-id="0e937-123">Microsoft Internet Explorer 10 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="0e937-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="0e937-124">**Примечание:** Корпорация Майкрософт не производит сторонние расширения или надстройки для приложений ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="0e937-124">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="0e937-125">Экспорт результатов поиска с использованием неподдерживаемого браузера со сторонними расширениями или надстройками не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0e937-125">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 

- <span data-ttu-id="0e937-126">Если предполагаемый общий размер результатов, возвращаемых службой поиска контента, превышает 2 ТБ, экспорт отчета завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0e937-126">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="0e937-127">Для успешного экспорта отчета попробуйте сузить область и повторно выполните поиск, чтобы предполагаемый размер результатов не превышал 2 ТБ.</span><span class="sxs-lookup"><span data-stu-id="0e937-127">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="0e937-128">При экспорте отчетов поиска контента учитываются максимальное число одновременно выполняемых операций экспорта и максимальное количество экспортируемых элементов, которое может выполнить один пользователь.</span><span class="sxs-lookup"><span data-stu-id="0e937-128">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="0e937-129">Более подробную информацию об ограничениях экспорта можно узнать в статье [Экспорт результатов поиска контента](export-search-results.md#export-limits).</span><span class="sxs-lookup"><span data-stu-id="0e937-129">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="0e937-130">Создание и скачивание отчета о поиске контента</span><span class="sxs-lookup"><span data-stu-id="0e937-130">Generate and download a Content Search report</span></span>

<span data-ttu-id="0e937-131">Действия по созданию и загрузке отчета о поиске контента аналогичны фактическому экспорту результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="0e937-131">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="0e937-132">Шаг 1: создание отчета для экспорта</span><span class="sxs-lookup"><span data-stu-id="0e937-132">Step 1: Generate the report for export</span></span>

<span data-ttu-id="0e937-133">Первым этапом является подготовка отчета для загрузки на компьютер экспорта.</span><span class="sxs-lookup"><span data-stu-id="0e937-133">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="0e937-134">При отправке отчета документы отчетов отправляются в область хранилища Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0e937-134">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="0e937-135">Перейдите по ссылке [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="0e937-135">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="0e937-136">Войдите в Office 365 с помощью своей рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="0e937-136">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="0e937-137">В левой области центра безопасности & соответствия **требованиям выберите** \> поиск **контента**поиска.</span><span class="sxs-lookup"><span data-stu-id="0e937-137">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="0e937-138">На странице **Поиск контента** выберите Поиск.</span><span class="sxs-lookup"><span data-stu-id="0e937-138">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="0e937-139">В области сведений в разделе **Экспорт отчета на компьютер**нажмите **создать отчет**.</span><span class="sxs-lookup"><span data-stu-id="0e937-139">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e937-140">Если результаты поиска старше 7 дней, вам будет предложено обновить результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="0e937-140">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="0e937-141">В этом случае отмените экспорт, щелкните **Обновить результаты поиска** в области сведений для выбранного поиска, а затем снова запустите экспорт отчета после обновления результатов.</span><span class="sxs-lookup"><span data-stu-id="0e937-141">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="0e937-142">На странице " **Экспорт отчета** " в разделе **включить эти элементы из поиска**выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="0e937-142">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="0e937-143">Экспортировать только индексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="0e937-143">Export only indexed items</span></span>
    
    - <span data-ttu-id="0e937-144">Экспортировать индексированные и неиндексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="0e937-144">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="0e937-145">Экспортировать только неиндексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="0e937-145">Export only unindexed items</span></span>
    
    <span data-ttu-id="0e937-146">Для получения дополнительных сведений об неиндексированных элементах просмотрите раздел " [частично индексированные элементы" в поиске контента](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="0e937-146">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="0e937-147">Выберите, чтобы включить статистику поиска для всех версий документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0e937-147">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="0e937-148">Этот параметр отображается только в том случае, если в качестве источников контента для сайтов SharePoint и OneDrive для бизнеса указан Поиск.</span><span class="sxs-lookup"><span data-stu-id="0e937-148">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="0e937-149">Нажмите **создать отчет**.</span><span class="sxs-lookup"><span data-stu-id="0e937-149">Click **Generate report**.</span></span>
    
    <span data-ttu-id="0e937-150">Отчет по результатам поиска готов к скачиванию, что означает, что документы отчета будут отправлены в область хранилища Azure в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="0e937-150">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="0e937-151">Когда отчет будет готов к скачиванию, ссылка **загрузить отчет** будет отображаться в разделе **Экспорт отчета на компьютер** в области сведений.</span><span class="sxs-lookup"><span data-stu-id="0e937-151">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0e937-152">Вы также можете экспортировать отчет для поиска контента, связанного с вариантом обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="0e937-152">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="0e937-153">Для этого **перейдите в** \> раздел **Обнаружение**электронных данных, выберите обращение и нажмите кнопку **изменить** ![значок](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)редактирования.</span><span class="sxs-lookup"><span data-stu-id="0e937-153">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="0e937-154">На странице **поиски** выберите Поиск, а затем нажмите кнопку **Экспорт** ![экспорта результатов](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> поиска **Экспорт отчета**.</span><span class="sxs-lookup"><span data-stu-id="0e937-154">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="0e937-155">Шаг 2: Скачайте отчет</span><span class="sxs-lookup"><span data-stu-id="0e937-155">Step 2: Download the report</span></span>

<span data-ttu-id="0e937-156">Следующий шаг — скачать отчет из области хранилища Azure на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="0e937-156">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="0e937-157">В области сведений для поиска, для которого был создан отчет, в разделе **Экспорт отчета на компьютер**нажмите кнопку **скачать отчет**.</span><span class="sxs-lookup"><span data-stu-id="0e937-157">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="0e937-158">Откроется страница " **отчет о загрузке** " со следующими сведениями о отчете, загруженном на компьютер.</span><span class="sxs-lookup"><span data-stu-id="0e937-158">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="0e937-159">Количество скачиваемых элементов.</span><span class="sxs-lookup"><span data-stu-id="0e937-159">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="0e937-160">Предполагаемый общий размер скачиваемых элементов.</span><span class="sxs-lookup"><span data-stu-id="0e937-160">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="0e937-161">Сведения о том, какие элементы будут экспортированы, индексированные или неиндексированные.</span><span class="sxs-lookup"><span data-stu-id="0e937-161">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="0e937-162">Неиндексированные элементы — это элементы, которые имеют распознаваемый формат, шифруются или не индексируются по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="0e937-162">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="0e937-163">Будут ли загружаться версии документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0e937-163">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="0e937-164">Состояние процесса экспорта отчета.</span><span class="sxs-lookup"><span data-stu-id="0e937-164">The status of the report export process.</span></span> <span data-ttu-id="0e937-165">Вы можете начать загрузку отчета, даже если подготовка отчета не завершена.</span><span class="sxs-lookup"><span data-stu-id="0e937-165">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="0e937-166">В разделе **Ключ экспорта** нажмите **Скопировать в буфер обмена**.</span><span class="sxs-lookup"><span data-stu-id="0e937-166">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="0e937-167">Чтобы скачать отчет, используйте этот ключ в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="0e937-167">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0e937-168">Так как любой пользователь может установить и запустить средство экспорта обнаружения электронных данных, а затем использовать этот ключ для загрузки отчета о поиске, обязательно примите меры предосторожности, чтобы защитить этот ключ так же, как и при защите паролей или других данных, связанных с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="0e937-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="0e937-169">Нажмите кнопку **загрузить отчет**.</span><span class="sxs-lookup"><span data-stu-id="0e937-169">Click **Download report**.</span></span>
    
4. <span data-ttu-id="0e937-170">Если вам будет предложено установить **средство экспорта майкрософтoffice 365 для обнаружения электронных**данных, нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="0e937-170">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="0e937-171">В **средстве экспорта службы обнаружения электронных данных** в соответствующее поле вставьте ключ экспорта, который вы скопировали в действии 2. </span><span class="sxs-lookup"><span data-stu-id="0e937-171">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="0e937-172">Нажмите кнопку **Обзор** , чтобы указать папку, в которую вы хотите скачать отчет.</span><span class="sxs-lookup"><span data-stu-id="0e937-172">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="0e937-173">Нажмите кнопку **Пуск**, чтобы скачать результаты поиска на свой компьютер.</span><span class="sxs-lookup"><span data-stu-id="0e937-173">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="0e937-174">**Средство экспорта службы обнаружения электронных данных** отображает сведения о состоянии процесса экспорта, в том числе о предполагаемом количестве (и размере) элементов, которые осталось скачать.</span><span class="sxs-lookup"><span data-stu-id="0e937-174">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="0e937-175">По завершении процесса экспорта можно получить доступ к файлам в том расположении, в котором они были скачаны.</span><span class="sxs-lookup"><span data-stu-id="0e937-175">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0e937-176">Вы можете скачать отчет для поиска контента, связанного с вариантом обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="0e937-176">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="0e937-177">Для этого **перейдите в** \> раздел **Обнаружение**электронных данных, выберите обращение и нажмите кнопку **изменить** ![значок](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)редактирования.</span><span class="sxs-lookup"><span data-stu-id="0e937-177">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="0e937-178">На странице " **Экспорт** " выберите Экспорт отчета, а затем нажмите кнопку **скачать отчет** в области сведений.</span><span class="sxs-lookup"><span data-stu-id="0e937-178">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="0e937-179">Что входит в отчет</span><span class="sxs-lookup"><span data-stu-id="0e937-179">What's included in the report</span></span>

<span data-ttu-id="0e937-180">При создании и экспорте отчета о результатах поиска контента загружаются следующие документы:</span><span class="sxs-lookup"><span data-stu-id="0e937-180">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="0e937-181">**Сводка по экспорту:** Документ Excel, который содержит сводку по экспорту.</span><span class="sxs-lookup"><span data-stu-id="0e937-181">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="0e937-182">Сюда входят такие сведения, как количество искомых источников контента, количество результатов поиска из каждого расположения контента, предполагаемое количество элементов, фактическое количество элементов, которые будут экспортированы, а также предполагаемый и фактический размер элементов. экспортируемый.</span><span class="sxs-lookup"><span data-stu-id="0e937-182">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0e937-183">Если вы включили неиндексированные элементы при экспорте отчета, число неиндексированных элементов будет включено в общее число оценочных результатов поиска и в общее число загруженных результатов поиска (если вы намерены экспортировать результаты поиска), перечисленные в разделе Сводный отчет по экспорту.</span><span class="sxs-lookup"><span data-stu-id="0e937-183">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="0e937-184">Другими словами, общее количество загружаемых элементов равно общему количеству предполагаемых результатов и общему количеству неиндексированных элементов.</span><span class="sxs-lookup"><span data-stu-id="0e937-184">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="0e937-185">**Манифест:** Файл манифеста (в формате XML), который содержит сведения о каждом элементе, включенном в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="0e937-185">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="0e937-186">**Результаты:** Документ Excel, содержащий строку со сведениями о каждом индексируемом элементе, который будет экспортирован в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="0e937-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="0e937-187">При выполнении поиска в почте журнал результатов содержит сведения о каждом сообщении, включая указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="0e937-187">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="0e937-188">Расположение сообщения в исходном почтовом ящике (включая сведения о том, в каком почтовом ящике находится сообщение, в основном или в архивном).</span><span class="sxs-lookup"><span data-stu-id="0e937-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="0e937-189">Дата отправки или получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="0e937-189">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="0e937-190">Тема сообщения.</span><span class="sxs-lookup"><span data-stu-id="0e937-190">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="0e937-191">Отправитель и получатели сообщения.</span><span class="sxs-lookup"><span data-stu-id="0e937-191">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="0e937-192">Для документов из сайтов SharePoint и OneDrive для бизнеса журнал результатов содержит сведения о каждом документе, в том числе:</span><span class="sxs-lookup"><span data-stu-id="0e937-192">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="0e937-193">URL-адрес документа.</span><span class="sxs-lookup"><span data-stu-id="0e937-193">The URL for the document.</span></span>
    
  - <span data-ttu-id="0e937-194">URL-адрес семейства веб-сайтов, в котором расположен документ.</span><span class="sxs-lookup"><span data-stu-id="0e937-194">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="0e937-195">Дата последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="0e937-195">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="0e937-196">Имя документа (которое указано в столбце "Тема" журнала результатов).</span><span class="sxs-lookup"><span data-stu-id="0e937-196">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e937-197">Количество строк в отчете о **результатах** должно равняться общему количеству результатов поиска за вычетом общего числа элементов, перечисленных в отчете **неиндексированные элементы** .</span><span class="sxs-lookup"><span data-stu-id="0e937-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="0e937-198">**Неиндексированные элементы:** Документ Excel, содержащий сведения обо всех неиндексированных элементах, включенных в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="0e937-198">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="0e937-199">Если вы не включаете неиндексированные элементы при создании отчета по результатам поиска, этот отчет по-прежнему будет скачан, но будет пустым.</span><span class="sxs-lookup"><span data-stu-id="0e937-199">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
