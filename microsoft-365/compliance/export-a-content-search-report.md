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
ms.openlocfilehash: fec6e441458ad7429067a1314a7aec3824aff11a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760157"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="84e73-104">Экспорт отчета о поиске контента</span><span class="sxs-lookup"><span data-stu-id="84e73-104">Export a Content Search report</span></span>

<span data-ttu-id="84e73-105">Вместо экспорта полного набора результатов поиска из центра обеспечения соответствия требованиям & контента (а также из поиска контента, связанного с делом об обнаружении электронных данных), можно экспортировать те же отчеты, которые создаются при экспорте результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="84e73-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="84e73-106">При экспорте отчета он загружается в папку с тем же именем, что и поиск контента, но она _ReportsOnly *.*</span><span class="sxs-lookup"><span data-stu-id="84e73-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="84e73-107">Например, если поиск контента называется  *ContosoCase0815,* отчет загружается в папку с именем *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="84e73-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="84e73-108">Список документов, включенных в отчет, см. в документе [What's included in the report.](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="84e73-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="assign-roles-and-check-system-requirements"></a><span data-ttu-id="84e73-109">Назначение ролей и требования системы проверки</span><span class="sxs-lookup"><span data-stu-id="84e73-109">Assign roles and check system requirements</span></span>

- <span data-ttu-id="84e73-110">Чтобы экспортировать отчет о поиске контента, необходимо навести роль управления поиском соответствия требованиям в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="84e73-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="84e73-111">Эта роль по умолчанию назначена встроенным группам управления электронными данными и группами ролей управления организацией.</span><span class="sxs-lookup"><span data-stu-id="84e73-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="84e73-112">Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="84e73-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="84e73-113">При экспорте отчета данные временно хранятся в уникальной служба хранилища Azure области в облаке Майкрософт перед загрузкой на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="84e73-113">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="84e73-114">Убедитесь, что ваша организация может подключиться к конечной точке Azure, которая **\* является .blob.core.windows.net** (подмывка представляет уникальный идентификатор для экспорта).</span><span class="sxs-lookup"><span data-stu-id="84e73-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="84e73-115">Данные результатов поиска удаляются из области служба хранилища Azure через две недели после создания.</span><span class="sxs-lookup"><span data-stu-id="84e73-115">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span>

- <span data-ttu-id="84e73-116">Компьютер, используемый для экспорта результатов поиска, должен соответствовать указанным ниже требованиям к системе.</span><span class="sxs-lookup"><span data-stu-id="84e73-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="84e73-117">Последняя версия Windows (32-битная или 64-битная)</span><span class="sxs-lookup"><span data-stu-id="84e73-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="84e73-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="84e73-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="84e73-119">Для запуска экспортного средства eDiscovery 1 необходимо использовать один из следующих поддерживаемых<sup>браузеров.</sup></span><span class="sxs-lookup"><span data-stu-id="84e73-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="84e73-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="84e73-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="84e73-121">OR</span><span class="sxs-lookup"><span data-stu-id="84e73-121">OR</span></span>

  - <span data-ttu-id="84e73-122">Microsoft Internet Explorer 10 и более поздних версиях</span><span class="sxs-lookup"><span data-stu-id="84e73-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="84e73-123"><sup>1</sup> Корпорация Майкрософт не производит сторонние расширения или надстройки для ClickOnce приложений.</span><span class="sxs-lookup"><span data-stu-id="84e73-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="84e73-124">Экспорт результатов поиска с помощью неподдермеченного браузера с сторонними расширениями или надстройки не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="84e73-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="84e73-125"><sup>2</sup> В результате недавних изменений Microsoft Edge ClickOnce по умолчанию поддержка больше не включена.</span><span class="sxs-lookup"><span data-stu-id="84e73-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="84e73-126">Инструкции по включению ClickOnce поддержки в Edge см. в инструкции [Use the eDiscovery Export Tool in Microsoft Edge.](configure-edge-to-export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="84e73-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="84e73-127">Если предполагаемый общий размер результатов, возвращенных поиском контента, превышает 2 ТБ, экспорт отчета не удается.</span><span class="sxs-lookup"><span data-stu-id="84e73-127">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="84e73-128">Чтобы успешно экспортировать отчет, попробуйте сузить область поиска и перезавести его, чтобы предполагаемый размер результатов не превышает 2 ТБ.</span><span class="sxs-lookup"><span data-stu-id="84e73-128">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="84e73-129">Экспорт отчетов о поиске контента учитывает максимальное количество экспортов, запущенных одновременно, и максимальное число экспортов, которые может выполнить один пользователь.</span><span class="sxs-lookup"><span data-stu-id="84e73-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="84e73-130">Дополнительные сведения об ограничениях экспорта см. в результатах [поиска по экспорту контента.](export-search-results.md#export-limits)</span><span class="sxs-lookup"><span data-stu-id="84e73-130">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="84e73-131">Создание и скачивание отчета о поиске контента</span><span class="sxs-lookup"><span data-stu-id="84e73-131">Generate and download a Content Search report</span></span>

<span data-ttu-id="84e73-132">Действия по генерации и загрузке отчета поиска контента аналогичны фактически экспорту результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="84e73-132">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="84e73-133">Шаг 1. Создание отчета для экспорта</span><span class="sxs-lookup"><span data-stu-id="84e73-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="84e73-134">Первый шаг — подготовка отчета для загрузки на экспорт компьютера.</span><span class="sxs-lookup"><span data-stu-id="84e73-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="84e73-135">При отправке отчета документы отчета загружаются в область служба хранилища Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="84e73-135">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="84e73-136">Перейдите по ссылке [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="84e73-136">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="84e73-137">Выполните вход с помощью рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="84e73-137">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="84e73-138">В левой области Центра & безопасности нажмите кнопку **Поиск** \> **контента**.</span><span class="sxs-lookup"><span data-stu-id="84e73-138">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="84e73-139">На странице **поиска контента** выберите поиск.</span><span class="sxs-lookup"><span data-stu-id="84e73-139">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="84e73-140">В области сведений, в **статье Экспорт отчет на компьютер,** нажмите Создать **отчет**.</span><span class="sxs-lookup"><span data-stu-id="84e73-140">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="84e73-141">Если результаты поиска старше 7 дней, вам будет предложено обновить результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="84e73-141">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="84e73-142">Если это произойдет, отмените экспорт, нажмите кнопку **Обновление** результатов поиска в области сведений для выбранного поиска, а затем снова запустите экспорт отчета после обновления результатов.</span><span class="sxs-lookup"><span data-stu-id="84e73-142">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="84e73-143">На странице **Экспорт отчетов** в статье **Включить эти элементы** из поиска выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="84e73-143">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="84e73-144">Экспортировать только индексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="84e73-144">Export only indexed items</span></span>
    
    - <span data-ttu-id="84e73-145">Экспортировать индексированные и неиндексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="84e73-145">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="84e73-146">Экспортировать только неиндексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="84e73-146">Export only unindexed items</span></span>
    
    <span data-ttu-id="84e73-147">Дополнительные сведения о неиндексуальных элементов см. в статьи Частично индексация элементов [в поиске контента.](partially-indexed-items-in-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="84e73-147">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="84e73-148">Выберите, чтобы включить статистику поиска для всех версий SharePoint документов.</span><span class="sxs-lookup"><span data-stu-id="84e73-148">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="84e73-149">Этот параметр отображается только в том случае, если источники контента поиска включают SharePoint или OneDrive для бизнеса сайты.</span><span class="sxs-lookup"><span data-stu-id="84e73-149">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="84e73-150">Щелкните **Создать отчет**.</span><span class="sxs-lookup"><span data-stu-id="84e73-150">Click **Generate report**.</span></span>
    
    <span data-ttu-id="84e73-151">Отчет о результатах поиска подготовлен для скачивания, что означает, что документы отчета будут загружены в область служба хранилища Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="84e73-151">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="84e73-152">Когда отчет будет готов к скачивке, **в** области сведений в отчете **"Экспорт"** на компьютер отображается ссылка "Скачать отчет".</span><span class="sxs-lookup"><span data-stu-id="84e73-152">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="84e73-153">Вы также можете экспортировать отчет для поиска контента, связанного с делом об обнаружении электронных сообщений.</span><span class="sxs-lookup"><span data-stu-id="84e73-153">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="84e73-154">Для этого перейдите в **eDiscovery eDiscovery,** выберите случай и нажмите \>  **кнопку Изменить значок** ![ Редактирование ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="84e73-154">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="84e73-155">На странице **Поиск** выберите поиск, а затем нажмите значок **экспортировать** результаты поиска ![ ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **экспортировать отчет**.</span><span class="sxs-lookup"><span data-stu-id="84e73-155">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="84e73-156">Шаг 2. Скачайте отчет</span><span class="sxs-lookup"><span data-stu-id="84e73-156">Step 2: Download the report</span></span>

<span data-ttu-id="84e73-157">Следующий шаг — скачивание отчета из области служба хранилища Azure на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="84e73-157">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="84e73-158">В области сведений для поиска, для который вы создали отчет, в статье Экспорт отчет на **компьютер,** нажмите **скачать отчет**.</span><span class="sxs-lookup"><span data-stu-id="84e73-158">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="84e73-159">Отображается **страница отчета** Загрузка и содержит следующую информацию о отчете, скачаемом на компьютер.</span><span class="sxs-lookup"><span data-stu-id="84e73-159">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="84e73-160">Количество скачиваемых элементов.</span><span class="sxs-lookup"><span data-stu-id="84e73-160">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="84e73-161">Предполагаемый общий размер скачиваемых элементов.</span><span class="sxs-lookup"><span data-stu-id="84e73-161">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="84e73-162">Сведения о том, какие элементы будут экспортированы, индексированные или неиндексированные.</span><span class="sxs-lookup"><span data-stu-id="84e73-162">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="84e73-163">Элементы unindexed — это элементы, которые имеют признанный формат, шифруются или не индексироваться по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="84e73-163">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="84e73-164">Будут ли загружены SharePoint документы.</span><span class="sxs-lookup"><span data-stu-id="84e73-164">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="84e73-165">Состояние процесса экспорта отчетов.</span><span class="sxs-lookup"><span data-stu-id="84e73-165">The status of the report export process.</span></span> <span data-ttu-id="84e73-166">Вы можете начать скачивать отчет, даже если подготовка отчета не завершена.</span><span class="sxs-lookup"><span data-stu-id="84e73-166">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="84e73-167">В разделе **Ключ экспорта** нажмите **Скопировать в буфер обмена**.</span><span class="sxs-lookup"><span data-stu-id="84e73-167">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="84e73-168">Этот ключ используется в шаге 5 для загрузки отчета.</span><span class="sxs-lookup"><span data-stu-id="84e73-168">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="84e73-169">Поскольку любой человек может установить и запустить средство экспорта электронных данных, а затем использовать этот ключ для загрузки отчета о поиске, не забудьте принять меры предосторожности для защиты этого ключа так же, как вы бы защитить пароли или другую информацию, связанную с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="84e73-169">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="84e73-170">Нажмите **кнопку Скачать отчет**.</span><span class="sxs-lookup"><span data-stu-id="84e73-170">Click **Download report**.</span></span>
    
4. <span data-ttu-id="84e73-171">Если вам предложено установить средство экспорта **электронных** обнаружений, нажмите кнопку **Установите**.</span><span class="sxs-lookup"><span data-stu-id="84e73-171">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="84e73-172">В **средстве экспорта службы обнаружения электронных данных** в соответствующее поле вставьте ключ экспорта, который вы скопировали в действии 2. </span><span class="sxs-lookup"><span data-stu-id="84e73-172">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="84e73-173">Щелкните **Обзор,** чтобы указать расположение, в котором необходимо скачать отчет.</span><span class="sxs-lookup"><span data-stu-id="84e73-173">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="84e73-174">Нажмите кнопку **Пуск**, чтобы скачать результаты поиска на свой компьютер.</span><span class="sxs-lookup"><span data-stu-id="84e73-174">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="84e73-175">**Средство экспорта службы обнаружения электронных данных** отображает сведения о состоянии процесса экспорта, в том числе о предполагаемом количестве (и размере) элементов, которые осталось скачать.</span><span class="sxs-lookup"><span data-stu-id="84e73-175">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="84e73-176">По завершению процесса экспорта можно получить доступ к файлам в том месте, где они были загружены.</span><span class="sxs-lookup"><span data-stu-id="84e73-176">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="84e73-177">Вы можете скачать отчет для поиска контента, связанного с делом об обнаружении электронных сообщений.</span><span class="sxs-lookup"><span data-stu-id="84e73-177">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="84e73-178">Для этого перейдите в **eDiscovery eDiscovery,** выберите случай и нажмите \>  **кнопку Изменить значок** ![ Редактирование ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="84e73-178">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="84e73-179">На странице **Экспорт выберите** экспорт отчета и нажмите кнопку **Скачать отчет** в области сведений.</span><span class="sxs-lookup"><span data-stu-id="84e73-179">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="84e73-180">Что включено в отчет</span><span class="sxs-lookup"><span data-stu-id="84e73-180">What's included in the report</span></span>

<span data-ttu-id="84e73-181">При генерации и экспорте отчета о результатах поиска контента загружаются следующие документы:</span><span class="sxs-lookup"><span data-stu-id="84e73-181">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="84e73-182">**Сводка экспорта:** Документ Excel, содержащий сводку экспорта.</span><span class="sxs-lookup"><span data-stu-id="84e73-182">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="84e73-183">К ним относятся такие сведения, как количество поисковых источников контента, количество результатов поиска из каждого расположения контента, предполагаемое количество элементов, фактическое число экспортируемого товара, а также предполагаемый и фактический размер экспортируемого товара.</span><span class="sxs-lookup"><span data-stu-id="84e73-183">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="84e73-184">Если при экспорте отчета включены неидексные элементы, количество неиндексуальных элементов включается в общее число предполагаемых результатов поиска и общее число скачанных результатов поиска (если необходимо экспортировать результаты поиска), указанных в отчете Export Summary.</span><span class="sxs-lookup"><span data-stu-id="84e73-184">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="84e73-185">Другими словами, общее число скачанных элементов равно общему числу оценных результатов и общему числу неиндексуальных элементов.</span><span class="sxs-lookup"><span data-stu-id="84e73-185">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="84e73-186">**Манифест:** Файл манифеста (в формате XML), содержащий сведения о каждом элементе, включенном в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="84e73-186">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="84e73-187">**Результаты:** Документ Excel, содержащий строку с информацией о каждом индексируемом элементе, который будет экспортироваться с результатами поиска.</span><span class="sxs-lookup"><span data-stu-id="84e73-187">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="84e73-188">При выполнении поиска в почте журнал результатов содержит сведения о каждом сообщении, включая указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="84e73-188">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="84e73-189">Расположение сообщения в исходном почтовом ящике (включая сведения о том, в каком почтовом ящике находится сообщение, в основном или в архивном).</span><span class="sxs-lookup"><span data-stu-id="84e73-189">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="84e73-190">Дата отправки или получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="84e73-190">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="84e73-191">Тема сообщения.</span><span class="sxs-lookup"><span data-stu-id="84e73-191">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="84e73-192">Отправитель и получатели сообщения.</span><span class="sxs-lookup"><span data-stu-id="84e73-192">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="84e73-193">Для документов с SharePoint OneDrive для бизнеса сайтов журнал Results содержит сведения о каждом документе, включая:</span><span class="sxs-lookup"><span data-stu-id="84e73-193">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="84e73-194">URL-адрес документа.</span><span class="sxs-lookup"><span data-stu-id="84e73-194">The URL for the document.</span></span>
    
  - <span data-ttu-id="84e73-195">URL-адрес семейства веб-сайтов, в котором расположен документ.</span><span class="sxs-lookup"><span data-stu-id="84e73-195">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="84e73-196">Дата последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="84e73-196">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="84e73-197">Имя документа (которое указано в столбце "Тема" журнала результатов).</span><span class="sxs-lookup"><span data-stu-id="84e73-197">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="84e73-198">Количество строк в отчете **"Результаты"** должно быть равно общему числу результатов поиска за вычетом общего числа элементов, перечисленных в отчете Об элементах **Unindexed.**</span><span class="sxs-lookup"><span data-stu-id="84e73-198">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="84e73-199">**Элементы unindexed:** Документ Excel, содержащий сведения о любых неиндексуальных элементов, включенных в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="84e73-199">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="84e73-200">Если при генерации отчета о результатах поиска не будут включены неидексные элементы, этот отчет будет по-прежнему загружен, но будет пустым.</span><span class="sxs-lookup"><span data-stu-id="84e73-200">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
