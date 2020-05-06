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
ms.openlocfilehash: 14de9d84ef19be3dcf1e630b2814a6060bfe7f27
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036503"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="2202f-104">Познакомьтесь с языком запросов расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="2202f-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="2202f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2202f-105">**Applies to:**</span></span>
- <span data-ttu-id="2202f-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="2202f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2202f-107">Расширенный поиск основывается на [языке запросов Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="2202f-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="2202f-108">С помощью синтаксиса и операторов Кусто можно создавать запросы, которые позволяют найти информацию в [схеме](advanced-hunting-schema-tables.md), специально структурированной для расширенного поиска.</span><span class="sxs-lookup"><span data-stu-id="2202f-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="2202f-109">Чтобы лучше понять эти концепции, запустите ваш первый запрос.</span><span class="sxs-lookup"><span data-stu-id="2202f-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="2202f-110">Попробуйте выполнить первый запрос</span><span class="sxs-lookup"><span data-stu-id="2202f-110">Try your first query</span></span>

<span data-ttu-id="2202f-111">В центре безопасности Microsoft 365 выберите Поиск, **чтобы запустить** первый запрос.</span><span class="sxs-lookup"><span data-stu-id="2202f-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="2202f-112">Используйте следующий пример:</span><span class="sxs-lookup"><span data-stu-id="2202f-112">Use the following example:</span></span>

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

<span data-ttu-id="2202f-113">Так это будет выглядеть в расширенной охоте.</span><span class="sxs-lookup"><span data-stu-id="2202f-113">This is how it will look like in advanced hunting.</span></span>

![Изображение запроса на расширенный поиск по защите от угроз Майкрософт](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="2202f-115">Опишите запрос и укажите таблицы для поиска</span><span class="sxs-lookup"><span data-stu-id="2202f-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="2202f-116">В начале запроса добавлен краткий комментарий, описывающий его назначение.</span><span class="sxs-lookup"><span data-stu-id="2202f-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="2202f-117">Это поможет в том случае, если позже вы решите сохранить запрос и поделиться им с другими пользователями в Организации.</span><span class="sxs-lookup"><span data-stu-id="2202f-117">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="2202f-118">Как правило, запрос начинается с имени таблицы, за которым следует ряд элементов, начинающихся с вертикальной черты (`|`).</span><span class="sxs-lookup"><span data-stu-id="2202f-118">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="2202f-119">В этом примере мы начнем с создания объединения двух таблиц `DeviceProcessEvents` и `DeviceNetworkEvents`добавления элементов перегрузки по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="2202f-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="2202f-120">Задание диапазона времени</span><span class="sxs-lookup"><span data-stu-id="2202f-120">Set the time range</span></span>
<span data-ttu-id="2202f-121">Первый элемент, который является фильтром по времени, ограничивается на предыдущие семь дней.</span><span class="sxs-lookup"><span data-stu-id="2202f-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="2202f-122">Сохранение как можно более узкого временного диапазона гарантирует, что запросы работают хорошо, возвращают управляемые результаты и не превышают времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="2202f-122">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="2202f-123">Проверка определенных процессов</span><span class="sxs-lookup"><span data-stu-id="2202f-123">Check specific processes</span></span>
<span data-ttu-id="2202f-124">За диапазоном времени следует Поиск имен файлов процессов, представляющих приложение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2202f-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="2202f-125">Поиск определенных командных строк</span><span class="sxs-lookup"><span data-stu-id="2202f-125">Search for specific command strings</span></span>
<span data-ttu-id="2202f-126">Затем запрос выполняет поиск строк в командных строках, которые обычно используются для загрузки файлов с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2202f-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="2202f-127">Настройка столбцов результатов и длины</span><span class="sxs-lookup"><span data-stu-id="2202f-127">Customize result columns and length</span></span> 
<span data-ttu-id="2202f-128">Теперь, когда ваш запрос четко определяет данные, которые вы хотите найти, вы можете добавить элементы, которые определяют то, как будут выглядеть результаты.</span><span class="sxs-lookup"><span data-stu-id="2202f-128">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="2202f-129">`project`Возвращает определенные столбцы и `top` позволяет ограничить количество результатов.</span><span class="sxs-lookup"><span data-stu-id="2202f-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="2202f-130">Эти операторы помогают убедиться в том, что результаты имеют правильный формат и их достаточно велики и просты в обработке.</span><span class="sxs-lookup"><span data-stu-id="2202f-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="2202f-131">Нажмите кнопку **Выполнить запрос**, чтобы увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="2202f-131">Click **Run query** to see the results.</span></span> <span data-ttu-id="2202f-132">Выберите значок развернуть в правом верхнем углу редактора запросов, чтобы сосредоточиться на запросе поиска и результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="2202f-132">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Изображение элемента управления "развернуть" в редакторе запросов поиска с расширенным поиском](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="2202f-134">Вы можете просматривать результаты запроса в виде диаграмм и быстро настраивать фильтры.</span><span class="sxs-lookup"><span data-stu-id="2202f-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="2202f-135">Рекомендации по [работе с результатами запросов](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="2202f-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="2202f-136">Познакомьтесь с обычными операторами запросов для расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="2202f-136">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="2202f-137">Теперь, когда вы выполнили свой первый запрос и получили общее представление о его компонентах, пришло время вернуться немного назад и изучить некоторые основы.</span><span class="sxs-lookup"><span data-stu-id="2202f-137">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="2202f-138">Язык запросов Kusto, используемый в расширенной охоте, поддерживает ряд операторов, включая обычные, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="2202f-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="2202f-139">Оператор</span><span class="sxs-lookup"><span data-stu-id="2202f-139">Operator</span></span> | <span data-ttu-id="2202f-140">Описание и использование</span><span class="sxs-lookup"><span data-stu-id="2202f-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="2202f-141">Фильтрация таблицы по подмножеству строк, удовлетворяющих предикату.</span><span class="sxs-lookup"><span data-stu-id="2202f-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="2202f-142">Создание таблицы, в которой объединяется содержимое исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="2202f-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="2202f-143">Объединение строк двух таблиц, чтобы сформировать новую таблицу, сопоставляя значения заданных столбцов из каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="2202f-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="2202f-144">Возврат количества записей в исходный набор записей.</span><span class="sxs-lookup"><span data-stu-id="2202f-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="2202f-145">Возврат первых N записей, отсортированных по заданным столбцам.</span><span class="sxs-lookup"><span data-stu-id="2202f-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="2202f-146">Возврат до заданного количества строк.</span><span class="sxs-lookup"><span data-stu-id="2202f-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="2202f-147">Выбор столбцов, которые нужно включить, переименовать или перетащить, и вставка новых вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="2202f-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="2202f-148">Создание вычисляемых столбцов и их добавление в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="2202f-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="2202f-149">Возврат динамического массива (JSON) множества различных значений, которые выражение (Expr) принимает в группе.</span><span class="sxs-lookup"><span data-stu-id="2202f-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="2202f-150">Поиск строк, соответствующих предикату, по набору таблиц.</span><span class="sxs-lookup"><span data-stu-id="2202f-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="2202f-151">Чтобы просмотреть реальные примеры этих операторов, запустите их из пункта **Начать работу** в разделе Расширенная охота.</span><span class="sxs-lookup"><span data-stu-id="2202f-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="2202f-152">Общие сведения о типах данных и их влиянии на синтаксис запроса</span><span class="sxs-lookup"><span data-stu-id="2202f-152">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="2202f-153">Данные в таблицах расширенной охоты, как правило, относятся к указанным ниже типам данных.</span><span class="sxs-lookup"><span data-stu-id="2202f-153">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="2202f-154">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2202f-154">Data type</span></span> | <span data-ttu-id="2202f-155">Описание и влияния запроса</span><span class="sxs-lookup"><span data-stu-id="2202f-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="2202f-156">Данные и сведения о времени, обычно представляющие временные метки событий</span><span class="sxs-lookup"><span data-stu-id="2202f-156">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="2202f-157">Строка символов</span><span class="sxs-lookup"><span data-stu-id="2202f-157">Character string</span></span> |
| `bool` | <span data-ttu-id="2202f-158">Истина или ложь</span><span class="sxs-lookup"><span data-stu-id="2202f-158">True or false</span></span> |
| `int` | <span data-ttu-id="2202f-159">32-разрядное числовое значение</span><span class="sxs-lookup"><span data-stu-id="2202f-159">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="2202f-160">64-разрядное числовое значение</span><span class="sxs-lookup"><span data-stu-id="2202f-160">64-bit numeric value</span></span> |

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="2202f-161">Помощь при написании запросов</span><span class="sxs-lookup"><span data-stu-id="2202f-161">Get help as you write queries</span></span>
<span data-ttu-id="2202f-162">Ниже перечислены функции, благодаря которым запросы можно создавать быстрее.</span><span class="sxs-lookup"><span data-stu-id="2202f-162">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="2202f-163">Автозаполнение **— при** написании запросов Расширенный поиск предоставляет рекомендации от IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="2202f-163">**Autosuggest** — as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="2202f-164">**Справочник по схеме** — справочник по схеме со списком таблиц и их столбцов, расположенный рядом с рабочей областью.</span><span class="sxs-lookup"><span data-stu-id="2202f-164">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="2202f-165">Чтобы получить об элементе дополнительные сведения, нужно навести на него указатель мыши.</span><span class="sxs-lookup"><span data-stu-id="2202f-165">For more information, hover over an item.</span></span> <span data-ttu-id="2202f-166">Чтобы вставить элемент в редактор запросов, нужно дважды щелкнуть по нему.</span><span class="sxs-lookup"><span data-stu-id="2202f-166">Double-click an item to insert it to the query editor.</span></span>

## <a name="use-sample-queries"></a><span data-ttu-id="2202f-167">Использование примеров запросов</span><span class="sxs-lookup"><span data-stu-id="2202f-167">Use sample queries</span></span>

<span data-ttu-id="2202f-168">Раздел **Начало работы** содержит несколько простых запросов, использующих часто используемые операторы.</span><span class="sxs-lookup"><span data-stu-id="2202f-168">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="2202f-169">Попробуйте выполнить эти запросы и внести в них небольшие изменения.</span><span class="sxs-lookup"><span data-stu-id="2202f-169">Try running these queries and making small modifications to them.</span></span>

![Изображение окна расширенной охоты](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="2202f-171">Кроме примеров базовых запросов, вы можете получить доступ к [общим запросам](advanced-hunting-shared-queries.md) для определенных сценариев охоты на угрозы.</span><span class="sxs-lookup"><span data-stu-id="2202f-171">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="2202f-172">Ознакомьтесь с общими запросами в левой части страницы репозитории запросов GitHub.</span><span class="sxs-lookup"><span data-stu-id="2202f-172">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="2202f-173">Документация по языку условий запросов</span><span class="sxs-lookup"><span data-stu-id="2202f-173">Access query language documentation</span></span>

<span data-ttu-id="2202f-174">Дополнительные сведения о языке запросов Kusto и поддерживаемых операторах см. в статье [Документация по языку запросов Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="2202f-174">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2202f-175">См. также</span><span class="sxs-lookup"><span data-stu-id="2202f-175">Related topics</span></span>
- [<span data-ttu-id="2202f-176">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="2202f-176">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2202f-177">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="2202f-177">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="2202f-178">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="2202f-178">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2202f-179">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="2202f-179">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2202f-180">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="2202f-180">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2202f-181">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="2202f-181">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
