---
title: Отключение отчетов при экспорте результатов поиска контента
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Изменить реестр Windows на локальном компьютере, чтобы отключить отчеты при экспорте результатов поиска контента из Центра & соответствия требованиям.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817858"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="1ee95-103">Отключение отчетов при экспорте результатов поиска контента</span><span class="sxs-lookup"><span data-stu-id="1ee95-103">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="1ee95-104">При экспорте результатов поиска контента в Центре соответствия требованиям & eDiscovery Export средство автоматически создает и экспортирует два отчета, содержащих дополнительные сведения об экспортируемом контенте.</span><span class="sxs-lookup"><span data-stu-id="1ee95-104">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="1ee95-105">Эти отчеты являются Results.csv и файл Manifest.xml (см. [](#frequently-asked-questions-about-disabling-export-reports) часто задамые вопросы об отключении экспорта отчетов в этом разделе для подробных описаний этих отчетов).</span><span class="sxs-lookup"><span data-stu-id="1ee95-105">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="1ee95-106">Поскольку эти файлы могут быть очень большими, можно ускорить время скачивания и сохранить пространство диска, не мешая экспортировать эти файлы.</span><span class="sxs-lookup"><span data-stu-id="1ee95-106">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="1ee95-107">Это можно сделать, изменив Windows реестра на компьютере, который используется для экспорта результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="1ee95-107">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="1ee95-108">Если вы хотите включить отчеты в более позднее время, вы можете изменить параметр реестра.</span><span class="sxs-lookup"><span data-stu-id="1ee95-108">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="1ee95-109">Создание параметров реестра для отключения отчетов об экспорте</span><span class="sxs-lookup"><span data-stu-id="1ee95-109">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="1ee95-110">Выполните следующую процедуру на компьютере, который будет использовать для экспорта результатов поиска контента.</span><span class="sxs-lookup"><span data-stu-id="1ee95-110">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="1ee95-111">Закрой средство экспорта электронных открытий, если оно открыто.</span><span class="sxs-lookup"><span data-stu-id="1ee95-111">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="1ee95-112">Выполните один или оба следующих шага в зависимости от того, какой отчет экспорта необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="1ee95-112">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="1ee95-113">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="1ee95-113">**Results.csv**</span></span>
    
      <span data-ttu-id="1ee95-114">Сохраните следующий текст в Windows реестра с помощью суффикса .reg; например, DisableResultsCsv.reg.</span><span class="sxs-lookup"><span data-stu-id="1ee95-114">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="1ee95-115">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="1ee95-115">**Manifest.xml**</span></span>
    
      <span data-ttu-id="1ee95-116">Сохраните следующий текст в Windows реестра с помощью суффикса .reg; например, DisableManifestXml.reg.</span><span class="sxs-lookup"><span data-stu-id="1ee95-116">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="1ee95-117">В Windows Explorer щелкните или дважды щелкните файл .reg, созданный в предыдущих действиях.</span><span class="sxs-lookup"><span data-stu-id="1ee95-117">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="1ee95-118">В окне Управления доступом пользователей щелкните **Да,** чтобы редактор реестра внести изменения.</span><span class="sxs-lookup"><span data-stu-id="1ee95-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="1ee95-119">Если вам будет предложено продолжить, нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="1ee95-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="1ee95-120">Редактор реестра отображает сообщение о том, что параметр успешно добавлен в реестр.</span><span class="sxs-lookup"><span data-stu-id="1ee95-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="1ee95-121">Изменение параметров реестра, чтобы повторно включить отчеты об экспорте</span><span class="sxs-lookup"><span data-stu-id="1ee95-121">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="1ee95-122">Если вы отключили отчеты Results.csv и Manifest.xml, создав файлы .reg в предыдущей процедуре, вы можете изменить эти файлы, чтобы повторно включить отчет, чтобы он экспортировался с результатами поиска.</span><span class="sxs-lookup"><span data-stu-id="1ee95-122">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="1ee95-123">Снова выполните следующую процедуру на компьютере, который будет использовать для экспорта результатов поиска контента.</span><span class="sxs-lookup"><span data-stu-id="1ee95-123">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="1ee95-124">Закрой средство экспорта электронных открытий, если оно открыто.</span><span class="sxs-lookup"><span data-stu-id="1ee95-124">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="1ee95-125">Изменить один или оба файла редактирования .reg, созданных в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="1ee95-125">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="1ee95-126">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="1ee95-126">**Results.csv**</span></span>
    
        <span data-ttu-id="1ee95-127">Откройте файл DisableResultsCsv.reg в Блокнот, измените значение и `False` `True` сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="1ee95-127">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="1ee95-128">Например, после редактирования файла выглядит так:</span><span class="sxs-lookup"><span data-stu-id="1ee95-128">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="1ee95-129">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="1ee95-129">**Manifest.xml**</span></span>
    
        <span data-ttu-id="1ee95-130">Откройте файл DisableManifestXml.reg в Блокнот, измените значение и `False` `True` сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="1ee95-130">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="1ee95-131">Например, после редактирования файла выглядит так:</span><span class="sxs-lookup"><span data-stu-id="1ee95-131">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="1ee95-132">В Windows Explorer щелкните или дважды щелкните файл .reg, который был отредактирован на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="1ee95-132">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="1ee95-133">В окне Управления доступом пользователей щелкните **Да,** чтобы редактор реестра внести изменения.</span><span class="sxs-lookup"><span data-stu-id="1ee95-133">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="1ee95-134">Если вам будет предложено продолжить, нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="1ee95-134">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="1ee95-135">Редактор реестра отображает сообщение о том, что параметр успешно добавлен в реестр.</span><span class="sxs-lookup"><span data-stu-id="1ee95-135">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="1ee95-136">Часто задамые вопросы об отключении отчетов об экспорте</span><span class="sxs-lookup"><span data-stu-id="1ee95-136">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="1ee95-137">**Какие отчеты Results.csv Manifest.xml отчеты?**</span><span class="sxs-lookup"><span data-stu-id="1ee95-137">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="1ee95-138">Файлы Results.csv Manifest.xml содержат дополнительные сведения о экспортируемом контенте.</span><span class="sxs-lookup"><span data-stu-id="1ee95-138">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="1ee95-139">**Results.csv** Документ Excel, содержащий сведения о каждом элементе, скачаемом в результате поиска.</span><span class="sxs-lookup"><span data-stu-id="1ee95-139">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="1ee95-140">При выполнении поиска в почте журнал результатов содержит сведения о каждом сообщении, включая указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="1ee95-140">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="1ee95-141">Расположение сообщения в исходном почтовом ящике (включая сведения о том, в каком почтовом ящике находится сообщение, в основном или в архивном).</span><span class="sxs-lookup"><span data-stu-id="1ee95-141">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="1ee95-142">Дата отправки или получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="1ee95-142">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="1ee95-143">Тема сообщения.</span><span class="sxs-lookup"><span data-stu-id="1ee95-143">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="1ee95-144">Отправитель и получатели сообщения.</span><span class="sxs-lookup"><span data-stu-id="1ee95-144">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="1ee95-145">Является ли сообщение дублирующим сообщением, если при экспорте результатов поиска включено де-дублирование.</span><span class="sxs-lookup"><span data-stu-id="1ee95-145">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="1ee95-146">Дубликат сообщений будет иметь значение в столбце **Parent ItemId,** которое определяет сообщение как дубликат.</span><span class="sxs-lookup"><span data-stu-id="1ee95-146">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="1ee95-147">Значение в столбце **Parent ItemId** такое же, как и значение в столбце **Item DocumentId** экспортируемого сообщения.</span><span class="sxs-lookup"><span data-stu-id="1ee95-147">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="1ee95-148">Для документов с SharePoint OneDrive для бизнеса сайтов журнал результатов содержит сведения о каждом документе, в том числе:</span><span class="sxs-lookup"><span data-stu-id="1ee95-148">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="1ee95-149">URL-адрес документа.</span><span class="sxs-lookup"><span data-stu-id="1ee95-149">The URL for the document.</span></span>
    
  - <span data-ttu-id="1ee95-150">URL-адрес семейства веб-сайтов, в котором расположен документ.</span><span class="sxs-lookup"><span data-stu-id="1ee95-150">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="1ee95-151">Дата последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="1ee95-151">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="1ee95-152">Имя документа (которое указано в столбце "Тема" журнала результатов).</span><span class="sxs-lookup"><span data-stu-id="1ee95-152">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="1ee95-153">**Manifest.xml** Файл манифеста (в формате XML), содержащий сведения о каждом элементе, включенном в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="1ee95-153">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="1ee95-154">Сведения в этом отчете те же, что и Results.csv отчете, но они в формате, указанном справочной моделью электронного обнаружения (EDRM).</span><span class="sxs-lookup"><span data-stu-id="1ee95-154">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="1ee95-155">Дополнительные сведения о EDRM перейдите к [https://www.edrm.net](https://www.edrm.net) .</span><span class="sxs-lookup"><span data-stu-id="1ee95-155">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="1ee95-156">**Когда следует отключить экспорт этих отчетов?**</span><span class="sxs-lookup"><span data-stu-id="1ee95-156">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="1ee95-157">Это зависит от конкретных потребностей.</span><span class="sxs-lookup"><span data-stu-id="1ee95-157">It depends on your specific needs.</span></span> <span data-ttu-id="1ee95-158">Многие организации не требуют дополнительных сведений о результатах поиска и не нуждаются в этих отчетах.</span><span class="sxs-lookup"><span data-stu-id="1ee95-158">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="1ee95-159">**На каком компьютере я должен это сделать?**</span><span class="sxs-lookup"><span data-stu-id="1ee95-159">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="1ee95-160">Необходимо изменить параметр реестра на любом локальном компьютере, на который вы запустите средство экспорта электронных открытий.</span><span class="sxs-lookup"><span data-stu-id="1ee95-160">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="1ee95-161">**После изменения этого параметра необходимо перезапустить компьютер?**</span><span class="sxs-lookup"><span data-stu-id="1ee95-161">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="1ee95-162">Нет, вам не нужно перезапустить компьютер.</span><span class="sxs-lookup"><span data-stu-id="1ee95-162">No, you don't have to restart the computer.</span></span> <span data-ttu-id="1ee95-163">Но если средство экспорта электронных обнаружений запущено, его необходимо закрыть, а затем перезапустить после изменения параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="1ee95-163">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="1ee95-164">**Редактируется ли существующий ключ реестра или создается новый ключ?**</span><span class="sxs-lookup"><span data-stu-id="1ee95-164">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="1ee95-165">При первом запуске файла .reg, созданного в процедуре в этом разделе, создается новый ключ реестра.</span><span class="sxs-lookup"><span data-stu-id="1ee95-165">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="1ee95-166">Затем параметр редактируется при каждом изменении и повторном запуске файла редактирования .reg.</span><span class="sxs-lookup"><span data-stu-id="1ee95-166">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
