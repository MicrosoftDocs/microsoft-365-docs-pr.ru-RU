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
description: Узнайте об основных действиях по устранению неполадок, которые можно предпринять для устранения распространенных проблем в office 365 eDiscovery.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a867ed2e55c73fe4bbd890273d78cf57f4bfbd2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926549"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="246a3-103">Изучение, устранение неполадок и устранение распространенных проблем с электронным открытием</span><span class="sxs-lookup"><span data-stu-id="246a3-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="246a3-104">В этом разделе описывается основные действия по устранению неполадок, которые можно предпринять для выявления и устранения проблем, с которыми вы можете столкнуться во время поиска по обнаружению электронных обнаружений или в других местах в процессе поиска электронной информации.</span><span class="sxs-lookup"><span data-stu-id="246a3-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="246a3-105">Для решения некоторых из этих сценариев требуется помощь службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="246a3-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="246a3-106">Сведения о том, когда обращаться в службу поддержки Майкрософт, включены в действия по разрешению.</span><span class="sxs-lookup"><span data-stu-id="246a3-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="246a3-107">Ошибка/проблема. Неоднозначное расположение</span><span class="sxs-lookup"><span data-stu-id="246a3-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="246a3-108">Если вы пытаетесь добавить расположение почтового ящика пользователя для поиска, а в каталоге Exchange Online Protection (EOP) есть дублирующие или конфликтующие объекты с одинаковым пользовательским интерфейсом, вы получите эту ошибку: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="246a3-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="246a3-109">Решение</span><span class="sxs-lookup"><span data-stu-id="246a3-109">Resolution</span></span>

<span data-ttu-id="246a3-110">Проверьте, есть ли повторяющиеся пользователи или список рассылки с тем же ИД пользователя.</span><span class="sxs-lookup"><span data-stu-id="246a3-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="246a3-111">Подключение к [центру & безопасности PowerShell.](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="246a3-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="246a3-112">Запустите следующую команду, чтобы получить все экземпляры имени пользователя:</span><span class="sxs-lookup"><span data-stu-id="246a3-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="246a3-113">Выход для "useralias@contoso.com" будет похож на следующий:</span><span class="sxs-lookup"><span data-stu-id="246a3-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="246a3-114">Имя</span><span class="sxs-lookup"><span data-stu-id="246a3-114">Name</span></span>|<span data-ttu-id="246a3-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="246a3-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="246a3-116">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="246a3-116">Alias, User</span></span>|<span data-ttu-id="246a3-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="246a3-117">MailUser</span></span>|
   > |<span data-ttu-id="246a3-118">Псевдоним, пользователь</span><span class="sxs-lookup"><span data-stu-id="246a3-118">Alias, User</span></span>|<span data-ttu-id="246a3-119">Пользователь</span><span class="sxs-lookup"><span data-stu-id="246a3-119">User</span></span>|

3. <span data-ttu-id="246a3-120">Если возвращается несколько пользователей, найдите и исправьте конфликтующий объект.</span><span class="sxs-lookup"><span data-stu-id="246a3-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="246a3-121">Ошибка/проблема: сбой поиска в определенных расположениях</span><span class="sxs-lookup"><span data-stu-id="246a3-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="246a3-122">Поиск электронных данных или контента может привести к следующей ошибке: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="246a3-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Расположение, определенное для поиска, не удается сделать снимок экрана ошибки](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="246a3-124">Решение</span><span class="sxs-lookup"><span data-stu-id="246a3-124">Resolution</span></span>

<span data-ttu-id="246a3-125">Если вы получили эту ошибку, рекомендуется проверить расположения, которые не удалось в поиске, а затем повторного поиска только в неудались расположения.</span><span class="sxs-lookup"><span data-stu-id="246a3-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="246a3-126">Подключись [к центру & безопасности PowerShell](/powershell/exchange/connect-to-scc-powershell) и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="246a3-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="246a3-127">На выходе PowerShell просмотреть неудачные расположения в поле ошибок или сведения о состоянии ошибки из вывода поиска.</span><span class="sxs-lookup"><span data-stu-id="246a3-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="246a3-128">Повторное поиск по обнаружению электронных обнаружений только в сбойных расположениях.</span><span class="sxs-lookup"><span data-stu-id="246a3-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="246a3-129">Если вы продолжаете получать эти ошибки, см. пункт [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) для получения дополнительных действий по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="246a3-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="246a3-130">Ошибка/проблема. Файл не найден</span><span class="sxs-lookup"><span data-stu-id="246a3-130">Error/issue: File not found</span></span>

<span data-ttu-id="246a3-131">При запуске поиска по обнаружению электронных данных, который включает расположения SharePoint Online и One Drive for Business, вы можете получить ошибку, хотя файл расположен `File Not Found` на сайте.</span><span class="sxs-lookup"><span data-stu-id="246a3-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="246a3-132">Эта ошибка будет в предупреждениях об экспорте и errors.csv или пропущена items.csv.</span><span class="sxs-lookup"><span data-stu-id="246a3-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="246a3-133">Это может произойти, если файл не может быть найден на сайте или если индекс устарел.</span><span class="sxs-lookup"><span data-stu-id="246a3-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="246a3-134">Вот текст фактической ошибки (с добавленным акцентом).</span><span class="sxs-lookup"><span data-stu-id="246a3-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="246a3-135">28.06.2019 10:02:19_FailedToExportItem_Failed скачать контент.</span><span class="sxs-lookup"><span data-stu-id="246a3-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="246a3-136">Дополнительные диагностические сведения: Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Не удалось скачать из контента 6ea52149-91cd-4965-b5bb-82ca6a3ec9be документа типа.</span><span class="sxs-lookup"><span data-stu-id="246a3-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="246a3-137">ID корреляции: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="246a3-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="246a3-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***файл не найден***.</span><span class="sxs-lookup"><span data-stu-id="246a3-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="246a3-139">в Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) в Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- Конец трассировки внутреннего стека исключений ---</span><span class="sxs-lookup"><span data-stu-id="246a3-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="246a3-140">Решение</span><span class="sxs-lookup"><span data-stu-id="246a3-140">Resolution</span></span>

1. <span data-ttu-id="246a3-141">Проверьте расположение, которое определено в поиске, чтобы убедиться в правильности расположения файла и его добавлении в расположениях поиска.</span><span class="sxs-lookup"><span data-stu-id="246a3-141">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="246a3-142">Используйте процедуры при ручном запросе обхода и повторной индексации [сайта,](/sharepoint/crawl-site-content) библиотеки или списка для повторного использования сайта.</span><span class="sxs-lookup"><span data-stu-id="246a3-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="246a3-143">Ошибка/проблема. Поиск не удается, так как получатель не найден</span><span class="sxs-lookup"><span data-stu-id="246a3-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="246a3-144">Поиск по обнаружению электронных данных не удается с ошибкой `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="246a3-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="246a3-145">Эта ошибка может возникнуть, если объект пользователя не может быть найден в Exchange Online Protection (EOP), так как объект не синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="246a3-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="246a3-146">Решение</span><span class="sxs-lookup"><span data-stu-id="246a3-146">Resolution</span></span>

1. <span data-ttu-id="246a3-147">Подключитесь к [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="246a3-147">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="246a3-148">Запустите следующую команду, чтобы проверить, синхронизирован ли пользователь с Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="246a3-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="246a3-149">Должен быть объект пользователя почты для пользовательского вопроса.</span><span class="sxs-lookup"><span data-stu-id="246a3-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="246a3-150">Если ничего не возвращается, изучите объект пользователя.</span><span class="sxs-lookup"><span data-stu-id="246a3-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="246a3-151">Если объект не синхронизирован, обратитесь в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="246a3-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="246a3-152">Ошибка/проблема. Экспорт результатов поиска идет медленно</span><span class="sxs-lookup"><span data-stu-id="246a3-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="246a3-153">При экспорте результатов поиска из центра поиска электронных данных или поиска контента в центре безопасности и соответствия требованиям загрузка занимает больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="246a3-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="246a3-154">Вы можете проверить количество скачиваемых данных и, возможно, увеличить скорость экспорта.</span><span class="sxs-lookup"><span data-stu-id="246a3-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="246a3-155">Решение</span><span class="sxs-lookup"><span data-stu-id="246a3-155">Resolution</span></span>

1. <span data-ttu-id="246a3-156">Подключись [к центру & безопасности PowerShell](/powershell/exchange/connect-to-scc-powershell) и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="246a3-156">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="246a3-157">Найдите количество данных, которые будут загружены в параметрах SearchResults и SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="246a3-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="246a3-158">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="246a3-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="246a3-159">В поле результатов найдите экспортируемую информацию и просматриваем все ошибки, с которыми столкнулись.</span><span class="sxs-lookup"><span data-stu-id="246a3-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="246a3-160">Проверьте файл trace.log, расположенный в каталоге, в который экспортируется содержимое, для любых ошибок.</span><span class="sxs-lookup"><span data-stu-id="246a3-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="246a3-161">Если у вас еще есть проблемы, подумайте о разделении поисков, возвращающих большой набор результатов в меньшие поиски.</span><span class="sxs-lookup"><span data-stu-id="246a3-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="246a3-162">Например, диапазоны дат можно использовать в поисковых запросах, чтобы вернуть меньший набор результатов, которые можно скачать быстрее.</span><span class="sxs-lookup"><span data-stu-id="246a3-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="246a3-163">Ошибка/проблема: "Произошла ошибка внутреннего сервера (500)"</span><span class="sxs-lookup"><span data-stu-id="246a3-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="246a3-164">При запуске поиска по обнаружению электронных данных при постоянном сбое поиска с ошибкой, аналогичной "Ошибка внутреннего сервера (500) произошла", может потребоваться повторное повторение поиска только в определенных расположениях почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="246a3-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Скриншот ошибки внутреннего сервера 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="246a3-166">Решение</span><span class="sxs-lookup"><span data-stu-id="246a3-166">Resolution</span></span>

1. <span data-ttu-id="246a3-167">Разорвать поиск на меньшие поиски и запустить поиск снова.</span><span class="sxs-lookup"><span data-stu-id="246a3-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="246a3-168">Попробуйте использовать меньший диапазон дат или ограничить количество поисковых местоположений.</span><span class="sxs-lookup"><span data-stu-id="246a3-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="246a3-169">Подключись [к центру & безопасности PowerShell](/powershell/exchange/connect-to-scc-powershell) и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="246a3-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="246a3-170">Изучите результаты и ошибки.</span><span class="sxs-lookup"><span data-stu-id="246a3-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="246a3-171">Изучите файл trace.log.</span><span class="sxs-lookup"><span data-stu-id="246a3-171">Examine the trace.log file.</span></span> <span data-ttu-id="246a3-172">Он расположен в той же папке, в которую экспортируются результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="246a3-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="246a3-173">Обратитесь в службу поддержки корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="246a3-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="246a3-174">Ошибка/проблема. Не синхронизируются удерживаемая</span><span class="sxs-lookup"><span data-stu-id="246a3-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="246a3-175">Ошибка распределения синхронизации политики при обнаружении электронных данных.</span><span class="sxs-lookup"><span data-stu-id="246a3-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="246a3-176">Ошибка гласит:</span><span class="sxs-lookup"><span data-stu-id="246a3-176">The error reads:</span></span>

> <span data-ttu-id="246a3-177">"Ресурсы. Развертывание политики может затметь больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="246a3-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="246a3-178">На обновление окончательного состояния развертывания может потребоваться еще 2 часа, поэтому проверьте это в течение нескольких часов".</span><span class="sxs-lookup"><span data-stu-id="246a3-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="246a3-179">Решение</span><span class="sxs-lookup"><span data-stu-id="246a3-179">Resolution</span></span>

1. <span data-ttu-id="246a3-180">Подключись к центру & безопасности [PowerShell](/powershell/exchange/connect-to-scc-powershell) и запустите следующую команду для удержания дела об обнаружении электронных данных:</span><span class="sxs-lookup"><span data-stu-id="246a3-180">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="246a3-181">Для политики хранения запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="246a3-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="246a3-182">Изучите значение параметра DistributionDetail для ошибок, таких как следующие:</span><span class="sxs-lookup"><span data-stu-id="246a3-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="246a3-183">Ошибка. Ресурсы. Развертывание политики проходит дольше, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="246a3-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="246a3-184">На обновление окончательного состояния развертывания может потребоваться еще 2 часа, поэтому проверьте это в течение нескольких часов".</span><span class="sxs-lookup"><span data-stu-id="246a3-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="246a3-185">Попробуйте запускать параметр RetryDistribution для политики, определимой:</span><span class="sxs-lookup"><span data-stu-id="246a3-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="246a3-186">Для дела об обнаружении электронных обнаружений:</span><span class="sxs-lookup"><span data-stu-id="246a3-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="246a3-187">Для политик хранения:</span><span class="sxs-lookup"><span data-stu-id="246a3-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="246a3-188">Обратитесь в службу поддержки корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="246a3-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="246a3-189">Ошибка: "Условие, указанное с помощью условного заголовка HTTP(ы) не выполнены"</span><span class="sxs-lookup"><span data-stu-id="246a3-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="246a3-190">При скачивании результатов поиска с помощью экспортного средства eDiscovery можно получить следующую ошибку: это преходящая ошибка, которая обычно возникает в расположении `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="246a3-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="246a3-191">Решение</span><span class="sxs-lookup"><span data-stu-id="246a3-191">Resolution</span></span>

<span data-ttu-id="246a3-192">Чтобы устранить эту проблему, повторите скачивание результатов [поиска,](export-search-results.md#step-2-download-the-search-results)которые перезапустят средство экспорта электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="246a3-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="246a3-193">Ошибка/проблема. Загруженный экспорт не показывает результатов</span><span class="sxs-lookup"><span data-stu-id="246a3-193">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="246a3-194">После успешного экспорта завершенная загрузка с помощью средства экспорта показывает нулевые файлы в результатах.</span><span class="sxs-lookup"><span data-stu-id="246a3-194">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="246a3-195">Решение</span><span class="sxs-lookup"><span data-stu-id="246a3-195">Resolution</span></span>

<span data-ttu-id="246a3-196">Это клиентская проблема, и для ее устранения попробуйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="246a3-196">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="246a3-197">Попробуйте скачать с помощью другого клиента или компьютера.</span><span class="sxs-lookup"><span data-stu-id="246a3-197">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="246a3-198">Не забудьте скачать на локальный диск.</span><span class="sxs-lookup"><span data-stu-id="246a3-198">Make sure to download to a local drive.</span></span>

3. <span data-ttu-id="246a3-199">Убедитесь, что сканер вирусов не запущен.</span><span class="sxs-lookup"><span data-stu-id="246a3-199">Make sure the virus scanner is not running.</span></span>

4. <span data-ttu-id="246a3-200">Убедитесь, что ни один другой экспорт не загружается в ту же папку или в родительской папке.</span><span class="sxs-lookup"><span data-stu-id="246a3-200">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

5. <span data-ttu-id="246a3-201">Если предыдущие действия не сработались, отключим отрезок и отключим дублирование.</span><span class="sxs-lookup"><span data-stu-id="246a3-201">If the previous steps did not work, disable zipping and de-duplication.</span></span>

6. <span data-ttu-id="246a3-202">Если это работает, то проблема вызвана локальным сканером вирусов или проблемой диска.</span><span class="sxs-lookup"><span data-stu-id="246a3-202">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>