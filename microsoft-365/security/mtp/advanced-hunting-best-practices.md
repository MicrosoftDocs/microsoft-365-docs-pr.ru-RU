---
title: Передовые методы запроса на охоту в Microsoft 365 Defender
description: Узнайте, как создавать запросы на быструю, эффективную и без ошибок охоту на угрозы с помощью расширенных методов охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema, kusto, avoid timeout, command lines, process id, optimize, best practice, parse, join, summarize
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
ms.openlocfilehash: 3e198f4a5800475b0c8efcd24e05ea00b8a17186
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925799"
---
# <a name="advanced-hunting-query-best-practices"></a>Рекомендации по использованию запросов расширенного выслеживания

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Применяем эти рекомендации, чтобы быстрее получать результаты и избегать периодов времени во время работы сложных запросов. Дополнительные руководства по повышению производительности запросов см. в статье [Рекомендации по использованию запросов Kusto](/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Понимание квот ресурсов ЦП
В зависимости от его размера каждый клиент имеет доступ к определенному объему ресурсов ЦП, выделенным для работы с расширенными запросами на охоту. Подробные сведения о различных ограничениях службы читайте в материале "Расширенные квоты на охоту и [параметры использования".](advanced-hunting-limits.md)

Клиенты, регулярно запускающие несколько запросов, должны отслеживать потребление и применять рекомендации по оптимизации в этой статье, чтобы свести к минимуму нарушения в результате превышения квот или параметров использования.

## <a name="general-optimization-tips"></a>Общие советы по оптимизации

- **Размер новых запросов**— Если вы подозреваете, что запрос возвращает большой набор результатов, сначала оцените его с помощью оператора [подсчета.](/azure/data-explorer/kusto/query/countoperator) Используйте [ограничение](/azure/data-explorer/kusto/query/limitoperator) или его синоним, `take` чтобы избежать больших наборов результатов.
- Применяйте фильтры на ранних стадиях **—** применяйте фильтры времени и другие фильтры, чтобы уменьшить набор данных, особенно перед использованием функций преобразования и анализа, таких как [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction) [или parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). В приведенной ниже примере [](/azure/data-explorer/kusto/query/extractjsonfunction) функция размыва используется после того, как операторы фильтрации сократили количество записей.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Имеет биты содержит**- Чтобы избежать поиска подстройки в словах излишне, используйте `has` оператора, а `contains` не . [Узнайте о операторах строки](/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Посмотрите в определенных столбцах**. Посмотрите в определенный столбец, а не выполняется полный текстовый поиск во всех столбцах. Не используйте для `*` проверки всех столбцов.
- **Деликатный для скорости**— поиски, чувствительные к конкретным случаям, являются более конкретными и, как правило, более исполняемыми. Имена чувствительных к делу [операторов](/azure/data-explorer/kusto/query/datatypes-string-operators)строк, таких как `has_cs` и , как `contains_cs` правило, заканчиваются `_cs` . Кроме того, можно использовать оператора равного с чувствительностью к `==` делу. `=~`
- **Размыть, не** извлекать -По [](/azure/data-explorer/kusto/query/parseoperator) возможности, используйте оператора размыва или функции размыва, [как parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). Избегайте `matches regex` оператора строки или [функции extract()](/azure/data-explorer/kusto/query/extractfunction)( оба из которых используют регулярное выражение. Зарезервировать использование регулярного выражения для более сложных сценариев. [Узнайте больше о функциях размыкания](#parse-strings)
- **Фильтрация таблиц не выражений**— не фильтруйте вычисляемую колонку, если можно фильтровать столбец таблицы.
- **Нет трех характерных терминов**— избегайте сравнения или фильтрации с помощью терминов с тремя символами или меньше. Эти термины не индексироваться, и их соответствие потребует дополнительных ресурсов.
- **Выборочно** проект — упростите понимание результатов, проецив только нужные столбцы. Проецация определенных столбцов перед запуском [присоединяющихся](/azure/data-explorer/kusto/query/joinoperator) или аналогичных операций также помогает повысить производительность.

## <a name="optimize-the-join-operator"></a>Оптимизация `join` оператора
Оператор [объединения объединяет](/azure/data-explorer/kusto/query/joinoperator) строки из двух таблиц, соединяя значения в указанных столбцах. Используйте эти советы для оптимизации запросов, которые используют этот оператор.

- **Более малая** таблица слева — оператор соединяет записи в таблице слева от заявления о присоединиться к записям `join` справа. Если таблица меньше слева, потребуется соблюсти меньше записей, что ускорит запрос. 

    В таблице ниже мы уменьшаем левую таблицу, чтобы охватить только три конкретных устройства перед присоединением к ней с помощью `DeviceLogonEvents` `IdentityLogonEvents` SID-данных учетной записи.
 
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

- **Используйте** внутренний примыкающий к нему аромат — аромат соедините по умолчанию или строки deduplicates [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) в левой таблице ключом соединителя перед возвращением строки для каждого совпадения в правую таблицу. [](/azure/data-explorer/kusto/query/joinoperator#join-flavors) Если в левой таблице имеется несколько строк с одинаковым значением для ключа, эти строки будут отлажены, чтобы оставить одну рандомную строку для каждого `join` уникального значения.

    Это поведение по умолчанию может оставить важные сведения из левой таблицы, которые могут предоставить полезные сведения. Например, в приведенном ниже запросе будет содержаться только одно сообщение, содержащее определенное вложение, даже если это же вложение было отправлено с помощью нескольких сообщений электронной почты:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Чтобы решить это ограничение, мы применяем аромат [внутреннего](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) присоединяния, указав, чтобы показать все строки в левой таблице со значениями в `kind=inner` правой части:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Регистрация записей из окне** времени . При расследовании событий безопасности аналитики изучают связанные события, которые происходят примерно в тот же период времени. Применение такого же подхода при использовании также приносит пользу производительности, уменьшая количество записей `join` для проверки.
    
    Запрос ниже проверяет события с логотипом в течение 30 минут после получения вредоносного файла:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **Применение фильтров** времени с обеих сторон — Даже если вы не изучаете определенное окно времени, применение фильтров времени как на левом, так и на правом столах может уменьшить количество записей для проверки и повышения `join` производительности. Ниже приведен запрос, применимый к обеим таблицам, чтобы он присоединялся только к записям за `Timestamp > ago(1h)` прошедший час:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Используйте подсказки для производительности**— Используйте подсказки с оператором, чтобы проинструктация backend для распределения нагрузки при работе с ресурсоемкими `join` операциями. [Дополнительные новости о подсказках о вступив](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Например, подсказка перетасовки помогает повысить производительность запроса при присоединении к таблицам с помощью ключа с высокой кардиналиальностью — ключа с множеством уникальных значений, таких как в нижеуказаемом **[](/azure/data-explorer/kusto/query/shufflequery)** `AccountObjectId` запросе:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    Подсказка **[на трансляцию](/azure/data-explorer/kusto/query/broadcastjoin)** помогает, если левая таблица небольшая (до 100 000 записей), а правая — очень большая. Например, в приведенной ниже области запрос пытается присоединиться к  нескольким электронным письмам с определенными субъектами со всеми сообщениями, содержащими ссылки в `EmailUrlInfo` таблице:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Оптимизация `summarize` оператора
Оператор [сводки](/azure/data-explorer/kusto/query/summarizeoperator) агрегирует содержимое таблицы. Используйте эти советы для оптимизации запросов, которые используют этот оператор.

- **Найдите различные значения**. В общем, используйте `summarize` для поиска различных значений, которые могут быть повторяющимися. Это может быть ненужным, чтобы использовать его для агрегированных столбцов, которые не имеют повторяющихся значений.

    Хотя одно сообщение электронной почты может быть  частью нескольких событий, пример ниже не является эффективным, так как сетевой ИД сообщения для отдельного электронного письма всегда поставляется с уникальным адресом `summarize` отправитель.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    Оператор можно легко заменить, что дает потенциально те же результаты, но при этом потребляет `summarize` `project` меньше ресурсов:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    В следующем примере используется более эффективное использование, так как может быть несколько различных экземпляров адреса отправитель отправки электронной почты на `summarize` тот же адрес получателя. Такие комбинации менее отличаются друг от друга и могут иметь дубликаты.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Перетасовка** запроса . Хотя лучше всего использовать в столбцах с повторяющимися значениями, те же столбцы также могут иметь высокий кардинальный характер или большое количество `summarize`  уникальных значений. Как и оператор, вы также можете применить подсказку перетасовки для распределения нагрузки на обработку и потенциально повысить производительность при работе на столбцах `join` с [](/azure/data-explorer/kusto/query/shufflequery) `summarize` высокой кардинальностью.

    В приведенного ниже запросе используется для подсчета определенного адреса электронной почты получателя, который может работать в сотнях тысяч `summarize` в крупных организациях. Чтобы повысить производительность, он включает `hint.shufflekey` в себя:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Сценарии запросов

### <a name="identify-unique-processes-with-process-ids"></a>Определение уникальных процессов с помощью идентификации процессов
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

### <a name="query-command-lines"></a>Строки команд запросов
Создать командную строку для выполнения задачи можно разными способами. Например, злоумышленник может ссылаться на файл изображений без пути, без расширения файла, с помощью переменных среды или с кавычками. Злоумышленник также может изменить порядок параметров или добавить несколько кавычках и пробелах.

Чтобы создать более надежные запросы вокруг командных строк, применяйте следующие практики:

- Определите известные процессы *(например,net.exe* *илиpsexec.exe)* путем совпадения на полях имен файлов, а не фильтрации на самой командной строке.
- Разделы командной строки parse с [помощью функции parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) 
- При запросе аргументов командной строки искать точное совпадение для нескольких несвязанных аргументов в определенном порядке не имеет смысла. Вместо этого используются регулярные выражения или несколько отдельных аргументов, содержащих операторы.
- Совпадения используются без учета регистра. Например, используйте `=~` `in~` , и вместо , `contains` и `==` `in` `contains_cs` .
- Чтобы смягчить методы запутывания командной строки, рекомендуется удалить кавычка, заменить запятые пробелами и заменить несколько последовательных пробелов одним пространством. Существуют более сложные методы запутывания, которые требуют других подходов, но эти настройки могут помочь в решении распространенных.

В следующих примерах покажите различные способы создания запроса, *который* ищет файлnet.exe, чтобы остановить службу брандмауэра "MpsSvc":

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
Чтобы включить длинные списки или большие таблицы в запрос, используйте [оператора externaldata](/azure/data-explorer/kusto/query/externaldata-operator) для пользования данными из указанного URI. Вы можете получать данные из файлов в TXT, CSV, JSON или [других форматах.](/azure/data-explorer/ingestion-supported-formats) В приведенной ниже примере показано, как можно использовать обширный список хеш-файлов SHA-256, предоставляемых MalwareBazaar (abuse.ch) для проверки вложений в сообщениях электронной почты:

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
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a>Строки parse
Существуют различные функции, которые можно использовать для эффективного обработки строк, которые нуждаются в размыве или преобразовании. 

| String | Функция | Пример использования |
|--|--|--|
| Командные строки | [parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) | Извлекать команду и все аргументы. | 
| Пути | [parse_path()](/azure/data-explorer/kusto/query/parsepathfunction) | Извлечение разделов пути файла или папки. |
| Номера версий | [parse_version()](/azure/data-explorer/kusto/query/parse-versionfunction) | Деконструировать номер версии с четырьмя разделами и до восьми символов в разделе. Чтобы сравнить возраст версии, используйте разносчетные данные. |
| Адреса IPv4 | [parse_ipv4()](/azure/data-explorer/kusto/query/parse-ipv4function) | Преобразование адреса IPv4 в длинный ряд. Чтобы сравнить адреса IPv4 без их преобразования, [используйте ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| Адреса IPv6 | [parse_ipv6()](/azure/data-explorer/kusto/query/parse-ipv6function)  | Преобразование адреса IPv4 или IPv6 в каноническую нотацию IPv6. Чтобы сравнить адреса IPv6, используйте [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Чтобы узнать обо всех поддерживаемых функциях размыва, [ознакомьтесь с функциями строк Kusto.](/azure/data-explorer/kusto/query/scalarfunctions#string-functions) 

## <a name="related-topics"></a>Родственные темы
- [Документация по языку запросов Kusto](/azure/data-explorer/kusto/query/)
- [Квоты и параметры использования](advanced-hunting-limits.md)
- [Обработка ошибок, совершенных в области охоты](advanced-hunting-errors.md)
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)