---
title: Расширенные рекомендации по запросу поиска при поиске в Microsoft Threat protection
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: af9579b94314375aa786782ea477bb11b0cd9c0b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198217"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="aacc9-104">Рекомендации по использованию запросов расширенного выслеживания</span><span class="sxs-lookup"><span data-stu-id="aacc9-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="aacc9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="aacc9-105">**Applies to:**</span></span>
- <span data-ttu-id="aacc9-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="aacc9-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="aacc9-107">Используйте эти рекомендации для ускорения получения результатов и предотвращения превышения времени ожидания при выполнении сложных запросов.</span><span class="sxs-lookup"><span data-stu-id="aacc9-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="aacc9-108">Дополнительные руководства по повышению производительности запросов см. в статье [Рекомендации по использованию запросов Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="aacc9-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-limits"></a><span data-ttu-id="aacc9-109">Общие сведения об ограничении ресурсов ЦП</span><span class="sxs-lookup"><span data-stu-id="aacc9-109">Understand CPU resource limits</span></span>
<span data-ttu-id="aacc9-110">В зависимости от размера у каждого клиента есть доступ к заданному объему ресурсов ЦП, выделенному для запуска расширенных запросов на поиск.</span><span class="sxs-lookup"><span data-stu-id="aacc9-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="aacc9-111">Для получения подробных сведений о различных пределах обслуживания [Ознакомьтесь с дополнительными пределами](advanced-hunting-limits.md).</span><span class="sxs-lookup"><span data-stu-id="aacc9-111">For detailed information about various service limits, [read about advanced hunting limits](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="aacc9-112">Клиенты, которые регулярно запускают несколько запросов, должны отслеживать потребление и применять рекомендации по оптимизации, описанные в этой статье, для минимизации сбоев, возникших в результате превышения предельных значений.</span><span class="sxs-lookup"><span data-stu-id="aacc9-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding the limits.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="aacc9-113">Общие рекомендации по оптимизации</span><span class="sxs-lookup"><span data-stu-id="aacc9-113">General optimization tips</span></span>

- <span data-ttu-id="aacc9-114">**Изменение размера новых запросов**— если вы подозреваете, что запрос возвратит большой набор результатов, сначала оцените его с помощью [оператора Count](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span><span class="sxs-lookup"><span data-stu-id="aacc9-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="aacc9-115">Используйте [ограничения](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) или синонимы `take` , чтобы избежать больших наборов результатов.</span><span class="sxs-lookup"><span data-stu-id="aacc9-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="aacc9-116">**Примените фильтры раньше**, примените фильтры времени и другие фильтры для сокращения набора данных, особенно перед использованием функций преобразования и синтаксического анализа, таких как [substring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [Replace ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [Trim ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [ToUpper ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)или [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="aacc9-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="aacc9-117">В приведенном ниже примере функция анализа [екстрактжсон ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) используется после уменьшения числа записей в операторах фильтрации.</span><span class="sxs-lookup"><span data-stu-id="aacc9-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="aacc9-118">**Содержит ритм**, чтобы избежать необязательного поиска подстрок в словах, используйте оператор, `has` а не `contains` .</span><span class="sxs-lookup"><span data-stu-id="aacc9-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="aacc9-119">Сведения об строковых операторах</span><span class="sxs-lookup"><span data-stu-id="aacc9-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="aacc9-120">**Искать в определенных столбцах**— искать в определенном столбце, а не выполнять полнотекстовый поиск по всем столбцам.</span><span class="sxs-lookup"><span data-stu-id="aacc9-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="aacc9-121">Не используйте `*` для проверки всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="aacc9-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="aacc9-122">**С учетом регистра для скорости**— Поиск с учетом регистра — более конкретный и более производительный.</span><span class="sxs-lookup"><span data-stu-id="aacc9-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="aacc9-123">Имена [строковых операторов](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)с учетом регистра, такие как `has_cs` и `contains_cs` , как правило, заканчивается на `_cs` .</span><span class="sxs-lookup"><span data-stu-id="aacc9-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="aacc9-124">Кроме того, можно использовать оператор равенства с учетом регистра, `==` а не `~=` .</span><span class="sxs-lookup"><span data-stu-id="aacc9-124">You can also use the case-sensitive equals operator `==` instead of `~=`.</span></span>
- <span data-ttu-id="aacc9-125">**Parse, не извлекайте**, когда это возможно, используйте [оператор Parse](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) или функцию синтаксического анализа, например [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="aacc9-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="aacc9-126">Избегайте `matches regex` строкового оператора или [функции extract ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), в которых используется регулярное выражение.</span><span class="sxs-lookup"><span data-stu-id="aacc9-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="aacc9-127">Зарезервируйте использование регулярных выражений для более сложных сценариев.</span><span class="sxs-lookup"><span data-stu-id="aacc9-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="aacc9-128">Подробнее о функциях синтаксического анализа</span><span class="sxs-lookup"><span data-stu-id="aacc9-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="aacc9-129">**Фильтрация таблиц без выражений**— не отфильтровывайте вычисляемый столбец, если вы можете выполнить фильтрацию по столбцу таблицы.</span><span class="sxs-lookup"><span data-stu-id="aacc9-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="aacc9-130">**Отсутствие трех символов**— Избегайте сравнения или фильтрации с использованием терминов, состоящих из трех или менее трех символов.</span><span class="sxs-lookup"><span data-stu-id="aacc9-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="aacc9-131">Эти термины не индексируются и их сопоставлению требуют больше ресурсов.</span><span class="sxs-lookup"><span data-stu-id="aacc9-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="aacc9-132">**Проект выборочно**— Сделайте результаты более понятными, выполнив только необходимые столбцы.</span><span class="sxs-lookup"><span data-stu-id="aacc9-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="aacc9-133">Запроектировать определенные столбцы перед выполнением [присоединения](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) или аналогичных операций также помогут увеличить производительность.</span><span class="sxs-lookup"><span data-stu-id="aacc9-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="aacc9-134">Оптимизация `join` оператора</span><span class="sxs-lookup"><span data-stu-id="aacc9-134">Optimize the `join` operator</span></span>
<span data-ttu-id="aacc9-135">[Оператор Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) объединяет строки из двух таблиц, сопоставляя значения в указанных столбцах.</span><span class="sxs-lookup"><span data-stu-id="aacc9-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="aacc9-136">Используйте приведенные ниже советы для оптимизации запросов, использующих этот оператор.</span><span class="sxs-lookup"><span data-stu-id="aacc9-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="aacc9-137">**Таблица меньшего размера слева**: `join` оператор сопоставляет записи в таблице, расположенной слева от оператора Join, с записями справа.</span><span class="sxs-lookup"><span data-stu-id="aacc9-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="aacc9-138">Если таблица меньше, чем слева, тем меньше записей потребуется сопоставлять, таким образом ускоряя запрос.</span><span class="sxs-lookup"><span data-stu-id="aacc9-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="aacc9-139">В приведенной ниже таблице мы уменьшаем левую таблицу, `DeviceLogonEvents` чтобы охватить только три определенных устройства перед присоединением их с `IdentityLogonEvents` помощью SID учетных записей.</span><span class="sxs-lookup"><span data-stu-id="aacc9-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="aacc9-140">**Используйте флаг INNER-JOIN** [, используемый по умолчанию](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) , или [иннеруникуе-Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) , возвращает строки в левой таблице с помощью ключа соединения, чтобы возвратить строку для каждого совпадения с правой таблицей.</span><span class="sxs-lookup"><span data-stu-id="aacc9-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="aacc9-141">Если в левой таблице есть несколько строк с одинаковым значением для `join` ключа, эти строки будут повторяться, чтобы оставить одну произвольную строку для каждого уникального значения.</span><span class="sxs-lookup"><span data-stu-id="aacc9-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="aacc9-142">Это поведение по умолчанию может оставить важную информацию из левой таблицы, которая поможет вам получить полезную информацию.</span><span class="sxs-lookup"><span data-stu-id="aacc9-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="aacc9-143">Например, приведенный ниже запрос будет содержать только одно сообщение электронной почты, содержащее определенное вложение, даже если оно было отправлено несколькими сообщениями электронной почты:</span><span class="sxs-lookup"><span data-stu-id="aacc9-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="aacc9-144">Чтобы устранить это ограничение, мы используем флаг [внутреннего соединения](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) , указав `kind=inner` для отображения всех строк в левой таблице с соответствующими значениями справа:</span><span class="sxs-lookup"><span data-stu-id="aacc9-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="aacc9-145">**Присоединение записей из временного окна**— при изучении событий безопасности аналитики ищут связанные события, происходящие за один и тот же период времени.</span><span class="sxs-lookup"><span data-stu-id="aacc9-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="aacc9-146">Применение того же подхода при использовании `join` повышения производительности также уменьшает число проверяемых записей.</span><span class="sxs-lookup"><span data-stu-id="aacc9-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="aacc9-147">В запросе ниже выполняется проверка событий входа в систему в течение 30 минут после получения вредоносного файла:</span><span class="sxs-lookup"><span data-stu-id="aacc9-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="aacc9-148">**Применить фильтры времени на обеих сторонах**, даже если вы не изучаете конкретное временное окно, применение фильтров времени в левой и правой таблицах позволяет сократить число проверяемых записей и повысить `join` производительность.</span><span class="sxs-lookup"><span data-stu-id="aacc9-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="aacc9-149">Приведенный ниже запрос применяется `Timestamp > ago(1h)` к обеим таблицам, чтобы присоединяться только к записям за последний час:</span><span class="sxs-lookup"><span data-stu-id="aacc9-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="aacc9-150">**Использование подсказок для повышения производительности**— используйте подсказки с `join` оператором, чтобы указать, что сервер будет распределять нагрузку при выполнении операций, интенсивно использующих ресурсы.</span><span class="sxs-lookup"><span data-stu-id="aacc9-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="aacc9-151">Дополнительные сведения о подсказках по объединению</span><span class="sxs-lookup"><span data-stu-id="aacc9-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="aacc9-152">Например, **[Подсказка в случайном порядке](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** помогает увеличить производительность запросов при соединении таблиц с помощью ключа с большим количеством уникальных значений, например, `AccountObjectId` в следующем запросе:</span><span class="sxs-lookup"><span data-stu-id="aacc9-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="aacc9-153">**[Подсказка о вещании](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** помогает в том случае, если левая таблица мала (до 100 000 записей), а правая таблица чрезвычайно велика.</span><span class="sxs-lookup"><span data-stu-id="aacc9-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="aacc9-154">Например, приведенный ниже запрос пытается присоединиться к нескольким сообщениям, которые содержат конкретные темы со _всеми_ сообщениями, содержащими ссылки в `EmailUrlInfo` таблице:</span><span class="sxs-lookup"><span data-stu-id="aacc9-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="aacc9-155">Оптимизация `summarize` оператора</span><span class="sxs-lookup"><span data-stu-id="aacc9-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="aacc9-156">[Оператор суммирования](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) собирает содержимое таблицы.</span><span class="sxs-lookup"><span data-stu-id="aacc9-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="aacc9-157">Используйте приведенные ниже советы для оптимизации запросов, использующих этот оператор.</span><span class="sxs-lookup"><span data-stu-id="aacc9-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="aacc9-158">**Поиск различных значений**— в общем случае используйте `summarize` для поиска различных значений, которые могут быть повторяющимися.</span><span class="sxs-lookup"><span data-stu-id="aacc9-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="aacc9-159">Она может быть ненужной для статистического использования столбцов без повторяющихся значений.</span><span class="sxs-lookup"><span data-stu-id="aacc9-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="aacc9-160">Хотя одно сообщение электронной почты может быть частью нескольких событий, приведенный ниже пример _не_ является эффективным, `summarize` так как в качестве идентификатора сетевого сообщения для отдельной электронной почты всегда используется уникальный адрес отправителя.</span><span class="sxs-lookup"><span data-stu-id="aacc9-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="aacc9-161">`summarize`Оператор можно легко заменять `project` , при этом результат может быть одинаковым при использовании меньшего числа ресурсов:</span><span class="sxs-lookup"><span data-stu-id="aacc9-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="aacc9-162">Ниже приведен пример более эффективного использования, `summarize` так как может быть несколько отдельных экземпляров адреса отправителя, которые отправляют электронную почту на один и тот же адрес получателя.</span><span class="sxs-lookup"><span data-stu-id="aacc9-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="aacc9-163">Такие сочетания не отличаются друг от друга и, скорее всего, имеют дубликаты.</span><span class="sxs-lookup"><span data-stu-id="aacc9-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="aacc9-164">В **случайном порядке для запроса**— хотя `summarize` в столбцах с повторяющимися значениями одни и те же столбцы также _high cardinality_ могут иметь большое количество уникальных значений.</span><span class="sxs-lookup"><span data-stu-id="aacc9-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="aacc9-165">Как и `join` оператор, вы также можете применить [подсказку в случайном порядке](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) , `summarize` чтобы распределять нагрузку обработки и потенциально повышать производительность при работе со столбцами с большим количеством элементов.</span><span class="sxs-lookup"><span data-stu-id="aacc9-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="aacc9-166">В запросе ниже показано `summarize` , как подсчитать различные адреса электронной почты получателей, которые могут выполняться на сотнях тысяч в крупных организациях.</span><span class="sxs-lookup"><span data-stu-id="aacc9-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="aacc9-167">Чтобы увеличить производительность, он включает `hint.shufflekey` :</span><span class="sxs-lookup"><span data-stu-id="aacc9-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="aacc9-168">Сценарии запросов</span><span class="sxs-lookup"><span data-stu-id="aacc9-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="aacc9-169">Определение уникальных процессов с помощью идентификаторов процессов</span><span class="sxs-lookup"><span data-stu-id="aacc9-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="aacc9-170">Идентификаторы процессов (PID) в Windows перерабатываются и используются для новых процессов.</span><span class="sxs-lookup"><span data-stu-id="aacc9-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="aacc9-171">Они не могут служить уникальными идентификаторами для определенных процессов сами по себе.</span><span class="sxs-lookup"><span data-stu-id="aacc9-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="aacc9-172">Чтобы создать уникальный идентификатор для процесса на определенном компьютере, идентификатор процесса нужно использовать вместе со временем создания процесса.</span><span class="sxs-lookup"><span data-stu-id="aacc9-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="aacc9-173">При объединении или обобщении данных по процессам рекомендуется включать столбцы для идентификатора компьютера (либо `DeviceId`, либо`DeviceName`), идентификатора процесса (`ProcessId` или `InitiatingProcessId`) и времени создания процесса (`ProcessCreationTime` или `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="aacc9-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="aacc9-174">В приведенном ниже примере запроса обнаружены процессы, имеющие доступ к более чем 10 IP-адресам через порт 445 (SMB) с одновременным возможным сканированием файловых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="aacc9-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="aacc9-175">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="aacc9-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="aacc9-176">В запросе указаны одновременно и `InitiatingProcessId`, и `InitiatingProcessCreationTime`. Благодаря этому запрос относится к одному единственному процессу, и при этом исключаются многочисленные другие процессы с аналогичным идентификатором процесса.</span><span class="sxs-lookup"><span data-stu-id="aacc9-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="aacc9-177">Строки команд запросов</span><span class="sxs-lookup"><span data-stu-id="aacc9-177">Query command lines</span></span>
<span data-ttu-id="aacc9-178">Создать командную строку для выполнения задачи можно разными способами.</span><span class="sxs-lookup"><span data-stu-id="aacc9-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="aacc9-179">Например, злоумышленник может ссылаться на файл изображения без пути, без расширения имени файла, с использованием переменных среды или с кавычками.</span><span class="sxs-lookup"><span data-stu-id="aacc9-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="aacc9-180">Злоумышленник также может изменить порядок параметров или добавить несколько кавычек и пробелов.</span><span class="sxs-lookup"><span data-stu-id="aacc9-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="aacc9-181">Чтобы создать более устойчивые запросы вокруг командных строк, примените следующие рекомендации:</span><span class="sxs-lookup"><span data-stu-id="aacc9-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="aacc9-182">Определите известные процессы (например, *net.exe* или *psexec.exe*), выполнив соответствующую команду в поле имя файла, а не в самом окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="aacc9-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="aacc9-183">Анализ разделов командной строки с помощью [функции parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="aacc9-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="aacc9-184">При запросе аргументов командной строки искать точное совпадение для нескольких несвязанных аргументов в определенном порядке не имеет смысла.</span><span class="sxs-lookup"><span data-stu-id="aacc9-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="aacc9-185">Вместо этого используются регулярные выражения или несколько отдельных аргументов, содержащих операторы.</span><span class="sxs-lookup"><span data-stu-id="aacc9-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="aacc9-186">Совпадения используются без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="aacc9-186">Use case insensitive matches.</span></span> <span data-ttu-id="aacc9-187">Например, используйте `=~` , `in~` , и `contains` вместо `==` , `in` и `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="aacc9-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="aacc9-188">Чтобы уменьшить методы запутывания командной строки, рекомендуется удалить кавычки, заменив запятые пробелами и заменив несколько последовательных пробелов одним пробелом.</span><span class="sxs-lookup"><span data-stu-id="aacc9-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="aacc9-189">Существуют более сложные методы запутывания, требующие других подходов, но эти настройки могут помочь в устранении распространенных задач.</span><span class="sxs-lookup"><span data-stu-id="aacc9-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="aacc9-190">В следующих примерах показаны различные способы создания запроса, который ищет *net.exe* файла для остановки службы брандмауэра "MPSSVC":</span><span class="sxs-lookup"><span data-stu-id="aacc9-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="aacc9-191">Прием данных из внешних источников</span><span class="sxs-lookup"><span data-stu-id="aacc9-191">Ingest data from external sources</span></span>
<span data-ttu-id="aacc9-192">Чтобы включить в запрос длинные списки или большие таблицы, используйте [оператор екстерналдата](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) для приема данных из указанного URI.</span><span class="sxs-lookup"><span data-stu-id="aacc9-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="aacc9-193">Вы можете получать данные из файлов в формате TXT, CSV, JSON или [других форматах](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span><span class="sxs-lookup"><span data-stu-id="aacc9-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="aacc9-194">В приведенном ниже примере показано, как можно использовать обширный список хеш-кодов SHA-256, предоставляемых службой Малваребазаар (abuse.ch), для проверки вложений в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="aacc9-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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

### <a name="parse-strings"></a><span data-ttu-id="aacc9-195">Синтаксический анализ строк</span><span class="sxs-lookup"><span data-stu-id="aacc9-195">Parse strings</span></span>
<span data-ttu-id="aacc9-196">Существует несколько функций, которые можно использовать для эффективного обработки строк, требующих синтаксического анализа или преобразования.</span><span class="sxs-lookup"><span data-stu-id="aacc9-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="aacc9-197">String</span><span class="sxs-lookup"><span data-stu-id="aacc9-197">String</span></span> | <span data-ttu-id="aacc9-198">Функция</span><span class="sxs-lookup"><span data-stu-id="aacc9-198">Function</span></span> | <span data-ttu-id="aacc9-199">Пример использования</span><span class="sxs-lookup"><span data-stu-id="aacc9-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="aacc9-200">Командная строка</span><span class="sxs-lookup"><span data-stu-id="aacc9-200">Command-lines</span></span> | [<span data-ttu-id="aacc9-201">parse_command_line ()</span><span class="sxs-lookup"><span data-stu-id="aacc9-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="aacc9-202">Извлеките команду и все аргументы.</span><span class="sxs-lookup"><span data-stu-id="aacc9-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="aacc9-203">Пути</span><span class="sxs-lookup"><span data-stu-id="aacc9-203">Paths</span></span> | [<span data-ttu-id="aacc9-204">parse_path ()</span><span class="sxs-lookup"><span data-stu-id="aacc9-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="aacc9-205">Извлечение разделов пути к файлу или папке.</span><span class="sxs-lookup"><span data-stu-id="aacc9-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="aacc9-206">Номера версий</span><span class="sxs-lookup"><span data-stu-id="aacc9-206">Version numbers</span></span> | [<span data-ttu-id="aacc9-207">parse_version ()</span><span class="sxs-lookup"><span data-stu-id="aacc9-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="aacc9-208">Разработайте номер версии, содержащий до четырех разделов и до восьми символов в разделе.</span><span class="sxs-lookup"><span data-stu-id="aacc9-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="aacc9-209">Используйте проанализированные данные для сравнения возраста версий.</span><span class="sxs-lookup"><span data-stu-id="aacc9-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="aacc9-210">IPv4-адреса</span><span class="sxs-lookup"><span data-stu-id="aacc9-210">IPv4 addresses</span></span> | [<span data-ttu-id="aacc9-211">parse_ipv4 ()</span><span class="sxs-lookup"><span data-stu-id="aacc9-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="aacc9-212">Преобразование IPv4-адреса в длинное целое число.</span><span class="sxs-lookup"><span data-stu-id="aacc9-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="aacc9-213">Для сравнения IPv4-адресов без их преобразования используйте [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="aacc9-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="aacc9-214">IPv6-адреса</span><span class="sxs-lookup"><span data-stu-id="aacc9-214">IPv6 addresses</span></span> | [<span data-ttu-id="aacc9-215">parse_ipv6 ()</span><span class="sxs-lookup"><span data-stu-id="aacc9-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="aacc9-216">Преобразование IPv4-или IPv6-адреса в каноническую нотацию IPv6.</span><span class="sxs-lookup"><span data-stu-id="aacc9-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="aacc9-217">Чтобы сравнить IPv6-адреса, используйте [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="aacc9-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="aacc9-218">Чтобы узнать обо всех поддерживаемых функциях синтаксического анализа, [прочитайте о функциях строк Кусто](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span><span class="sxs-lookup"><span data-stu-id="aacc9-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="aacc9-219">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="aacc9-219">Related topics</span></span>
- [<span data-ttu-id="aacc9-220">Документация по языку запросов Кусто</span><span class="sxs-lookup"><span data-stu-id="aacc9-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="aacc9-221">Ограничения службы</span><span class="sxs-lookup"><span data-stu-id="aacc9-221">Service limits</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="aacc9-222">Обработка дополнительных ошибок при поиске</span><span class="sxs-lookup"><span data-stu-id="aacc9-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="aacc9-223">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="aacc9-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="aacc9-224">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="aacc9-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
