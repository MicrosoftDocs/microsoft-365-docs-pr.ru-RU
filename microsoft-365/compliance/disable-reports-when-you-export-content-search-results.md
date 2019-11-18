---
title: Отключение отчетов при экспорте результатов поиска контента
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: Отредактируйте реестр Windows на локальном компьютере, чтобы отключить отчеты при экспорте результатов поиска контента из центра безопасности & соответствия требованиям в Office 365. Отключение этих отчетов может ускорить загрузку и сэкономить место на диске.
ms.openlocfilehash: f9b999eaf3f1924012c9d4899b0e234f0893fc2c
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38687541"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="e3bb6-104">Отключение отчетов при экспорте результатов поиска контента</span><span class="sxs-lookup"><span data-stu-id="e3bb6-104">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="e3bb6-105">При использовании средства экспорта eDiscovery для Office 365 для экспорта результатов поиска контента в центре безопасности & соответствия требованиям средство автоматически создает и экспортирует два отчета, которые содержат дополнительные сведения о экспортированном содержимом.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-105">When you use the Office 365 eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="e3bb6-106">Эти отчеты представляют собой файл Results. csv и файл manifest. XML (Дополнительные сведения об отключении этих отчетов можно найти в разделе вопросы и ответы [по отключению экспорта отчетов](#frequently-asked-questions-about-disabling-export-reports) в этом разделе).</span><span class="sxs-lookup"><span data-stu-id="e3bb6-106">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="e3bb6-107">Так как эти файлы могут быть очень большими, вы можете ускорить загрузку и сэкономить место на диске, предотвращая экспорт этих файлов.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-107">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="e3bb6-108">Это можно сделать, изменив реестр Windows на компьютере, который будет использоваться для экспорта результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-108">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="e3bb6-109">Если вы хотите включить отчеты позже, вы можете изменить параметр реестра.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-109">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="e3bb6-110">Создание параметров реестра для отключения отчетов по экспорту</span><span class="sxs-lookup"><span data-stu-id="e3bb6-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="e3bb6-111">Выполните следующую процедуру на компьютере, который будет использоваться для экспорта результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="e3bb6-112">Закройте средство экспорта eDiscovery для Office 365, если оно открыто.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-112">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="e3bb6-113">Выполните одно или оба следующих действия, в зависимости от того, какой отчет экспорта требуется отключить.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="e3bb6-114">**Results. CSV**</span><span class="sxs-lookup"><span data-stu-id="e3bb6-114">**Results.csv**</span></span>
    
      <span data-ttu-id="e3bb6-115">Сохраните приведенный ниже текст в файле реестра Windows, используя суффикс имени файла. reg; Например, Дисаблересултсксв. reg.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="e3bb6-116">**Manifest. XML**</span><span class="sxs-lookup"><span data-stu-id="e3bb6-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="e3bb6-117">Сохраните приведенный ниже текст в файле реестра Windows, используя суффикс имени файла. reg; Например, Дисаблеманифестксмл. reg.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="e3bb6-118">В проводнике Windows щелкните или дважды щелкните файл. reg, созданный на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="e3bb6-119">В окне управления доступом пользователей нажмите кнопку **Да** , чтобы разрешить редактору реестра внести изменения.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="e3bb6-120">При появлении запроса на продолжение нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="e3bb6-121">Редактор реестра выводит сообщение о том, что параметр был успешно добавлен в реестр.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="e3bb6-122">Изменение параметров реестра для повторного включения отчетов по экспорту</span><span class="sxs-lookup"><span data-stu-id="e3bb6-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="e3bb6-123">Если вы отключили отчеты Results. csv и manifest. XML, создав reg-файлы в предыдущей процедуре, вы можете изменить эти файлы, чтобы снова включить отчет, чтобы он был экспортирован вместе с результатами поиска.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-123">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="e3bb6-124">Опять же, выполните следующую процедуру на компьютере, который будет использоваться для экспорта результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-124">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="e3bb6-125">Закройте средство экспорта eDiscovery для Office 365, если оно открыто.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-125">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="e3bb6-126">Измените один или оба REG файлов редактирования, которые были созданы в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="e3bb6-127">**Results. CSV**</span><span class="sxs-lookup"><span data-stu-id="e3bb6-127">**Results.csv**</span></span>
    
        <span data-ttu-id="e3bb6-128">Откройте файл Дисаблересултсксв. reg в блокноте, измените значение `False` на `True`, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-128">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="e3bb6-129">Например, после редактирования файла он выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e3bb6-129">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="e3bb6-130">**Manifest. XML**</span><span class="sxs-lookup"><span data-stu-id="e3bb6-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="e3bb6-131">Откройте файл Дисаблеманифестксмл. reg в блокноте, измените значение `False` на `True`, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-131">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="e3bb6-132">Например, после редактирования файла он выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e3bb6-132">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="e3bb6-133">В проводнике Windows щелкните или дважды щелкните файл REG, который вы редактировали на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="e3bb6-134">В окне управления доступом пользователей нажмите кнопку **Да** , чтобы разрешить редактору реестра внести изменения.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="e3bb6-135">При появлении запроса на продолжение нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="e3bb6-136">Редактор реестра выводит сообщение о том, что параметр был успешно добавлен в реестр.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="e3bb6-137">Часто задаваемые вопросы об отключении отчетов об экспорте</span><span class="sxs-lookup"><span data-stu-id="e3bb6-137">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="e3bb6-138">**Что такое отчеты Results. csv и manifest. XML?**</span><span class="sxs-lookup"><span data-stu-id="e3bb6-138">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="e3bb6-139">Файлы results. csv и manifest. XML содержат дополнительные сведения о экспортированном контенте.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-139">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="e3bb6-140">**Results. csv** документ Excel, который содержит сведения о каждом элементе, загружаемом в качестве результата поиска.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-140">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="e3bb6-141">При выполнении поиска в почте журнал результатов содержит сведения о каждом сообщении, включая указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-141">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="e3bb6-142">Расположение сообщения в исходном почтовом ящике (включая сведения о том, в каком почтовом ящике находится сообщение, в основном или в архивном).</span><span class="sxs-lookup"><span data-stu-id="e3bb6-142">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="e3bb6-143">Дата отправки или получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-143">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="e3bb6-144">Тема сообщения.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-144">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="e3bb6-145">Отправитель и получатели сообщения.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-145">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="e3bb6-146">Указывает, является ли сообщение повторяющимся, если вы включили дедупликацию при экспорте результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-146">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="e3bb6-147">Повторяющиеся сообщения будут иметь значение в **родительском столбце ItemId** , которое идентифицирует сообщение как повторяющееся.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-147">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="e3bb6-148">Значение в **родительском столбце ItemId** совпадает со значением в столбце **элемент DocumentID** экспортируемого сообщения.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-148">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="e3bb6-149">Для документов из сайтов SharePoint и OneDrive для бизнеса журнал результатов содержит сведения о каждом документе, включая:</span><span class="sxs-lookup"><span data-stu-id="e3bb6-149">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="e3bb6-150">URL-адрес документа.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-150">The URL for the document.</span></span>
    
  - <span data-ttu-id="e3bb6-151">URL-адрес семейства веб-сайтов, в котором расположен документ.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-151">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="e3bb6-152">Дата последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-152">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="e3bb6-153">Имя документа (которое указано в столбце "Тема" журнала результатов).</span><span class="sxs-lookup"><span data-stu-id="e3bb6-153">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="e3bb6-154">**Manifest. XML** файл манифеста (в формате XML), который содержит сведения о каждом элементе, включенном в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-154">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="e3bb6-155">Сведения, представленные в этом отчете, совпадают с отчетом Results. csv, но указаны в формате, заданном в модели электронного обнаружения (EDRM).</span><span class="sxs-lookup"><span data-stu-id="e3bb6-155">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="e3bb6-156">Чтобы получить дополнительные сведения о EDRM, перейдите [https://www.edrm.net](https://www.edrm.net)на страницу.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-156">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="e3bb6-157">**Когда следует отключать экспорт этих отчетов?**</span><span class="sxs-lookup"><span data-stu-id="e3bb6-157">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="e3bb6-158">Это зависит от конкретных потребностей.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-158">It depends on your specific needs.</span></span> <span data-ttu-id="e3bb6-159">Многим организациям не требуются дополнительные сведения о результатах поиска, и эти отчеты не нужны.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-159">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="e3bb6-160">**На каком компьютере необходимо сделать это?**</span><span class="sxs-lookup"><span data-stu-id="e3bb6-160">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="e3bb6-161">Необходимо изменить параметр реестра на любом локальном компьютере, на котором запущено средство экспорта eDiscovery для Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-161">You have to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="e3bb6-162">**Когда я изменяю этот параметр, необходимо перезапустить компьютер?**</span><span class="sxs-lookup"><span data-stu-id="e3bb6-162">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="e3bb6-163">Нет, перезагружать компьютер не требуется.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-163">No, you don't have to restart the computer.</span></span> <span data-ttu-id="e3bb6-164">Но если средство экспорта eDiscovery Office 365 запущено, его необходимо закрыть и перезапустить после изменения параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-164">But if the Office 365 eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="e3bb6-165">**Редактируется ли существующий раздел реестра или создается новый ключ?**</span><span class="sxs-lookup"><span data-stu-id="e3bb6-165">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="e3bb6-166">Новый раздел реестра создается при первом запуске REG-файла, созданного в процедуре, описанной в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-166">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="e3bb6-167">Затем этот параметр изменяется каждый раз, когда вы изменяете и повторно запускаете reg-файл редактирования.</span><span class="sxs-lookup"><span data-stu-id="e3bb6-167">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
