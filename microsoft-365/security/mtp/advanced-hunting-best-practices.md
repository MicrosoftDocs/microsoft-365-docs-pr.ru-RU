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
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="c3c7d-104">Рекомендации по использованию запросов расширенного выслеживания</span><span class="sxs-lookup"><span data-stu-id="c3c7d-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c3c7d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c3c7d-105">**Applies to:**</span></span>
- <span data-ttu-id="c3c7d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3c7d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c3c7d-107">Применив эти рекомендации, вы можете быстрее получать результаты и избегать периодов времени в ходе работы со сложными запросами.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="c3c7d-108">Дополнительные руководства по повышению производительности запросов см. в статье [Рекомендации по использованию запросов Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="c3c7d-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="c3c7d-109">Понимание квот ресурсов ЦП</span><span class="sxs-lookup"><span data-stu-id="c3c7d-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="c3c7d-110">В зависимости от размера каждый клиент имеет доступ к определенному объему ресурсов ЦП, выделенным для запросов на расширенный поиск.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="c3c7d-111">Подробные сведения о различных ограничениях службы можно узнать о квотах и параметрах использования для расширенных [сервисов.](advanced-hunting-limits.md)</span><span class="sxs-lookup"><span data-stu-id="c3c7d-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="c3c7d-112">Клиенты, регулярно запускающие несколько запросов, должны отслеживать потребление и применять рекомендации по оптимизации в этой статье, чтобы свести к минимуму нарушения в результате превышения квот или параметров использования.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="c3c7d-113">Общие советы по оптимизации</span><span class="sxs-lookup"><span data-stu-id="c3c7d-113">General optimization tips</span></span>

- <span data-ttu-id="c3c7d-114">**Размер новых запросов**— если вы подозреваете, что запрос возвратит большой набор результатов, сначала оцените его с помощью оператора [подсчета.](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)</span><span class="sxs-lookup"><span data-stu-id="c3c7d-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="c3c7d-115">Используйте [ограничение](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) или его синоним, `take` чтобы избежать больших наборов результатов.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="c3c7d-116">Применяйте фильтры на ранних стадиях — применяйте фильтры времени и другие фильтры, чтобы уменьшить набор данных, особенно перед использованием функций преобразования и анализа, таких как [подстрока()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)или [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="c3c7d-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="c3c7d-117">В примере ниже функция различета [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) используется после уменьшения числа записей операторами фильтрации.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="c3c7d-118">**Содержит биты**— чтобы не искать подстроки в словах без необходимости, используйте `has` оператор вместо `contains` .</span><span class="sxs-lookup"><span data-stu-id="c3c7d-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="c3c7d-119">Узнайте об операторах строк</span><span class="sxs-lookup"><span data-stu-id="c3c7d-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="c3c7d-120">**Посмотрите в определенных столбцах**— посмотрите на определенный столбец, а не на полно текстовом поиске во всех столбцах.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="c3c7d-121">Не используйте для `*` проверки всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="c3c7d-122">**Для скорости чувствительный** к конкретному делу поиск более конкретный и, как правило, более емкий.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="c3c7d-123">Имена операторов строк с чувствительным к [делу,](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators) `has_cs` `contains_cs` например, и, как правило, заканчиваются `_cs` на .</span><span class="sxs-lookup"><span data-stu-id="c3c7d-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="c3c7d-124">Вы также можете использовать оператор равного с чувствительностью к делу вместо `==` `=~` .</span><span class="sxs-lookup"><span data-stu-id="c3c7d-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="c3c7d-125">**Размыть, не** извлекать — по [](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) возможности используйте оператор разбиение или функцию, например [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="c3c7d-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="c3c7d-126">Избегайте `matches regex` оператора строки или [функции extract(),](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)в обеих из которых используется регулярное выражение.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="c3c7d-127">Зарезервировать использование регулярных выражений для более сложных сценариев.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="c3c7d-128">Дополнительные информацию о функциях различета</span><span class="sxs-lookup"><span data-stu-id="c3c7d-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="c3c7d-129">**Фильтровать таблицы, а не выражения**— не фильтруйте вычисляемую таблицу, если вы можете фильтровать столбец таблицы.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="c3c7d-130">**Нет трех символьных терминов**— избегайте сравнения или фильтрации с использованием терминов с тремя символами или меньше.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="c3c7d-131">Эти термины не индексироваться, и для их совпадения потребуется больше ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="c3c7d-132">**Проект выборочно**— упростите понимание результатов, проецируемые только из нужных столбцов.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="c3c7d-133">Проецируемые отдельные столбцы перед выполнением операции [реализации](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) проектов или аналогичных операций также помогают повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="c3c7d-134">Оптимизация `join` оператора</span><span class="sxs-lookup"><span data-stu-id="c3c7d-134">Optimize the `join` operator</span></span>
<span data-ttu-id="c3c7d-135">Оператор [объединения объединяет](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) строки из двух таблиц путем совпадения значений в указанных столбцах.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="c3c7d-136">Используйте эти советы для оптимизации запросов, которые используют этот оператор.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="c3c7d-137">**Небольшая таблица слева**— оператор соединит записи в таблице слева от оператора join с записями `join` справа.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="c3c7d-138">Если таблица меньшего размеров слева, потребуется найти меньше записей, что ускоряет запрос.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="c3c7d-139">В приведенной ниже таблице мы уменьшаем левую таблицу, чтобы охватить только три конкретных устройства, прежде чем присоединяться к ней с помощью ИД безопасности учетных `DeviceLogonEvents` `IdentityLogonEvents` записей.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="c3c7d-140">Используйте внутренний привязок [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) — по [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) умолчанию при подмывке или в левой таблице по клавише слева по строкам для каждого совпадения с правой таблицей. </span><span class="sxs-lookup"><span data-stu-id="c3c7d-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="c3c7d-141">Если в левой таблице несколько строк с одинаковым значением для ключа, эти строки будут отсортированы, чтобы оставить одну случайную строку для каждого `join` уникального значения.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="c3c7d-142">Это поведение по умолчанию может не использовать важные сведения из левой таблицы, которые могут предоставлять полезные сведения.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="c3c7d-143">Например, в приведенном ниже запросе будет отобрано только одно сообщение электронной почты, содержащее определенное вложение, даже если это же вложение было отправлено с помощью нескольких сообщений электронной почты:</span><span class="sxs-lookup"><span data-stu-id="c3c7d-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="c3c7d-144">Чтобы решить это ограничение, [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) мы применяем внутренний примеся, указав, чтобы все строки в левой таблице со значениями, совпадающие в `kind=inner` правой части:</span><span class="sxs-lookup"><span data-stu-id="c3c7d-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="c3c7d-145">**Присоедините записи из периода** времени — при расследовании событий безопасности аналитики будут искать связанные события, которые происходят за тот же период времени.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="c3c7d-146">Применение такого же подхода при использовании также дает преимущества производительности за счет уменьшения количества `join` проверяемой записи.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="c3c7d-147">В приведенном ниже запросе проверяется наличие событий для эмблемы в течение 30 минут после получения вредоносного файла:</span><span class="sxs-lookup"><span data-stu-id="c3c7d-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="c3c7d-148">Применяйте фильтры времени с обеих сторон — даже если вы не изучаете конкретный период времени, применение фильтров времени как в левой, так и в правой таблицах может уменьшить количество записей для проверки и повышения `join` производительности.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="c3c7d-149">Запрос ниже применяется к обеим таблицам, чтобы он присоединялся только к записям за `Timestamp > ago(1h)` последний час:</span><span class="sxs-lookup"><span data-stu-id="c3c7d-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="c3c7d-150">**Используйте подсказки для производительности**— используйте подсказки с оператором, чтобы у ручить тыловой части распределять нагрузку при запуске ресурсоемких `join` операций.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="c3c7d-151">Узнайте больше о подсказках о подступах</span><span class="sxs-lookup"><span data-stu-id="c3c7d-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="c3c7d-152">Например, подсказка рывка помогает повысить производительность запроса при объединении таблиц с помощью ключа с высокой стесностью ключа со множеством уникальных значений, например в **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** `AccountObjectId` запросе ниже:</span><span class="sxs-lookup"><span data-stu-id="c3c7d-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="c3c7d-153">Подсказка **[вещания](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** помогает, если левая таблица небольшая (до 100 000 записей), а правая — очень большая.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="c3c7d-154">Например, в приведенной ниже запросе пытается присоединиться к  нескольким электронным письмам с определенными темами со всеми сообщениями, содержащими ссылки в `EmailUrlInfo` таблице:</span><span class="sxs-lookup"><span data-stu-id="c3c7d-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="c3c7d-155">Оптимизация `summarize` оператора</span><span class="sxs-lookup"><span data-stu-id="c3c7d-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="c3c7d-156">Оператор [сводки](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) объединяет содержимое таблицы.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="c3c7d-157">Используйте эти советы для оптимизации запросов, которые используют этот оператор.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="c3c7d-158">**Найдите отдельные значения**— как правило, используйте для поиска различных значений, `summarize` которые могут повторяться.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="c3c7d-159">Использовать его для сводные данные столбцов, которые не имеют повторяющихся значений, может быть ненужным.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="c3c7d-160">Хотя одно сообщение электронной почты может быть  частью нескольких событий, пример ниже не является эффективным, так как сетевой ИД сообщения для отдельного сообщения всегда поставляется с уникальным адресом `summarize` отправитель.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="c3c7d-161">Оператор можно легко заменить, что может привести к таким же результатам, одновременно потребляя `summarize` `project` меньше ресурсов:</span><span class="sxs-lookup"><span data-stu-id="c3c7d-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="c3c7d-162">В следующем примере более эффективное использование, так как может быть несколько разных экземпляров адреса отправитель отправки электронной почты на один `summarize` и тот же адрес получателя.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="c3c7d-163">Такие сочетания менее четки и могут иметь дубликаты.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="c3c7d-164">**Мешайте** запросу — хотя лучше всего использовать в столбцах с повторяющимися значениями, одинаковые столбцы также могут иметь высокий уровень высокой высокой высоты или большое количество `summarize` уникальных значений. </span><span class="sxs-lookup"><span data-stu-id="c3c7d-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="c3c7d-165">Как и в случае с оператором, вы также можете применять подсказку мякиша для распределения нагрузки на обработку и потенциально повысить производительность при работе со столбцами с `join` [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` высокой тщательностью.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="c3c7d-166">В приведенного ниже запросе учитывается отдельный адрес электронной почты получателя, который может работать в сотнях `summarize` тысяч в крупных организациях.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="c3c7d-167">Для повышения производительности он `hint.shufflekey` включает:</span><span class="sxs-lookup"><span data-stu-id="c3c7d-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="c3c7d-168">Сценарии запросов</span><span class="sxs-lookup"><span data-stu-id="c3c7d-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="c3c7d-169">Определение уникальных процессов с помощью ИД процессов</span><span class="sxs-lookup"><span data-stu-id="c3c7d-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="c3c7d-170">Идентификаторы процессов (PID) в Windows перерабатываются и используются для новых процессов.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="c3c7d-171">Они не могут служить уникальными идентификаторами для определенных процессов сами по себе.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="c3c7d-172">Чтобы создать уникальный идентификатор для процесса на определенном компьютере, идентификатор процесса нужно использовать вместе со временем создания процесса.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="c3c7d-173">При объединении или обобщении данных по процессам рекомендуется включать столбцы для идентификатора компьютера (либо `DeviceId`, либо`DeviceName`), идентификатора процесса (`ProcessId` или `InitiatingProcessId`) и времени создания процесса (`ProcessCreationTime` или `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="c3c7d-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="c3c7d-174">В приведенном ниже примере запроса обнаружены процессы, имеющие доступ к более чем 10 IP-адресам через порт 445 (SMB) с одновременным возможным сканированием файловых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="c3c7d-175">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="c3c7d-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="c3c7d-176">В запросе указаны одновременно и `InitiatingProcessId`, и `InitiatingProcessCreationTime`. Благодаря этому запрос относится к одному единственному процессу, и при этом исключаются многочисленные другие процессы с аналогичным идентификатором процесса.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="c3c7d-177">Командные строки запроса</span><span class="sxs-lookup"><span data-stu-id="c3c7d-177">Query command lines</span></span>
<span data-ttu-id="c3c7d-178">Создать командную строку для выполнения задачи можно разными способами.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="c3c7d-179">Например, злоумышленник может ссылаться на файл изображения без пути, без расширения файла, с помощью переменных среды или с кавычками.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="c3c7d-180">Злоумышленник также может изменить порядок параметров или добавить несколько кавычках и пробелов.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="c3c7d-181">Чтобы создать более длительные запросы вокруг командных строк, следуйте следующим методикам:</span><span class="sxs-lookup"><span data-stu-id="c3c7d-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="c3c7d-182">Определите известные процессы  (например,net.exe *илиpsexec.exe)* путем совпадения в полях имени файла вместо фильтрации по самой командной строке.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="c3c7d-183">Разчет разделов командной строки с помощью [функции parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="c3c7d-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="c3c7d-184">При запросе аргументов командной строки искать точное совпадение для нескольких несвязанных аргументов в определенном порядке не имеет смысла.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="c3c7d-185">Вместо этого используются регулярные выражения или несколько отдельных аргументов, содержащих операторы.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="c3c7d-186">Совпадения используются без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-186">Use case insensitive matches.</span></span> <span data-ttu-id="c3c7d-187">Например, используйте `=~` , и вместо , и `in~` `contains` `==` `in` `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="c3c7d-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="c3c7d-188">Чтобы устранить методы обфускации командной строки, рекомендуется удалить кавычка, заменить запятые пробелами и заменить несколько последовательных пробелов одним пробелом.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="c3c7d-189">Существуют более сложные методы обфускации, которые требуют других подходов, но эти изменения могут помочь решить распространенные из них.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="c3c7d-190">В следующих примерах демонстрируются различные способы создания запроса, *который* ищет файлnet.exeостановить службу брандмауэра "MpsSvc":</span><span class="sxs-lookup"><span data-stu-id="c3c7d-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="c3c7d-191">Ingest data from external sources</span><span class="sxs-lookup"><span data-stu-id="c3c7d-191">Ingest data from external sources</span></span>
<span data-ttu-id="c3c7d-192">Чтобы включить длинные списки или большие таблицы в запрос, используйте оператор [externaldata,](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) чтобы получить данные из указанного URI.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="c3c7d-193">Вы можете получить данные из файлов в форматах TXT, CSV, JSON и [других форматах.](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)</span><span class="sxs-lookup"><span data-stu-id="c3c7d-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="c3c7d-194">В примере ниже показано, как можно использовать обширный список вредоносных хешов SHA-256, предоставляемых MalwareBazaar (abuse.ch) для проверки вложений в сообщениях электронной почты:</span><span class="sxs-lookup"><span data-stu-id="c3c7d-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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

### <a name="parse-strings"></a><span data-ttu-id="c3c7d-195">Строки parse</span><span class="sxs-lookup"><span data-stu-id="c3c7d-195">Parse strings</span></span>
<span data-ttu-id="c3c7d-196">Существуют различные функции, которые можно использовать для эффективной обработки строк, которые требуют различета или преобразования.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="c3c7d-197">String</span><span class="sxs-lookup"><span data-stu-id="c3c7d-197">String</span></span> | <span data-ttu-id="c3c7d-198">Функция</span><span class="sxs-lookup"><span data-stu-id="c3c7d-198">Function</span></span> | <span data-ttu-id="c3c7d-199">Пример использования</span><span class="sxs-lookup"><span data-stu-id="c3c7d-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="c3c7d-200">Командные строки</span><span class="sxs-lookup"><span data-stu-id="c3c7d-200">Command-lines</span></span> | [<span data-ttu-id="c3c7d-201">parse_command_line()</span><span class="sxs-lookup"><span data-stu-id="c3c7d-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="c3c7d-202">Извлекать команду и все аргументы.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="c3c7d-203">Пути</span><span class="sxs-lookup"><span data-stu-id="c3c7d-203">Paths</span></span> | [<span data-ttu-id="c3c7d-204">parse_path()</span><span class="sxs-lookup"><span data-stu-id="c3c7d-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="c3c7d-205">Извлекать разделы пути к файлу или папке.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="c3c7d-206">Номера версий</span><span class="sxs-lookup"><span data-stu-id="c3c7d-206">Version numbers</span></span> | [<span data-ttu-id="c3c7d-207">parse_version()</span><span class="sxs-lookup"><span data-stu-id="c3c7d-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="c3c7d-208">Декодировать номер версии с четырьмя разделами и до восьми символов на раздел.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="c3c7d-209">Используйте анализ данных для сравнения возраста версии.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="c3c7d-210">IPv4-адреса</span><span class="sxs-lookup"><span data-stu-id="c3c7d-210">IPv4 addresses</span></span> | [<span data-ttu-id="c3c7d-211">parse_ipv4()</span><span class="sxs-lookup"><span data-stu-id="c3c7d-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="c3c7d-212">Преобразуйте IPv4-адрес в длинное integer.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="c3c7d-213">Чтобы сравнить IPv4-адреса без их преобразования, используйте [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="c3c7d-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="c3c7d-214">IPv6-адреса</span><span class="sxs-lookup"><span data-stu-id="c3c7d-214">IPv6 addresses</span></span> | [<span data-ttu-id="c3c7d-215">parse_ipv6()</span><span class="sxs-lookup"><span data-stu-id="c3c7d-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="c3c7d-216">Преобразуем IPv4- или IPv6-адрес в каноническую нотацию IPv6.</span><span class="sxs-lookup"><span data-stu-id="c3c7d-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="c3c7d-217">Для сравнения IPv6-адресов используйте [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="c3c7d-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="c3c7d-218">Чтобы узнать обо всех поддерживаемых функциях разбиение, ознакомьтесь [со строками Kusto.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)</span><span class="sxs-lookup"><span data-stu-id="c3c7d-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="c3c7d-219">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c3c7d-219">Related topics</span></span>
- [<span data-ttu-id="c3c7d-220">Документация по языку запросов Kusto</span><span class="sxs-lookup"><span data-stu-id="c3c7d-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="c3c7d-221">Квоты и параметры использования</span><span class="sxs-lookup"><span data-stu-id="c3c7d-221">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="c3c7d-222">Обработка ошибок расширенных поисков</span><span class="sxs-lookup"><span data-stu-id="c3c7d-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="c3c7d-223">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="c3c7d-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c3c7d-224">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="c3c7d-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
