---
title: Узнайте язык расширенных запросов на охоту в Microsoft 365 Defender
description: Создайте ваш первый запрос охоты на угрозы и узнайте о распространенных операторах и других аспектах языка запросов расширенной охоты на угрозы
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft threat protection, Microsoft 365, mtp, m365, search, query, language, learn, first query, telemetry, events, telemetry, custom detections, schema, kusto, operators, data types, powershell download, query example
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 7ce3053fbc05f7340eea8dff08c9f7aaaeb9d7c0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076302"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="4b538-104">Познакомьтесь с языком запросов расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="4b538-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4b538-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4b538-105">**Applies to:**</span></span>
- <span data-ttu-id="4b538-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b538-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4b538-107">Расширенный поиск основывается на [языке запросов Kusto](/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="4b538-107">Advanced hunting is based on the [Kusto query language](/azure/kusto/query/).</span></span> <span data-ttu-id="4b538-108">Вы можете использовать операторы Kusto и операторы для создания запросов, которые размещают сведения в специализированной [схеме.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="4b538-108">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="4b538-109">Чтобы лучше понять эти концепции, запустите ваш первый запрос.</span><span class="sxs-lookup"><span data-stu-id="4b538-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="4b538-110">Попробуйте выполнить первый запрос</span><span class="sxs-lookup"><span data-stu-id="4b538-110">Try your first query</span></span>

<span data-ttu-id="4b538-111">В центре безопасности Microsoft 365 перейдите в **Службу охоты,** чтобы выполнить первый запрос.</span><span class="sxs-lookup"><span data-stu-id="4b538-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="4b538-112">Используйте следующий пример:</span><span class="sxs-lookup"><span data-stu-id="4b538-112">Use the following example:</span></span>

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

<span data-ttu-id="4b538-113">**[Запуск этого запроса в продвинутой охоте](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="4b538-113">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="4b538-114">Описание запроса и указание таблиц для поиска</span><span class="sxs-lookup"><span data-stu-id="4b538-114">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="4b538-115">В начале запроса добавлен краткий комментарий, чтобы описать его.</span><span class="sxs-lookup"><span data-stu-id="4b538-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="4b538-116">Этот комментарий поможет, если позже вы решите сохранить запрос и поделиться им с другими в организации.</span><span class="sxs-lookup"><span data-stu-id="4b538-116">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="4b538-117">Сам запрос обычно начинается с имени таблицы с несколькими элементами, которые начинаются с трубки ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="4b538-117">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="4b538-118">В этом примере мы начинаем с создания объединения из двух таблиц и добавления элементов по мере  `DeviceProcessEvents` `DeviceNetworkEvents` необходимости.</span><span class="sxs-lookup"><span data-stu-id="4b538-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="4b538-119">Установите диапазон времени</span><span class="sxs-lookup"><span data-stu-id="4b538-119">Set the time range</span></span>
<span data-ttu-id="4b538-120">Первый элемент с конвейером — это фильтр времени, который был в течение предыдущих семи дней.</span><span class="sxs-lookup"><span data-stu-id="4b538-120">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="4b538-121">Ограничение диапазона времени позволяет убедиться, что запросы выполняются хорошо, возвращают управляемые результаты и не отжимаются.</span><span class="sxs-lookup"><span data-stu-id="4b538-121">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="4b538-122">Проверка определенных процессов</span><span class="sxs-lookup"><span data-stu-id="4b538-122">Check specific processes</span></span>
<span data-ttu-id="4b538-123">За диапазоном времени сразу последует поиск имен файлов процессов, представляющих приложение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b538-123">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="4b538-124">Поиск определенных строк команд</span><span class="sxs-lookup"><span data-stu-id="4b538-124">Search for specific command strings</span></span>
<span data-ttu-id="4b538-125">После этого запрос ищет строки в строках команд, которые обычно используются для скачивания файлов с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b538-125">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="4b538-126">Настройка столбцов результатов и длины</span><span class="sxs-lookup"><span data-stu-id="4b538-126">Customize result columns and length</span></span> 
<span data-ttu-id="4b538-127">Теперь, когда запрос четко определяет данные, которые необходимо найти, можно определить, как выглядят результаты.</span><span class="sxs-lookup"><span data-stu-id="4b538-127">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="4b538-128">`project` возвращает определенные столбцы и `top` ограничивает количество результатов.</span><span class="sxs-lookup"><span data-stu-id="4b538-128">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="4b538-129">Эти операторы помогают обеспечить, чтобы результаты были хорошо отформатированы и достаточно большие и просты в обработке.</span><span class="sxs-lookup"><span data-stu-id="4b538-129">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="4b538-130">Выберите **запрос Run,** чтобы увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="4b538-130">Select **Run query** to see the results.</span></span> <span data-ttu-id="4b538-131">Используйте значок расширения в правом верхнем справа от редактора запроса, чтобы сосредоточиться на запросе и результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="4b538-131">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Изображение управления Expand в редакторе расширенного запроса на охоту](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="4b538-133">Результаты запроса можно просматривать как диаграммы и быстро настраивать фильтры.</span><span class="sxs-lookup"><span data-stu-id="4b538-133">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="4b538-134">Инструкции по [работе с результатами запросов](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="4b538-134">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="4b538-135">Узнайте об общих операторах запросов</span><span class="sxs-lookup"><span data-stu-id="4b538-135">Learn common query operators</span></span>

<span data-ttu-id="4b538-136">Вы только что запустите первый запрос и имеете общее представление о его компонентах.</span><span class="sxs-lookup"><span data-stu-id="4b538-136">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="4b538-137">Пришло время немного отойтки и изучить некоторые основы.</span><span class="sxs-lookup"><span data-stu-id="4b538-137">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="4b538-138">Язык запросов Kusto, используемый в расширенной охоте, поддерживает ряд операторов, включая обычные, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="4b538-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="4b538-139">Оператор</span><span class="sxs-lookup"><span data-stu-id="4b538-139">Operator</span></span> | <span data-ttu-id="4b538-140">Описание и использование</span><span class="sxs-lookup"><span data-stu-id="4b538-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="4b538-141">Фильтрация таблицы по подмножеству строк, удовлетворяющих предикату.</span><span class="sxs-lookup"><span data-stu-id="4b538-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="4b538-142">Создание таблицы, в которой объединяется содержимое исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="4b538-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="4b538-143">Объединение строк двух таблиц, чтобы сформировать новую таблицу, сопоставляя значения заданных столбцов из каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="4b538-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="4b538-144">Возврат количества записей в исходный набор записей.</span><span class="sxs-lookup"><span data-stu-id="4b538-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="4b538-145">Возврат первых N записей, отсортированных по заданным столбцам.</span><span class="sxs-lookup"><span data-stu-id="4b538-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="4b538-146">Возврат до заданного количества строк.</span><span class="sxs-lookup"><span data-stu-id="4b538-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="4b538-147">Выбор столбцов, которые нужно включить, переименовать или перетащить, и вставка новых вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="4b538-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="4b538-148">Создание вычисляемых столбцов и их добавление в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="4b538-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="4b538-149">Возврат динамического массива (JSON) множества различных значений, которые выражение (Expr) принимает в группе.</span><span class="sxs-lookup"><span data-stu-id="4b538-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="4b538-150">Поиск строк, соответствующих предикату, по набору таблиц.</span><span class="sxs-lookup"><span data-stu-id="4b538-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="4b538-151">Чтобы просмотреть реальные примеры этих операторов, запустите их из пункта **Начать работу** в разделе Расширенная охота.</span><span class="sxs-lookup"><span data-stu-id="4b538-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="4b538-152">Понимание типов данных</span><span class="sxs-lookup"><span data-stu-id="4b538-152">Understand data types</span></span>

<span data-ttu-id="4b538-153">Расширенный поиск поддерживает типы данных Kusto, включая следующие распространенные типы:</span><span class="sxs-lookup"><span data-stu-id="4b538-153">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="4b538-154">Тип данных</span><span class="sxs-lookup"><span data-stu-id="4b538-154">Data type</span></span> | <span data-ttu-id="4b538-155">Описание и влияния запроса</span><span class="sxs-lookup"><span data-stu-id="4b538-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="4b538-156">Данные и сведения о времени, как правило, представляющие время событий.</span><span class="sxs-lookup"><span data-stu-id="4b538-156">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="4b538-157">См. поддерживаемые форматы дат</span><span class="sxs-lookup"><span data-stu-id="4b538-157">See supported datetime formats</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="4b538-158">Строка символов в UTF-8, заключенная в одиночные кавычка () или `'` двойные кавычка ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="4b538-158">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="4b538-159">Подробнее о строках</span><span class="sxs-lookup"><span data-stu-id="4b538-159">Read more about strings</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="4b538-160">Этот тип данных поддерживает `true` или `false` заявляет.</span><span class="sxs-lookup"><span data-stu-id="4b538-160">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="4b538-161">См. поддерживаемые литералы и операторы</span><span class="sxs-lookup"><span data-stu-id="4b538-161">See supported literals and operators</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="4b538-162">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="4b538-162">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="4b538-163">64-bit integer</span><span class="sxs-lookup"><span data-stu-id="4b538-163">64-bit integer</span></span> |

<span data-ttu-id="4b538-164">Дополнительные сведения об этих типах данных читайте в [материале о типах данных Kusto scalar.](/azure/data-explorer/kusto/query/scalar-data-types/)</span><span class="sxs-lookup"><span data-stu-id="4b538-164">To learn more about these data types, [read about Kusto scalar data types](/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="4b538-165">Помощь при написании запросов</span><span class="sxs-lookup"><span data-stu-id="4b538-165">Get help as you write queries</span></span>
<span data-ttu-id="4b538-166">Ниже перечислены функции, благодаря которым запросы можно создавать быстрее.</span><span class="sxs-lookup"><span data-stu-id="4b538-166">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="4b538-167">**Autosuggest**— при записи запросов расширенный поиск предоставляет предложения из IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4b538-167">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="4b538-168">**Дерево схемы**— представление схемы, которое включает список таблиц и их столбцов, предоставляется рядом с рабочей областью.</span><span class="sxs-lookup"><span data-stu-id="4b538-168">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="4b538-169">Чтобы получить об элементе дополнительные сведения, нужно навести на него указатель мыши.</span><span class="sxs-lookup"><span data-stu-id="4b538-169">For more information, hover over an item.</span></span> <span data-ttu-id="4b538-170">Чтобы вставить элемент в редактор запросов, нужно дважды щелкнуть по нему.</span><span class="sxs-lookup"><span data-stu-id="4b538-170">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="4b538-171">**[Ссылка схемы](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**— ссылка на портал с описаниями таблиц и столбцов, а также поддерживаемые типы событий `ActionType` (значения) и примеры запросов</span><span class="sxs-lookup"><span data-stu-id="4b538-171">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="4b538-172">Работа с несколькими запросами в редакторе</span><span class="sxs-lookup"><span data-stu-id="4b538-172">Work with multiple queries in the editor</span></span>
<span data-ttu-id="4b538-173">Редактор запроса можно использовать для экспериментов с несколькими запросами.</span><span class="sxs-lookup"><span data-stu-id="4b538-173">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="4b538-174">Использование нескольких запросов:</span><span class="sxs-lookup"><span data-stu-id="4b538-174">To use multiple queries:</span></span>

- <span data-ttu-id="4b538-175">Отделяйте каждый запрос пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="4b538-175">Separate each query with an empty line.</span></span>
- <span data-ttu-id="4b538-176">Поместите курсор в любую часть запроса, чтобы выбрать этот запрос перед его запуском.</span><span class="sxs-lookup"><span data-stu-id="4b538-176">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="4b538-177">При этом будет работать только выбранный запрос.</span><span class="sxs-lookup"><span data-stu-id="4b538-177">This will run only the selected query.</span></span> <span data-ttu-id="4b538-178">Чтобы запустить другой запрос, переместим курсор соответствующим образом и выберите **запрос Run.**</span><span class="sxs-lookup"><span data-stu-id="4b538-178">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Изображение редактора запроса с несколькими запросами](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="4b538-180">Использование примеров запросов</span><span class="sxs-lookup"><span data-stu-id="4b538-180">Use sample queries</span></span>

<span data-ttu-id="4b538-181">Раздел **Начало работы** содержит несколько простых запросов, использующих часто используемые операторы.</span><span class="sxs-lookup"><span data-stu-id="4b538-181">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="4b538-182">Попробуйте выполнить эти запросы и внести в них небольшие изменения.</span><span class="sxs-lookup"><span data-stu-id="4b538-182">Try running these queries and making small modifications to them.</span></span>

![Изображение окна расширенной охоты](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="4b538-184">Кроме примеров базовых запросов, вы можете получить доступ к [общим запросам](advanced-hunting-shared-queries.md) для определенных сценариев охоты на угрозы.</span><span class="sxs-lookup"><span data-stu-id="4b538-184">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="4b538-185">Ознакомьтесь с общими запросами на левой стороне страницы или репозиторием [запросов GitHub.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="4b538-185">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="4b538-186">Документация по языку условий запросов</span><span class="sxs-lookup"><span data-stu-id="4b538-186">Access query language documentation</span></span>

<span data-ttu-id="4b538-187">Дополнительные сведения о языке запросов Kusto и поддерживаемых операторах см. в статье [Документация по языку запросов Kusto](/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="4b538-187">For more information on Kusto query language and supported operators, see [Kusto query language documentation](/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4b538-188">См. также</span><span class="sxs-lookup"><span data-stu-id="4b538-188">Related topics</span></span>
- [<span data-ttu-id="4b538-189">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="4b538-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4b538-190">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="4b538-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="4b538-191">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="4b538-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4b538-192">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="4b538-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4b538-193">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="4b538-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4b538-194">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="4b538-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)