---
title: Устранение распространенных проблем с электронным открытием
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте об основных действиях по устранению неполадок, которые можно предпринять для решения распространенных проблем в Office 365 eDiscovery.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0b118a97df765321704a995905de797e06a60108
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339422"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="141fa-103">Изучение, устранение неполадок и устранение распространенных проблем с электронным открытием</span><span class="sxs-lookup"><span data-stu-id="141fa-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="141fa-104">В этом разделе описывается основные действия по устранению неполадок, которые можно предпринять для выявления и устранения проблем, с которыми вы можете столкнуться во время поиска по обнаружению электронных обнаружений или в других местах в процессе поиска электронной информации.</span><span class="sxs-lookup"><span data-stu-id="141fa-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="141fa-105">Для решения некоторых из этих сценариев требуется помощь службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="141fa-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="141fa-106">Сведения о том, когда обращаться в службу поддержки Майкрософт, включены в действия по разрешению.</span><span class="sxs-lookup"><span data-stu-id="141fa-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="141fa-107">Ошибка/проблема. Неоднозначное расположение</span><span class="sxs-lookup"><span data-stu-id="141fa-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="141fa-108">Если вы пытаетесь добавить расположение почтового ящика пользователя для поиска, и в каталоге Exchange Online Protection EOP имеются дублирующиеся или конфликтующие объекты: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="141fa-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="141fa-109">Решение</span><span class="sxs-lookup"><span data-stu-id="141fa-109">Resolution</span></span>

<span data-ttu-id="141fa-110">Проверьте, есть ли повторяющиеся пользователи или список рассылки с тем же ИД пользователя.</span><span class="sxs-lookup"><span data-stu-id="141fa-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="141fa-111">Подключение [службе безопасности & Центра соответствия требованиям PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="141fa-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="141fa-112">Запустите следующую команду, чтобы получить все экземпляры имени пользователя:</span><span class="sxs-lookup"><span data-stu-id="141fa-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="141fa-113">Выход для "useralias@contoso.com" будет похож на следующий:</span><span class="sxs-lookup"><span data-stu-id="141fa-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="141fa-114">Имя</span><span class="sxs-lookup"><span data-stu-id="141fa-114">Name</span></span>|<span data-ttu-id="141fa-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="141fa-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="141fa-116">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="141fa-116">Alias, User</span></span>|<span data-ttu-id="141fa-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="141fa-117">MailUser</span></span>|
   > |<span data-ttu-id="141fa-118">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="141fa-118">Alias, User</span></span>|<span data-ttu-id="141fa-119">User</span><span class="sxs-lookup"><span data-stu-id="141fa-119">User</span></span>|

3. <span data-ttu-id="141fa-120">Если возвращается несколько пользователей, найдите и исправьте конфликтующий объект.</span><span class="sxs-lookup"><span data-stu-id="141fa-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="141fa-121">Ошибка/проблема: сбой поиска в определенных расположениях</span><span class="sxs-lookup"><span data-stu-id="141fa-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="141fa-122">Поиск электронных данных или контента может привести к следующей ошибке: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="141fa-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Расположение, определенное для поиска, не удается сделать снимок экрана ошибки](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="141fa-124">Решение</span><span class="sxs-lookup"><span data-stu-id="141fa-124">Resolution</span></span>

<span data-ttu-id="141fa-125">Если вы получили эту ошибку, рекомендуется проверить расположения, которые не удалось в поиске, а затем повторного поиска только в неудались расположения.</span><span class="sxs-lookup"><span data-stu-id="141fa-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="141fa-126">Подключение в Центр & безопасности [PowerShell,](/powershell/exchange/connect-to-scc-powershell) а затем запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="141fa-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="141fa-127">На выходе PowerShell просмотреть неудачные расположения в поле ошибок или сведения о состоянии ошибки из вывода поиска.</span><span class="sxs-lookup"><span data-stu-id="141fa-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="141fa-128">Повторное поиск по обнаружению электронных обнаружений только в сбойных расположениях.</span><span class="sxs-lookup"><span data-stu-id="141fa-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="141fa-129">Если вы продолжаете получать эти ошибки, см. пункт [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) для получения дополнительных действий по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="141fa-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="141fa-130">Ошибка/проблема. Файл не найден</span><span class="sxs-lookup"><span data-stu-id="141fa-130">Error/issue: File not found</span></span>

<span data-ttu-id="141fa-131">При запуске поиска по обнаружению электронных данных, включаемого в SharePoint Online и One Drive for Business, вы можете получить ошибку, хотя файл расположен `File Not Found` на сайте.</span><span class="sxs-lookup"><span data-stu-id="141fa-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="141fa-132">Эта ошибка будет в предупреждениях об экспорте и errors.csv или пропущена items.csv.</span><span class="sxs-lookup"><span data-stu-id="141fa-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="141fa-133">Это может произойти, если файл не может быть найден на сайте или если индекс устарел.</span><span class="sxs-lookup"><span data-stu-id="141fa-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="141fa-134">Вот текст фактической ошибки (с добавленным акцентом).</span><span class="sxs-lookup"><span data-stu-id="141fa-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="141fa-135">28.06.2019 10:02:19_FailedToExportItem_Failed скачать контент.</span><span class="sxs-lookup"><span data-stu-id="141fa-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="141fa-136">Дополнительные диагностические сведения: Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span><span class="sxs-lookup"><span data-stu-id="141fa-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="141fa-137">ID корреляции: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="141fa-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="141fa-138">ServerErrorCode: -2147024894 ---> Microsoft. SharePoint. Client.ServerException: ***файл не найден.***</span><span class="sxs-lookup"><span data-stu-id="141fa-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="141fa-139">в Корпорации Майкрософт. SharePoint. Client.ClientRequest.ProcessResponseStream (Stream responseStream) в Корпорации Майкрософт. SharePoint. Client.ClientRequest.ProcessResponse() --- окончания трассировки внутреннего стека исключений ---</span><span class="sxs-lookup"><span data-stu-id="141fa-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="141fa-140">Решение</span><span class="sxs-lookup"><span data-stu-id="141fa-140">Resolution</span></span>

1. <span data-ttu-id="141fa-141">Проверьте расположение, которое определено в поиске, чтобы убедиться, что файл находится правильно и добавлен в расположениях поиска.</span><span class="sxs-lookup"><span data-stu-id="141fa-141">Check location identified in the search to ensure that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="141fa-142">Используйте процедуры при ручном запросе обхода и повторной индексации [сайта,](/sharepoint/crawl-site-content) библиотеки или списка для повторного использования сайта.</span><span class="sxs-lookup"><span data-stu-id="141fa-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a><span data-ttu-id="141fa-143">Ошибка/проблема. Этот файл не экспортируется, так как он больше не существует.</span><span class="sxs-lookup"><span data-stu-id="141fa-143">Error/issue: This file wasn't exported because it doesn't exist anymore.</span></span> <span data-ttu-id="141fa-144">Файл был включен в число предполагаемых результатов поиска, так как он по-прежнему указан в индексе.</span><span class="sxs-lookup"><span data-stu-id="141fa-144">The file was included in the count of estimated search results because it's still listed in the index.</span></span> <span data-ttu-id="141fa-145">Файл в конечном итоге будет удален из индекса и не вызовет ошибку в будущем.</span><span class="sxs-lookup"><span data-stu-id="141fa-145">The file will eventually be removed from the index, and won't cause an error in the future.</span></span>

<span data-ttu-id="141fa-146">Вы можете увидеть эту ошибку при запуске поиска по обнаружению электронных данных, который включает SharePoint Online и One Drive For Business.</span><span class="sxs-lookup"><span data-stu-id="141fa-146">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="141fa-147">eDiscovery использует индекс SPO для определения расположения файлов.</span><span class="sxs-lookup"><span data-stu-id="141fa-147">eDiscovery relies on the SPO index to identify the file locations.</span></span> <span data-ttu-id="141fa-148">Если файл был удален, но индекс SPO еще не обновлен, эта ошибка может возникнуть.</span><span class="sxs-lookup"><span data-stu-id="141fa-148">If the file was deleted but the SPO index was not yet updated this error may occur.</span></span>

### <a name="resolution"></a><span data-ttu-id="141fa-149">Решение</span><span class="sxs-lookup"><span data-stu-id="141fa-149">Resolution</span></span> 
<span data-ttu-id="141fa-150">Откройте расположение SPO и убедитесь, что этот файл действительно не существует.</span><span class="sxs-lookup"><span data-stu-id="141fa-150">Open the SPO location and verify that this file indeed is not there.</span></span>
<span data-ttu-id="141fa-151">Рекомендуемое решение состоит в том, чтобы вручную реиндексовать сайт или подождать, пока сайт переустановит автоматический фоновый процесс.</span><span class="sxs-lookup"><span data-stu-id="141fa-151">Suggested solution is to manually reindex the site, or wait till the site reindexes by the automatic background process.</span></span>


## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artifact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a><span data-ttu-id="141fa-152">Ошибка/проблема. Этот результат поиска не был скачен, так как это папка или другой артефакт, которые не могут быть загружены самостоятельно, все элементы в папке или библиотеке будут загружены.</span><span class="sxs-lookup"><span data-stu-id="141fa-152">Error/issue: This search result was not downloaded as it is a folder or other artifact that can't be downloaded by itself, any items inside the folder or library will be downloaded.</span></span>

<span data-ttu-id="141fa-153">Вы можете увидеть эту ошибку при запуске поиска по обнаружению электронных данных, который включает SharePoint Online и One Drive For Business.</span><span class="sxs-lookup"><span data-stu-id="141fa-153">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="141fa-154">Это означает, что мы собирались попытаться экспортировать элемент, который был включен в индекс, но он оказался папкой, поэтому мы не экспортируем его.</span><span class="sxs-lookup"><span data-stu-id="141fa-154">It means that we were going to try and export the item reported in the index, but it turned out to be a folder so we did not export it.</span></span> <span data-ttu-id="141fa-155">Как упоминалось в ошибке, мы не экспортируем элементы папок, но экспортируем их содержимое.</span><span class="sxs-lookup"><span data-stu-id="141fa-155">As mentioned in the error, we don't export folder items but we do export their contents.</span></span>


## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="141fa-156">Ошибка/проблема. Поиск не удается, так как получатель не найден</span><span class="sxs-lookup"><span data-stu-id="141fa-156">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="141fa-157">Поиск по обнаружению электронных данных не удается с ошибкой `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="141fa-157">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="141fa-158">Эта ошибка может возникнуть, если объект пользователя не может быть найден в Exchange Online Protection (EOP), так как объект не синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="141fa-158">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="141fa-159">Решение</span><span class="sxs-lookup"><span data-stu-id="141fa-159">Resolution</span></span>

1. <span data-ttu-id="141fa-160">Подключитесь к [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="141fa-160">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="141fa-161">Запустите следующую команду, чтобы проверить, синхронизируется ли пользователь с Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="141fa-161">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="141fa-162">Должен быть объект пользователя почты для пользовательского вопроса.</span><span class="sxs-lookup"><span data-stu-id="141fa-162">There should be a mail user object for the user question.</span></span> <span data-ttu-id="141fa-163">Если ничего не возвращается, изучите объект пользователя.</span><span class="sxs-lookup"><span data-stu-id="141fa-163">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="141fa-164">Если объект не синхронизирован, обратитесь в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="141fa-164">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="141fa-165">Ошибка/проблема. Экспорт результатов поиска идет медленно</span><span class="sxs-lookup"><span data-stu-id="141fa-165">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="141fa-166">При экспорте результатов поиска из core eDiscovery или Content search в Центр соответствия требованиям Microsoft 365 загрузка занимает больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="141fa-166">When exporting search results from Core eDiscovery or Content search in the Microsoft 365 compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="141fa-167">Вы можете проверить количество скачиваемых данных и, возможно, увеличить скорость экспорта.</span><span class="sxs-lookup"><span data-stu-id="141fa-167">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="141fa-168">Решение</span><span class="sxs-lookup"><span data-stu-id="141fa-168">Resolution</span></span>

1. <span data-ttu-id="141fa-169">Подключение в Центр & безопасности [PowerShell,](/powershell/exchange/connect-to-scc-powershell) а затем запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="141fa-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="141fa-170">Найдите количество данных, которые будут загружены в параметрах SearchResults и SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="141fa-170">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="141fa-171">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="141fa-171">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="141fa-172">В поле результатов найдите экспортируемую информацию и просматриваем все ошибки, с которыми столкнулись.</span><span class="sxs-lookup"><span data-stu-id="141fa-172">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="141fa-173">Проверьте файл trace.log, расположенный в каталоге, в который экспортируется содержимое, для любых ошибок.</span><span class="sxs-lookup"><span data-stu-id="141fa-173">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="141fa-174">Если у вас еще есть проблемы, подумайте о разделении поисков, возвращающих большой набор результатов в меньшие поиски.</span><span class="sxs-lookup"><span data-stu-id="141fa-174">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="141fa-175">Например, диапазоны дат можно использовать в поисковых запросах, чтобы вернуть меньший набор результатов, которые можно скачать быстрее.</span><span class="sxs-lookup"><span data-stu-id="141fa-175">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-export-process-not-progressing-or-is-stuck"></a><span data-ttu-id="141fa-176">Ошибка/проблема: процесс экспорта не развивается или не застрянет</span><span class="sxs-lookup"><span data-stu-id="141fa-176">Error/issue: Export process not progressing or is stuck</span></span>

<span data-ttu-id="141fa-177">При экспорте результатов поиска из core eDiscovery или content search in the Центр соответствия требованиям Microsoft 365, процесс экспорта не развивается или, как представляется, завис.</span><span class="sxs-lookup"><span data-stu-id="141fa-177">When exporting search results from Core eDiscovery or Content search in the Microsoft 365 compliance center, the export process is not progressing or appears to be stuck.</span></span>

### <a name="resolution"></a><span data-ttu-id="141fa-178">Решение</span><span class="sxs-lookup"><span data-stu-id="141fa-178">Resolution</span></span>

1. <span data-ttu-id="141fa-179">При необходимости перезахоранить поиск.</span><span class="sxs-lookup"><span data-stu-id="141fa-179">If necessary, rerun the search.</span></span> <span data-ttu-id="141fa-180">Если поиск был последний раз, более 7 дней назад, необходимо повторно перезахоранить поиск.</span><span class="sxs-lookup"><span data-stu-id="141fa-180">If the search was last ran more than 7 days ago, you have to rerun the search.</span></span>

2. <span data-ttu-id="141fa-181">Перезапустите экспорт.</span><span class="sxs-lookup"><span data-stu-id="141fa-181">Restart the export.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="141fa-182">Ошибка/проблема: "Произошла ошибка внутреннего сервера (500)"</span><span class="sxs-lookup"><span data-stu-id="141fa-182">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="141fa-183">При запуске поиска по обнаружению электронных данных при постоянном сбое поиска с ошибкой, аналогичной "Ошибка внутреннего сервера (500) произошла", может потребоваться повторное повторение поиска только в определенных расположениях почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="141fa-183">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Скриншот ошибки внутреннего сервера 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="141fa-185">Решение</span><span class="sxs-lookup"><span data-stu-id="141fa-185">Resolution</span></span>

1. <span data-ttu-id="141fa-186">Разорвать поиск на меньшие поиски и запустить поиск снова.</span><span class="sxs-lookup"><span data-stu-id="141fa-186">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="141fa-187">Попробуйте использовать меньший диапазон дат или ограничить количество поисковых местоположений.</span><span class="sxs-lookup"><span data-stu-id="141fa-187">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="141fa-188">Подключение в Центр & безопасности [PowerShell,](/powershell/exchange/connect-to-scc-powershell) а затем запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="141fa-188">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="141fa-189">Изучите результаты и ошибки.</span><span class="sxs-lookup"><span data-stu-id="141fa-189">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="141fa-190">Изучите файл trace.log.</span><span class="sxs-lookup"><span data-stu-id="141fa-190">Examine the trace.log file.</span></span> <span data-ttu-id="141fa-191">Он расположен в той же папке, в которую экспортируются результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="141fa-191">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="141fa-192">Обратитесь в службу поддержки корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="141fa-192">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="141fa-193">Ошибка/проблема. Не синхронизируются удерживаемая</span><span class="sxs-lookup"><span data-stu-id="141fa-193">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="141fa-194">Ошибка распределения синхронизации политики при обнаружении электронных данных.</span><span class="sxs-lookup"><span data-stu-id="141fa-194">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="141fa-195">Ошибка гласит:</span><span class="sxs-lookup"><span data-stu-id="141fa-195">The error reads:</span></span>

> <span data-ttu-id="141fa-196">"Ресурсы. Развертывание политики может затметь больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="141fa-196">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="141fa-197">На обновление окончательного состояния развертывания может потребоваться еще 2 часа, поэтому проверьте это в течение нескольких часов".</span><span class="sxs-lookup"><span data-stu-id="141fa-197">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="141fa-198">Решение</span><span class="sxs-lookup"><span data-stu-id="141fa-198">Resolution</span></span>

1. <span data-ttu-id="141fa-199">Подключение [центр & PowerShell,](/powershell/exchange/connect-to-scc-powershell) а затем запустите следующую команду для удержания дела об обнаружении электронных данных:</span><span class="sxs-lookup"><span data-stu-id="141fa-199">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="141fa-200">Для политики хранения запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="141fa-200">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="141fa-201">Изучите значение параметра DistributionDetail для ошибок, таких как следующие:</span><span class="sxs-lookup"><span data-stu-id="141fa-201">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="141fa-202">Ошибка. Ресурсы. Развертывание политики проходит дольше, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="141fa-202">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="141fa-203">На обновление окончательного состояния развертывания может потребоваться еще 2 часа, поэтому проверьте это в течение нескольких часов".</span><span class="sxs-lookup"><span data-stu-id="141fa-203">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="141fa-204">Попробуйте запускать параметр RetryDistribution для политики, определимой:</span><span class="sxs-lookup"><span data-stu-id="141fa-204">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="141fa-205">Для дела об обнаружении электронных обнаружений:</span><span class="sxs-lookup"><span data-stu-id="141fa-205">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="141fa-206">Для политик хранения:</span><span class="sxs-lookup"><span data-stu-id="141fa-206">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="141fa-207">Обратитесь в службу поддержки корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="141fa-207">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="141fa-208">Ошибка: "Условие, указанное с помощью условного заголовка HTTP(ы) не выполнены"</span><span class="sxs-lookup"><span data-stu-id="141fa-208">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="141fa-209">При загрузке результатов поиска с помощью экспортного средства eDiscovery можно получить следующую ошибку: это преходящая ошибка, которая обычно возникает в служба хранилища Azure `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` расположении.</span><span class="sxs-lookup"><span data-stu-id="141fa-209">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="141fa-210">Решение</span><span class="sxs-lookup"><span data-stu-id="141fa-210">Resolution</span></span>

<span data-ttu-id="141fa-211">Чтобы устранить эту проблему, повторите скачивание результатов [поиска,](export-search-results.md#step-2-download-the-search-results)которые перезапустят средство экспорта электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="141fa-211">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="141fa-212">Ошибка/проблема. Загруженный экспорт не показывает результатов</span><span class="sxs-lookup"><span data-stu-id="141fa-212">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="141fa-213">После успешного экспорта завершенная загрузка с помощью средства экспорта показывает нулевые файлы в результатах.</span><span class="sxs-lookup"><span data-stu-id="141fa-213">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="141fa-214">Решение</span><span class="sxs-lookup"><span data-stu-id="141fa-214">Resolution</span></span>

<span data-ttu-id="141fa-215">Это клиентская проблема.</span><span class="sxs-lookup"><span data-stu-id="141fa-215">This is a client-side issue.</span></span> <span data-ttu-id="141fa-216">Чтобы ее исправление, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="141fa-216">To remediate it, follow these steps:</span></span>

1. <span data-ttu-id="141fa-217">Попробуйте скачать с помощью другого клиента или компьютера.</span><span class="sxs-lookup"><span data-stu-id="141fa-217">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="141fa-218">Удалите старые поиски, которые больше не нужны с помощью [cmdlet Remove-ComplianceSearch.](/powershell/module/exchange/remove-compliancesearch)</span><span class="sxs-lookup"><span data-stu-id="141fa-218">Remove old searches that are no longer needed using [Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) cmdlet.</span></span>

3. <span data-ttu-id="141fa-219">Не забудьте скачать на локальный диск.</span><span class="sxs-lookup"><span data-stu-id="141fa-219">Make sure to download to a local drive.</span></span>

4. <span data-ttu-id="141fa-220">Убедитесь, что сканер вирусов не запущен.</span><span class="sxs-lookup"><span data-stu-id="141fa-220">Make sure the virus scanner is not running.</span></span>

5. <span data-ttu-id="141fa-221">Убедитесь, что ни один другой экспорт не загружается в ту же папку или в родительской папке.</span><span class="sxs-lookup"><span data-stu-id="141fa-221">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

6. <span data-ttu-id="141fa-222">Если предыдущие действия не сработают, отключим отрезок и отключим дублирование.</span><span class="sxs-lookup"><span data-stu-id="141fa-222">If the previous steps don't work, disable zipping and de-duplication.</span></span>

7. <span data-ttu-id="141fa-223">Если это работает, то проблема вызвана локальным сканером вирусов или проблемой диска.</span><span class="sxs-lookup"><span data-stu-id="141fa-223">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
