---
title: Экспорт отчета о поиске контента
f1.keywords:
- NOCSH
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 25525a0670f31a7e962fb72f6d1559381e8b33cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817778"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="8b2d3-104">Экспорт отчета о поиске контента</span><span class="sxs-lookup"><span data-stu-id="8b2d3-104">Export a Content Search report</span></span>

<span data-ttu-id="8b2d3-105">Вместо того чтобы экспортировать полный набор результатов поиска из поиска контента в центре безопасности & соответствия требованиям (и из поиска контента, связанного с вариантом обнаружения электронных данных), можно экспортировать те же отчеты, которые создаются при экспорте результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="8b2d3-106">При экспорте отчета он загружается в папку с таким же именем, что и для поиска контента, но добавляется с *_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="8b2d3-107">Например, если поиск контента имеет имя *ContosoCase0815*, то отчет загружается в папку с именем *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="8b2d3-108">Список документов, включенных в отчет, приведен в разделе сведения, [включенные в отчет](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="8b2d3-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="assign-roles-and-check-system-requirements"></a><span data-ttu-id="8b2d3-109">Назначение ролей и проверка требований к системе</span><span class="sxs-lookup"><span data-stu-id="8b2d3-109">Assign roles and check system requirements</span></span>

- <span data-ttu-id="8b2d3-110">Для экспорта отчета о поиске контента необходимо назначить роль управления поиском соответствия требованиям в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="8b2d3-111">Эта роль назначается по умолчанию встроенным диспетчером eDiscovery и группам ролей управления Организацией.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="8b2d3-112">Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8b2d3-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="8b2d3-113">При экспорте отчета данные временно хранятся в уникальной области хранилища Azure в облаке Майкрософт, прежде чем она будет загружена на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-113">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="8b2d3-114">Убедитесь, что ваша организация может подключаться к конечной точке в Azure, т \*\* \* . е. BLOB.Core.Windows.NET\*\* (подстановочный знак представляет уникальный идентификатор для экспорта).</span><span class="sxs-lookup"><span data-stu-id="8b2d3-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="8b2d3-115">Данные результатов поиска удаляются из области хранилища Azure две недели после ее создания.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-115">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="8b2d3-116">Компьютер, используемый для экспорта результатов поиска, должен соответствовать указанным ниже требованиям к системе.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-116">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="8b2d3-117">32 — разрядная или 64 – разрядная версия Windows 7 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="8b2d3-117">32-bit or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="8b2d3-118">Microsoft .NET Framework 4,7</span><span class="sxs-lookup"><span data-stu-id="8b2d3-118">Microsoft .NET Framework 4.7</span></span>
    
- <span data-ttu-id="8b2d3-119">Для запуска средства экспорта eDiscovery<sup>1</sup>необходимо использовать один из следующих поддерживаемых браузеров:</span><span class="sxs-lookup"><span data-stu-id="8b2d3-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="8b2d3-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8b2d3-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="8b2d3-121">OR</span><span class="sxs-lookup"><span data-stu-id="8b2d3-121">OR</span></span>

  - <span data-ttu-id="8b2d3-122">Microsoft Internet Explorer 10 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="8b2d3-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="8b2d3-123"><sup>1</sup> . Корпорация Майкрософт не производит сторонние расширения или надстройки для приложений ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="8b2d3-124">Экспорт результатов поиска с использованием неподдерживаемого браузера со сторонними расширениями или надстройками не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="8b2d3-125"><sup>2</sup> в результате последних изменений в Microsoft EDGE поддержка ClickOnce больше не включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="8b2d3-126">Инструкции по включению поддержки ClickOnce в пограничных пограничных приложений можно найти [в разделе Использование средства экспорта eDiscovery в Microsoft Edge](configure-edge-to-export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="8b2d3-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="8b2d3-127">Если предполагаемый общий размер результатов, возвращаемых службой поиска контента, превышает 2 ТБ, экспорт отчета завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-127">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="8b2d3-128">Для успешного экспорта отчета попробуйте сузить область и повторно выполните поиск, чтобы предполагаемый размер результатов не превышал 2 ТБ.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-128">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="8b2d3-129">При экспорте отчетов поиска контента учитываются максимальное число одновременно выполняемых операций экспорта и максимальное количество экспортируемых элементов, которое может выполнить один пользователь.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="8b2d3-130">Более подробную информацию об ограничениях экспорта можно узнать в статье [Экспорт результатов поиска контента](export-search-results.md#export-limits).</span><span class="sxs-lookup"><span data-stu-id="8b2d3-130">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="8b2d3-131">Создание и скачивание отчета о поиске контента</span><span class="sxs-lookup"><span data-stu-id="8b2d3-131">Generate and download a Content Search report</span></span>

<span data-ttu-id="8b2d3-132">Действия по созданию и загрузке отчета о поиске контента аналогичны фактическому экспорту результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-132">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="8b2d3-133">Шаг 1: создание отчета для экспорта</span><span class="sxs-lookup"><span data-stu-id="8b2d3-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="8b2d3-134">Первым этапом является подготовка отчета для загрузки на компьютер экспорта.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="8b2d3-135">При отправке отчета документы отчетов отправляются в область хранилища Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-135">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="8b2d3-136">Перейдите по ссылке [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="8b2d3-136">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="8b2d3-137">Выполните вход с помощью рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-137">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="8b2d3-138">В левой области центра безопасности & соответствия **требованиям выберите Поиск** \> **контента**поиска.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-138">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="8b2d3-139">На странице **Поиск контента** выберите Поиск.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-139">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="8b2d3-140">В области сведений в разделе **Экспорт отчета на компьютер**нажмите **создать отчет**.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-140">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8b2d3-141">Если результаты поиска старше 7 дней, вам будет предложено обновить результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-141">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="8b2d3-142">В этом случае отмените экспорт, щелкните **Обновить результаты поиска** в области сведений для выбранного поиска, а затем снова запустите экспорт отчета после обновления результатов.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-142">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="8b2d3-143">На странице " **Экспорт отчета** " в разделе **включить эти элементы из поиска**выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="8b2d3-143">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="8b2d3-144">Экспортировать только индексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-144">Export only indexed items</span></span>
    
    - <span data-ttu-id="8b2d3-145">Экспортировать индексированные и неиндексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-145">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="8b2d3-146">Экспортировать только неиндексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-146">Export only unindexed items</span></span>
    
    <span data-ttu-id="8b2d3-147">Для получения дополнительных сведений об неиндексированных элементах просмотрите раздел " [частично индексированные элементы" в поиске контента](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="8b2d3-147">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="8b2d3-148">Выберите, чтобы включить статистику поиска для всех версий документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-148">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="8b2d3-149">Этот параметр отображается только в том случае, если в качестве источников контента для сайтов SharePoint и OneDrive для бизнеса указан Поиск.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-149">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="8b2d3-150">Нажмите **создать отчет**.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-150">Click **Generate report**.</span></span>
    
    <span data-ttu-id="8b2d3-151">Отчет по результатам поиска готов к скачиванию, что означает, что документы отчета будут отправлены в область хранилища Azure в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-151">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="8b2d3-152">Когда отчет будет готов к скачиванию, ссылка **загрузить отчет** будет отображаться в разделе **Экспорт отчета на компьютер** в области сведений.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-152">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8b2d3-153">Вы также можете экспортировать отчет для поиска контента, связанного с вариантом обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-153">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="8b2d3-154">Для этого перейдите в раздел Обнаружение **электронных данных** \> **eDiscovery**, выберите обращение и нажмите кнопку **изменить** ![ значок редактирования ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="8b2d3-154">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="8b2d3-155">На странице **поиски** выберите Поиск, а затем нажмите кнопку **Экспорт** ![ экспорта результатов поиска ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Экспорт отчета**.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-155">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="8b2d3-156">Шаг 2: Скачайте отчет</span><span class="sxs-lookup"><span data-stu-id="8b2d3-156">Step 2: Download the report</span></span>

<span data-ttu-id="8b2d3-157">Следующий шаг — скачать отчет из области хранилища Azure на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-157">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="8b2d3-158">В области сведений для поиска, для которого был создан отчет, в разделе **Экспорт отчета на компьютер**нажмите кнопку **скачать отчет**.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-158">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="8b2d3-159">Откроется страница " **отчет о загрузке** " со следующими сведениями о отчете, загруженном на компьютер.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-159">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="8b2d3-160">Количество скачиваемых элементов.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-160">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="8b2d3-161">Предполагаемый общий размер скачиваемых элементов.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-161">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="8b2d3-162">Сведения о том, какие элементы будут экспортированы, индексированные или неиндексированные.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-162">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="8b2d3-163">Неиндексированные элементы — это элементы, которые имеют распознаваемый формат, шифруются или не индексируются по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-163">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="8b2d3-164">Будут ли загружаться версии документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-164">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="8b2d3-165">Состояние процесса экспорта отчета.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-165">The status of the report export process.</span></span> <span data-ttu-id="8b2d3-166">Вы можете начать загрузку отчета, даже если подготовка отчета не завершена.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-166">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="8b2d3-167">В разделе **Ключ экспорта** нажмите **Скопировать в буфер обмена**.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-167">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="8b2d3-168">Чтобы скачать отчет, используйте этот ключ в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-168">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8b2d3-169">Так как любой пользователь может установить и запустить средство экспорта обнаружения электронных данных, а затем использовать этот ключ для загрузки отчета о поиске, обязательно примите меры предосторожности, чтобы защитить этот ключ так же, как и при защите паролей или других данных, связанных с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-169">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="8b2d3-170">Нажмите кнопку **загрузить отчет**.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-170">Click **Download report**.</span></span>
    
4. <span data-ttu-id="8b2d3-171">Если вам будет предложено установить **средство экспорта eDiscovery**, нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-171">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="8b2d3-172">В **средстве экспорта службы обнаружения электронных данных** в соответствующее поле вставьте ключ экспорта, который вы скопировали в действии 2. </span><span class="sxs-lookup"><span data-stu-id="8b2d3-172">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="8b2d3-173">Нажмите кнопку **Обзор** , чтобы указать папку, в которую вы хотите скачать отчет.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-173">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="8b2d3-174">Нажмите кнопку **Пуск**, чтобы скачать результаты поиска на свой компьютер.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-174">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="8b2d3-175">**Средство экспорта службы обнаружения электронных данных** отображает сведения о состоянии процесса экспорта, в том числе о предполагаемом количестве (и размере) элементов, которые осталось скачать.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-175">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="8b2d3-176">По завершении процесса экспорта можно получить доступ к файлам в том расположении, в котором они были скачаны.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-176">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8b2d3-177">Вы можете скачать отчет для поиска контента, связанного с вариантом обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-177">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="8b2d3-178">Для этого перейдите в раздел Обнаружение **электронных данных** \> **eDiscovery**, выберите обращение и нажмите кнопку **изменить** ![ значок редактирования ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="8b2d3-178">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="8b2d3-179">На странице " **Экспорт** " выберите Экспорт отчета, а затем нажмите кнопку **скачать отчет** в области сведений.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-179">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="8b2d3-180">Что входит в отчет</span><span class="sxs-lookup"><span data-stu-id="8b2d3-180">What's included in the report</span></span>

<span data-ttu-id="8b2d3-181">При создании и экспорте отчета о результатах поиска контента загружаются следующие документы:</span><span class="sxs-lookup"><span data-stu-id="8b2d3-181">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="8b2d3-182">**Сводка по экспорту:** Документ Excel, который содержит сводку по экспорту.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-182">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="8b2d3-183">Сюда входят такие сведения, как количество искомых источников контента, количество результатов поиска из каждого расположения контента, предполагаемое количество элементов, фактическое количество элементов, которые будут экспортированы, а также предполагаемый и фактический размер экспортируемых элементов.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-183">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8b2d3-184">Если вы включили неиндексированные элементы при экспорте отчета, число неиндексированных элементов будет включено в общее число оценочных результатов поиска и в общее число загруженных результатов поиска (если вы намерены экспортировать результаты поиска), указанные в сводном отчете по экспорту.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-184">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="8b2d3-185">Другими словами, общее количество загружаемых элементов равно общему количеству предполагаемых результатов и общему количеству неиндексированных элементов.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-185">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="8b2d3-186">**Манифест:** Файл манифеста (в формате XML), который содержит сведения о каждом элементе, включенном в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-186">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="8b2d3-187">**Результаты:** Документ Excel, содержащий строку со сведениями о каждом индексируемом элементе, который будет экспортирован в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-187">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="8b2d3-188">При выполнении поиска в почте журнал результатов содержит сведения о каждом сообщении, включая указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-188">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="8b2d3-189">Расположение сообщения в исходном почтовом ящике (включая сведения о том, в каком почтовом ящике находится сообщение, в основном или в архивном).</span><span class="sxs-lookup"><span data-stu-id="8b2d3-189">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="8b2d3-190">Дата отправки или получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-190">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="8b2d3-191">Тема сообщения.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-191">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="8b2d3-192">Отправитель и получатели сообщения.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-192">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="8b2d3-193">Для документов из сайтов SharePoint и OneDrive для бизнеса журнал результатов содержит сведения о каждом документе, в том числе:</span><span class="sxs-lookup"><span data-stu-id="8b2d3-193">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="8b2d3-194">URL-адрес документа.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-194">The URL for the document.</span></span>
    
  - <span data-ttu-id="8b2d3-195">URL-адрес семейства веб-сайтов, в котором расположен документ.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-195">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="8b2d3-196">Дата последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-196">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="8b2d3-197">Имя документа (которое указано в столбце "Тема" журнала результатов).</span><span class="sxs-lookup"><span data-stu-id="8b2d3-197">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8b2d3-198">Количество строк в отчете о **результатах** должно равняться общему количеству результатов поиска за вычетом общего числа элементов, перечисленных в отчете **неиндексированные элементы** .</span><span class="sxs-lookup"><span data-stu-id="8b2d3-198">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="8b2d3-199">**Неиндексированные элементы:** Документ Excel, содержащий сведения обо всех неиндексированных элементах, включенных в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-199">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="8b2d3-200">Если вы не включаете неиндексированные элементы при создании отчета по результатам поиска, этот отчет по-прежнему будет скачан, но будет пустым.</span><span class="sxs-lookup"><span data-stu-id="8b2d3-200">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
