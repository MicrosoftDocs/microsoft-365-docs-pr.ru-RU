---
title: Расширенные методы запросов на поиск в Защитнике Microsoft 365
description: Узнайте, как создавать быстрые, эффективные и без ошибок запросы охоты на угрозы с расширенным поиском
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, kusto, avoid timeout, command lines, process id, optimize, best practice, parse, join, summarize
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cc6110cdd7dd71f80f6897cfbb0026ccce301cf7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928478"
---
# <a name="advanced-hunting-query-best-practices"></a>Рекомендации по использованию запросов расширенного выслеживания

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Применив эти рекомендации, вы можете быстрее получать результаты и избегать периодов времени в ходе работы со сложными запросами. Дополнительные руководства по повышению производительности запросов см. в статье [Рекомендации по использованию запросов Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Понимание квот ресурсов ЦП
В зависимости от размера каждый клиент имеет доступ к определенному объему ресурсов ЦП, выделенным для запросов на расширенный поиск. Подробные сведения о различных ограничениях службы можно узнать о квотах и параметрах использования для расширенных [сервисов.](advanced-hunting-limits.md)

Клиенты, регулярно запускающие несколько запросов, должны отслеживать потребление и применять рекомендации по оптимизации в этой статье, чтобы свести к минимуму нарушения в результате превышения квот или параметров использования.

## <a name="general-optimization-tips"></a>Общие советы по оптимизации

- **Размер новых запросов**— если вы подозреваете, что запрос возвратит большой набор результатов, сначала оцените его с помощью оператора [подсчета.](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator) Используйте [ограничение](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) или его синоним, `take` чтобы избежать больших наборов результатов.
- Применяйте фильтры на ранних стадиях — применяйте фильтры времени и другие фильтры, чтобы уменьшить набор данных, особенно перед использованием функций преобразования и анализа, таких как [подстрока()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)или [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). В примере ниже функция различета [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) используется после уменьшения числа записей операторами фильтрации.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Содержит биты**— чтобы не искать подстроки в словах без необходимости, используйте `has` оператор вместо `contains` . [Узнайте об операторах строк](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Посмотрите в определенных столбцах**— посмотрите на определенный столбец, а не на полно текстовом поиске во всех столбцах. Не используйте для `*` проверки всех столбцов.
- **Для скорости чувствительный** к конкретному делу поиск более конкретный и, как правило, более емкий. Имена операторов строк с чувствительным к [делу,](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators) `has_cs` `contains_cs` например, и, как правило, заканчиваются `_cs` на . Вы также можете использовать оператор равного с чувствительностью к делу вместо `==` `=~` .
- **Размыть, не** извлекать — по [](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) возможности используйте оператор разбиение или функцию, например [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Избегайте `matches regex` оператора строки или [функции extract(),](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)в обеих из которых используется регулярное выражение. Зарезервировать использование регулярных выражений для более сложных сценариев. [Дополнительные информацию о функциях различета](#parse-strings)
- **Фильтровать таблицы, а не выражения**— не фильтруйте вычисляемую таблицу, если вы можете фильтровать столбец таблицы.
- **Нет трех символьных терминов**— избегайте сравнения или фильтрации с использованием терминов с тремя символами или меньше. Эти термины не индексироваться, и для их совпадения потребуется больше ресурсов.
- **Проект выборочно**— упростите понимание результатов, проецируемые только из нужных столбцов. Проецируемые отдельные столбцы перед выполнением операции [реализации](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) проектов или аналогичных операций также помогают повысить производительность.

## <a name="optimize-the-join-operator"></a>Оптимизация `join` оператора
Оператор [объединения объединяет](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) строки из двух таблиц путем совпадения значений в указанных столбцах. Используйте эти советы для оптимизации запросов, которые используют этот оператор.

- **Небольшая таблица слева**— оператор соединит записи в таблице слева от оператора join с записями `join` справа. Если таблица меньшего размеров слева, потребуется найти меньше записей, что ускоряет запрос. 

    В приведенной ниже таблице мы уменьшаем левую таблицу, чтобы охватить только три конкретных устройства, прежде чем присоединяться к ней с помощью ИД безопасности учетных `DeviceLogonEvents` `IdentityLogonEvents` записей.
 
    ```kusto
    DeviceLogonEvents 
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- Используйте внутренний привязок [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) — по [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) умолчанию при подмывке или в левой таблице по клавише слева по строкам для каждого совпадения с правой таблицей.  Если в левой таблице несколько строк с одинаковым значением для ключа, эти строки будут отсортированы, чтобы оставить одну случайную строку для каждого `join` уникального значения.

    Это поведение по умолчанию может не использовать важные сведения из левой таблицы, которые могут предоставлять полезные сведения. Например, в приведенном ниже запросе будет отобрано только одно сообщение электронной почты, содержащее определенное вложение, даже если это же вложение было отправлено с помощью нескольких сообщений электронной почты:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Чтобы решить это ограничение, [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) мы применяем внутренний примеся, указав, чтобы все строки в левой таблице со значениями, совпадающие в `kind=inner` правой части:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Присоедините записи из периода** времени — при расследовании событий безопасности аналитики будут искать связанные события, которые происходят за тот же период времени. Применение такого же подхода при использовании также дает преимущества производительности за счет уменьшения количества `join` проверяемой записи.
    
    В приведенном ниже запросе проверяется наличие событий для эмблемы в течение 30 минут после получения вредоносного файла:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- Применяйте фильтры времени с обеих сторон — даже если вы не изучаете конкретный период времени, применение фильтров времени как в левой, так и в правой таблицах может уменьшить количество записей для проверки и повышения `join` производительности. Запрос ниже применяется к обеим таблицам, чтобы он присоединялся только к записям за `Timestamp > ago(1h)` последний час:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Используйте подсказки для производительности**— используйте подсказки с оператором, чтобы у ручить тыловой части распределять нагрузку при запуске ресурсоемких `join` операций. [Узнайте больше о подсказках о подступах](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Например, подсказка рывка помогает повысить производительность запроса при объединении таблиц с помощью ключа с высокой стесностью ключа со множеством уникальных значений, например в **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** `AccountObjectId` запросе ниже:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    Подсказка **[вещания](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** помогает, если левая таблица небольшая (до 100 000 записей), а правая — очень большая. Например, в приведенной ниже запросе пытается присоединиться к  нескольким электронным письмам с определенными темами со всеми сообщениями, содержащими ссылки в `EmailUrlInfo` таблице:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Оптимизация `summarize` оператора
Оператор [сводки](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) объединяет содержимое таблицы. Используйте эти советы для оптимизации запросов, которые используют этот оператор.

- **Найдите отдельные значения**— как правило, используйте для поиска различных значений, `summarize` которые могут повторяться. Использовать его для сводные данные столбцов, которые не имеют повторяющихся значений, может быть ненужным.

    Хотя одно сообщение электронной почты может быть  частью нескольких событий, пример ниже не является эффективным, так как сетевой ИД сообщения для отдельного сообщения всегда поставляется с уникальным адресом `summarize` отправитель.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    Оператор можно легко заменить, что может привести к таким же результатам, одновременно потребляя `summarize` `project` меньше ресурсов:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    В следующем примере более эффективное использование, так как может быть несколько разных экземпляров адреса отправитель отправки электронной почты на один `summarize` и тот же адрес получателя. Такие сочетания менее четки и могут иметь дубликаты.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Мешайте** запросу — хотя лучше всего использовать в столбцах с повторяющимися значениями, одинаковые столбцы также могут иметь высокий уровень высокой высокой высоты или большое количество `summarize` уникальных значений.  Как и в случае с оператором, вы также можете применять подсказку мякиша для распределения нагрузки на обработку и потенциально повысить производительность при работе со столбцами с `join` [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` высокой тщательностью.

    В приведенного ниже запросе учитывается отдельный адрес электронной почты получателя, который может работать в сотнях `summarize` тысяч в крупных организациях. Для повышения производительности он `hint.shufflekey` включает:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Сценарии запросов

### <a name="identify-unique-processes-with-process-ids"></a>Определение уникальных процессов с помощью ИД процессов
Идентификаторы процессов (PID) в Windows перерабатываются и используются для новых процессов. Они не могут служить уникальными идентификаторами для определенных процессов сами по себе.

Чтобы создать уникальный идентификатор для процесса на определенном компьютере, идентификатор процесса нужно использовать вместе со временем создания процесса. При объединении или обобщении данных по процессам рекомендуется включать столбцы для идентификатора компьютера (либо `DeviceId`, либо`DeviceName`), идентификатора процесса (`ProcessId` или `InitiatingProcessId`) и времени создания процесса (`ProcessCreationTime` или `InitiatingProcessCreationTime`)

В приведенном ниже примере запроса обнаружены процессы, имеющие доступ к более чем 10 IP-адресам через порт 445 (SMB) с одновременным возможным сканированием файловых ресурсов.

Пример запроса
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

В запросе указаны одновременно и `InitiatingProcessId`, и `InitiatingProcessCreationTime`. Благодаря этому запрос относится к одному единственному процессу, и при этом исключаются многочисленные другие процессы с аналогичным идентификатором процесса.

### <a name="query-command-lines"></a>Командные строки запроса
Создать командную строку для выполнения задачи можно разными способами. Например, злоумышленник может ссылаться на файл изображения без пути, без расширения файла, с помощью переменных среды или с кавычками. Злоумышленник также может изменить порядок параметров или добавить несколько кавычках и пробелов.

Чтобы создать более длительные запросы вокруг командных строк, следуйте следующим методикам:

- Определите известные процессы  (например,net.exe *илиpsexec.exe)* путем совпадения в полях имени файла вместо фильтрации по самой командной строке.
- Разчет разделов командной строки с помощью [функции parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- При запросе аргументов командной строки искать точное совпадение для нескольких несвязанных аргументов в определенном порядке не имеет смысла. Вместо этого используются регулярные выражения или несколько отдельных аргументов, содержащих операторы.
- Совпадения используются без учета регистра. Например, используйте `=~` , и вместо , и `in~` `contains` `==` `in` `contains_cs` .
- Чтобы устранить методы обфускации командной строки, рекомендуется удалить кавычка, заменить запятые пробелами и заменить несколько последовательных пробелов одним пробелом. Существуют более сложные методы обфускации, которые требуют других подходов, но эти изменения могут помочь решить распространенные из них.

В следующих примерах демонстрируются различные способы создания запроса, *который* ищет файлnet.exeостановить службу брандмауэра "MpsSvc":

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

### <a name="ingest-data-from-external-sources"></a>Ingest data from external sources
Чтобы включить длинные списки или большие таблицы в запрос, используйте оператор [externaldata,](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) чтобы получить данные из указанного URI. Вы можете получить данные из файлов в форматах TXT, CSV, JSON и [других форматах.](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats) В примере ниже показано, как можно использовать обширный список вредоносных хешов SHA-256, предоставляемых MalwareBazaar (abuse.ch) для проверки вложений в сообщениях электронной почты:

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a>Строки parse
Существуют различные функции, которые можно использовать для эффективной обработки строк, которые требуют различета или преобразования. 

| String | Функция | Пример использования |
|--|--|--|
| Командные строки | [parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | Извлекать команду и все аргументы. | 
| Пути | [parse_path()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | Извлекать разделы пути к файлу или папке. |
| Номера версий | [parse_version()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Декодировать номер версии с четырьмя разделами и до восьми символов на раздел. Используйте анализ данных для сравнения возраста версии. |
| IPv4-адреса | [parse_ipv4()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Преобразуйте IPv4-адрес в длинное integer. Чтобы сравнить IPv4-адреса без их преобразования, используйте [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| IPv6-адреса | [parse_ipv6()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Преобразуем IPv4- или IPv6-адрес в каноническую нотацию IPv6. Для сравнения IPv6-адресов используйте [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Чтобы узнать обо всех поддерживаемых функциях разбиение, ознакомьтесь [со строками Kusto.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions) 

## <a name="related-topics"></a>Статьи по теме
- [Документация по языку запросов Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Квоты и параметры использования](advanced-hunting-limits.md)
- [Обработка ошибок расширенных поисков](advanced-hunting-errors.md)
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
