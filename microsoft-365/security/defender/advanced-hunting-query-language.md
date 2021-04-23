---
title: Узнайте язык расширенных запросов на охоту в Microsoft 365 Defender
description: Создайте ваш первый запрос охоты на угрозы и узнайте о распространенных операторах и других аспектах языка запросов расширенной охоты на угрозы
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, language, learn, first query, telemetry, events, telemetry, custom detections, schema, kusto, operators, data types, powershell download, query example
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 14287fb6dea9dda8accb580246b383f0427c3b3f
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952624"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="fa49d-104">Познакомьтесь с языком запросов расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="fa49d-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fa49d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="fa49d-105">**Applies to:**</span></span>
- <span data-ttu-id="fa49d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fa49d-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="fa49d-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fa49d-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="fa49d-108">Расширенный поиск основывается на [языке запросов Kusto](/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="fa49d-108">Advanced hunting is based on the [Kusto query language](/azure/kusto/query/).</span></span> <span data-ttu-id="fa49d-109">Вы можете использовать операторы Kusto и операторы для создания запросов, которые размещают сведения в специализированной [схеме.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="fa49d-109">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="fa49d-110">Чтобы лучше понять эти концепции, запустите ваш первый запрос.</span><span class="sxs-lookup"><span data-stu-id="fa49d-110">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="fa49d-111">Попробуйте выполнить первый запрос</span><span class="sxs-lookup"><span data-stu-id="fa49d-111">Try your first query</span></span>

<span data-ttu-id="fa49d-112">В центре безопасности Microsoft 365 перейдите в **Службу охоты,** чтобы выполнить первый запрос.</span><span class="sxs-lookup"><span data-stu-id="fa49d-112">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="fa49d-113">Используйте следующий пример:</span><span class="sxs-lookup"><span data-stu-id="fa49d-113">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="fa49d-114">**[Запуск этого запроса в продвинутой охоте](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="fa49d-114">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="fa49d-115">Описание запроса и указание таблиц для поиска</span><span class="sxs-lookup"><span data-stu-id="fa49d-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="fa49d-116">В начале запроса добавлен краткий комментарий, чтобы описать его.</span><span class="sxs-lookup"><span data-stu-id="fa49d-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="fa49d-117">Этот комментарий поможет, если позже вы решите сохранить запрос и поделиться им с другими в организации.</span><span class="sxs-lookup"><span data-stu-id="fa49d-117">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="fa49d-118">Сам запрос обычно начинается с имени таблицы с несколькими элементами, которые начинаются с трубки ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="fa49d-118">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="fa49d-119">В этом примере мы начинаем с создания объединения из двух таблиц и добавления элементов по мере  `DeviceProcessEvents` `DeviceNetworkEvents` необходимости.</span><span class="sxs-lookup"><span data-stu-id="fa49d-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="fa49d-120">Установите диапазон времени</span><span class="sxs-lookup"><span data-stu-id="fa49d-120">Set the time range</span></span>
<span data-ttu-id="fa49d-121">Первый элемент с конвейером — это фильтр времени, который был в течение предыдущих семи дней.</span><span class="sxs-lookup"><span data-stu-id="fa49d-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="fa49d-122">Ограничение диапазона времени позволяет убедиться, что запросы выполняются хорошо, возвращают управляемые результаты и не отжимаются.</span><span class="sxs-lookup"><span data-stu-id="fa49d-122">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="fa49d-123">Проверка определенных процессов</span><span class="sxs-lookup"><span data-stu-id="fa49d-123">Check specific processes</span></span>
<span data-ttu-id="fa49d-124">За диапазоном времени сразу последует поиск имен файлов процессов, представляющих приложение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa49d-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="fa49d-125">Поиск определенных строк команд</span><span class="sxs-lookup"><span data-stu-id="fa49d-125">Search for specific command strings</span></span>
<span data-ttu-id="fa49d-126">После этого запрос ищет строки в строках команд, которые обычно используются для скачивания файлов с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa49d-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="fa49d-127">Настройка столбцов результатов и длины</span><span class="sxs-lookup"><span data-stu-id="fa49d-127">Customize result columns and length</span></span> 
<span data-ttu-id="fa49d-128">Теперь, когда запрос четко определяет данные, которые необходимо найти, можно определить, как выглядят результаты.</span><span class="sxs-lookup"><span data-stu-id="fa49d-128">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="fa49d-129">`project` возвращает определенные столбцы и `top` ограничивает количество результатов.</span><span class="sxs-lookup"><span data-stu-id="fa49d-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="fa49d-130">Эти операторы помогают обеспечить, чтобы результаты были хорошо отформатированы и достаточно большие и просты в обработке.</span><span class="sxs-lookup"><span data-stu-id="fa49d-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="fa49d-131">Выберите **запрос Run,** чтобы увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="fa49d-131">Select **Run query** to see the results.</span></span> <span data-ttu-id="fa49d-132">Используйте значок расширения в правом верхнем справа от редактора запроса, чтобы сосредоточиться на запросе и результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="fa49d-132">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Изображение управления Expand в редакторе расширенного запроса на охоту](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="fa49d-134">Результаты запроса можно просматривать как диаграммы и быстро настраивать фильтры.</span><span class="sxs-lookup"><span data-stu-id="fa49d-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="fa49d-135">Инструкции по [работе с результатами запросов](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="fa49d-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="fa49d-136">Узнайте об общих операторах запросов</span><span class="sxs-lookup"><span data-stu-id="fa49d-136">Learn common query operators</span></span>

<span data-ttu-id="fa49d-137">Вы только что запустите первый запрос и имеете общее представление о его компонентах.</span><span class="sxs-lookup"><span data-stu-id="fa49d-137">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="fa49d-138">Пришло время немного отойтки и изучить некоторые основы.</span><span class="sxs-lookup"><span data-stu-id="fa49d-138">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="fa49d-139">Язык запросов Kusto, используемый в расширенной охоте, поддерживает ряд операторов, включая обычные, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="fa49d-139">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="fa49d-140">Оператор</span><span class="sxs-lookup"><span data-stu-id="fa49d-140">Operator</span></span> | <span data-ttu-id="fa49d-141">Описание и использование</span><span class="sxs-lookup"><span data-stu-id="fa49d-141">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="fa49d-142">Фильтрация таблицы по подмножеству строк, удовлетворяющих предикату.</span><span class="sxs-lookup"><span data-stu-id="fa49d-142">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="fa49d-143">Создание таблицы, в которой объединяется содержимое исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="fa49d-143">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="fa49d-144">Объединение строк двух таблиц, чтобы сформировать новую таблицу, сопоставляя значения заданных столбцов из каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="fa49d-144">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="fa49d-145">Возврат количества записей в исходный набор записей.</span><span class="sxs-lookup"><span data-stu-id="fa49d-145">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="fa49d-146">Возврат первых N записей, отсортированных по заданным столбцам.</span><span class="sxs-lookup"><span data-stu-id="fa49d-146">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="fa49d-147">Возврат до заданного количества строк.</span><span class="sxs-lookup"><span data-stu-id="fa49d-147">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="fa49d-148">Выбор столбцов, которые нужно включить, переименовать или перетащить, и вставка новых вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="fa49d-148">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="fa49d-149">Создание вычисляемых столбцов и их добавление в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="fa49d-149">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="fa49d-150">Возврат динамического массива (JSON) множества различных значений, которые выражение (Expr) принимает в группе.</span><span class="sxs-lookup"><span data-stu-id="fa49d-150">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="fa49d-151">Поиск строк, соответствующих предикату, по набору таблиц.</span><span class="sxs-lookup"><span data-stu-id="fa49d-151">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="fa49d-152">Чтобы просмотреть реальные примеры этих операторов, запустите их из пункта **Начать работу** в разделе Расширенная охота.</span><span class="sxs-lookup"><span data-stu-id="fa49d-152">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="fa49d-153">Понимание типов данных</span><span class="sxs-lookup"><span data-stu-id="fa49d-153">Understand data types</span></span>

<span data-ttu-id="fa49d-154">Расширенный поиск поддерживает типы данных Kusto, включая следующие распространенные типы:</span><span class="sxs-lookup"><span data-stu-id="fa49d-154">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="fa49d-155">Тип данных</span><span class="sxs-lookup"><span data-stu-id="fa49d-155">Data type</span></span> | <span data-ttu-id="fa49d-156">Описание и влияния запроса</span><span class="sxs-lookup"><span data-stu-id="fa49d-156">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="fa49d-157">Данные и сведения о времени, как правило, представляющие время событий.</span><span class="sxs-lookup"><span data-stu-id="fa49d-157">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="fa49d-158">См. поддерживаемые форматы дат</span><span class="sxs-lookup"><span data-stu-id="fa49d-158">See supported datetime formats</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="fa49d-159">Строка символов в UTF-8, заключенная в одиночные кавычка () или `'` двойные кавычка ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="fa49d-159">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="fa49d-160">Подробнее о строках</span><span class="sxs-lookup"><span data-stu-id="fa49d-160">Read more about strings</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="fa49d-161">Этот тип данных поддерживает `true` или `false` заявляет.</span><span class="sxs-lookup"><span data-stu-id="fa49d-161">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="fa49d-162">См. поддерживаемые литералы и операторы</span><span class="sxs-lookup"><span data-stu-id="fa49d-162">See supported literals and operators</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="fa49d-163">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="fa49d-163">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="fa49d-164">64-bit integer</span><span class="sxs-lookup"><span data-stu-id="fa49d-164">64-bit integer</span></span> |

<span data-ttu-id="fa49d-165">Дополнительные сведения об этих типах данных читайте в [материале о типах данных Kusto scalar.](/azure/data-explorer/kusto/query/scalar-data-types/)</span><span class="sxs-lookup"><span data-stu-id="fa49d-165">To learn more about these data types, [read about Kusto scalar data types](/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="fa49d-166">Помощь при написании запросов</span><span class="sxs-lookup"><span data-stu-id="fa49d-166">Get help as you write queries</span></span>
<span data-ttu-id="fa49d-167">Ниже перечислены функции, благодаря которым запросы можно создавать быстрее.</span><span class="sxs-lookup"><span data-stu-id="fa49d-167">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="fa49d-168">**Autosuggest**— при записи запросов расширенный поиск предоставляет предложения из IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="fa49d-168">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="fa49d-169">**Дерево схемы**— представление схемы, которое включает список таблиц и их столбцов, предоставляется рядом с рабочей областью.</span><span class="sxs-lookup"><span data-stu-id="fa49d-169">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="fa49d-170">Чтобы получить об элементе дополнительные сведения, нужно навести на него указатель мыши.</span><span class="sxs-lookup"><span data-stu-id="fa49d-170">For more information, hover over an item.</span></span> <span data-ttu-id="fa49d-171">Чтобы вставить элемент в редактор запросов, нужно дважды щелкнуть по нему.</span><span class="sxs-lookup"><span data-stu-id="fa49d-171">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="fa49d-172">**[Ссылка схемы](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**— ссылка на портал с описаниями таблиц и столбцов, а также поддерживаемые типы событий `ActionType` (значения) и примеры запросов</span><span class="sxs-lookup"><span data-stu-id="fa49d-172">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="fa49d-173">Работа с несколькими запросами в редакторе</span><span class="sxs-lookup"><span data-stu-id="fa49d-173">Work with multiple queries in the editor</span></span>
<span data-ttu-id="fa49d-174">Редактор запроса можно использовать для экспериментов с несколькими запросами.</span><span class="sxs-lookup"><span data-stu-id="fa49d-174">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="fa49d-175">Использование нескольких запросов:</span><span class="sxs-lookup"><span data-stu-id="fa49d-175">To use multiple queries:</span></span>

- <span data-ttu-id="fa49d-176">Отделяйте каждый запрос пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="fa49d-176">Separate each query with an empty line.</span></span>
- <span data-ttu-id="fa49d-177">Поместите курсор в любую часть запроса, чтобы выбрать этот запрос перед его запуском.</span><span class="sxs-lookup"><span data-stu-id="fa49d-177">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="fa49d-178">При этом будет работать только выбранный запрос.</span><span class="sxs-lookup"><span data-stu-id="fa49d-178">This will run only the selected query.</span></span> <span data-ttu-id="fa49d-179">Чтобы запустить другой запрос, переместим курсор соответствующим образом и выберите **запрос Run.**</span><span class="sxs-lookup"><span data-stu-id="fa49d-179">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Изображение редактора запроса с несколькими запросами](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="fa49d-181">Использование примеров запросов</span><span class="sxs-lookup"><span data-stu-id="fa49d-181">Use sample queries</span></span>

<span data-ttu-id="fa49d-182">Раздел **Начало работы** содержит несколько простых запросов, использующих часто используемые операторы.</span><span class="sxs-lookup"><span data-stu-id="fa49d-182">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="fa49d-183">Попробуйте выполнить эти запросы и внести в них небольшие изменения.</span><span class="sxs-lookup"><span data-stu-id="fa49d-183">Try running these queries and making small modifications to them.</span></span>

![Изображение окна расширенной охоты](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="fa49d-185">Кроме примеров базовых запросов, вы можете получить доступ к [общим запросам](advanced-hunting-shared-queries.md) для определенных сценариев охоты на угрозы.</span><span class="sxs-lookup"><span data-stu-id="fa49d-185">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="fa49d-186">Ознакомьтесь с общими запросами на левой стороне страницы или репозиторием [запросов GitHub.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="fa49d-186">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="fa49d-187">Документация по языку условий запросов</span><span class="sxs-lookup"><span data-stu-id="fa49d-187">Access query language documentation</span></span>

<span data-ttu-id="fa49d-188">Дополнительные сведения о языке запросов Kusto и поддерживаемых операторах см. в статье [Документация по языку запросов Kusto](/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="fa49d-188">For more information on Kusto query language and supported operators, see [Kusto query language documentation](/azure/kusto/query/).</span></span>

>[!NOTE]
><span data-ttu-id="fa49d-189">Некоторые таблицы в этой статье могут быть недоступны в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fa49d-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="fa49d-190">[Включи Microsoft 365 Defender для](m365d-enable.md) охоты на угрозы с помощью дополнительных источников данных.</span><span class="sxs-lookup"><span data-stu-id="fa49d-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="fa49d-191">Вы можете переместить расширенные процессы охоты из Microsoft Defender для конечной точки в Microsoft 365 Defender, следуя шагам в миграции расширенных запросов охоты из [Microsoft Defender для конечной](advanced-hunting-migrate-from-mde.md)точки .</span><span class="sxs-lookup"><span data-stu-id="fa49d-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fa49d-192">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="fa49d-192">Related topics</span></span>
- [<span data-ttu-id="fa49d-193">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="fa49d-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fa49d-194">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="fa49d-194">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="fa49d-195">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="fa49d-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fa49d-196">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="fa49d-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fa49d-197">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="fa49d-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fa49d-198">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="fa49d-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)