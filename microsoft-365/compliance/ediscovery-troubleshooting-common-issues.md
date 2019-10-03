---
title: Устранение распространенных проблем с обнаружением электронных данных
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Проанализируйте, устраните и устраните распространенные проблемы, связанные с обнаружением электронных данных в Office 365.
siblings_only: true
ms.openlocfilehash: 0d411976ecf6adba9df1f75eb8a45409647b3e1a
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378641"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="3696b-103">Исследование, устранение неполадок и устранение распространенных проблем обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="3696b-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="3696b-104">В этом разделе описываются основные действия по устранению неполадок, которые можно предпринять для определения и устранения проблем, которые могут возникать во время поиска обнаружения электронных данных или в другом месте процесса обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="3696b-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="3696b-105">Для устранения некоторых из этих сценариев необходима помощь в службе поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3696b-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="3696b-106">Сведения о том, когда следует обращаться в службу поддержки Майкрософт, приведены в разделе действия по разрешению.</span><span class="sxs-lookup"><span data-stu-id="3696b-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="3696b-107">Ошибка/Ошибка: неоднозначное расположение</span><span class="sxs-lookup"><span data-stu-id="3696b-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="3696b-108">Если вы попытаетесь добавить расположение почтового ящика пользователя в поиск, и в каталоге Exchange Online Protection (EOP) имеются дублирующиеся или конфликтующие объекты с тем же userID, появится следующее сообщение `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`об ошибке:.</span><span class="sxs-lookup"><span data-stu-id="3696b-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you will receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span> 

### <a name="resolution"></a><span data-ttu-id="3696b-109">Разрешение</span><span class="sxs-lookup"><span data-stu-id="3696b-109">Resolution</span></span>

<span data-ttu-id="3696b-110">Проверьте наличие дубликатов пользователей или списка рассылки с одинаковым ИДЕНТИФИКАТОРом пользователя.</span><span class="sxs-lookup"><span data-stu-id="3696b-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="3696b-111">Подключение к [PowerShell центра безопасности & центра соответствия требованиям Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="3696b-111">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="3696b-112">Получите все экземпляры имени пользователя, введите:</span><span class="sxs-lookup"><span data-stu-id="3696b-112">Retrieve all instances of the username, type:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

<span data-ttu-id="3696b-113">Выходные данные для "useralias@contoso.com" будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3696b-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

> 
> |<span data-ttu-id="3696b-114">Имя</span><span class="sxs-lookup"><span data-stu-id="3696b-114">Name</span></span>  |<span data-ttu-id="3696b-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="3696b-115">RecipientType</span></span>  |
> |---------|---------|
> |<span data-ttu-id="3696b-116">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="3696b-116">Alias, User</span></span>     |<span data-ttu-id="3696b-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="3696b-117">MailUser</span></span>         |
> |<span data-ttu-id="3696b-118">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="3696b-118">Alias, User</span></span>     |<span data-ttu-id="3696b-119">Пользователь</span><span class="sxs-lookup"><span data-stu-id="3696b-119">User</span></span>         |

3. <span data-ttu-id="3696b-120">Если возвращается несколько пользователей, разместите и устраните конфликтующий объект.</span><span class="sxs-lookup"><span data-stu-id="3696b-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="3696b-121">Ошибка/Ошибка: сбой поиска в определенных расположениях</span><span class="sxs-lookup"><span data-stu-id="3696b-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="3696b-122">Поиск обнаружения электронных данных или контента может привести к возникновению следующей ошибки:</span><span class="sxs-lookup"><span data-stu-id="3696b-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="3696b-123">Поиск завершился с ошибками (#).</span><span class="sxs-lookup"><span data-stu-id="3696b-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="3696b-124">Вы хотите повторить поиск в расположениях с ошибками?</span><span class="sxs-lookup"><span data-stu-id="3696b-124">Would you like to retry the search on the failed locations?</span></span>

![Снимок экрана с определенным расположением для поиска со сбоем]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="3696b-126">Разрешение</span><span class="sxs-lookup"><span data-stu-id="3696b-126">Resolution</span></span>

<span data-ttu-id="3696b-127">При возникновении этой ошибки рекомендуется проверить расположения, в которых произошел сбой, а затем повторить поиск только в расположениях, на которых не удалось выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="3696b-127">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="3696b-128">Подключитесь к [оболочке PowerShell центра & безопасности Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3696b-128">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then enter the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL 
    ```

2. <span data-ttu-id="3696b-129">В выходных данных PowerShell просмотрите сведения о неудачных расположениях в поле ошибки или сведения о состоянии, указанные в сообщении об ошибке, из результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="3696b-129">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="3696b-130">Повторите поиск обнаружения электронных данных для неудачных расположений.</span><span class="sxs-lookup"><span data-stu-id="3696b-130">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="3696b-131">Если вы продолжаете получать эти ошибки, обратитесь к разделу [Retry Fail Failed Locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for more Errors.</span><span class="sxs-lookup"><span data-stu-id="3696b-131">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="3696b-132">Ошибка/Ошибка: файл не найден</span><span class="sxs-lookup"><span data-stu-id="3696b-132">Error/issue: File not found</span></span>

<span data-ttu-id="3696b-133">При выполнении поиска обнаружения электронных данных, включающего SharePoint Online и один диск для размещения бизнеса, может появиться сообщение `File Not Found` об ошибке, несмотря на то, что файл находится на сайте.</span><span class="sxs-lookup"><span data-stu-id="3696b-133">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="3696b-134">Эта ошибка будет находиться в разделе Экспорт предупреждений и ошибок. CSV или пропущенных элементов. csv.</span><span class="sxs-lookup"><span data-stu-id="3696b-134">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="3696b-135">Это может произойти, если файл не удается найти на сайте или индекс устарел.</span><span class="sxs-lookup"><span data-stu-id="3696b-135">This may occur if the file cannot be located on the site or the index is out of date.</span></span> <span data-ttu-id="3696b-136">Вот текст фактической ошибки с добавленным выделением.</span><span class="sxs-lookup"><span data-stu-id="3696b-136">Here's the text of an actual error, with emphasis added.</span></span>
  
> <span data-ttu-id="3696b-137">28.06.2019 10:02:19_FailedToExportItem_Failed для скачивания контента.</span><span class="sxs-lookup"><span data-stu-id="3696b-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="3696b-138">Дополнительные диагностические сведения: Microsoft. Office. соответствие. EDiscovery. Експортворкер. Exceptions. Контентдовнлоадтемпорарифаилуре: не удалось скачать из контента 6ea52149 — 91cd – 4965 – b5bb – 82ca6a3ec9be типа Document.</span><span class="sxs-lookup"><span data-stu-id="3696b-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="3696b-139">Идентификатор корреляции: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="3696b-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="3696b-140">Серверерроркоде: – 2147024894---> Microsoft. SharePoint. Client. Серверексцептион: ***файл не найден***.</span><span class="sxs-lookup"><span data-stu-id="3696b-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="3696b-141">в Microsoft. SharePoint. Client. Клиентрекуест. Процессреспонсестреам (Stream Респонсестреам) на сайте Microsoft. SharePoint. Client. Клиентрекуест. Процессреспонсе ()---конец трассировки стека внутренних исключений---</span><span class="sxs-lookup"><span data-stu-id="3696b-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="3696b-142">Разрешение</span><span class="sxs-lookup"><span data-stu-id="3696b-142">Resolution</span></span>

1. <span data-ttu-id="3696b-143">Проверьте расположение, указанное в поиске, чтобы убедиться в том, что расположение файла указано правильно и добавляется в расположений для поиска.</span><span class="sxs-lookup"><span data-stu-id="3696b-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="3696b-144">Используйте процедуры при [ручном запросе на обход контента и повторной индексации сайта, библиотеки или списка](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) для повторного индексирования сайта.</span><span class="sxs-lookup"><span data-stu-id="3696b-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) to re-index the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="3696b-145">Ошибка/Ошибка: не удается выполнить поиск, так как получатель не найден</span><span class="sxs-lookup"><span data-stu-id="3696b-145">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="3696b-146">Сбой поиска обнаружения электронных данных с ошибкой `recipient not found`.</span><span class="sxs-lookup"><span data-stu-id="3696b-146">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="3696b-147">Эта ошибка может возникнуть, если объект пользователя не удается найти в Exchange Online Protection (EOP), так как объект не синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="3696b-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="3696b-148">Разрешение</span><span class="sxs-lookup"><span data-stu-id="3696b-148">Resolution</span></span>

1. <span data-ttu-id="3696b-149">Подключитесь к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3696b-149">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3696b-150">Проверьте, синхронизирован ли объект пользователя с типом защиты Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="3696b-150">Check to see if the user object is synced to Exchange Online Protection type:</span></span>

    ```powershell
    Get-Recipient <userId> | FL
    ```

3. <span data-ttu-id="3696b-151">Для ответа пользователя должен быть объект пользователя почты.</span><span class="sxs-lookup"><span data-stu-id="3696b-151">There should be a mail user object for the user question.</span></span> <span data-ttu-id="3696b-152">Если ничего не возвращается, изучите объект User.</span><span class="sxs-lookup"><span data-stu-id="3696b-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="3696b-153">Если не удается синхронизировать объект, обратитесь в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3696b-153">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="3696b-154">Ошибка/Ошибка: немедленный экспорт результатов поиска</span><span class="sxs-lookup"><span data-stu-id="3696b-154">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="3696b-155">При экспорте результатов поиска из обнаружения электронных данных или поиска контента в центре безопасности и соответствия требованиям Загрузка занимает больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="3696b-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="3696b-156">Вы можете проверить количество загружаемых данных и, возможно, увеличить скорость экспорта.</span><span class="sxs-lookup"><span data-stu-id="3696b-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="3696b-157">Разрешение</span><span class="sxs-lookup"><span data-stu-id="3696b-157">Resolution</span></span>

1.  <span data-ttu-id="3696b-158">Попробуйте использовать шаги, описанные в статье, чтобы [увеличить скорость загрузки](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span><span class="sxs-lookup"><span data-stu-id="3696b-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>

2.  <span data-ttu-id="3696b-159">Если проблема не устранена, подключитесь к [PowerShell в центре безопасности Office 365 &](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3696b-159">If you still have issues, connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then enter the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

4. <span data-ttu-id="3696b-160">Найдите объем данных для загрузки в параметрах SearchResults и Сеарчстатистикс.</span><span class="sxs-lookup"><span data-stu-id="3696b-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

5. <span data-ttu-id="3696b-161">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3696b-161">Enter the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

6. <span data-ttu-id="3696b-162">В поле Результаты найдите экспортированные данные и просмотрите все обнаруженные ошибки.</span><span class="sxs-lookup"><span data-stu-id="3696b-162">In the results field, find the data that has been exported and view any errors encountered.</span></span>

7. <span data-ttu-id="3696b-163">Проверьте файл Trace. log, находящийся в каталоге, в который вы экспортировали содержимое для любых ошибок.</span><span class="sxs-lookup"><span data-stu-id="3696b-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="3696b-164">Ошибка/Ошибка: ошибка "Внутренняя ошибка сервера (500)"</span><span class="sxs-lookup"><span data-stu-id="3696b-164">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="3696b-165">При выполнении поиска обнаружения электронных данных, если поиск заканчивается неудачей с ошибкой "Внутренняя ошибка сервера (500)", может потребоваться повторный поиск только в определенных расположениях почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="3696b-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Снимок экрана "Внутренняя ошибка сервера 500"](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="3696b-167">Разрешение</span><span class="sxs-lookup"><span data-stu-id="3696b-167">Resolution</span></span>

1. <span data-ttu-id="3696b-168">Разбейте Поиск на небольшие поиски и снова запустите поиск.</span><span class="sxs-lookup"><span data-stu-id="3696b-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="3696b-169">Попробуйте использовать меньший диапазон дат или ограничить количество искомых расположений.</span><span class="sxs-lookup"><span data-stu-id="3696b-169">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="3696b-170">Подключитесь к [оболочке PowerShell центра & безопасности Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3696b-170">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then enter the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

3. <span data-ttu-id="3696b-171">Изучите выходные данные для результатов и ошибок.</span><span class="sxs-lookup"><span data-stu-id="3696b-171">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="3696b-172">Изучите файл Trace. log.</span><span class="sxs-lookup"><span data-stu-id="3696b-172">Examine the trace.log file.</span></span> <span data-ttu-id="3696b-173">Он будет находиться в той же папке, куда вы отправили экспорт.</span><span class="sxs-lookup"><span data-stu-id="3696b-173">It will be in the same folder that you sent the export to.</span></span>

5. <span data-ttu-id="3696b-174">Обратитесь в службу поддержки корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3696b-174">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="3696b-175">Ошибка/Ошибка: удержания не синхронизируются</span><span class="sxs-lookup"><span data-stu-id="3696b-175">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="3696b-176">Ошибка распространения синхронизации политики обнаружения электронных данных для обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="3696b-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="3696b-177">Сообщение об ошибке выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3696b-177">The error reads:</span></span>

> <span data-ttu-id="3696b-178">"Resources: для развертывания политики требуется больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="3696b-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="3696b-179">Обновление последнего состояния развертывания может занять два часа, поэтому выполните проверку в течение нескольких часов. "</span><span class="sxs-lookup"><span data-stu-id="3696b-179">It might take an additional two hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="3696b-180">Разрешение</span><span class="sxs-lookup"><span data-stu-id="3696b-180">Resolution</span></span>

1.  <span data-ttu-id="3696b-181">Подключитесь к [оболочке PowerShell центра & безопасности Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3696b-181">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then enter the following command:</span></span>

    ```powershell
    Get-RetentionCompliancePolicy  <policyname> - DistributionDetail | FL
    ```

2. <span data-ttu-id="3696b-182">Проверьте значение параметра Дистрибутиондетаил на наличие ошибок, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="3696b-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="3696b-183">Если ошибка существует, создайте укрупнение для PG, чтобы принудительно выполнить повторную синхронизацию вручную для политики.</span><span class="sxs-lookup"><span data-stu-id="3696b-183">If error exists, create escalation to PG to force a manual re-sync on the Policy.</span></span>

3. <span data-ttu-id="3696b-184">Обратитесь в службу поддержки корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3696b-184">Contact Microsoft Support.</span></span>

## <a name="see-also"></a><span data-ttu-id="3696b-185">См. также</span><span class="sxs-lookup"><span data-stu-id="3696b-185">See Also</span></span>

- [<span data-ttu-id="3696b-186">Советы по предотвращению ошибок расположения контента</span><span class="sxs-lookup"><span data-stu-id="3696b-186">Tips to avoid content location errors</span></span>](retry-failed-content-search.md#tips-to-avoid-content-location-errors)