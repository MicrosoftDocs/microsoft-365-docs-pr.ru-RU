---
title: Распространенные проблемы обнаружения электронных данных траублшутинг
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
description: Проанализируйте, устраните проблемы и устраните распространенные проблемы в Office 365 eDiscovery.
siblings_only: true
ms.openlocfilehash: db355067aa4e3fc41541e6414b59c92aaac1b5b3
ms.sourcegitcommit: 75c8f89049081f08852699c8d51c3a07b12165da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2019
ms.locfileid: "37207300"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="2a66c-103">Исследование, устранение неполадок и устранение распространенных проблем обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="2a66c-103">Investigate, troubleshoot and resolve common eDiscovery issues</span></span>

<span data-ttu-id="2a66c-104">В этом разделе описываются основные действия по устранению неполадок, которые можно предпринять для определения и устранения проблем, которые могут возникать во время поиска обнаружения электронных данных или в другом месте процесса обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="2a66c-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="2a66c-105">Для устранения некоторых из этих сценариев необходима помощь в службе поддержки клиентов (CSS).</span><span class="sxs-lookup"><span data-stu-id="2a66c-105">Resolving some of these scenarios requires help from Customer Support Services (CSS).</span></span> <span data-ttu-id="2a66c-106">Сведения о том, когда следует обращаться к CSS, включаются в процедуру решения.</span><span class="sxs-lookup"><span data-stu-id="2a66c-106">Information on when to contact CSS is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="2a66c-107">Неоднозначное расположение ошибки или выдача</span><span class="sxs-lookup"><span data-stu-id="2a66c-107">Error/issue ambiguous location</span></span>

<span data-ttu-id="2a66c-108">Появится сообщение об ошибке "Поиск соответствия содержит следующее недопустимое расположение `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` ", если вы попытались добавить расположение почтового ящика пользователя в поиск и в Exchange Online Protection имеются дублирующиеся или конфликтующие объекты с таким же идентификатором пользователя (EOP) каталога.</span><span class="sxs-lookup"><span data-stu-id="2a66c-108">You'll receive this error "The compliance search contains the following invalid location `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` if you tried to add user’s mailbox location to search and there are duplicate or conflicting objects with the same user id in the Exchange Online Protection (EOP) directory.</span></span>

### <a name="resolution"></a><span data-ttu-id="2a66c-109">Разрешение</span><span class="sxs-lookup"><span data-stu-id="2a66c-109">Resolution</span></span>

<span data-ttu-id="2a66c-110">Проверьте наличие дубликатов пользователей или списка рассылки с одинаковым ИДЕНТИФИКАТОРом пользователя.</span><span class="sxs-lookup"><span data-stu-id="2a66c-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="2a66c-111">Подключитесь к [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="2a66c-111">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="2a66c-112">Получите все экземпляры имени пользователя, введите:</span><span class="sxs-lookup"><span data-stu-id="2a66c-112">Retrieve all instances of the username, type:</span></span>

```powershell
Get-Recipient <username>
```

<span data-ttu-id="2a66c-113">Выходные данные для "useralias@contoso.com" могут быть</span><span class="sxs-lookup"><span data-stu-id="2a66c-113">The output for 'useralias@contoso.com' might be</span></span>

> 
> |<span data-ttu-id="2a66c-114">Имя</span><span class="sxs-lookup"><span data-stu-id="2a66c-114">Name</span></span>  |<span data-ttu-id="2a66c-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="2a66c-115">RecipientType</span></span>  |
> |---------|---------|
> |<span data-ttu-id="2a66c-116">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="2a66c-116">Alias, User</span></span>     |<span data-ttu-id="2a66c-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="2a66c-117">MailUser</span></span>         |
> |<span data-ttu-id="2a66c-118">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="2a66c-118">Alias, User</span></span>     |<span data-ttu-id="2a66c-119">Пользователь</span><span class="sxs-lookup"><span data-stu-id="2a66c-119">User</span></span>         |

3. <span data-ttu-id="2a66c-120">Если возвращается несколько пользователей, разместите и устраните конфликтующий объект.</span><span class="sxs-lookup"><span data-stu-id="2a66c-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="2a66c-121">Ошибка/Ошибка поиска не удается в определенных расположениях</span><span class="sxs-lookup"><span data-stu-id="2a66c-121">Error/issue search fails on specific locations</span></span>

<span data-ttu-id="2a66c-122">Поиск обнаружения электронных данных или контента может привести к возникновению следующей ошибки:</span><span class="sxs-lookup"><span data-stu-id="2a66c-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="2a66c-123">Поиск завершился с ошибками (#).</span><span class="sxs-lookup"><span data-stu-id="2a66c-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="2a66c-124">Вы хотите повторить поиск в расположениях с ошибками?</span><span class="sxs-lookup"><span data-stu-id="2a66c-124">Would you like to retry the search on the failed locations?</span></span>

![снимок экрана с определенным расположением для поиска со сбоем]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="2a66c-126">Разрешение</span><span class="sxs-lookup"><span data-stu-id="2a66c-126">Resolution</span></span>

<span data-ttu-id="2a66c-127">При возникновении этой ошибки рекомендуется проверить расположения, в которых произошел сбой, а затем повторно выполнить поиск только в расположениях, на которых не удалось выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="2a66c-127">If you receive this error, we recommend that you verify the locations that failed in the search  then re-run the search only on the failed locations.</span></span>

1. <span data-ttu-id="2a66c-128">Подключитесь к [PowerShell Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="2a66c-128">Connect to [Exchange Online Protection Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="2a66c-129">Тип:</span><span class="sxs-lookup"><span data-stu-id="2a66c-129">Type:</span></span>

```powershell
Get-Compliancesearch searchname|fl 
```

3. <span data-ttu-id="2a66c-130">В выходных данных PowerShell просмотрите сведения о неудачных расположениях в поле ошибки или сведения о состоянии, указанные в сообщении об ошибке, из результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="2a66c-130">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>
1. <span data-ttu-id="2a66c-131">Повторите поиск обнаружения электронных данных для неудачных расположений.</span><span class="sxs-lookup"><span data-stu-id="2a66c-131">Retry the eDiscovery search on the failed locations only.</span></span>
1. <span data-ttu-id="2a66c-132">Если вы продолжаете получать эти сообщения об ошибке, обратитесь к разделу [Retry Failed Locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for дополнительные действия по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="2a66c-132">If you continue to receive these error, see [Retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for additional troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="2a66c-133">Ошибка/файл вопроса не найден</span><span class="sxs-lookup"><span data-stu-id="2a66c-133">Error/issue file not found</span></span>

<span data-ttu-id="2a66c-134">При выполнении поиска обнаружения электронных данных, включающего SharePoint Online и один диск для размещения бизнеса, может появиться сообщение `File Not Found` об ошибке, несмотря на то, что файл находится на сайте.</span><span class="sxs-lookup"><span data-stu-id="2a66c-134">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="2a66c-135">Эта ошибка будет указана в разделе Export and Errors. CSV или пропущенные элементы. csv это может произойти, если не удается найти файл на сайте или индекс устарел.</span><span class="sxs-lookup"><span data-stu-id="2a66c-135">This error will be in the export warnings and errors.csv or skipped items.csv  This may occur if the file cannot be located on the site or the index is out of date.</span></span> <span data-ttu-id="2a66c-136">Вот текст фактической ошибки с добавленным выделением.</span><span class="sxs-lookup"><span data-stu-id="2a66c-136">Here's the text of an actual error, with emphasis added.</span></span>
  
> <span data-ttu-id="2a66c-137">28.06.2019 10:02:19_FailedToExportItem_Failed для скачивания контента.</span><span class="sxs-lookup"><span data-stu-id="2a66c-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="2a66c-138">Дополнительные диагностические сведения: Microsoft. Office. соответствие. EDiscovery. Експортворкер. Exceptions. Контентдовнлоадтемпорарифаилуре: не удалось скачать из контента 6ea52149 — 91cd – 4965 – b5bb – 82ca6a3ec9be типа Document.</span><span class="sxs-lookup"><span data-stu-id="2a66c-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="2a66c-139">Идентификатор корреляции: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="2a66c-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="2a66c-140">Серверерроркоде: – 2147024894---> Microsoft. SharePoint. Client. Серверексцептион: ***файл не найден***.</span><span class="sxs-lookup"><span data-stu-id="2a66c-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="2a66c-141">в Microsoft. SharePoint. Client. Клиентрекуест. Процессреспонсестреам (Stream Респонсестреам) на сайте Microsoft. SharePoint. Client. Клиентрекуест. Процессреспонсе ()---конец трассировки стека внутренних исключений---</span><span class="sxs-lookup"><span data-stu-id="2a66c-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="2a66c-142">Разрешение</span><span class="sxs-lookup"><span data-stu-id="2a66c-142">Resolution</span></span>

1. <span data-ttu-id="2a66c-143">Проверьте расположение, указанное в поиске, чтобы убедиться в том, что расположение файла указано правильно и добавляется в расположений для поиска.</span><span class="sxs-lookup"><span data-stu-id="2a66c-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>
2. <span data-ttu-id="2a66c-144">Используйте процедуры при [ручном запросе на обход контента и повторной индексации сайта, библиотеки или списка](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) для повторного индексирования сайта.</span><span class="sxs-lookup"><span data-stu-id="2a66c-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) to re-index the site.</span></span>

## <a name="errorissue-search-fails-recipient-not-found"></a><span data-ttu-id="2a66c-145">Ошибка/Ошибка поиска не удалось найти получателя</span><span class="sxs-lookup"><span data-stu-id="2a66c-145">Error/issue search fails recipient not found</span></span>

<span data-ttu-id="2a66c-146">не удается выполнить поиск обнаружения `recipient not found`электронных данных с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="2a66c-146">eDiscovery search fails with error `recipient not found`.</span></span> <span data-ttu-id="2a66c-147">Эта ошибка может возникнуть, если объект пользователя не удается найти в Exchange Online Protection (EOP), так как объект не синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="2a66c-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="2a66c-148">Разрешение</span><span class="sxs-lookup"><span data-stu-id="2a66c-148">Resolution</span></span>

1. <span data-ttu-id="2a66c-149">Подключитесь к [PowerShell Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="2a66c-149">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="2a66c-150">Проверьте, синхронизирован ли объект пользователя с типом защиты Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="2a66c-150">Check to see if the user object is synced to Exchange Online Protection type:</span></span>

```powershell
Get-Recipient userId|fl
```

3. <span data-ttu-id="2a66c-151">Для ответа пользователя должен быть указан объект MailUser.</span><span class="sxs-lookup"><span data-stu-id="2a66c-151">There should be a mailuser object for the user question.</span></span> <span data-ttu-id="2a66c-152">Если ничего не возвращается, изучите объект User.</span><span class="sxs-lookup"><span data-stu-id="2a66c-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="2a66c-153">Если не удается синхронизировать объект, обратитесь в CSS.</span><span class="sxs-lookup"><span data-stu-id="2a66c-153">Contact CSS if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="2a66c-154">Ошибка/Ошибка при экспорте результатов поиска выполняется медленно</span><span class="sxs-lookup"><span data-stu-id="2a66c-154">Error/issue exporting search results is slow</span></span>

<span data-ttu-id="2a66c-155">При экспорте результатов поиска из обнаружения электронных данных или поиска контента в центре безопасности и соответствия требованиям Загрузка занимает больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="2a66c-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="2a66c-156">Вы можете проверить количество загружаемых данных и, возможно, увеличить скорость экспорта.</span><span class="sxs-lookup"><span data-stu-id="2a66c-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="2a66c-157">Разрешение</span><span class="sxs-lookup"><span data-stu-id="2a66c-157">Resolution</span></span>

1.  <span data-ttu-id="2a66c-158">Попробуйте использовать шаги, описанные в статье, чтобы [увеличить скорость загрузки](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span><span class="sxs-lookup"><span data-stu-id="2a66c-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>
2.  <span data-ttu-id="2a66c-159">Если у вас по-прежнему возникают проблемы, подключитесь к [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) и введите:</span><span class="sxs-lookup"><span data-stu-id="2a66c-159">If you still have issues, connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname\fl
```

4. <span data-ttu-id="2a66c-160">Найдите объем данных для загрузки в параметрах SearchResults и Сеарчстатистикс.</span><span class="sxs-lookup"><span data-stu-id="2a66c-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>
5. <span data-ttu-id="2a66c-161">Тип:</span><span class="sxs-lookup"><span data-stu-id="2a66c-161">Type:</span></span>

```powershell
Get-ComplianceSearchAction |fl
```

6. <span data-ttu-id="2a66c-162">В поле Результаты найдите экспортированные данные и просмотрите все обнаруженные ошибки.</span><span class="sxs-lookup"><span data-stu-id="2a66c-162">In the results field find the data that has been exported and view any errors encountered.</span></span>
7. <span data-ttu-id="2a66c-163">Проверьте файл Trace. log, находящийся в каталоге, в который вы экспортировали содержимое для любых ошибок.</span><span class="sxs-lookup"><span data-stu-id="2a66c-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="2a66c-164">Ошибка или возникла ошибка "Внутренняя ошибка сервера (500)"</span><span class="sxs-lookup"><span data-stu-id="2a66c-164">Error/issue "Internal server error (500) occurred"</span></span>

<span data-ttu-id="2a66c-165">При выполнении поиска обнаружения электронных данных, если поиск заканчивается неудачей с ошибкой "Внутренняя ошибка сервера (500)", возможно, потребуется повторно выполнить поиск только в определенных расположениях почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="2a66c-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need re-run the search only on specific mailbox locations.</span></span>

![снимок экрана "Внутренняя ошибка сервера 500"](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="2a66c-167">Разрешение</span><span class="sxs-lookup"><span data-stu-id="2a66c-167">Resolution</span></span>

1. <span data-ttu-id="2a66c-168">Разбейте Поиск на небольшие поиски и снова запустите поиск.</span><span class="sxs-lookup"><span data-stu-id="2a66c-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="2a66c-169">Попробуйте использовать меньший диапазон дат или ограничить количество искомых расположений.</span><span class="sxs-lookup"><span data-stu-id="2a66c-169">Try using a smaller date range or limit the number of locations being searched.</span></span>
2. <span data-ttu-id="2a66c-170">Подключитесь к [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) и введите:</span><span class="sxs-lookup"><span data-stu-id="2a66c-170">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname |fl
```

3. <span data-ttu-id="2a66c-171">Изучите выходные данные для результатов и ошибок.</span><span class="sxs-lookup"><span data-stu-id="2a66c-171">Examine the output for results and errors.</span></span>
3. <span data-ttu-id="2a66c-172">Изучите файл Trace. log.</span><span class="sxs-lookup"><span data-stu-id="2a66c-172">Examine the trace.log file.</span></span> <span data-ttu-id="2a66c-173">Он будет находиться в той же папке, куда вы отправили экспорт.</span><span class="sxs-lookup"><span data-stu-id="2a66c-173">It will be in the same folder that you sent the export to.</span></span>
4. <span data-ttu-id="2a66c-174">Обратитесь в службу поддержки CSS.</span><span class="sxs-lookup"><span data-stu-id="2a66c-174">Contact Support CSS.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="2a66c-175">Ошибка/ошибка удержания не синхронизируются</span><span class="sxs-lookup"><span data-stu-id="2a66c-175">Error/issue holds don't sync</span></span>

<span data-ttu-id="2a66c-176">Ошибка распространения синхронизации политики обнаружения электронных данных для обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="2a66c-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="2a66c-177">Сообщение об ошибке выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2a66c-177">The error reads:</span></span>

> <span data-ttu-id="2a66c-178">"Resources: для развертывания политики требуется больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="2a66c-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="2a66c-179">Обновление последнего состояния развертывания может занять два часа, поэтому выполните проверку в течение нескольких часов. "</span><span class="sxs-lookup"><span data-stu-id="2a66c-179">It might take an additional two hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="2a66c-180">Разрешение</span><span class="sxs-lookup"><span data-stu-id="2a66c-180">Resolution</span></span>

1.  <span data-ttu-id="2a66c-181">Подключитесь к [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) и введите:</span><span class="sxs-lookup"><span data-stu-id="2a66c-181">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. <span data-ttu-id="2a66c-182">Проверьте значение параметра Дистрибутиондетаил на наличие ошибок, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="2a66c-182">Examine the value in the Distributiondetail parameter for errors like the following:</span></span>

> <span data-ttu-id="2a66c-183">Если ошибка существует, создайте укрупнение для PG, чтобы принудительно выполнить повторную синхронизацию вручную для политики.</span><span class="sxs-lookup"><span data-stu-id="2a66c-183">If error exists, create escalation to PG to force a manual re-sync on the Policy.</span></span>

3. <span data-ttu-id="2a66c-184">Обратитесь в службу поддержки CSS.</span><span class="sxs-lookup"><span data-stu-id="2a66c-184">Contact CSS.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a66c-185">См. также</span><span class="sxs-lookup"><span data-stu-id="2a66c-185">See Also</span></span>
- [<span data-ttu-id="2a66c-186">Советы по предотвращению ошибок расположения контента</span><span class="sxs-lookup"><span data-stu-id="2a66c-186">Tips to avoid content location errors</span></span>](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)