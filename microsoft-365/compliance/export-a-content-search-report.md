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
description: Вместо экспорта фактических результатов поиска контента в Центре безопасности & соответствия требованиям в Office 365 можно экспортировать отчет о результатах поиска. Отчет содержит сводку результатов поиска и документ с подробными сведениями о каждом элементе, который будет экспортирован.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de27e25945f14f6a6119b4c1776eebca5e84d8ce
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358305"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="c0dea-104">Экспорт отчета о поиске контента</span><span class="sxs-lookup"><span data-stu-id="c0dea-104">Export a Content Search report</span></span>

<span data-ttu-id="c0dea-105">Вместо того чтобы экспортировать полный набор результатов поиска контента в Центре безопасности и & соответствия требованиям (и из поиска контента, связанного с делом eDiscovery), можно экспортировать те же отчеты, которые создаются при экспорте результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="c0dea-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="c0dea-106">При экспорте отчета он загружается в папку с тем же именем, что и поиск контента, но к ней *_ReportsOnly.*</span><span class="sxs-lookup"><span data-stu-id="c0dea-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="c0dea-107">Например, если поиск контента называется *ContosoCase0815,* то отчет загружается в папку с именем *ContosoCase0815_ReportsOnly.*</span><span class="sxs-lookup"><span data-stu-id="c0dea-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="c0dea-108">Список документов, включенных в отчет, см. в документе ["Что включено в отчет".](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="c0dea-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="assign-roles-and-check-system-requirements"></a><span data-ttu-id="c0dea-109">Назначение ролей и проверка системных требований</span><span class="sxs-lookup"><span data-stu-id="c0dea-109">Assign roles and check system requirements</span></span>

- <span data-ttu-id="c0dea-110">Чтобы экспортировать отчет о поиске контента, вам должна быть назначена роль управления поиском соответствия в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c0dea-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="c0dea-111">Эта роль по умолчанию назначена встроенной группе ролей "Диспетчер eDiscovery" и "Управление организацией".</span><span class="sxs-lookup"><span data-stu-id="c0dea-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="c0dea-112">Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c0dea-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="c0dea-113">При экспорте отчета данные временно хранятся в уникальном хранилище Azure в облаке Майкрософт перед их загрузкой на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="c0dea-113">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="c0dea-114">Убедитесь, что ваша организация может подключиться к конечной точке в **\* Azure,blob.core.windows.net** (поддиапная знак представляет уникальный идентификатор для экспорта).</span><span class="sxs-lookup"><span data-stu-id="c0dea-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="c0dea-115">Данные результатов поиска удаляются из хранилища Azure через две недели после их создания.</span><span class="sxs-lookup"><span data-stu-id="c0dea-115">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="c0dea-116">Компьютер, используемый для экспорта результатов поиска, должен соответствовать указанным ниже требованиям к системе.</span><span class="sxs-lookup"><span data-stu-id="c0dea-116">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="c0dea-117">32- или 64-битные версии Windows 7 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="c0dea-117">32-bit or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="c0dea-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="c0dea-118">Microsoft .NET Framework 4.7</span></span>
    
- <span data-ttu-id="c0dea-119">Для запуска средства экспорта eDiscovery 1 необходимо использовать один из следующих поддерживаемых<sup>браузеров:</sup></span><span class="sxs-lookup"><span data-stu-id="c0dea-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="c0dea-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c0dea-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="c0dea-121">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="c0dea-121">OR</span></span>

  - <span data-ttu-id="c0dea-122">Microsoft Internet Explorer 10 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="c0dea-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="c0dea-123"><sup>1</sup> Корпорация Майкрософт не выпускает сторонние расширения или надстройки для ClickOnce приложений.</span><span class="sxs-lookup"><span data-stu-id="c0dea-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="c0dea-124">Экспорт результатов поиска с помощью неподдергодного браузера со сторонними расширениями или надстройки не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c0dea-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="c0dea-125"><sup>2.</sup> В результате последних изменений в Microsoft Edge поддержка ClickOnce больше не включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c0dea-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="c0dea-126">Инструкции по включению поддержки ClickOnce в Edge см. в средстве экспорта [eDiscovery в Microsoft Edge.](configure-edge-to-export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="c0dea-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="c0dea-127">Если предполагаемый общий размер результатов, возвращаемого поиском контента, превышает 2 ТБ, экспорт отчета не удастся.</span><span class="sxs-lookup"><span data-stu-id="c0dea-127">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="c0dea-128">Чтобы успешно экспортировать отчет, попробуйте сузить область поиска и повторного поиска, чтобы предполагаемый размер результатов был меньше 2 ТБ.</span><span class="sxs-lookup"><span data-stu-id="c0dea-128">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="c0dea-129">При экспорте отчетов о поиске контента учитывается максимальное число одновременно запущенных экспортов и максимальное число экспортов, которое может выполнить один пользователь.</span><span class="sxs-lookup"><span data-stu-id="c0dea-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="c0dea-130">Дополнительные сведения об ограничениях на экспорт см. в [экспорте результатов поиска контента.](export-search-results.md#export-limits)</span><span class="sxs-lookup"><span data-stu-id="c0dea-130">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="c0dea-131">Создание и загрузка отчета о поиске контента</span><span class="sxs-lookup"><span data-stu-id="c0dea-131">Generate and download a Content Search report</span></span>

<span data-ttu-id="c0dea-132">Действия по генерации и загрузке отчета поиска контента похожи на фактический экспорт результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="c0dea-132">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="c0dea-133">Шаг 1. Создание отчета для экспорта</span><span class="sxs-lookup"><span data-stu-id="c0dea-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="c0dea-134">Первым шагом является подготовка отчета для загрузки на экспорт компьютера.</span><span class="sxs-lookup"><span data-stu-id="c0dea-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="c0dea-135">При отправке отчета документы отчетов загружаются в хранилище Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c0dea-135">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="c0dea-136">Перейдите по ссылке [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="c0dea-136">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c0dea-137">Выполните вход с помощью рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="c0dea-137">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="c0dea-138">В левой области Центра безопасности и & соответствия требованиям щелкните **"Поиск** \> **контента".**</span><span class="sxs-lookup"><span data-stu-id="c0dea-138">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="c0dea-139">На странице **"Поиск контента"** выберите поиск.</span><span class="sxs-lookup"><span data-stu-id="c0dea-139">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="c0dea-140">В области сведений в области **"Экспорт отчета** на компьютер" щелкните **"Создать отчет".**</span><span class="sxs-lookup"><span data-stu-id="c0dea-140">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c0dea-141">Если результаты поиска старше 7 дней, вам будет предложено обновить результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="c0dea-141">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="c0dea-142">В этом случае отмените  экспорт, щелкните "Обновить результаты поиска" в области сведений для выбранного поиска, а затем снова запустите экспорт отчета после обновления результатов.</span><span class="sxs-lookup"><span data-stu-id="c0dea-142">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="c0dea-143">На странице **"Экспорт отчета"** в области "Включить эти элементы **из** поиска" выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="c0dea-143">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="c0dea-144">Экспортировать только индексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="c0dea-144">Export only indexed items</span></span>
    
    - <span data-ttu-id="c0dea-145">Экспортировать индексированные и неиндексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="c0dea-145">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="c0dea-146">Экспортировать только неиндексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="c0dea-146">Export only unindexed items</span></span>
    
    <span data-ttu-id="c0dea-147">Дополнительные сведения о неиндексациях элементов см. в подразделе "Частично индексные элементы [в поиске контента".](partially-indexed-items-in-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="c0dea-147">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="c0dea-148">Выберите, чтобы включить статистику поиска для всех версий документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c0dea-148">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="c0dea-149">Этот параметр отображается, только если источниками контента поиска являются сайты SharePoint или OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c0dea-149">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="c0dea-150">Нажмите **кнопку "Создать отчет"**.</span><span class="sxs-lookup"><span data-stu-id="c0dea-150">Click **Generate report**.</span></span>
    
    <span data-ttu-id="c0dea-151">Отчет о результатах поиска подготовлен для загрузки, то есть документы отчетов будут загружены в хранилище Azure в Облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c0dea-151">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="c0dea-152">Когда отчет готов к загрузке, ссылка на  отчет о загрузке отображается в отчете "Экспорт" на компьютер в области сведений. </span><span class="sxs-lookup"><span data-stu-id="c0dea-152">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c0dea-153">Вы также можете экспортировать отчет для поиска контента, связанного с делом eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c0dea-153">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="c0dea-154">Для этого перейдите в **eDiscovery eDiscovery,** выберите дело и нажмите значок \>  **редактирования.** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)</span><span class="sxs-lookup"><span data-stu-id="c0dea-154">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="c0dea-155">На странице **"Поиск"** выберите поиск  и нажмите значок экспорта результатов поиска ![ ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **"Экспортировать отчет".**</span><span class="sxs-lookup"><span data-stu-id="c0dea-155">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="c0dea-156">Шаг 2. Загрузка отчета</span><span class="sxs-lookup"><span data-stu-id="c0dea-156">Step 2: Download the report</span></span>

<span data-ttu-id="c0dea-157">Следующим шагом является загрузка отчета из хранилища Azure на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="c0dea-157">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="c0dea-158">В области сведений о поиске, для который был создан отчет, в области "Экспорт отчета на компьютер" щелкните "Загрузить **отчет".**</span><span class="sxs-lookup"><span data-stu-id="c0dea-158">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="c0dea-159">**Отобразить** страницу отчета загрузки и содержит следующие сведения об отчете, который загружен на компьютер.</span><span class="sxs-lookup"><span data-stu-id="c0dea-159">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="c0dea-160">Количество скачиваемых элементов.</span><span class="sxs-lookup"><span data-stu-id="c0dea-160">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="c0dea-161">Предполагаемый общий размер скачиваемых элементов.</span><span class="sxs-lookup"><span data-stu-id="c0dea-161">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="c0dea-162">Сведения о том, какие элементы будут экспортированы, индексированные или неиндексированные.</span><span class="sxs-lookup"><span data-stu-id="c0dea-162">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="c0dea-163">Неиндексные элементы — это элементы, которые имеют распознавательный формат, шифруются или не индексироваться по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="c0dea-163">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="c0dea-164">Будет ли загружаться версия документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c0dea-164">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="c0dea-165">Состояние процесса экспорта отчета.</span><span class="sxs-lookup"><span data-stu-id="c0dea-165">The status of the report export process.</span></span> <span data-ttu-id="c0dea-166">Вы можете начать скачивать отчет, даже если подготовка отчета не завершена.</span><span class="sxs-lookup"><span data-stu-id="c0dea-166">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="c0dea-167">В разделе **Ключ экспорта** нажмите **Скопировать в буфер обмена**.</span><span class="sxs-lookup"><span data-stu-id="c0dea-167">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="c0dea-168">Этот ключ используется в шаге 5 для загрузки отчета.</span><span class="sxs-lookup"><span data-stu-id="c0dea-168">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c0dea-169">Так как любой может установить и запустить средство экспорта eDiscovery, а затем использовать этот ключ для загрузки отчета о поиске, необходимо принять меры предосторожности для защиты этого ключа так же, как вы защищаете пароли или другую информацию, связанную с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="c0dea-169">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="c0dea-170">Click **Download report**.</span><span class="sxs-lookup"><span data-stu-id="c0dea-170">Click **Download report**.</span></span>
    
4. <span data-ttu-id="c0dea-171">Если вам будет предложено установить средство экспорта **для eDiscovery,** нажмите кнопку **"Установить".**</span><span class="sxs-lookup"><span data-stu-id="c0dea-171">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="c0dea-172">В **средстве экспорта службы обнаружения электронных данных** в соответствующее поле вставьте ключ экспорта, который вы скопировали в действии 2. </span><span class="sxs-lookup"><span data-stu-id="c0dea-172">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="c0dea-173">Нажмите **кнопку** "Обзор", чтобы указать расположение, в котором вы хотите скачать отчет.</span><span class="sxs-lookup"><span data-stu-id="c0dea-173">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="c0dea-174">Нажмите кнопку **Пуск**, чтобы скачать результаты поиска на свой компьютер.</span><span class="sxs-lookup"><span data-stu-id="c0dea-174">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="c0dea-175">**Средство экспорта службы обнаружения электронных данных** отображает сведения о состоянии процесса экспорта, в том числе о предполагаемом количестве (и размере) элементов, которые осталось скачать.</span><span class="sxs-lookup"><span data-stu-id="c0dea-175">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="c0dea-176">После завершения экспорта вы сможете получить доступ к файлам в расположении, где они были загружены.</span><span class="sxs-lookup"><span data-stu-id="c0dea-176">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c0dea-177">Вы можете скачать отчет для поиска контента, связанного с делом eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c0dea-177">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="c0dea-178">Для этого перейдите в **eDiscovery eDiscovery,** выберите дело и нажмите значок \>  **редактирования.** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)</span><span class="sxs-lookup"><span data-stu-id="c0dea-178">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="c0dea-179">На странице **"Экспорт"** выберите экспорт отчета и нажмите кнопку "Загрузить **отчет"** в области сведений.</span><span class="sxs-lookup"><span data-stu-id="c0dea-179">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="c0dea-180">Что включено в отчет</span><span class="sxs-lookup"><span data-stu-id="c0dea-180">What's included in the report</span></span>

<span data-ttu-id="c0dea-181">При генерации и экспорте отчета о результатах поиска контента загружаются следующие документы:</span><span class="sxs-lookup"><span data-stu-id="c0dea-181">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="c0dea-182">**Сводка по экспорту:** Документ Excel, содержащий сводку по экспорту.</span><span class="sxs-lookup"><span data-stu-id="c0dea-182">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="c0dea-183">К ним относятся такие сведения, как количество источников контента, в которых был поиск, количество результатов поиска из каждого расположения контента, предполагаемое количество элементов, фактическое число экспортируемого элементов, а также предполагаемый и фактический размер экспортируемого элементов.</span><span class="sxs-lookup"><span data-stu-id="c0dea-183">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c0dea-184">Если при экспорте отчета включаются неndexed элементы, количество неиndexed элементов включается в общее число предполагаемых результатов поиска и общее количество загруженных результатов поиска (если вы хотите экспортировать результаты поиска), перечисленных в сводном отчете об экспорте.</span><span class="sxs-lookup"><span data-stu-id="c0dea-184">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="c0dea-185">Другими словами, общее число скачиваемых элементов равно общему числу предполагаемых результатов и общему числу неиndexed элементов.</span><span class="sxs-lookup"><span data-stu-id="c0dea-185">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="c0dea-186">**Манифест:** Файл манифеста (в формате XML), содержащий сведения о каждом элементе, включенном в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="c0dea-186">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="c0dea-187">**Результаты:** Документ Excel, содержащий строку с информацией о каждом индексируемом элементе, который будет экспортироваться вместе с результатами поиска.</span><span class="sxs-lookup"><span data-stu-id="c0dea-187">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="c0dea-188">При выполнении поиска в почте журнал результатов содержит сведения о каждом сообщении, включая указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="c0dea-188">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="c0dea-189">Расположение сообщения в исходном почтовом ящике (включая сведения о том, в каком почтовом ящике находится сообщение, в основном или в архивном).</span><span class="sxs-lookup"><span data-stu-id="c0dea-189">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="c0dea-190">Дата отправки или получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="c0dea-190">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="c0dea-191">Тема сообщения.</span><span class="sxs-lookup"><span data-stu-id="c0dea-191">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="c0dea-192">Отправитель и получатели сообщения.</span><span class="sxs-lookup"><span data-stu-id="c0dea-192">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="c0dea-193">Для документов с сайтов SharePoint и OneDrive для бизнеса журнал результатов содержит сведения о каждом документе, в том числе:</span><span class="sxs-lookup"><span data-stu-id="c0dea-193">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="c0dea-194">URL-адрес документа.</span><span class="sxs-lookup"><span data-stu-id="c0dea-194">The URL for the document.</span></span>
    
  - <span data-ttu-id="c0dea-195">URL-адрес семейства веб-сайтов, в котором расположен документ.</span><span class="sxs-lookup"><span data-stu-id="c0dea-195">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="c0dea-196">Дата последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="c0dea-196">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="c0dea-197">Имя документа (которое указано в столбце "Тема" журнала результатов).</span><span class="sxs-lookup"><span data-stu-id="c0dea-197">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c0dea-198">Число строк в отчете "Результаты" должно быть равно общему числу результатов поиска за вычетом общего количества элементов, перечисленных в отчете "Неиндексные **элементы".** </span><span class="sxs-lookup"><span data-stu-id="c0dea-198">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="c0dea-199">**Неndexed Items:** Документ Excel, содержащий сведения обо всех неndexed элементов, включенных в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="c0dea-199">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="c0dea-200">Если не включить неndexed элементы при генерации отчета результатов поиска, этот отчет будет по-прежнему загружен, но будет пустым.</span><span class="sxs-lookup"><span data-stu-id="c0dea-200">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
