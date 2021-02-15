---
title: Устранение распространенных проблем с eDiscovery
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
description: Узнайте об основных действиях по устранению неполадок, которые можно предпринять для устранения распространенных проблем с eDiscovery в Office 365.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1fbda23b730956db42d8e7a92218fb9837868b8
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988143"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="cded7-103">Исследование, устранение и устранение распространенных проблем с eDiscovery</span><span class="sxs-lookup"><span data-stu-id="cded7-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="cded7-104">В этом разделе описывается основные действия по устранению неполадок, которые можно предпринять для выявления и устранения проблем, которые могут возникнуть во время поиска с целью eDiscovery или в другом месте процесса eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="cded7-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="cded7-105">Для разрешения некоторых из этих сценариев требуется помощь службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cded7-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="cded7-106">Сведения о том, когда обращаться в службу поддержки Майкрософт, включены в действия по разрешению.</span><span class="sxs-lookup"><span data-stu-id="cded7-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="cded7-107">Ошибка/проблема: неоднозначное расположение</span><span class="sxs-lookup"><span data-stu-id="cded7-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="cded7-108">Если попытаться добавить расположение почтового ящика пользователя для поиска, а в каталоге Exchange Online Protection (EOP) имеются дублирующиеся или конфликтующие объекты с одинаковым userID, вы получите сообщение об `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` ошибке:</span><span class="sxs-lookup"><span data-stu-id="cded7-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="cded7-109">Решение</span><span class="sxs-lookup"><span data-stu-id="cded7-109">Resolution</span></span>

<span data-ttu-id="cded7-110">Проверьте, есть ли дублирующиеся пользователи или список рассылки с одинаковым ИД пользователя.</span><span class="sxs-lookup"><span data-stu-id="cded7-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="cded7-111">Подключение к [PowerShell Центра & безопасности](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="cded7-111">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="cded7-112">Чтобы получить все экземпляры имени пользователя, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cded7-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="cded7-113">Выходные данные для "useralias@contoso.com" будут похожи на следующие:</span><span class="sxs-lookup"><span data-stu-id="cded7-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="cded7-114">Имя</span><span class="sxs-lookup"><span data-stu-id="cded7-114">Name</span></span>|<span data-ttu-id="cded7-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="cded7-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="cded7-116">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="cded7-116">Alias, User</span></span>|<span data-ttu-id="cded7-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="cded7-117">MailUser</span></span>|
   > |<span data-ttu-id="cded7-118">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="cded7-118">Alias, User</span></span>|<span data-ttu-id="cded7-119">Пользователь</span><span class="sxs-lookup"><span data-stu-id="cded7-119">User</span></span>|

3. <span data-ttu-id="cded7-120">Если возвращается несколько пользователей, найдите и исправьте конфликтующий объект.</span><span class="sxs-lookup"><span data-stu-id="cded7-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="cded7-121">Ошибка или проблема: поиск не удается в определенных расположениях</span><span class="sxs-lookup"><span data-stu-id="cded7-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="cded7-122">При обнаружении электронных данных или поиске контента может возникнуть следующая ошибка: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="cded7-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Снимок экрана с ошибкой для конкретного расположения поиска](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="cded7-124">Решение</span><span class="sxs-lookup"><span data-stu-id="cded7-124">Resolution</span></span>

<span data-ttu-id="cded7-125">Если вы получили эту ошибку, рекомендуется проверить расположения, которые не удалось найти, а затем повторно использовать поиск только в тех расположениях, которые не удалось найти.</span><span class="sxs-lookup"><span data-stu-id="cded7-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="cded7-126">Подключись [к PowerShell & Центра](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) безопасности и соответствия требованиям, а затем запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cded7-126">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="cded7-127">Из выходных данных PowerShell можно просмотреть расположения с ошибками в поле "Ошибки" или сведения о состоянии ошибки из выходных данных поиска.</span><span class="sxs-lookup"><span data-stu-id="cded7-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="cded7-128">Повторить поиск eDiscovery только в расположениях, которые не удалось найти.</span><span class="sxs-lookup"><span data-stu-id="cded7-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="cded7-129">Если вы по-прежнему будете получать эти ошибки, дополнительные действия по устранению неполадок см. в подсетях [retry failed](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) locations.</span><span class="sxs-lookup"><span data-stu-id="cded7-129">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="cded7-130">Ошибка/проблема: файл не найден</span><span class="sxs-lookup"><span data-stu-id="cded7-130">Error/issue: File not found</span></span>

<span data-ttu-id="cded7-131">При запуске поиска eDiscovery, включаемого в расположения SharePoint Online и One Drive для бизнеса, может возникнуть ошибка, хотя файл находится `File Not Found` на сайте.</span><span class="sxs-lookup"><span data-stu-id="cded7-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="cded7-132">Эта ошибка будет в предупреждениях об экспорте и errors.csv или пропущена items.csv.</span><span class="sxs-lookup"><span data-stu-id="cded7-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="cded7-133">Это может произойти, если файл не найден на сайте или если индекс устарел.</span><span class="sxs-lookup"><span data-stu-id="cded7-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="cded7-134">Вот текст фактической ошибки (с добавленным акцентом).</span><span class="sxs-lookup"><span data-stu-id="cded7-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="cded7-135">28.06.2019 10:02:19_FailedToExportItem_Failed скачать содержимое.</span><span class="sxs-lookup"><span data-stu-id="cded7-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="cded7-136">Дополнительные диагностические сведения: Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: не удалось скачать содержимое 6ea52149-91cd-4965-b5bb-82ca6a3ec9be типа Document.</span><span class="sxs-lookup"><span data-stu-id="cded7-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="cded7-137">ИД корреляции: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="cded7-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="cded7-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***файл не найден.***</span><span class="sxs-lookup"><span data-stu-id="cded7-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="cded7-139">на сайте Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) в Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span><span class="sxs-lookup"><span data-stu-id="cded7-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="cded7-140">Решение</span><span class="sxs-lookup"><span data-stu-id="cded7-140">Resolution</span></span>

1. <span data-ttu-id="cded7-141">Проверьте расположение, которое определено в поиске, чтобы убедиться в правильности расположения файла и его добавлении в расположения поиска.</span><span class="sxs-lookup"><span data-stu-id="cded7-141">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="cded7-142">Используйте процедуры, которые необходимо вручную запросить обход и переиндексацию [сайта,](https://docs.microsoft.com/sharepoint/crawl-site-content) библиотеки или списка для переиндексации сайта.</span><span class="sxs-lookup"><span data-stu-id="cded7-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](https://docs.microsoft.com/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="cded7-143">Ошибка/проблема: поиск не удается, так как получатель не найден</span><span class="sxs-lookup"><span data-stu-id="cded7-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="cded7-144">Сбой поиска при обнаружении электронных данных с ошибкой `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="cded7-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="cded7-145">Эта ошибка может возникнуть, если не удается найти объект пользователя в Exchange Online Protection (EOP), так как объект не синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="cded7-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="cded7-146">Решение</span><span class="sxs-lookup"><span data-stu-id="cded7-146">Resolution</span></span>

1. <span data-ttu-id="cded7-147">Подключитесь к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="cded7-147">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="cded7-148">Чтобы проверить, синхронизирован ли пользователь с Exchange Online Protection, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cded7-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="cded7-149">Для вопроса пользователя должен быть объект пользователя почты.</span><span class="sxs-lookup"><span data-stu-id="cded7-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="cded7-150">Если ничего не возвращается, изучите объект пользователя.</span><span class="sxs-lookup"><span data-stu-id="cded7-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="cded7-151">Обратитесь в службу поддержки Майкрософт, если объект не может быть синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="cded7-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="cded7-152">Ошибка или проблема: экспорт результатов поиска медленный</span><span class="sxs-lookup"><span data-stu-id="cded7-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="cded7-153">При экспорте результатов поиска из службы eDiscovery или поиска контента в Центре безопасности и соответствия требованиям загрузка занимает больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="cded7-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="cded7-154">Вы можете проверить объем загружаемых данных и, возможно, увеличить скорость экспорта.</span><span class="sxs-lookup"><span data-stu-id="cded7-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="cded7-155">Решение</span><span class="sxs-lookup"><span data-stu-id="cded7-155">Resolution</span></span>

1. <span data-ttu-id="cded7-156">Подключись [к PowerShell & Центра](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) безопасности и соответствия требованиям, а затем запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cded7-156">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="cded7-157">Найдите объем данных, которые необходимо скачать, в параметрах SearchResults и SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="cded7-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="cded7-158">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cded7-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="cded7-159">В поле результатов найдите данные, которые были экспортируются, и просматриваем все ошибки.</span><span class="sxs-lookup"><span data-stu-id="cded7-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="cded7-160">Проверьте файл trace.log, расположенный в каталоге, в который экспортируется контент, на все ошибки.</span><span class="sxs-lookup"><span data-stu-id="cded7-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="cded7-161">Если у вас по-прежнему есть проблемы, рассмотрите возможность деления поиска, возвращающих большой набор результатов, на более мелкие.</span><span class="sxs-lookup"><span data-stu-id="cded7-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="cded7-162">Например, вы можете использовать диапазоны дат в поисковых запросах, чтобы получить меньший набор результатов, который можно скачать быстрее.</span><span class="sxs-lookup"><span data-stu-id="cded7-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="cded7-163">Ошибка/проблема: "Возникла внутренняя ошибка сервера (500)</span><span class="sxs-lookup"><span data-stu-id="cded7-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="cded7-164">При запуске поиска при обнаружении электронных данных, если поиск постоянно заканчивается ошибкой, аналогичной "Возникла внутренняя ошибка сервера (500),может потребоваться повторное запуск поиска только в определенных расположениях почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="cded7-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Снимок экрана с ошибкой внутреннего сервера 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="cded7-166">Решение</span><span class="sxs-lookup"><span data-stu-id="cded7-166">Resolution</span></span>

1. <span data-ttu-id="cded7-167">Раз break the search into smaller searches and run the search again.</span><span class="sxs-lookup"><span data-stu-id="cded7-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="cded7-168">Попробуйте использовать меньший диапазон дат или ограничить число мест поиска.</span><span class="sxs-lookup"><span data-stu-id="cded7-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="cded7-169">Подключись [к PowerShell & Центра](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) безопасности и соответствия требованиям, а затем запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cded7-169">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="cded7-170">Проверьте результаты и ошибки.</span><span class="sxs-lookup"><span data-stu-id="cded7-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="cded7-171">Проверьте файл trace.log.</span><span class="sxs-lookup"><span data-stu-id="cded7-171">Examine the trace.log file.</span></span> <span data-ttu-id="cded7-172">Она расположена в той же папке, в которую экспортируются результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="cded7-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="cded7-173">Обратитесь в службу поддержки корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cded7-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="cded7-174">Ошибка/проблема: не синхронизируются удерживаемой информации</span><span class="sxs-lookup"><span data-stu-id="cded7-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="cded7-175">Ошибка распространения синхронизации политики удержания дела eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="cded7-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="cded7-176">Ошибка считывет:</span><span class="sxs-lookup"><span data-stu-id="cded7-176">The error reads:</span></span>

> <span data-ttu-id="cded7-177">"Ресурсы: развертывание политики проходит больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="cded7-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="cded7-178">Обновление итогового состояния развертывания может занять еще 2 часа, поэтому вернемся через пару часов".</span><span class="sxs-lookup"><span data-stu-id="cded7-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="cded7-179">Решение</span><span class="sxs-lookup"><span data-stu-id="cded7-179">Resolution</span></span>

1. <span data-ttu-id="cded7-180">Подключись [к PowerShell &](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Центра безопасности и соответствия требованиям, а затем запустите следующую команду для удержания дела eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="cded7-180">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="cded7-181">Для политики хранения запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cded7-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="cded7-182">Проверьте значение параметра DistributionDetail на ошибки, такие как следующие:</span><span class="sxs-lookup"><span data-stu-id="cded7-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="cded7-183">Ошибка: ресурсы: развертывание политики проходит больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="cded7-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="cded7-184">Обновление итогового состояния развертывания может занять еще 2 часа, поэтому вернемся через пару часов".</span><span class="sxs-lookup"><span data-stu-id="cded7-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="cded7-185">Попробуйте запускать параметр RetryDistribution для политики, определимой:</span><span class="sxs-lookup"><span data-stu-id="cded7-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="cded7-186">Для дела eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="cded7-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="cded7-187">Для политик хранения:</span><span class="sxs-lookup"><span data-stu-id="cded7-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="cded7-188">Обратитесь в службу поддержки корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cded7-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="cded7-189">Ошибка: "Условие, заданное с помощью условных http-заголовок, не совме"</span><span class="sxs-lookup"><span data-stu-id="cded7-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="cded7-190">При скачивании результатов поиска с помощью средства экспорта eDiscovery может возникнуть следующая ошибка: это временные ошибки, которые обычно возникают в хранилище `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure.</span><span class="sxs-lookup"><span data-stu-id="cded7-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="cded7-191">Решение</span><span class="sxs-lookup"><span data-stu-id="cded7-191">Resolution</span></span>

<span data-ttu-id="cded7-192">Чтобы устранить эту проблему, повторите [скачивание](export-search-results.md#step-2-download-the-search-results)результатов поиска, после чего перезапустите средство экспорта eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="cded7-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="cded7-193">Ошибка/проблема: загруженный экспорт не показывает результатов</span><span class="sxs-lookup"><span data-stu-id="cded7-193">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="cded7-194">После успешного экспорта завершенная загрузка с помощью средства экспорта отображает в результатах ноль файлов.</span><span class="sxs-lookup"><span data-stu-id="cded7-194">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="cded7-195">Решение</span><span class="sxs-lookup"><span data-stu-id="cded7-195">Resolution</span></span>

<span data-ttu-id="cded7-196">Это проблема на стороне клиента, и чтобы ее решить, попробуйте сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="cded7-196">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="cded7-197">Попробуйте скачать другой клиент или компьютер.</span><span class="sxs-lookup"><span data-stu-id="cded7-197">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="cded7-198">Обязательно скачайте файл на локальный диск.</span><span class="sxs-lookup"><span data-stu-id="cded7-198">Make sure to download to a local drive.</span></span>

3. <span data-ttu-id="cded7-199">Убедитесь, что антивирусная сканер не запущена.</span><span class="sxs-lookup"><span data-stu-id="cded7-199">Make sure the virus scanner is not running.</span></span>

4. <span data-ttu-id="cded7-200">Убедитесь, что в ту же или родительную папку не загружается никакой другой экспорт.</span><span class="sxs-lookup"><span data-stu-id="cded7-200">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

5. <span data-ttu-id="cded7-201">Если предыдущие действия не сработают, отключает заглушку и дублирование.</span><span class="sxs-lookup"><span data-stu-id="cded7-201">If the previous steps did not work, disable zipping and de-duplication.</span></span>

6. <span data-ttu-id="cded7-202">Если это работает, проблема вызвана локальной антивирусной сканером или проблемой с диском.</span><span class="sxs-lookup"><span data-stu-id="cded7-202">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
