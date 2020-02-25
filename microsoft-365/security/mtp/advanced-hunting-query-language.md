---
title: Познакомьтесь с языком запросов расширенной охоты на угрозы в службе защиты от угроз (Майкрософт)
description: Создайте ваш первый запрос охоты на угрозы и узнайте о распространенных операторах и других аспектах языка запросов расширенной охоты на угрозы
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, язык, сведения, первый запрос, телеметрии, события, телеметрия, пользовательские обнаружения, схема, Кусто, операторы, типы данных
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
ms.openlocfilehash: eda9b893057afd54a644f0091bf4e1b421bd5439
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234698"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="82a58-104">Познакомьтесь с языком запросов расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="82a58-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="82a58-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="82a58-105">**Applies to:**</span></span>
- <span data-ttu-id="82a58-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="82a58-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="82a58-107">Расширенный поиск основывается на [языке запросов Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="82a58-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="82a58-108">С помощью синтаксиса и операторов Кусто можно создавать запросы, которые позволяют найти информацию в [схеме](advanced-hunting-schema-tables.md), специально структурированной для расширенного поиска.</span><span class="sxs-lookup"><span data-stu-id="82a58-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="82a58-109">Чтобы лучше понять эти концепции, запустите ваш первый запрос.</span><span class="sxs-lookup"><span data-stu-id="82a58-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="82a58-110">Попробуйте выполнить первый запрос</span><span class="sxs-lookup"><span data-stu-id="82a58-110">Try your first query</span></span>

<span data-ttu-id="82a58-111">Чтобы выполнить ваш первый запрос, в центре безопасности Microsoft 365 перейдите в раздел **Охота**.</span><span class="sxs-lookup"><span data-stu-id="82a58-111">in the Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="82a58-112">Используйте следующий пример:</span><span class="sxs-lookup"><span data-stu-id="82a58-112">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents 
| where Timestamp > ago(7d)
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE") 
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

<span data-ttu-id="82a58-113">Так это будет выглядеть в расширенной охоте.</span><span class="sxs-lookup"><span data-stu-id="82a58-113">This is how it will look like in advanced hunting.</span></span>

![Изображение запроса расширенной охоты в ATP в Microsoft Defender](../../media/advanced-hunting-query-example.png)

<span data-ttu-id="82a58-115">Запрос начинается с короткого комментария, описывающего назначение запроса.</span><span class="sxs-lookup"><span data-stu-id="82a58-115">The query starts with a short comment describing what it is for.</span></span> <span data-ttu-id="82a58-116">Это будет полезным, если впоследствии вы решите сохранить свой запрос и поделиться им с другими пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="82a58-116">This helps if you later decide to save your query and share it with others in your organization.</span></span>

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents
```

<span data-ttu-id="82a58-117">Как правило, запрос начинается с имени таблицы, за которым следует ряд элементов, начинающихся с вертикальной черты (`|`).</span><span class="sxs-lookup"><span data-stu-id="82a58-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="82a58-118">В этом примере мы начинаем с добавления имени таблицы `DeviceProcessEvents` и при необходимости добавляем элементы, отмеченные вертикальной чертой.</span><span class="sxs-lookup"><span data-stu-id="82a58-118">In this example, we start by adding  with the table name `DeviceProcessEvents` and add piped elements as needed.</span></span>

<span data-ttu-id="82a58-119">Первый элемент, отмеченный вертикальной чертой, является фильтром времени, ограниченном предыдущими семью днями.</span><span class="sxs-lookup"><span data-stu-id="82a58-119">The first piped element is a time filter scoped within the previous seven days.</span></span> <span data-ttu-id="82a58-120">Сохранение как можно более узкого временного диапазона гарантирует, что запросы работают хорошо, возвращают управляемые результаты и не превышают времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="82a58-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

<span data-ttu-id="82a58-121">За диапазоном времени непосредственно следует поиск файлов, представляющих приложение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82a58-121">The time range is immediately followed by a search for files representing the PowerShell application.</span></span>

```kusto
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

<span data-ttu-id="82a58-122">Затем запрос ищет командные строки, которые, как правило, используются с PowerShell для скачивания файлов.</span><span class="sxs-lookup"><span data-stu-id="82a58-122">Afterwards, the query looks for command lines that are typically used with PowerShell to download files.</span></span>

```kusto
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

<span data-ttu-id="82a58-123">Теперь, когда ваш запрос четко определяет данные, которые вы хотите найти, вы можете добавить элементы, которые определяют то, как будут выглядеть результаты.</span><span class="sxs-lookup"><span data-stu-id="82a58-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="82a58-124">`project` возвращает определенные столбцы и `top` ограничивает количество результатов, делая результаты хорошо отформатированными и достаточно большими и простыми в обработке.</span><span class="sxs-lookup"><span data-stu-id="82a58-124">`project` returns specific columns and `top` limits the number of results, making the results well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

<span data-ttu-id="82a58-125">Нажмите кнопку **Выполнить запрос**, чтобы увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="82a58-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="82a58-126">Вы можете развернуть экран, чтобы сосредоточиться на вашем запросе охоты и результатах.</span><span class="sxs-lookup"><span data-stu-id="82a58-126">You can expand the screen view so you can focus on your hunting query and the results.</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="82a58-127">Познакомьтесь с обычными операторами запросов для расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="82a58-127">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="82a58-128">Теперь, когда вы выполнили свой первый запрос и получили общее представление о его компонентах, пришло время вернуться немного назад и изучить некоторые основы.</span><span class="sxs-lookup"><span data-stu-id="82a58-128">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="82a58-129">Язык запросов Kusto, используемый в расширенной охоте, поддерживает ряд операторов, включая обычные, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="82a58-129">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="82a58-130">Оператор</span><span class="sxs-lookup"><span data-stu-id="82a58-130">Operator</span></span> | <span data-ttu-id="82a58-131">Описание и использование</span><span class="sxs-lookup"><span data-stu-id="82a58-131">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="82a58-132">Фильтрация таблицы по подмножеству строк, удовлетворяющих предикату.</span><span class="sxs-lookup"><span data-stu-id="82a58-132">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="82a58-133">Создание таблицы, в которой объединяется содержимое исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="82a58-133">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="82a58-134">Объединение строк двух таблиц, чтобы сформировать новую таблицу, сопоставляя значения заданных столбцов из каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="82a58-134">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="82a58-135">Возврат количества записей в исходный набор записей.</span><span class="sxs-lookup"><span data-stu-id="82a58-135">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="82a58-136">Возврат первых N записей, отсортированных по заданным столбцам.</span><span class="sxs-lookup"><span data-stu-id="82a58-136">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="82a58-137">Возврат до заданного количества строк.</span><span class="sxs-lookup"><span data-stu-id="82a58-137">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="82a58-138">Выбор столбцов, которые нужно включить, переименовать или перетащить, и вставка новых вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="82a58-138">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="82a58-139">Создание вычисляемых столбцов и их добавление в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="82a58-139">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="82a58-140">Возврат динамического массива (JSON) множества различных значений, которые выражение (Expr) принимает в группе.</span><span class="sxs-lookup"><span data-stu-id="82a58-140">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="82a58-141">Поиск строк, соответствующих предикату, по набору таблиц.</span><span class="sxs-lookup"><span data-stu-id="82a58-141">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="82a58-142">Чтобы просмотреть реальные примеры этих операторов, запустите их из пункта **Начать работу** в разделе Расширенная охота.</span><span class="sxs-lookup"><span data-stu-id="82a58-142">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="82a58-143">Общие сведения о типах данных и их влиянии на синтаксис запроса</span><span class="sxs-lookup"><span data-stu-id="82a58-143">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="82a58-144">Данные в таблицах расширенной охоты, как правило, относятся к указанным ниже типам данных.</span><span class="sxs-lookup"><span data-stu-id="82a58-144">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="82a58-145">Тип данных</span><span class="sxs-lookup"><span data-stu-id="82a58-145">Data type</span></span> | <span data-ttu-id="82a58-146">Описание и влияния запроса</span><span class="sxs-lookup"><span data-stu-id="82a58-146">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="82a58-147">Данные и сведения о времени, обычно представляющие временные метки событий</span><span class="sxs-lookup"><span data-stu-id="82a58-147">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="82a58-148">Строка символов</span><span class="sxs-lookup"><span data-stu-id="82a58-148">Character string</span></span> |
| `bool` | <span data-ttu-id="82a58-149">Истина или ложь</span><span class="sxs-lookup"><span data-stu-id="82a58-149">True or false</span></span> |
| `int` | <span data-ttu-id="82a58-150">32-разрядное числовое значение</span><span class="sxs-lookup"><span data-stu-id="82a58-150">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="82a58-151">64-разрядное числовое значение</span><span class="sxs-lookup"><span data-stu-id="82a58-151">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="82a58-152">Использование примеров запросов</span><span class="sxs-lookup"><span data-stu-id="82a58-152">Use sample queries</span></span>

<span data-ttu-id="82a58-153">Раздел **Начало работы** содержит несколько простых запросов, использующих часто используемые операторы.</span><span class="sxs-lookup"><span data-stu-id="82a58-153">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="82a58-154">Попробуйте выполнить эти запросы и внести в них небольшие изменения.</span><span class="sxs-lookup"><span data-stu-id="82a58-154">Try running these queries and making small modifications to them.</span></span>

![Изображение окна расширенной охоты](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="82a58-156">Кроме примеров базовых запросов, вы можете получить доступ к [общим запросам](advanced-hunting-shared-queries.md) для определенных сценариев охоты на угрозы.</span><span class="sxs-lookup"><span data-stu-id="82a58-156">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="82a58-157">Ознакомьтесь с общими запросами в левой части страницы репозитории запросов GitHub.</span><span class="sxs-lookup"><span data-stu-id="82a58-157">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="82a58-158">Документация по языку условий запросов</span><span class="sxs-lookup"><span data-stu-id="82a58-158">Access query language documentation</span></span>

<span data-ttu-id="82a58-159">Дополнительные сведения о языке запросов Kusto и поддерживаемых операторах см. в статье [Документация по языку запросов Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="82a58-159">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="82a58-160">См. также</span><span class="sxs-lookup"><span data-stu-id="82a58-160">Related topics</span></span>
- [<span data-ttu-id="82a58-161">Активная охота на угрозы</span><span class="sxs-lookup"><span data-stu-id="82a58-161">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="82a58-162">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="82a58-162">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="82a58-163">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="82a58-163">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="82a58-164">Общие сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="82a58-164">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="82a58-165">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="82a58-165">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
