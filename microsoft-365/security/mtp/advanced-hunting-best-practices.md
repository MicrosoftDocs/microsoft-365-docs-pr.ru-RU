---
title: Расширенные рекомендации по поиску запросов поиска в защитнике Microsoft 365
description: Сведения о том, как создавать быстрые, эффективные и бесплатные сообщения о поиске угроз с помощью расширенного запроса
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, схема, Кусто, предотвращение времени ожидания, командные строки, идентификатор процесса, оптимизация, рекомендации, анализ, присоединение, подведение итогов
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 2b2ac519e63e5a7cba648dba67d2780bb7600e14
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843076"
---
# <a name="advanced-hunting-query-best-practices"></a>Рекомендации по использованию запросов расширенного выслеживания

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защитник Microsoft 365

Используйте эти рекомендации для ускорения получения результатов и предотвращения превышения времени ожидания при выполнении сложных запросов. Дополнительные руководства по повышению производительности запросов см. в статье [Рекомендации по использованию запросов Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Общие сведения о квотах ресурсов ЦП
В зависимости от размера у каждого клиента есть доступ к заданному объему ресурсов ЦП, выделенному для запуска расширенных запросов на поиск. Для получения подробных сведений о различных ограничениях для служб [Ознакомьтесь со сведениями о дополнительных квотах и параметрах использования](advanced-hunting-limits.md).

Клиенты, которые регулярно запускают несколько запросов, должны отслеживать потребление и применять рекомендации по оптимизации, описанные в этой статье, для минимизации сбоев, возникших в результате превышения квот или параметров использования.

## <a name="general-optimization-tips"></a>Общие рекомендации по оптимизации

- **Изменение размера новых запросов** — если вы подозреваете, что запрос возвратит большой набор результатов, сначала оцените его с помощью [оператора Count](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator). Используйте [ограничения](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) или синонимы `take` , чтобы избежать больших наборов результатов.
- **Примените фильтры раньше** , примените фильтры времени и другие фильтры для сокращения набора данных, особенно перед использованием функций преобразования и синтаксического анализа, таких как [substring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [Replace ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [Trim ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [ToUpper ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)или [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). В приведенном ниже примере функция анализа [екстрактжсон ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) используется после уменьшения числа записей в операторах фильтрации.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Содержит ритм** , чтобы избежать необязательного поиска подстрок в словах, используйте оператор, `has` а не `contains` . [Сведения об строковых операторах](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Искать в определенных столбцах** — искать в определенном столбце, а не выполнять полнотекстовый поиск по всем столбцам. Не используйте `*` для проверки всех столбцов.
- **С учетом регистра для скорости** — Поиск с учетом регистра — более конкретный и более производительный. Имена [строковых операторов](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)с учетом регистра, такие как `has_cs` и `contains_cs` , как правило, заканчивается на `_cs` . Кроме того, можно использовать оператор равенства с учетом регистра, `==` а не `=~` .
- **Parse, не извлекайте** , когда это возможно, используйте [оператор Parse](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) или функцию синтаксического анализа, например [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Избегайте `matches regex` строкового оператора или [функции extract ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), в которых используется регулярное выражение. Зарезервируйте использование регулярных выражений для более сложных сценариев. [Подробнее о функциях синтаксического анализа](#parse-strings)
- **Фильтрация таблиц без выражений** — не отфильтровывайте вычисляемый столбец, если вы можете выполнить фильтрацию по столбцу таблицы.
- **Отсутствие трех символов** — Избегайте сравнения или фильтрации с использованием терминов, состоящих из трех или менее трех символов. Эти термины не индексируются и их сопоставлению требуют больше ресурсов.
- **Проект выборочно** — Сделайте результаты более понятными, выполнив только необходимые столбцы. Запроектировать определенные столбцы перед выполнением [присоединения](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) или аналогичных операций также помогут увеличить производительность.

## <a name="optimize-the-join-operator"></a>Оптимизация `join` оператора
[Оператор Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) объединяет строки из двух таблиц, сопоставляя значения в указанных столбцах. Используйте приведенные ниже советы для оптимизации запросов, использующих этот оператор.

- **Таблица меньшего размера слева** : `join` оператор сопоставляет записи в таблице, расположенной слева от оператора Join, с записями справа. Если таблица меньше, чем слева, тем меньше записей потребуется сопоставлять, таким образом ускоряя запрос. 

    В приведенной ниже таблице мы уменьшаем левую таблицу, `DeviceLogonEvents` чтобы охватить только три определенных устройства перед присоединением их с `IdentityLogonEvents` помощью SID учетных записей.
 
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

- **Используйте флаг INNER-JOIN** [, используемый по умолчанию](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) , или [иннеруникуе-Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) , возвращает строки в левой таблице с помощью ключа соединения, чтобы возвратить строку для каждого совпадения с правой таблицей. Если в левой таблице есть несколько строк с одинаковым значением для `join` ключа, эти строки будут повторяться, чтобы оставить одну произвольную строку для каждого уникального значения.

    Это поведение по умолчанию может оставить важную информацию из левой таблицы, которая поможет вам получить полезную информацию. Например, приведенный ниже запрос будет содержать только одно сообщение электронной почты, содержащее определенное вложение, даже если оно было отправлено несколькими сообщениями электронной почты:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Чтобы устранить это ограничение, мы используем флаг [внутреннего соединения](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) , указав `kind=inner` для отображения всех строк в левой таблице с соответствующими значениями справа:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Присоединение записей из временного окна** — при изучении событий безопасности аналитики ищут связанные события, происходящие за один и тот же период времени. Применение того же подхода при использовании `join` повышения производительности также уменьшает число проверяемых записей.
    
    В запросе ниже выполняется проверка событий входа в систему в течение 30 минут после получения вредоносного файла:

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
- **Применить фильтры времени на обеих сторонах** , даже если вы не изучаете конкретное временное окно, применение фильтров времени в левой и правой таблицах позволяет сократить число проверяемых записей и повысить `join` производительность. Приведенный ниже запрос применяется `Timestamp > ago(1h)` к обеим таблицам, чтобы присоединяться только к записям за последний час:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Использование подсказок для повышения производительности** — используйте подсказки с `join` оператором, чтобы указать, что сервер будет распределять нагрузку при выполнении операций, интенсивно использующих ресурсы. [Дополнительные сведения о подсказках по объединению](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Например, **[Подсказка в случайном порядке](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** помогает увеличить производительность запросов при соединении таблиц с помощью ключа с большим количеством уникальных значений, например, `AccountObjectId` в следующем запросе:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    **[Подсказка о вещании](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** помогает в том случае, если левая таблица мала (до 100 000 записей), а правая таблица чрезвычайно велика. Например, приведенный ниже запрос пытается присоединиться к нескольким сообщениям, которые содержат конкретные темы со _всеми_ сообщениями, содержащими ссылки в `EmailUrlInfo` таблице:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Оптимизация `summarize` оператора
[Оператор суммирования](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) собирает содержимое таблицы. Используйте приведенные ниже советы для оптимизации запросов, использующих этот оператор.

- **Поиск различных значений** — в общем случае используйте `summarize` для поиска различных значений, которые могут быть повторяющимися. Она может быть ненужной для статистического использования столбцов без повторяющихся значений.

    Хотя одно сообщение электронной почты может быть частью нескольких событий, приведенный ниже пример _не_ является эффективным, `summarize` так как в качестве идентификатора сетевого сообщения для отдельной электронной почты всегда используется уникальный адрес отправителя.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    `summarize`Оператор можно легко заменять `project` , при этом результат может быть одинаковым при использовании меньшего числа ресурсов:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    Ниже приведен пример более эффективного использования, `summarize` так как может быть несколько отдельных экземпляров адреса отправителя, которые отправляют электронную почту на один и тот же адрес получателя. Такие сочетания не отличаются друг от друга и, скорее всего, имеют дубликаты.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- В **случайном порядке для запроса** — хотя `summarize` в столбцах с повторяющимися значениями одни и те же столбцы также _high cardinality_ могут иметь большое количество уникальных значений. Как и `join` оператор, вы также можете применить [подсказку в случайном порядке](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) , `summarize` чтобы распределять нагрузку обработки и потенциально повышать производительность при работе со столбцами с большим количеством элементов.

    В запросе ниже показано `summarize` , как подсчитать различные адреса электронной почты получателей, которые могут выполняться на сотнях тысяч в крупных организациях. Чтобы увеличить производительность, он включает `hint.shufflekey` :

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Сценарии запросов

### <a name="identify-unique-processes-with-process-ids"></a>Определение уникальных процессов с помощью идентификаторов процессов
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
Создать командную строку для выполнения задачи можно разными способами. Например, злоумышленник может ссылаться на файл изображения без пути, без расширения имени файла, с использованием переменных среды или с кавычками. Злоумышленник также может изменить порядок параметров или добавить несколько кавычек и пробелов.

Чтобы создать более устойчивые запросы вокруг командных строк, примените следующие рекомендации:

- Определите известные процессы (например, *net.exe* или *psexec.exe* ), выполнив соответствующую команду в поле имя файла, а не в самом окне командной строки.
- Анализ разделов командной строки с помощью [функции parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- При запросе аргументов командной строки искать точное совпадение для нескольких несвязанных аргументов в определенном порядке не имеет смысла. Вместо этого используются регулярные выражения или несколько отдельных аргументов, содержащих операторы.
- Совпадения используются без учета регистра. Например, используйте `=~` , `in~` , и `contains` вместо `==` , `in` и `contains_cs` .
- Чтобы уменьшить методы запутывания командной строки, рекомендуется удалить кавычки, заменив запятые пробелами и заменив несколько последовательных пробелов одним пробелом. Существуют более сложные методы запутывания, требующие других подходов, но эти настройки могут помочь в устранении распространенных задач.

В следующих примерах показаны различные способы создания запроса, который ищет *net.exe* файла для остановки службы брандмауэра "MPSSVC":

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

### <a name="ingest-data-from-external-sources"></a>Прием данных из внешних источников
Чтобы включить в запрос длинные списки или большие таблицы, используйте [оператор екстерналдата](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) для приема данных из указанного URI. Вы можете получать данные из файлов в формате TXT, CSV, JSON или [других форматах](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats). В приведенном ниже примере показано, как можно использовать обширный список хеш-кодов SHA-256, предоставляемых службой Малваребазаар (abuse.ch), для проверки вложений в сообщениях электронной почты.

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

### <a name="parse-strings"></a>Синтаксический анализ строк
Существует несколько функций, которые можно использовать для эффективного обработки строк, требующих синтаксического анализа или преобразования. 

| String | Функция | Пример использования |
|--|--|--|
| Командная строка | [parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | Извлеките команду и все аргументы. | 
| Пути | [parse_path ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | Извлечение разделов пути к файлу или папке. |
| Номера версий | [parse_version ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Разработайте номер версии, содержащий до четырех разделов и до восьми символов в разделе. Используйте проанализированные данные для сравнения возраста версий. |
| IPv4-адреса | [parse_ipv4 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Преобразование IPv4-адреса в длинное целое число. Для сравнения IPv4-адресов без их преобразования используйте [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| IPv6-адреса | [parse_ipv6 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Преобразование IPv4-или IPv6-адреса в каноническую нотацию IPv6. Чтобы сравнить IPv6-адреса, используйте [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Чтобы узнать обо всех поддерживаемых функциях синтаксического анализа, [прочитайте о функциях строк Кусто](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions). 

## <a name="related-topics"></a>Статьи по теме
- [Документация по языку запросов Кусто](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Квоты и параметры использования](advanced-hunting-limits.md)
- [Обработка дополнительных ошибок при поиске](advanced-hunting-errors.md)
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
