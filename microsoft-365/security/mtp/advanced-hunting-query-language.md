---
title: Познакомьтесь с языком запросов расширенной охоты на угрозы в службе защиты от угроз (Майкрософт)
description: Создайте ваш первый запрос охоты на угрозы и узнайте о распространенных операторах и других аспектах языка запросов расширенной охоты на угрозы
keywords: расширенная охота, охота на угрозы, поиск киберугроз, поиск, запрос, язык, изучение, первый запрос, телеметрия, события, телеметрия, пользовательские обнаружения, схема, kusto, операторы, типы данных
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 7c6c92aeec6c1644472103a1aaf175eb813d5758
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808684"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="bcb07-104">Познакомьтесь с языком запросов расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="bcb07-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="bcb07-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="bcb07-105">**Applies to:**</span></span>
- <span data-ttu-id="bcb07-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="bcb07-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="bcb07-107">Расширенный поиск основывается на [языке запросов Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="bcb07-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="bcb07-108">С помощью синтаксиса и операторов Кусто можно создавать запросы, которые позволяют найти информацию в [схеме](advanced-hunting-schema-tables.md), специально структурированной для расширенного поиска.</span><span class="sxs-lookup"><span data-stu-id="bcb07-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="bcb07-109">Чтобы лучше понять эти концепции, запустите ваш первый запрос.</span><span class="sxs-lookup"><span data-stu-id="bcb07-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="bcb07-110">Попробуйте выполнить первый запрос</span><span class="sxs-lookup"><span data-stu-id="bcb07-110">Try your first query</span></span>

<span data-ttu-id="bcb07-111">Чтобы выполнить ваш первый запрос, в центре безопасности Microsoft 365 перейдите в раздел **Охота**.</span><span class="sxs-lookup"><span data-stu-id="bcb07-111">in the Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="bcb07-112">Используйте следующий пример:</span><span class="sxs-lookup"><span data-stu-id="bcb07-112">Use the following example:</span></span>

```
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

<span data-ttu-id="bcb07-113">Так это будет выглядеть в расширенной охоте.</span><span class="sxs-lookup"><span data-stu-id="bcb07-113">This is how it will look like in advanced hunting.</span></span>

![Изображение запроса расширенной охоты в ATP в Microsoft Defender](../images/advanced-hunting-query-example.png)

<span data-ttu-id="bcb07-115">Запрос начинается с короткого комментария, описывающего назначение запроса.</span><span class="sxs-lookup"><span data-stu-id="bcb07-115">The query starts with a short comment describing what it is for.</span></span> <span data-ttu-id="bcb07-116">Это будет полезным, если впоследствии вы решите сохранить свой запрос и поделиться им с другими пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bcb07-116">This helps if you later decide to save your query and share it with others in your organization.</span></span>

```
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents
```

<span data-ttu-id="bcb07-117">Как правило, запрос начинается с имени таблицы, за которым следует ряд элементов, начинающихся с вертикальной черты (`|`).</span><span class="sxs-lookup"><span data-stu-id="bcb07-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="bcb07-118">В этом примере мы начинаем с добавления имени таблицы `DeviceProcessEvents` и при необходимости добавляем элементы, отмеченные вертикальной чертой.</span><span class="sxs-lookup"><span data-stu-id="bcb07-118">In this example, we start by adding  with the table name `DeviceProcessEvents` and add piped elements as needed.</span></span>

<span data-ttu-id="bcb07-119">Первый элемент, отмеченный вертикальной чертой, является фильтром времени, ограниченном предыдущими семью днями.</span><span class="sxs-lookup"><span data-stu-id="bcb07-119">The first piped element is a time filter scoped within the previous seven days.</span></span> <span data-ttu-id="bcb07-120">Сохранение как можно более узкого временного диапазона гарантирует, что запросы работают хорошо, возвращают управляемые результаты и не превышают времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="bcb07-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```
| where Timestamp > ago(7d)
```

<span data-ttu-id="bcb07-121">За диапазоном времени непосредственно следует поиск файлов, представляющих приложение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bcb07-121">The time range is immediately followed by a search for files representing the PowerShell application.</span></span>

```
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

<span data-ttu-id="bcb07-122">Затем запрос ищет командные строки, которые, как правило, используются с PowerShell для скачивания файлов.</span><span class="sxs-lookup"><span data-stu-id="bcb07-122">Afterwards, the query looks for command lines that are typically used with PowerShell to download files.</span></span>

```
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

<span data-ttu-id="bcb07-123">Теперь, когда ваш запрос четко определяет данные, которые вы хотите найти, вы можете добавить элементы, которые определяют то, как будут выглядеть результаты.</span><span class="sxs-lookup"><span data-stu-id="bcb07-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="bcb07-124">`project` возвращает определенные столбцы и `top` ограничивает количество результатов, делая результаты хорошо отформатированными и достаточно большими и простыми в обработке.</span><span class="sxs-lookup"><span data-stu-id="bcb07-124">`project` returns specific columns and `top` limits the number of results, making the results well-formatted and reasonably large and easy to process.</span></span>

```
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp'
```

<span data-ttu-id="bcb07-125">Нажмите кнопку **Выполнить запрос**, чтобы увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="bcb07-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="bcb07-126">Вы можете развернуть экран, чтобы сосредоточиться на вашем запросе охоты и результатах.</span><span class="sxs-lookup"><span data-stu-id="bcb07-126">You can expand the screen view so you can focus on your hunting query and the results.</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="bcb07-127">Познакомьтесь с обычными операторами запросов для расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="bcb07-127">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="bcb07-128">Теперь, когда вы выполнили свой первый запрос и получили общее представление о его компонентах, пришло время вернуться немного назад и изучить некоторые основы.</span><span class="sxs-lookup"><span data-stu-id="bcb07-128">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="bcb07-129">Язык запросов Kusto, используемый в расширенной охоте, поддерживает ряд операторов, включая обычные, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="bcb07-129">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="bcb07-130">Оператор</span><span class="sxs-lookup"><span data-stu-id="bcb07-130">Operator</span></span> | <span data-ttu-id="bcb07-131">Описание и использование</span><span class="sxs-lookup"><span data-stu-id="bcb07-131">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="bcb07-132">Фильтрация таблицы по подмножеству строк, удовлетворяющих предикату.</span><span class="sxs-lookup"><span data-stu-id="bcb07-132">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="bcb07-133">Создание таблицы, в которой объединяется содержимое исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="bcb07-133">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="bcb07-134">Объединение строк двух таблиц, чтобы сформировать новую таблицу, сопоставляя значения заданных столбцов из каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="bcb07-134">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="bcb07-135">Возврат количества записей в исходный набор записей.</span><span class="sxs-lookup"><span data-stu-id="bcb07-135">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="bcb07-136">Возврат первых N записей, отсортированных по заданным столбцам.</span><span class="sxs-lookup"><span data-stu-id="bcb07-136">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="bcb07-137">Возврат до заданного количества строк.</span><span class="sxs-lookup"><span data-stu-id="bcb07-137">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="bcb07-138">Выбор столбцов, которые нужно включить, переименовать или перетащить, и вставка новых вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="bcb07-138">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="bcb07-139">Создание вычисляемых столбцов и их добавление в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="bcb07-139">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="bcb07-140">Возврат динамического массива (JSON) множества различных значений, которые выражение (Expr) принимает в группе.</span><span class="sxs-lookup"><span data-stu-id="bcb07-140">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="bcb07-141">Поиск строк, соответствующих предикату, по набору таблиц.</span><span class="sxs-lookup"><span data-stu-id="bcb07-141">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="bcb07-142">Чтобы просмотреть реальные примеры этих операторов, запустите их из пункта **Начать работу** в разделе Расширенная охота.</span><span class="sxs-lookup"><span data-stu-id="bcb07-142">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="bcb07-143">Общие сведения о типах данных и их влиянии на синтаксис запроса</span><span class="sxs-lookup"><span data-stu-id="bcb07-143">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="bcb07-144">Данные в таблицах расширенной охоты, как правило, относятся к указанным ниже типам данных.</span><span class="sxs-lookup"><span data-stu-id="bcb07-144">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="bcb07-145">Тип данных</span><span class="sxs-lookup"><span data-stu-id="bcb07-145">Data type</span></span> | <span data-ttu-id="bcb07-146">Описание и влияния запроса</span><span class="sxs-lookup"><span data-stu-id="bcb07-146">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="bcb07-147">Данные и сведения о времени, обычно представляющие временные метки событий</span><span class="sxs-lookup"><span data-stu-id="bcb07-147">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="bcb07-148">Строка символов</span><span class="sxs-lookup"><span data-stu-id="bcb07-148">Character string</span></span> |
| `bool` | <span data-ttu-id="bcb07-149">Истина или ложь</span><span class="sxs-lookup"><span data-stu-id="bcb07-149">True or false</span></span> |
| `int` | <span data-ttu-id="bcb07-150">32-разрядное числовое значение</span><span class="sxs-lookup"><span data-stu-id="bcb07-150">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="bcb07-151">64-разрядное числовое значение</span><span class="sxs-lookup"><span data-stu-id="bcb07-151">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="bcb07-152">Использование примеров запросов</span><span class="sxs-lookup"><span data-stu-id="bcb07-152">Use sample queries</span></span>

<span data-ttu-id="bcb07-153">Раздел **Начало работы** содержит несколько простых запросов, использующих часто используемые операторы.</span><span class="sxs-lookup"><span data-stu-id="bcb07-153">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="bcb07-154">Попробуйте выполнить эти запросы и внести в них небольшие изменения.</span><span class="sxs-lookup"><span data-stu-id="bcb07-154">Try running these queries and making small modifications to them.</span></span>

![Изображение окна расширенной охоты](../images/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="bcb07-156">Кроме примеров базовых запросов, вы можете получить доступ к [общим запросам](advanced-hunting-shared-queries.md) для определенных сценариев охоты на угрозы.</span><span class="sxs-lookup"><span data-stu-id="bcb07-156">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="bcb07-157">Ознакомьтесь с общими запросами в левой части страницы репозитории запросов GitHub.</span><span class="sxs-lookup"><span data-stu-id="bcb07-157">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="bcb07-158">Документация по языку условий запросов</span><span class="sxs-lookup"><span data-stu-id="bcb07-158">Access query language documentation</span></span>

<span data-ttu-id="bcb07-159">Дополнительные сведения о языке запросов Kusto и поддерживаемых операторах см. в статье [Документация по языку запросов Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="bcb07-159">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="bcb07-160">См. также</span><span class="sxs-lookup"><span data-stu-id="bcb07-160">Related topics</span></span>
- [<span data-ttu-id="bcb07-161">Активная охота на угрозы</span><span class="sxs-lookup"><span data-stu-id="bcb07-161">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bcb07-162">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="bcb07-162">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="bcb07-163">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="bcb07-163">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bcb07-164">Общие сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="bcb07-164">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bcb07-165">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="bcb07-165">Apply query best practices</span></span>](advanced-hunting-best-practices.md)