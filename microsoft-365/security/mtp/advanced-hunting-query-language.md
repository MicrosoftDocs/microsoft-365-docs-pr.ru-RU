---
title: Познакомьтесь с языком запросов расширенной охоты на угрозы в службе защиты от угроз (Майкрософт)
description: Создайте ваш первый запрос охоты на угрозы и узнайте о распространенных операторах и других аспектах языка запросов расширенной охоты на угрозы
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, язык, сведения, первый запрос, телеметрии, события, телеметрии, пользовательские обнаружения, схема, события, телеметрии, пользовательские обнаружения, схема, Кусто, операторы, типы данных, Загрузка PowerShell, пример запроса
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
ms.openlocfilehash: 64f0b19cfd9588e975b06cb43ca73270b00c5e26
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649395"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="be11b-104">Познакомьтесь с языком запросов расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="be11b-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="be11b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="be11b-105">**Applies to:**</span></span>
- <span data-ttu-id="be11b-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="be11b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="be11b-107">Расширенный поиск основывается на [языке запросов Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="be11b-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="be11b-108">С помощью синтаксиса и операторов Кусто можно создавать запросы, которые позволяют найти информацию в [схеме](advanced-hunting-schema-tables.md), специально структурированной для расширенного поиска.</span><span class="sxs-lookup"><span data-stu-id="be11b-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="be11b-109">Чтобы лучше понять эти концепции, запустите ваш первый запрос.</span><span class="sxs-lookup"><span data-stu-id="be11b-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="be11b-110">Попробуйте выполнить первый запрос</span><span class="sxs-lookup"><span data-stu-id="be11b-110">Try your first query</span></span>

<span data-ttu-id="be11b-111">В центре безопасности Microsoft 365 выберите Поиск, **чтобы запустить** первый запрос.</span><span class="sxs-lookup"><span data-stu-id="be11b-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="be11b-112">Используйте следующий пример:</span><span class="sxs-lookup"><span data-stu-id="be11b-112">Use the following example:</span></span>

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

<span data-ttu-id="be11b-113">Так это будет выглядеть в расширенной охоте.</span><span class="sxs-lookup"><span data-stu-id="be11b-113">This is how it will look like in advanced hunting.</span></span>

![Изображение запроса на расширенный поиск по защите от угроз Майкрософт](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="be11b-115">Опишите запрос и укажите таблицы для поиска</span><span class="sxs-lookup"><span data-stu-id="be11b-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="be11b-116">В начале запроса добавлен краткий комментарий, описывающий его назначение.</span><span class="sxs-lookup"><span data-stu-id="be11b-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="be11b-117">Это поможет в том случае, если позже вы решите сохранить запрос и поделиться им с другими пользователями в Организации.</span><span class="sxs-lookup"><span data-stu-id="be11b-117">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="be11b-118">Как правило, запрос начинается с имени таблицы, за которым следует ряд элементов, начинающихся с вертикальной черты (`|`).</span><span class="sxs-lookup"><span data-stu-id="be11b-118">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="be11b-119">В этом примере мы начнем с создания объединения двух таблиц `DeviceProcessEvents` и добавления элементов перегрузки `DeviceNetworkEvents` по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="be11b-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="be11b-120">Задание диапазона времени</span><span class="sxs-lookup"><span data-stu-id="be11b-120">Set the time range</span></span>
<span data-ttu-id="be11b-121">Первый элемент, который является фильтром по времени, ограничивается на предыдущие семь дней.</span><span class="sxs-lookup"><span data-stu-id="be11b-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="be11b-122">Сохранение как можно более узкого временного диапазона гарантирует, что запросы работают хорошо, возвращают управляемые результаты и не превышают времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="be11b-122">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="be11b-123">Проверка определенных процессов</span><span class="sxs-lookup"><span data-stu-id="be11b-123">Check specific processes</span></span>
<span data-ttu-id="be11b-124">За диапазоном времени следует Поиск имен файлов процессов, представляющих приложение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be11b-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="be11b-125">Поиск определенных командных строк</span><span class="sxs-lookup"><span data-stu-id="be11b-125">Search for specific command strings</span></span>
<span data-ttu-id="be11b-126">Затем запрос выполняет поиск строк в командных строках, которые обычно используются для загрузки файлов с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be11b-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="be11b-127">Настройка столбцов результатов и длины</span><span class="sxs-lookup"><span data-stu-id="be11b-127">Customize result columns and length</span></span> 
<span data-ttu-id="be11b-128">Теперь, когда ваш запрос четко определяет данные, которые вы хотите найти, вы можете добавить элементы, которые определяют то, как будут выглядеть результаты.</span><span class="sxs-lookup"><span data-stu-id="be11b-128">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="be11b-129">`project`Возвращает определенные столбцы и позволяет `top` ограничить количество результатов.</span><span class="sxs-lookup"><span data-stu-id="be11b-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="be11b-130">Эти операторы помогают убедиться в том, что результаты имеют правильный формат и их достаточно велики и просты в обработке.</span><span class="sxs-lookup"><span data-stu-id="be11b-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="be11b-131">Нажмите кнопку **Выполнить запрос**, чтобы увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="be11b-131">Click **Run query** to see the results.</span></span> <span data-ttu-id="be11b-132">Выберите значок развернуть в правом верхнем углу редактора запросов, чтобы сосредоточиться на запросе поиска и результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="be11b-132">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Изображение элемента управления "развернуть" в редакторе запросов поиска с расширенным поиском](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="be11b-134">Вы можете просматривать результаты запроса в виде диаграмм и быстро настраивать фильтры.</span><span class="sxs-lookup"><span data-stu-id="be11b-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="be11b-135">Рекомендации по [работе с результатами запросов](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="be11b-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="be11b-136">Познакомьтесь с обычными операторами запросов для расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="be11b-136">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="be11b-137">Теперь, когда вы выполнили свой первый запрос и получили общее представление о его компонентах, пришло время вернуться немного назад и изучить некоторые основы.</span><span class="sxs-lookup"><span data-stu-id="be11b-137">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="be11b-138">Язык запросов Kusto, используемый в расширенной охоте, поддерживает ряд операторов, включая обычные, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="be11b-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="be11b-139">Оператор</span><span class="sxs-lookup"><span data-stu-id="be11b-139">Operator</span></span> | <span data-ttu-id="be11b-140">Описание и использование</span><span class="sxs-lookup"><span data-stu-id="be11b-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="be11b-141">Фильтрация таблицы по подмножеству строк, удовлетворяющих предикату.</span><span class="sxs-lookup"><span data-stu-id="be11b-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="be11b-142">Создание таблицы, в которой объединяется содержимое исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="be11b-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="be11b-143">Объединение строк двух таблиц, чтобы сформировать новую таблицу, сопоставляя значения заданных столбцов из каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="be11b-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="be11b-144">Возврат количества записей в исходный набор записей.</span><span class="sxs-lookup"><span data-stu-id="be11b-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="be11b-145">Возврат первых N записей, отсортированных по заданным столбцам.</span><span class="sxs-lookup"><span data-stu-id="be11b-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="be11b-146">Возврат до заданного количества строк.</span><span class="sxs-lookup"><span data-stu-id="be11b-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="be11b-147">Выбор столбцов, которые нужно включить, переименовать или перетащить, и вставка новых вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="be11b-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="be11b-148">Создание вычисляемых столбцов и их добавление в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="be11b-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="be11b-149">Возврат динамического массива (JSON) множества различных значений, которые выражение (Expr) принимает в группе.</span><span class="sxs-lookup"><span data-stu-id="be11b-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="be11b-150">Поиск строк, соответствующих предикату, по набору таблиц.</span><span class="sxs-lookup"><span data-stu-id="be11b-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="be11b-151">Чтобы просмотреть реальные примеры этих операторов, запустите их из пункта **Начать работу** в разделе Расширенная охота.</span><span class="sxs-lookup"><span data-stu-id="be11b-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="be11b-152">Общие сведения о типах данных и их влиянии на синтаксис запроса</span><span class="sxs-lookup"><span data-stu-id="be11b-152">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="be11b-153">Данные в таблицах расширенной охоты, как правило, относятся к указанным ниже типам данных.</span><span class="sxs-lookup"><span data-stu-id="be11b-153">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="be11b-154">Тип данных</span><span class="sxs-lookup"><span data-stu-id="be11b-154">Data type</span></span> | <span data-ttu-id="be11b-155">Описание и влияния запроса</span><span class="sxs-lookup"><span data-stu-id="be11b-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="be11b-156">Данные и сведения о времени, обычно представляющие временные метки событий</span><span class="sxs-lookup"><span data-stu-id="be11b-156">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="be11b-157">Строка символов</span><span class="sxs-lookup"><span data-stu-id="be11b-157">Character string</span></span> |
| `bool` | <span data-ttu-id="be11b-158">Истина или ложь</span><span class="sxs-lookup"><span data-stu-id="be11b-158">True or false</span></span> |
| `int` | <span data-ttu-id="be11b-159">32-разрядное числовое значение</span><span class="sxs-lookup"><span data-stu-id="be11b-159">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="be11b-160">64-разрядное числовое значение</span><span class="sxs-lookup"><span data-stu-id="be11b-160">64-bit numeric value</span></span> |

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="be11b-161">Помощь при написании запросов</span><span class="sxs-lookup"><span data-stu-id="be11b-161">Get help as you write queries</span></span>
<span data-ttu-id="be11b-162">Ниже перечислены функции, благодаря которым запросы можно создавать быстрее.</span><span class="sxs-lookup"><span data-stu-id="be11b-162">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="be11b-163">Автозаполнение **— при** написании запросов Расширенный поиск предоставляет рекомендации от IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="be11b-163">**Autosuggest** — as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="be11b-164">**Дерево схемы** — представление схемы, включающее список таблиц и их столбцов, предоставляется рядом с рабочей областью.</span><span class="sxs-lookup"><span data-stu-id="be11b-164">**Schema tree** — a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="be11b-165">Чтобы получить об элементе дополнительные сведения, нужно навести на него указатель мыши.</span><span class="sxs-lookup"><span data-stu-id="be11b-165">For more information, hover over an item.</span></span> <span data-ttu-id="be11b-166">Чтобы вставить элемент в редактор запросов, нужно дважды щелкнуть по нему.</span><span class="sxs-lookup"><span data-stu-id="be11b-166">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="be11b-167">**[Справочник по схеме](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — ссылка на портал со описаниями таблиц и столбцов, а также поддерживаемые типы событий ( `ActionType` значения) и примеры запросов</span><span class="sxs-lookup"><span data-stu-id="be11b-167">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="be11b-168">Работать с несколькими запросами в редакторе</span><span class="sxs-lookup"><span data-stu-id="be11b-168">Work with multiple queries in the editor</span></span>
<span data-ttu-id="be11b-169">Редактор запросов может служить в качестве рабочей панели для экспериментов с несколькими запросами.</span><span class="sxs-lookup"><span data-stu-id="be11b-169">The query editor can serve as your scratch pad for experimenting with multiple queries.</span></span> <span data-ttu-id="be11b-170">Чтобы использовать несколько запросов, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="be11b-170">To use multiple queries:</span></span>

- <span data-ttu-id="be11b-171">Разделяйте каждый запрос на пустую строку.</span><span class="sxs-lookup"><span data-stu-id="be11b-171">Separate each query with an empty line.</span></span>
- <span data-ttu-id="be11b-172">Поместите курсор в любую часть запроса, чтобы выбрать этот запрос перед его запуском.</span><span class="sxs-lookup"><span data-stu-id="be11b-172">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="be11b-173">При этом будет запущен только выбранный запрос.</span><span class="sxs-lookup"><span data-stu-id="be11b-173">This will run only the selected query.</span></span> <span data-ttu-id="be11b-174">Чтобы выполнить другой запрос, переместите курсор соответствующим образом и выберите команду **выполнить запрос**.</span><span class="sxs-lookup"><span data-stu-id="be11b-174">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Изображение редактора запросов с несколькими запросами](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="be11b-176">Использование примеров запросов</span><span class="sxs-lookup"><span data-stu-id="be11b-176">Use sample queries</span></span>

<span data-ttu-id="be11b-177">Раздел **Начало работы** содержит несколько простых запросов, использующих часто используемые операторы.</span><span class="sxs-lookup"><span data-stu-id="be11b-177">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="be11b-178">Попробуйте выполнить эти запросы и внести в них небольшие изменения.</span><span class="sxs-lookup"><span data-stu-id="be11b-178">Try running these queries and making small modifications to them.</span></span>

![Изображение окна расширенной охоты](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="be11b-180">Кроме примеров базовых запросов, вы можете получить доступ к [общим запросам](advanced-hunting-shared-queries.md) для определенных сценариев охоты на угрозы.</span><span class="sxs-lookup"><span data-stu-id="be11b-180">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="be11b-181">Ознакомьтесь с общими запросами в левой части страницы репозитории запросов GitHub.</span><span class="sxs-lookup"><span data-stu-id="be11b-181">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="be11b-182">Документация по языку условий запросов</span><span class="sxs-lookup"><span data-stu-id="be11b-182">Access query language documentation</span></span>

<span data-ttu-id="be11b-183">Дополнительные сведения о языке запросов Kusto и поддерживаемых операторах см. в статье [Документация по языку запросов Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="be11b-183">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="be11b-184">См. также</span><span class="sxs-lookup"><span data-stu-id="be11b-184">Related topics</span></span>
- [<span data-ttu-id="be11b-185">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="be11b-185">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="be11b-186">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="be11b-186">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="be11b-187">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="be11b-187">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="be11b-188">Слежение за устройствами, сообщениями электронной почты, приложениями и удостоверениями</span><span class="sxs-lookup"><span data-stu-id="be11b-188">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="be11b-189">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="be11b-189">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="be11b-190">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="be11b-190">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
