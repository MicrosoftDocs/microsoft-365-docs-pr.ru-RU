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
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Исследование, устранение и устранение распространенных проблем с eDiscovery

В этом разделе описывается основные действия по устранению неполадок, которые можно предпринять для выявления и устранения проблем, которые могут возникнуть во время поиска с целью eDiscovery или в другом месте процесса eDiscovery. Для разрешения некоторых из этих сценариев требуется помощь службы поддержки Майкрософт. Сведения о том, когда обращаться в службу поддержки Майкрософт, включены в действия по разрешению.

## <a name="errorissue-ambiguous-location"></a>Ошибка/проблема: неоднозначное расположение

Если попытаться добавить расположение почтового ящика пользователя для поиска, а в каталоге Exchange Online Protection (EOP) имеются дублирующиеся или конфликтующие объекты с одинаковым userID, вы получите сообщение об `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` ошибке:

### <a name="resolution"></a>Решение

Проверьте, есть ли дублирующиеся пользователи или список рассылки с одинаковым ИД пользователя.

1. Подключение к [PowerShell Центра & безопасности](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)и соответствия требованиям.

2. Чтобы получить все экземпляры имени пользователя, запустите следующую команду:

    ```powershell
    Get-Recipient <username>
    ```

   Выходные данные для "useralias@contoso.com" будут похожи на следующие:

   > 
   > |Name|RecipientType|
   > |---|---|
   > |Псевдоним, пользователь|MailUser|
   > |Псевдоним, пользователь|Пользователь|

3. Если возвращается несколько пользователей, найдите и исправьте конфликтующий объект.

## <a name="errorissue-search-fails-on-specific-locations"></a>Ошибка или проблема: поиск не удается в определенных расположениях

При обнаружении электронных данных или поиске контента может возникнуть следующая ошибка: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![Снимок экрана с ошибкой для конкретного расположения поиска](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Решение

Если вы получили эту ошибку, рекомендуется проверить расположения, которые не удалось найти, а затем повторно использовать поиск только в тех расположениях, которые не удалось найти.

1. Подключись [к PowerShell & Центра](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) безопасности и соответствия требованиям, а затем запустите следующую команду:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Из выходных данных PowerShell можно просмотреть расположения с ошибками в поле ошибок или сведения о состоянии ошибки из выходных данных поиска.

3. Повторить поиск eDiscovery только в расположениях, которые не удалось найти.

4. Если вы по-прежнему будете получать эти ошибки, дополнительные действия по устранению неполадок см. в подсетях [retry failed](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) locations.

## <a name="errorissue-file-not-found"></a>Ошибка/проблема: файл не найден

При запуске поиска eDiscovery, включаемого в расположения SharePoint Online и One Drive для бизнеса, может возникнуть ошибка, хотя файл находится `File Not Found` на сайте. Эта ошибка будет в предупреждениях об экспорте и errors.csv или пропущена items.csv. Это может произойти, если файл не найден на сайте или если индекс устарел. Вот текст фактической ошибки (с добавленным акцентом).

> 28.06.2019 10:02:19_FailedToExportItem_Failed скачать содержимое. Дополнительные диагностические сведения: Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: не удалось скачать содержимое 6ea52149-91cd-4965-b5bb-82ca6a3ec9be типа Document. ИД корреляции: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***файл не найден.*** на сайте Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) в Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---

### <a name="resolution"></a>Решение

1. Проверьте расположение, которое определено в поиске, чтобы убедиться в правильности расположения файла и его добавлении в расположения поиска.

2. Используйте процедуры, которые необходимо вручную запросить обход и переиндексацию [сайта,](https://docs.microsoft.com/sharepoint/crawl-site-content) библиотеки или списка для переиндексации сайта.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Ошибка/проблема: поиск не удается, так как получатель не найден

Сбой поиска при обнаружении электронных данных с ошибкой `recipient not found` . Эта ошибка может возникнуть, если не удается найти объект пользователя в Exchange Online Protection (EOP), так как объект не синхронизирован.

### <a name="resolution"></a>Решение

1. Подключитесь к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Чтобы проверить, синхронизирован ли пользователь с Exchange Online Protection, запустите следующую команду:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Для вопроса пользователя должен быть объект пользователя почты. Если ничего не возвращается, изучите объект пользователя. Обратитесь в службу поддержки Майкрософт, если объект не может быть синхронизирован.

## <a name="errorissue-exporting-search-results-is-slow"></a>Ошибка или проблема: экспорт результатов поиска медленный

При экспорте результатов поиска из службы eDiscovery или поиска контента в Центре безопасности и соответствия требованиям загрузка занимает больше времени, чем ожидалось.  Вы можете проверить объем загружаемых данных и, возможно, увеличить скорость экспорта.

### <a name="resolution"></a>Решение

1. Подключись [к PowerShell & Центра](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) безопасности и соответствия требованиям, а затем запустите следующую команду:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Найдите объем данных, которые необходимо скачать, в параметрах SearchResults и SearchStatistics.

3. Выполните следующую команду:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. В поле результатов найдите данные, которые были экспортировали, и просматриваем все ошибки.

5. Проверьте файл trace.log, расположенный в каталоге, в который экспортируется контент, на все ошибки.

6. Если у вас по-прежнему есть проблемы, рассмотрите возможность деления поиска, возвращающих большой набор результатов, на более мелкие. Например, вы можете использовать диапазоны дат в поисковых запросах, чтобы получить меньший набор результатов, который можно скачать быстрее.

## <a name="errorissue-internal-server-error-500-occurred"></a>Ошибка/проблема: "Возникла внутренняя ошибка сервера (500)

При запуске поиска при обнаружении электронных данных, если поиск постоянно заканчивается ошибкой, аналогичной "Возникла внутренняя ошибка сервера (500),может потребоваться повторное запуск поиска только в определенных расположениях почтовых ящиков.

![Снимок экрана с ошибкой внутреннего сервера 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Решение

1. Раз break the search into smaller searches and run the search again.  Попробуйте использовать меньший диапазон дат или ограничить количество поисков в расположениях.

2. Подключись [к PowerShell & Центра](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) безопасности и соответствия требованиям, а затем запустите следующую команду:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Проверьте результаты и ошибки.

4. Проверьте файл trace.log. Она расположена в той же папке, в которую экспортируются результаты поиска.

5. Обратитесь в службу поддержки корпорации Майкрософт.

## <a name="errorissue-holds-dont-sync"></a>Ошибка/проблема: не синхронизируются удерживаемой информации

Ошибка распространения синхронизации политики удержания дела eDiscovery. Ошибка считывется:

> "Ресурсы: развертывание политики проходит больше времени, чем ожидалось. Обновление итогового состояния развертывания может занять еще 2 часа, поэтому вернемся через пару часов".

### <a name="resolution"></a>Решение

1. Подключись [к PowerShell &](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Центра безопасности и соответствия требованиям, а затем запустите следующую команду для удержания дела eDiscovery:

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    Для политики хранения запустите следующую команду:

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. Проверьте значение параметра DistributionDetail на следующие ошибки:

   > Ошибка: ресурсы: развертывание политики проходит больше времени, чем ожидалось. Обновление итогового состояния развертывания может занять еще 2 часа, поэтому вернемся через пару часов".

3. Попробуйте запускать параметр RetryDistribution для политики, определимой:

   Для дела eDiscovery:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   Для политик хранения:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Обратитесь в службу поддержки корпорации Майкрософт.

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>Ошибка: "Условие, заданное с помощью условных http-заголовок, не совме"

При скачивании результатов поиска с помощью средства экспорта методом eDiscovery может возникнуть следующая ошибка: это временные ошибки, которые обычно возникают в хранилище `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure.

### <a name="resolution"></a>Решение

Чтобы устранить эту проблему, повторите скачивание результатов [поиска,](export-search-results.md#step-2-download-the-search-results)после чего перезапустите средство экспорта eDiscovery.

## <a name="errorissue-downloaded-export-shows-no-results"></a>Ошибка/проблема: загруженный экспорт не показывает результатов

После успешного экспорта завершенная загрузка с помощью средства экспорта отображает в результатах ноль файлов.

### <a name="resolution"></a>Решение

Это проблема на стороне клиента, и чтобы ее решить, попробуйте сделать следующее:

1. Попробуйте скачать другой клиент или компьютер.

2. Обязательно скачайте файл на локальный диск.

3. Убедитесь, что антивирусная сканер не запущена.

4. Убедитесь, что в ту же или родительную папку не загружается никакой другой экспорт.

5. Если предыдущие действия не сработают, отключает заглушку и дублирование.

6. Если это работает, проблема вызвана локальной антивирусной сканером или проблемой с диском.
