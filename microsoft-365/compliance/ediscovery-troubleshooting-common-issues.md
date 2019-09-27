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
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Исследование, устранение неполадок и устранение распространенных проблем обнаружения электронных данных

В этом разделе описываются основные действия по устранению неполадок, которые можно предпринять для определения и устранения проблем, которые могут возникать во время поиска обнаружения электронных данных или в другом месте процесса обнаружения электронных данных. Для устранения некоторых из этих сценариев необходима помощь в службе поддержки клиентов (CSS). Сведения о том, когда следует обращаться к CSS, включаются в процедуру решения.

## <a name="errorissue-ambiguous-location"></a>Неоднозначное расположение ошибки или выдача

Появится сообщение об ошибке "Поиск соответствия содержит следующее недопустимое расположение `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` ", если вы попытались добавить расположение почтового ящика пользователя в поиск и в Exchange Online Protection имеются дублирующиеся или конфликтующие объекты с таким же идентификатором пользователя (EOP) каталога.

### <a name="resolution"></a>Разрешение

Проверьте наличие дубликатов пользователей или списка рассылки с одинаковым ИДЕНТИФИКАТОРом пользователя.

1. Подключитесь к [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
2. Получите все экземпляры имени пользователя, введите:

```powershell
Get-Recipient <username>
```

Выходные данные для "useralias@contoso.com" могут быть

> 
> |Имя  |RecipientType  |
> |---------|---------|
> |Псевдоним, пользователь     |MailUser         |
> |Псевдоним, пользователь     |Пользователь         |

3. Если возвращается несколько пользователей, разместите и устраните конфликтующий объект.

## <a name="errorissue-search-fails-on-specific-locations"></a>Ошибка/Ошибка поиска не удается в определенных расположениях

Поиск обнаружения электронных данных или контента может привести к возникновению следующей ошибки:
>Поиск завершился с ошибками (#).  Вы хотите повторить поиск в расположениях с ошибками?

![снимок экрана с определенным расположением для поиска со сбоем]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Разрешение

При возникновении этой ошибки рекомендуется проверить расположения, в которых произошел сбой, а затем повторно выполнить поиск только в расположениях, на которых не удалось выполнить поиск.

1. Подключитесь к [PowerShell Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).
1. Тип:

```powershell
Get-Compliancesearch searchname|fl 
```

3. В выходных данных PowerShell просмотрите сведения о неудачных расположениях в поле ошибки или сведения о состоянии, указанные в сообщении об ошибке, из результатов поиска.
1. Повторите поиск обнаружения электронных данных для неудачных расположений.
1. Если вы продолжаете получать эти сообщения об ошибке, обратитесь к разделу [Retry Failed Locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for дополнительные действия по устранению неполадок.

## <a name="errorissue-file-not-found"></a>Ошибка/файл вопроса не найден

При выполнении поиска обнаружения электронных данных, включающего SharePoint Online и один диск для размещения бизнеса, может появиться сообщение `File Not Found` об ошибке, несмотря на то, что файл находится на сайте. Эта ошибка будет указана в разделе Export and Errors. CSV или пропущенные элементы. csv это может произойти, если не удается найти файл на сайте или индекс устарел. Вот текст фактической ошибки с добавленным выделением.
  
> 28.06.2019 10:02:19_FailedToExportItem_Failed для скачивания контента. Дополнительные диагностические сведения: Microsoft. Office. соответствие. EDiscovery. Експортворкер. Exceptions. Контентдовнлоадтемпорарифаилуре: не удалось скачать из контента 6ea52149 — 91cd – 4965 – b5bb – 82ca6a3ec9be типа Document. Идентификатор корреляции: 3bd84722-937b-4c23-b61b-08d6fba9ec32. Серверерроркоде: – 2147024894---> Microsoft. SharePoint. Client. Серверексцептион: ***файл не найден***. в Microsoft. SharePoint. Client. Клиентрекуест. Процессреспонсестреам (Stream Респонсестреам) на сайте Microsoft. SharePoint. Client. Клиентрекуест. Процессреспонсе ()---конец трассировки стека внутренних исключений---

### <a name="resolution"></a>Разрешение

1. Проверьте расположение, указанное в поиске, чтобы убедиться в том, что расположение файла указано правильно и добавляется в расположений для поиска.
2. Используйте процедуры при [ручном запросе на обход контента и повторной индексации сайта, библиотеки или списка](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) для повторного индексирования сайта.

## <a name="errorissue-search-fails-recipient-not-found"></a>Ошибка/Ошибка поиска не удалось найти получателя

не удается выполнить поиск обнаружения `recipient not found`электронных данных с ошибкой. Эта ошибка может возникнуть, если объект пользователя не удается найти в Exchange Online Protection (EOP), так как объект не синхронизирован.

### <a name="resolution"></a>Разрешение

1. Подключитесь к [PowerShell Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).
1. Проверьте, синхронизирован ли объект пользователя с типом защиты Exchange Online:

```powershell
Get-Recipient userId|fl
```

3. Для ответа пользователя должен быть указан объект MailUser. Если ничего не возвращается, изучите объект User. Если не удается синхронизировать объект, обратитесь в CSS.

## <a name="errorissue-exporting-search-results-is-slow"></a>Ошибка/Ошибка при экспорте результатов поиска выполняется медленно

При экспорте результатов поиска из обнаружения электронных данных или поиска контента в центре безопасности и соответствия требованиям Загрузка занимает больше времени, чем ожидалось.  Вы можете проверить количество загружаемых данных и, возможно, увеличить скорость экспорта.

### <a name="resolution"></a>Разрешение

1.  Попробуйте использовать шаги, описанные в статье, чтобы [увеличить скорость загрузки](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).
2.  Если у вас по-прежнему возникают проблемы, подключитесь к [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) и введите:

```powershell
Get-ComplianceSearch searchname\fl
```

4. Найдите объем данных для загрузки в параметрах SearchResults и Сеарчстатистикс.
5. Тип:

```powershell
Get-ComplianceSearchAction |fl
```

6. В поле Результаты найдите экспортированные данные и просмотрите все обнаруженные ошибки.
7. Проверьте файл Trace. log, находящийся в каталоге, в который вы экспортировали содержимое для любых ошибок.

## <a name="errorissue-internal-server-error-500-occurred"></a>Ошибка или возникла ошибка "Внутренняя ошибка сервера (500)"

При выполнении поиска обнаружения электронных данных, если поиск заканчивается неудачей с ошибкой "Внутренняя ошибка сервера (500)", возможно, потребуется повторно выполнить поиск только в определенных расположениях почтовых ящиков.

![снимок экрана "Внутренняя ошибка сервера 500"](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Разрешение

1. Разбейте Поиск на небольшие поиски и снова запустите поиск.  Попробуйте использовать меньший диапазон дат или ограничить количество искомых расположений.
2. Подключитесь к [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) и введите:

```powershell
Get-ComplianceSearch searchname |fl
```

3. Изучите выходные данные для результатов и ошибок.
3. Изучите файл Trace. log. Он будет находиться в той же папке, куда вы отправили экспорт.
4. Обратитесь в службу поддержки CSS.

## <a name="errorissue-holds-dont-sync"></a>Ошибка/ошибка удержания не синхронизируются

Ошибка распространения синхронизации политики обнаружения электронных данных для обнаружения электронных данных. Сообщение об ошибке выглядит следующим образом:

> "Resources: для развертывания политики требуется больше времени, чем ожидалось. Обновление последнего состояния развертывания может занять два часа, поэтому выполните проверку в течение нескольких часов. "

### <a name="resolution"></a>Разрешение

1.  Подключитесь к [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) и введите:

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. Проверьте значение параметра Дистрибутиондетаил на наличие ошибок, как показано ниже.

> Если ошибка существует, создайте укрупнение для PG, чтобы принудительно выполнить повторную синхронизацию вручную для политики.

3. Обратитесь в службу поддержки CSS.

## <a name="see-also"></a>См. также
- [Советы по предотвращению ошибок расположения контента](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)