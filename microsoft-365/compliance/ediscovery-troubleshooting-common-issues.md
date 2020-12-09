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
ms.openlocfilehash: 4f1bad23705729c15976959a3902501f05da7600
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602040"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="f5df9-103">Исследование, устранение неполадок и устранение распространенных проблем обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="f5df9-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="f5df9-104">В этом разделе описываются основные действия по устранению неполадок, которые можно предпринять для определения и устранения проблем, которые могут возникать во время поиска обнаружения электронных данных или в другом месте процесса обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="f5df9-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="f5df9-105">Для устранения некоторых из этих сценариев необходима помощь в службе поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f5df9-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="f5df9-106">Сведения о том, когда следует обращаться в службу поддержки Майкрософт, приведены в разделе действия по разрешению.</span><span class="sxs-lookup"><span data-stu-id="f5df9-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="f5df9-107">Ошибка/Ошибка: неоднозначное расположение</span><span class="sxs-lookup"><span data-stu-id="f5df9-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="f5df9-108">Если попытаться добавить в поиск расположение почтового ящика пользователя, а в каталоге Exchange Online Protection (EOP) имеются повторяющиеся или конфликтующие объекты с тем же userID, возникает следующая ошибка: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="f5df9-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="f5df9-109">Решение</span><span class="sxs-lookup"><span data-stu-id="f5df9-109">Resolution</span></span>

<span data-ttu-id="f5df9-110">Проверьте наличие дубликатов пользователей или списка рассылки с одинаковым ИДЕНТИФИКАТОРом пользователя.</span><span class="sxs-lookup"><span data-stu-id="f5df9-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="f5df9-111">Подключитесь к [PowerShell центра безопасности & соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="f5df9-111">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="f5df9-112">Выполните следующую команду, чтобы получить все экземпляры имени пользователя:</span><span class="sxs-lookup"><span data-stu-id="f5df9-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="f5df9-113">Выходные данные для "useralias@contoso.com" будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f5df9-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="f5df9-114">Имя</span><span class="sxs-lookup"><span data-stu-id="f5df9-114">Name</span></span>|<span data-ttu-id="f5df9-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="f5df9-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="f5df9-116">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="f5df9-116">Alias, User</span></span>|<span data-ttu-id="f5df9-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="f5df9-117">MailUser</span></span>|
   > |<span data-ttu-id="f5df9-118">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="f5df9-118">Alias, User</span></span>|<span data-ttu-id="f5df9-119">User</span><span class="sxs-lookup"><span data-stu-id="f5df9-119">User</span></span>|

3. <span data-ttu-id="f5df9-120">Если возвращается несколько пользователей, разместите и устраните конфликтующий объект.</span><span class="sxs-lookup"><span data-stu-id="f5df9-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="f5df9-121">Ошибка/Ошибка: сбой поиска в определенных расположениях</span><span class="sxs-lookup"><span data-stu-id="f5df9-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="f5df9-122">Поиск обнаружения электронных данных или контента может привести к возникновению следующей ошибки: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="f5df9-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Снимок экрана с расположением для поиска со сбоем](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="f5df9-124">Решение</span><span class="sxs-lookup"><span data-stu-id="f5df9-124">Resolution</span></span>

<span data-ttu-id="f5df9-125">При возникновении этой ошибки рекомендуется проверить расположения, в которых произошел сбой, а затем повторить поиск только в расположениях, на которых не удалось выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="f5df9-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="f5df9-126">Подключитесь к [PowerShell центра безопасности & соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) , а затем выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f5df9-126">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="f5df9-127">В выходных данных PowerShell просмотрите сведения о неудачных расположениях в поле ошибки или сведения о состоянии, указанные в сообщении об ошибке, из результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="f5df9-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="f5df9-128">Повторите поиск обнаружения электронных данных для неудачных расположений.</span><span class="sxs-lookup"><span data-stu-id="f5df9-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="f5df9-129">Если вы продолжаете получать эти ошибки, обратитесь к разделу [Retry Fail Failed Locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more Errors.</span><span class="sxs-lookup"><span data-stu-id="f5df9-129">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="f5df9-130">Ошибка/Ошибка: файл не найден</span><span class="sxs-lookup"><span data-stu-id="f5df9-130">Error/issue: File not found</span></span>

<span data-ttu-id="f5df9-131">При выполнении поиска обнаружения электронных данных, включающего SharePoint Online и один диск для размещения бизнеса, может появиться сообщение об ошибке, несмотря на то, что `File Not Found` файл находится на сайте.</span><span class="sxs-lookup"><span data-stu-id="f5df9-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="f5df9-132">Эта ошибка будет присутствовать в предупреждениях экспорта, errors.csv или пропущенных items.csv.</span><span class="sxs-lookup"><span data-stu-id="f5df9-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="f5df9-133">Это может произойти, если не удается найти файл на сайте или индекс устарел.</span><span class="sxs-lookup"><span data-stu-id="f5df9-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="f5df9-134">Вот текст фактической ошибки (с добавленным выделением).</span><span class="sxs-lookup"><span data-stu-id="f5df9-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="f5df9-135">28.06.2019 10:02:19_FailedToExportItem_Failed для скачивания контента.</span><span class="sxs-lookup"><span data-stu-id="f5df9-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="f5df9-136">Дополнительные диагностические сведения: Microsoft. Office. соответствие. EDiscovery. Експортворкер. Exceptions. Контентдовнлоадтемпорарифаилуре: не удалось скачать из контента 6ea52149 — 91cd – 4965 – b5bb – 82ca6a3ec9be типа Document.</span><span class="sxs-lookup"><span data-stu-id="f5df9-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="f5df9-137">Идентификатор корреляции: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="f5df9-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="f5df9-138">Серверерроркоде: – 2147024894---> Microsoft. SharePoint. Client. Серверексцептион: ***файл не найден***.</span><span class="sxs-lookup"><span data-stu-id="f5df9-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="f5df9-139">в Microsoft. SharePoint. Client. Клиентрекуест. Процессреспонсестреам (Stream Респонсестреам) на сайте Microsoft. SharePoint. Client. Клиентрекуест. Процессреспонсе ()---конец трассировки стека внутренних исключений---</span><span class="sxs-lookup"><span data-stu-id="f5df9-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="f5df9-140">Решение</span><span class="sxs-lookup"><span data-stu-id="f5df9-140">Resolution</span></span>

1. <span data-ttu-id="f5df9-141">Проверьте расположение, указанное в поиске, чтобы убедиться в том, что расположение файла указано правильно и добавляется в расположений для поиска.</span><span class="sxs-lookup"><span data-stu-id="f5df9-141">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="f5df9-142">Используйте процедуры при [ручном запросе на обход контента и повторной индексации сайта, библиотеки или списка](https://docs.microsoft.com/sharepoint/crawl-site-content) , чтобы переиндексировать сайт.</span><span class="sxs-lookup"><span data-stu-id="f5df9-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](https://docs.microsoft.com/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="f5df9-143">Ошибка/Ошибка: не удается выполнить поиск, так как получатель не найден</span><span class="sxs-lookup"><span data-stu-id="f5df9-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="f5df9-144">Сбой поиска обнаружения электронных данных с ошибкой `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="f5df9-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="f5df9-145">Эта ошибка может возникнуть, если объект пользователя не удается найти в Exchange Online Protection (EOP), так как объект не синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="f5df9-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="f5df9-146">Решение</span><span class="sxs-lookup"><span data-stu-id="f5df9-146">Resolution</span></span>

1. <span data-ttu-id="f5df9-147">Подключитесь к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f5df9-147">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f5df9-148">Выполните следующую команду, чтобы проверить, синхронизирован ли пользователь с Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="f5df9-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="f5df9-149">Для ответа пользователя должен быть объект пользователя почты.</span><span class="sxs-lookup"><span data-stu-id="f5df9-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="f5df9-150">Если ничего не возвращается, изучите объект User.</span><span class="sxs-lookup"><span data-stu-id="f5df9-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="f5df9-151">Если не удается синхронизировать объект, обратитесь в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f5df9-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="f5df9-152">Ошибка/Ошибка: немедленный экспорт результатов поиска</span><span class="sxs-lookup"><span data-stu-id="f5df9-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="f5df9-153">При экспорте результатов поиска из обнаружения электронных данных или поиска контента в центре безопасности и соответствия требованиям Загрузка занимает больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="f5df9-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="f5df9-154">Вы можете проверить количество загружаемых данных и, возможно, увеличить скорость экспорта.</span><span class="sxs-lookup"><span data-stu-id="f5df9-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="f5df9-155">Решение</span><span class="sxs-lookup"><span data-stu-id="f5df9-155">Resolution</span></span>

1. <span data-ttu-id="f5df9-156">Подключитесь к [PowerShell центра безопасности & соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) , а затем выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f5df9-156">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="f5df9-157">Найдите объем данных для загрузки в параметрах SearchResults и Сеарчстатистикс.</span><span class="sxs-lookup"><span data-stu-id="f5df9-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="f5df9-158">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f5df9-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="f5df9-159">В поле Результаты найдите экспортированные данные и просмотрите все обнаруженные ошибки.</span><span class="sxs-lookup"><span data-stu-id="f5df9-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="f5df9-160">Проверьте файл Trace. log, находящийся в каталоге, в который вы экспортировали содержимое для любых ошибок.</span><span class="sxs-lookup"><span data-stu-id="f5df9-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="f5df9-161">Если у вас по-прежнему возникают проблемы, рассмотрите возможность разделения результатов поиска, возвращающих большой набор результатов, на небольшие поисковые запросы.</span><span class="sxs-lookup"><span data-stu-id="f5df9-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="f5df9-162">Например, вы можете использовать диапазоны дат в поисковых запросах, чтобы получить уменьшенный набор результатов, который можно скачать быстрее.</span><span class="sxs-lookup"><span data-stu-id="f5df9-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="f5df9-163">Ошибка/Ошибка: ошибка "Внутренняя ошибка сервера (500)"</span><span class="sxs-lookup"><span data-stu-id="f5df9-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="f5df9-164">При выполнении поиска обнаружения электронных данных, если поиск заканчивается неудачей с ошибкой "Внутренняя ошибка сервера (500)", может потребоваться повторный поиск только в определенных расположениях почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="f5df9-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Снимок экрана "Внутренняя ошибка сервера 500"](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="f5df9-166">Решение</span><span class="sxs-lookup"><span data-stu-id="f5df9-166">Resolution</span></span>

1. <span data-ttu-id="f5df9-167">Разбейте Поиск на небольшие поиски и снова запустите поиск.</span><span class="sxs-lookup"><span data-stu-id="f5df9-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="f5df9-168">Попробуйте использовать меньший диапазон дат или ограничить количество искомых расположений.</span><span class="sxs-lookup"><span data-stu-id="f5df9-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="f5df9-169">Подключитесь к [PowerShell центра безопасности & соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) , а затем выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f5df9-169">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="f5df9-170">Изучите выходные данные для результатов и ошибок.</span><span class="sxs-lookup"><span data-stu-id="f5df9-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="f5df9-171">Изучите файл Trace. log.</span><span class="sxs-lookup"><span data-stu-id="f5df9-171">Examine the trace.log file.</span></span> <span data-ttu-id="f5df9-172">Он находится в той же папке, в которую вы экспортировали результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="f5df9-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="f5df9-173">Обратитесь в службу поддержки корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f5df9-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="f5df9-174">Ошибка/Ошибка: удержания не синхронизируются</span><span class="sxs-lookup"><span data-stu-id="f5df9-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="f5df9-175">Ошибка распространения синхронизации политики обнаружения электронных данных для обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="f5df9-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="f5df9-176">Сообщение об ошибке выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f5df9-176">The error reads:</span></span>

> <span data-ttu-id="f5df9-177">"Resources: для развертывания политики требуется больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="f5df9-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="f5df9-178">Для обновления состояния развертывания может потребоваться еще 2 часа, поэтому выполните проверку в течение нескольких часов. "</span><span class="sxs-lookup"><span data-stu-id="f5df9-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="f5df9-179">Решение</span><span class="sxs-lookup"><span data-stu-id="f5df9-179">Resolution</span></span>

1. <span data-ttu-id="f5df9-180">Подключитесь к [PowerShell центра безопасности & соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) , а затем выполните следующую команду, чтобы сохранить регистр для обнаружения электронных данных:</span><span class="sxs-lookup"><span data-stu-id="f5df9-180">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="f5df9-181">Для политики хранения выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f5df9-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="f5df9-182">Проверьте значение параметра Дистрибутиондетаил на наличие ошибок, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f5df9-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="f5df9-183">Ошибка: Resources: для развертывания политики требуется больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="f5df9-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="f5df9-184">Для обновления состояния развертывания может потребоваться еще 2 часа, поэтому выполните проверку в течение нескольких часов. "</span><span class="sxs-lookup"><span data-stu-id="f5df9-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="f5df9-185">Попробуйте выполнить параметр Ретридистрибутион для рассматриваемой политики:</span><span class="sxs-lookup"><span data-stu-id="f5df9-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="f5df9-186">Для дел eDiscovery содержит:</span><span class="sxs-lookup"><span data-stu-id="f5df9-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="f5df9-187">Для политик хранения:</span><span class="sxs-lookup"><span data-stu-id="f5df9-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="f5df9-188">Обратитесь в службу поддержки корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f5df9-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="f5df9-189">Ошибка: "условие, указанное с использованием условных заголовков HTTP, не выполнено"</span><span class="sxs-lookup"><span data-stu-id="f5df9-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="f5df9-190">При загрузке результатов поиска с помощью средства экспорта eDiscovery возможно возникновение следующей ошибки: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` это временная ошибка, которая обычно возникает в расположении хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="f5df9-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="f5df9-191">Решение</span><span class="sxs-lookup"><span data-stu-id="f5df9-191">Resolution</span></span>

<span data-ttu-id="f5df9-192">Чтобы устранить эту проблему, повторно попытайтесь [скачать результаты поиска](export-search-results.md#step-2-download-the-search-results), перезапустите средство экспорта eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f5df9-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5df9-193">См. также</span><span class="sxs-lookup"><span data-stu-id="f5df9-193">See Also</span></span>

- [<span data-ttu-id="f5df9-194">Советы по предотвращению ошибок расположения контента</span><span class="sxs-lookup"><span data-stu-id="f5df9-194">Tips to avoid content location errors</span></span>](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
