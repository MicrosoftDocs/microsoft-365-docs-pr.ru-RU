---
title: Устранение распространенных проблем с обнаружением электронных данных
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
description: Сведения об основных этапах устранения неполадок, которые можно предпринять для решения распространенных проблем, связанных с обнаружением электронных данных в Office 365.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5c9d917306c1a4ffd0dd1e11e1dd87c135e94f05
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545957"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="ae1e2-103">Исследование, устранение неполадок и устранение распространенных проблем обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="ae1e2-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="ae1e2-104">В этом разделе описываются основные действия по устранению неполадок, которые можно предпринять для определения и устранения проблем, которые могут возникать во время поиска обнаружения электронных данных или в другом месте процесса обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="ae1e2-105">Для устранения некоторых из этих сценариев необходима помощь в службе поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="ae1e2-106">Сведения о том, когда следует обращаться в службу поддержки Майкрософт, приведены в разделе действия по разрешению.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="ae1e2-107">Ошибка/Ошибка: неоднозначное расположение</span><span class="sxs-lookup"><span data-stu-id="ae1e2-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="ae1e2-108">Если попытаться добавить в поиск расположение почтового ящика пользователя, а в каталоге Exchange Online Protection (EOP) имеются повторяющиеся или конфликтующие объекты с тем же userID, возникает следующая ошибка: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="ae1e2-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="ae1e2-109">Решение</span><span class="sxs-lookup"><span data-stu-id="ae1e2-109">Resolution</span></span>

<span data-ttu-id="ae1e2-110">Проверьте наличие дубликатов пользователей или списка рассылки с одинаковым ИДЕНТИФИКАТОРом пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="ae1e2-111">Подключитесь к [PowerShell центра безопасности & соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="ae1e2-111">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="ae1e2-112">Выполните следующую команду, чтобы получить все экземпляры имени пользователя:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="ae1e2-113">Выходные данные для "useralias@contoso.com" будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="ae1e2-114">Имя</span><span class="sxs-lookup"><span data-stu-id="ae1e2-114">Name</span></span>|<span data-ttu-id="ae1e2-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="ae1e2-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="ae1e2-116">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="ae1e2-116">Alias, User</span></span>|<span data-ttu-id="ae1e2-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="ae1e2-117">MailUser</span></span>|
   > |<span data-ttu-id="ae1e2-118">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="ae1e2-118">Alias, User</span></span>|<span data-ttu-id="ae1e2-119">Пользователь</span><span class="sxs-lookup"><span data-stu-id="ae1e2-119">User</span></span>|

3. <span data-ttu-id="ae1e2-120">Если возвращается несколько пользователей, разместите и устраните конфликтующий объект.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="ae1e2-121">Ошибка/Ошибка: сбой поиска в определенных расположениях</span><span class="sxs-lookup"><span data-stu-id="ae1e2-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="ae1e2-122">Поиск обнаружения электронных данных или контента может привести к возникновению следующей ошибки:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="ae1e2-123">Поиск завершился с ошибками (#).</span><span class="sxs-lookup"><span data-stu-id="ae1e2-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="ae1e2-124">Вы хотите повторить поиск в расположениях с ошибками?</span><span class="sxs-lookup"><span data-stu-id="ae1e2-124">Would you like to retry the search on the failed locations?</span></span>

![Снимок экрана с расположением для поиска со сбоем](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="ae1e2-126">Решение</span><span class="sxs-lookup"><span data-stu-id="ae1e2-126">Resolution</span></span>

<span data-ttu-id="ae1e2-127">При возникновении этой ошибки рекомендуется проверить расположения, в которых произошел сбой, а затем повторить поиск только в расположениях, на которых не удалось выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-127">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="ae1e2-128">Подключитесь к [PowerShell центра безопасности & соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) , а затем выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-128">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="ae1e2-129">В выходных данных PowerShell просмотрите сведения о неудачных расположениях в поле ошибки или сведения о состоянии, указанные в сообщении об ошибке, из результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-129">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="ae1e2-130">Повторите поиск обнаружения электронных данных для неудачных расположений.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-130">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="ae1e2-131">Если вы продолжаете получать эти ошибки, обратитесь к разделу [Retry Fail Failed Locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more Errors.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-131">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="ae1e2-132">Ошибка/Ошибка: файл не найден</span><span class="sxs-lookup"><span data-stu-id="ae1e2-132">Error/issue: File not found</span></span>

<span data-ttu-id="ae1e2-133">При выполнении поиска обнаружения электронных данных, включающего SharePoint Online и один диск для размещения бизнеса, может появиться сообщение об ошибке, несмотря на то, что `File Not Found` файл находится на сайте.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-133">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="ae1e2-134">Эта ошибка будет присутствовать в предупреждениях экспорта, errors.csv или пропущенных items.csv.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-134">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="ae1e2-135">Это может произойти, если не удается найти файл на сайте или индекс устарел.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-135">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="ae1e2-136">Вот текст фактической ошибки (с добавленным выделением).</span><span class="sxs-lookup"><span data-stu-id="ae1e2-136">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="ae1e2-137">28.06.2019 10:02:19_FailedToExportItem_Failed для скачивания контента.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="ae1e2-138">Дополнительные диагностические сведения: Microsoft. Office. соответствие. EDiscovery. Експортворкер. Exceptions. Контентдовнлоадтемпорарифаилуре: не удалось скачать из контента 6ea52149 — 91cd – 4965 – b5bb – 82ca6a3ec9be типа Document.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="ae1e2-139">Идентификатор корреляции: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="ae1e2-140">Серверерроркоде: – 2147024894---> Microsoft. SharePoint. Client. Серверексцептион: ***файл не найден***.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="ae1e2-141">в Microsoft. SharePoint. Client. Клиентрекуест. Процессреспонсестреам (Stream Респонсестреам) на сайте Microsoft. SharePoint. Client. Клиентрекуест. Процессреспонсе ()---конец трассировки стека внутренних исключений---</span><span class="sxs-lookup"><span data-stu-id="ae1e2-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="ae1e2-142">Решение</span><span class="sxs-lookup"><span data-stu-id="ae1e2-142">Resolution</span></span>

1. <span data-ttu-id="ae1e2-143">Проверьте расположение, указанное в поиске, чтобы убедиться в том, что расположение файла указано правильно и добавляется в расположений для поиска.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="ae1e2-144">Используйте процедуры при [ручном запросе на обход контента и повторной индексации сайта, библиотеки или списка](https://docs.microsoft.com/sharepoint/crawl-site-content) , чтобы переиндексировать сайт.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](https://docs.microsoft.com/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="ae1e2-145">Ошибка/Ошибка: не удается выполнить поиск, так как получатель не найден</span><span class="sxs-lookup"><span data-stu-id="ae1e2-145">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="ae1e2-146">Сбой поиска обнаружения электронных данных с ошибкой `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="ae1e2-146">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="ae1e2-147">Эта ошибка может возникнуть, если объект пользователя не удается найти в Exchange Online Protection (EOP), так как объект не синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="ae1e2-148">Решение</span><span class="sxs-lookup"><span data-stu-id="ae1e2-148">Resolution</span></span>

1. <span data-ttu-id="ae1e2-149">Подключитесь к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ae1e2-149">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="ae1e2-150">Выполните следующую команду, чтобы проверить, синхронизирован ли пользователь с Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-150">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="ae1e2-151">Для ответа пользователя должен быть объект пользователя почты.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-151">There should be a mail user object for the user question.</span></span> <span data-ttu-id="ae1e2-152">Если ничего не возвращается, изучите объект User.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="ae1e2-153">Если не удается синхронизировать объект, обратитесь в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-153">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="ae1e2-154">Ошибка/Ошибка: немедленный экспорт результатов поиска</span><span class="sxs-lookup"><span data-stu-id="ae1e2-154">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="ae1e2-155">При экспорте результатов поиска из обнаружения электронных данных или поиска контента в центре безопасности и соответствия требованиям Загрузка занимает больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="ae1e2-156">Вы можете проверить количество загружаемых данных и, возможно, увеличить скорость экспорта.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="ae1e2-157">Решение</span><span class="sxs-lookup"><span data-stu-id="ae1e2-157">Resolution</span></span>

1. <span data-ttu-id="ae1e2-158">Попробуйте использовать шаги, описанные в статье, чтобы [увеличить скорость загрузки](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span><span class="sxs-lookup"><span data-stu-id="ae1e2-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>

2. <span data-ttu-id="ae1e2-159">Если проблема не устранена, подключитесь к [PowerShell центра безопасности & соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) , а затем выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-159">If you still have issues, connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="ae1e2-160">Найдите объем данных для загрузки в параметрах SearchResults и Сеарчстатистикс.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

4. <span data-ttu-id="ae1e2-161">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-161">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

5. <span data-ttu-id="ae1e2-162">В поле Результаты найдите экспортированные данные и просмотрите все обнаруженные ошибки.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-162">In the results field, find the data that has been exported and view any errors encountered.</span></span>

6. <span data-ttu-id="ae1e2-163">Проверьте файл Trace. log, находящийся в каталоге, в который вы экспортировали содержимое для любых ошибок.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="ae1e2-164">Ошибка/Ошибка: ошибка "Внутренняя ошибка сервера (500)"</span><span class="sxs-lookup"><span data-stu-id="ae1e2-164">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="ae1e2-165">При выполнении поиска обнаружения электронных данных, если поиск заканчивается неудачей с ошибкой "Внутренняя ошибка сервера (500)", может потребоваться повторный поиск только в определенных расположениях почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Снимок экрана "Внутренняя ошибка сервера 500"](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="ae1e2-167">Решение</span><span class="sxs-lookup"><span data-stu-id="ae1e2-167">Resolution</span></span>

1. <span data-ttu-id="ae1e2-168">Разбейте Поиск на небольшие поиски и снова запустите поиск.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="ae1e2-169">Попробуйте использовать меньший диапазон дат или ограничить количество искомых расположений.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-169">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="ae1e2-170">Подключитесь к [PowerShell центра безопасности & соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) , а затем выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-170">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="ae1e2-171">Изучите выходные данные для результатов и ошибок.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-171">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="ae1e2-172">Изучите файл Trace. log.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-172">Examine the trace.log file.</span></span> <span data-ttu-id="ae1e2-173">Он находится в той же папке, в которую вы экспортировали результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-173">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="ae1e2-174">Обратитесь в службу поддержки корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-174">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="ae1e2-175">Ошибка/Ошибка: удержания не синхронизируются</span><span class="sxs-lookup"><span data-stu-id="ae1e2-175">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="ae1e2-176">Ошибка распространения синхронизации политики обнаружения электронных данных для обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="ae1e2-177">Сообщение об ошибке выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-177">The error reads:</span></span>

> <span data-ttu-id="ae1e2-178">"Resources: для развертывания политики требуется больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="ae1e2-179">Для обновления состояния развертывания может потребоваться еще 2 часа, поэтому выполните проверку в течение нескольких часов. "</span><span class="sxs-lookup"><span data-stu-id="ae1e2-179">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="ae1e2-180">Решение</span><span class="sxs-lookup"><span data-stu-id="ae1e2-180">Resolution</span></span>

1. <span data-ttu-id="ae1e2-181">Подключитесь к [PowerShell центра безопасности & соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) , а затем выполните следующую команду, чтобы сохранить регистр для обнаружения электронных данных:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-181">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="ae1e2-182">Для политики хранения выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-182">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="ae1e2-183">Проверьте значение параметра Дистрибутиондетаил на наличие ошибок, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-183">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="ae1e2-184">Ошибка: Resources: для развертывания политики требуется больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-184">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="ae1e2-185">Для обновления состояния развертывания может потребоваться еще 2 часа, поэтому выполните проверку в течение нескольких часов. "</span><span class="sxs-lookup"><span data-stu-id="ae1e2-185">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="ae1e2-186">Попробуйте выполнить параметр Ретридистрибутион для рассматриваемой политики:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-186">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="ae1e2-187">Для дел eDiscovery содержит:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-187">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="ae1e2-188">Для политик хранения:</span><span class="sxs-lookup"><span data-stu-id="ae1e2-188">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="ae1e2-189">Обратитесь в службу поддержки корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ae1e2-189">Contact Microsoft Support.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae1e2-190">См. также</span><span class="sxs-lookup"><span data-stu-id="ae1e2-190">See Also</span></span>

- [<span data-ttu-id="ae1e2-191">Советы по предотвращению ошибок расположения контента</span><span class="sxs-lookup"><span data-stu-id="ae1e2-191">Tips to avoid content location errors</span></span>](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
