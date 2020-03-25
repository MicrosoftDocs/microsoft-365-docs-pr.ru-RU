---
title: Познакомьтесь с языком запросов расширенной охоты на угрозы в службе защиты от угроз (Майкрософт)
description: Создайте ваш первый запрос охоты на угрозы и узнайте о распространенных операторах и других аспектах языка запросов расширенной охоты на угрозы
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, язык, сведения, первый запрос, телеметрии, события, телеметрии, пользовательские обнаружения, схема, события, телеметрии, пользовательские обнаружения, схема, Кусто, операторы, типы данных, PowerShell Загрузка, пример запроса
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
ms.openlocfilehash: e093bd9c5a76b44cf66591b4212f37014189186e
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929000"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="b6111-104">Познакомьтесь с языком запросов расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="b6111-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="b6111-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b6111-105">**Applies to:**</span></span>
- <span data-ttu-id="b6111-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b6111-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b6111-107">Расширенный поиск основывается на [языке запросов Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="b6111-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="b6111-108">С помощью синтаксиса и операторов Кусто можно создавать запросы, которые позволяют найти информацию в [схеме](advanced-hunting-schema-tables.md), специально структурированной для расширенного поиска.</span><span class="sxs-lookup"><span data-stu-id="b6111-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="b6111-109">Чтобы лучше понять эти концепции, запустите ваш первый запрос.</span><span class="sxs-lookup"><span data-stu-id="b6111-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="b6111-110">Попробуйте выполнить первый запрос</span><span class="sxs-lookup"><span data-stu-id="b6111-110">Try your first query</span></span>

<span data-ttu-id="b6111-111">В центре безопасности Microsoft 365 выберите Поиск, **чтобы запустить** первый запрос.</span><span class="sxs-lookup"><span data-stu-id="b6111-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="b6111-112">Используйте следующий пример:</span><span class="sxs-lookup"><span data-stu-id="b6111-112">Use the following example:</span></span>

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

<span data-ttu-id="b6111-113">Так это будет выглядеть в расширенной охоте.</span><span class="sxs-lookup"><span data-stu-id="b6111-113">This is how it will look like in advanced hunting.</span></span>

![Изображение запроса на расширенный поиск по защите от угроз Майкрософт](../../media/advanced-hunting-query-example.png)

<span data-ttu-id="b6111-115">В начале запроса добавлен краткий комментарий, описывающий его назначение.</span><span class="sxs-lookup"><span data-stu-id="b6111-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="b6111-116">Это поможет в том случае, если позже вы решите сохранить запрос и поделиться им с другими пользователями в Организации.</span><span class="sxs-lookup"><span data-stu-id="b6111-116">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="b6111-117">Как правило, запрос начинается с имени таблицы, за которым следует ряд элементов, начинающихся с вертикальной черты (`|`).</span><span class="sxs-lookup"><span data-stu-id="b6111-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="b6111-118">В этом примере мы начнем с создания объединения двух таблиц `DeviceProcessEvents` и `DeviceNetworkEvents`добавления элементов перегрузки по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="b6111-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
<span data-ttu-id="b6111-119">Первый элемент, который является фильтром по времени, ограничивается на предыдущие семь дней.</span><span class="sxs-lookup"><span data-stu-id="b6111-119">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="b6111-120">Сохранение как можно более узкого временного диапазона гарантирует, что запросы работают хорошо, возвращают управляемые результаты и не превышают времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="b6111-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

<span data-ttu-id="b6111-121">За диапазоном времени следует Поиск имен файлов процессов, представляющих приложение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6111-121">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

<span data-ttu-id="b6111-122">Затем запрос выполняет поиск строк в командных строках, которые обычно используются для загрузки файлов с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6111-122">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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
<span data-ttu-id="b6111-123">Теперь, когда ваш запрос четко определяет данные, которые вы хотите найти, вы можете добавить элементы, которые определяют то, как будут выглядеть результаты.</span><span class="sxs-lookup"><span data-stu-id="b6111-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="b6111-124">`project`Возвращает определенные столбцы и `top` позволяет ограничить количество результатов, чтобы результаты правильно отформатированы и были достаточно велики и легко обработаны.</span><span class="sxs-lookup"><span data-stu-id="b6111-124">`project` returns specific columns and `top` limits the number of results, helping ensure the results well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="b6111-125">Нажмите кнопку **Выполнить запрос**, чтобы увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="b6111-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="b6111-126">Выберите значок развернуть в правом верхнем углу редактора запросов, чтобы сосредоточиться на запросе поиска и результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="b6111-126">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span>

![Изображение элемента управления "развернуть" в редакторе запросов поиска с расширенным поиском](../../media/advanced-hunting-expand.png)

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="b6111-128">Познакомьтесь с обычными операторами запросов для расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="b6111-128">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="b6111-129">Теперь, когда вы выполнили свой первый запрос и получили общее представление о его компонентах, пришло время вернуться немного назад и изучить некоторые основы.</span><span class="sxs-lookup"><span data-stu-id="b6111-129">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="b6111-130">Язык запросов Kusto, используемый в расширенной охоте, поддерживает ряд операторов, включая обычные, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="b6111-130">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="b6111-131">Оператор</span><span class="sxs-lookup"><span data-stu-id="b6111-131">Operator</span></span> | <span data-ttu-id="b6111-132">Описание и использование</span><span class="sxs-lookup"><span data-stu-id="b6111-132">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="b6111-133">Фильтрация таблицы по подмножеству строк, удовлетворяющих предикату.</span><span class="sxs-lookup"><span data-stu-id="b6111-133">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="b6111-134">Создание таблицы, в которой объединяется содержимое исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="b6111-134">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="b6111-135">Объединение строк двух таблиц, чтобы сформировать новую таблицу, сопоставляя значения заданных столбцов из каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="b6111-135">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="b6111-136">Возврат количества записей в исходный набор записей.</span><span class="sxs-lookup"><span data-stu-id="b6111-136">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="b6111-137">Возврат первых N записей, отсортированных по заданным столбцам.</span><span class="sxs-lookup"><span data-stu-id="b6111-137">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="b6111-138">Возврат до заданного количества строк.</span><span class="sxs-lookup"><span data-stu-id="b6111-138">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="b6111-139">Выбор столбцов, которые нужно включить, переименовать или перетащить, и вставка новых вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="b6111-139">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="b6111-140">Создание вычисляемых столбцов и их добавление в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="b6111-140">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="b6111-141">Возврат динамического массива (JSON) множества различных значений, которые выражение (Expr) принимает в группе.</span><span class="sxs-lookup"><span data-stu-id="b6111-141">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="b6111-142">Поиск строк, соответствующих предикату, по набору таблиц.</span><span class="sxs-lookup"><span data-stu-id="b6111-142">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="b6111-143">Чтобы просмотреть реальные примеры этих операторов, запустите их из пункта **Начать работу** в разделе Расширенная охота.</span><span class="sxs-lookup"><span data-stu-id="b6111-143">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="b6111-144">Общие сведения о типах данных и их влиянии на синтаксис запроса</span><span class="sxs-lookup"><span data-stu-id="b6111-144">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="b6111-145">Данные в таблицах расширенной охоты, как правило, относятся к указанным ниже типам данных.</span><span class="sxs-lookup"><span data-stu-id="b6111-145">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="b6111-146">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b6111-146">Data type</span></span> | <span data-ttu-id="b6111-147">Описание и влияния запроса</span><span class="sxs-lookup"><span data-stu-id="b6111-147">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="b6111-148">Данные и сведения о времени, обычно представляющие временные метки событий</span><span class="sxs-lookup"><span data-stu-id="b6111-148">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="b6111-149">Строка символов</span><span class="sxs-lookup"><span data-stu-id="b6111-149">Character string</span></span> |
| `bool` | <span data-ttu-id="b6111-150">Истина или ложь</span><span class="sxs-lookup"><span data-stu-id="b6111-150">True or false</span></span> |
| `int` | <span data-ttu-id="b6111-151">32-разрядное числовое значение</span><span class="sxs-lookup"><span data-stu-id="b6111-151">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="b6111-152">64-разрядное числовое значение</span><span class="sxs-lookup"><span data-stu-id="b6111-152">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="b6111-153">Использование примеров запросов</span><span class="sxs-lookup"><span data-stu-id="b6111-153">Use sample queries</span></span>

<span data-ttu-id="b6111-154">Раздел **Начало работы** содержит несколько простых запросов, использующих часто используемые операторы.</span><span class="sxs-lookup"><span data-stu-id="b6111-154">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="b6111-155">Попробуйте выполнить эти запросы и внести в них небольшие изменения.</span><span class="sxs-lookup"><span data-stu-id="b6111-155">Try running these queries and making small modifications to them.</span></span>

![Изображение окна расширенной охоты](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="b6111-157">Кроме примеров базовых запросов, вы можете получить доступ к [общим запросам](advanced-hunting-shared-queries.md) для определенных сценариев охоты на угрозы.</span><span class="sxs-lookup"><span data-stu-id="b6111-157">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="b6111-158">Ознакомьтесь с общими запросами в левой части страницы репозитории запросов GitHub.</span><span class="sxs-lookup"><span data-stu-id="b6111-158">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="b6111-159">Документация по языку условий запросов</span><span class="sxs-lookup"><span data-stu-id="b6111-159">Access query language documentation</span></span>

<span data-ttu-id="b6111-160">Дополнительные сведения о языке запросов Kusto и поддерживаемых операторах см. в статье [Документация по языку запросов Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="b6111-160">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b6111-161">См. также</span><span class="sxs-lookup"><span data-stu-id="b6111-161">Related topics</span></span>
- [<span data-ttu-id="b6111-162">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="b6111-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b6111-163">Работать с результатами запроса</span><span class="sxs-lookup"><span data-stu-id="b6111-163">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="b6111-164">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="b6111-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b6111-165">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="b6111-165">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b6111-166">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="b6111-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b6111-167">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="b6111-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
