---
title: Рекомендации по расширенному выслеживанию в службе Защиты от угроз (Майкрософт)
description: В этой статье можно узнать о том, как формировать оперативные, эффективные и безошибочные запросы в ходе расширенного выслеживания.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, пользовательские обнаружения, схема, Кусто, предотвращение времени ожидания, командные строки, идентификатор процесса
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
ms.openlocfilehash: b5cd421770469e674e66045ac341d12a2808da09
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602846"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="f23a8-104">Рекомендации по использованию запросов расширенного выслеживания</span><span class="sxs-lookup"><span data-stu-id="f23a8-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="f23a8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f23a8-105">**Applies to:**</span></span>
- <span data-ttu-id="f23a8-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f23a8-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="optimize-query-performance"></a><span data-ttu-id="f23a8-107">Оптимизация производительности запросов</span><span class="sxs-lookup"><span data-stu-id="f23a8-107">Optimize query performance</span></span>
<span data-ttu-id="f23a8-108">Использование указанных ниже рекомендаций позволит получать результаты быстрее и избегать временных затрат на ожидание при выполнении сложных запросов.</span><span class="sxs-lookup"><span data-stu-id="f23a8-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="f23a8-109">Чтобы избежать чрезвычайно больших наборов результатов, при попытках ввода новых запросов нужно всегда использовать `limit`.</span><span class="sxs-lookup"><span data-stu-id="f23a8-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="f23a8-110">Кроме того, с помощью `count` можно заранее задать размеры набора результатов.</span><span class="sxs-lookup"><span data-stu-id="f23a8-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="f23a8-111">Временные фильтры рекомендуется применять в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="f23a8-111">Use time filters first.</span></span> <span data-ttu-id="f23a8-112">При запросах лучше всего применять ограничения в несколько дней.</span><span class="sxs-lookup"><span data-stu-id="f23a8-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="f23a8-113">Рекомендуется устанавливать фильтры, предназначенные для удаления большей части данных в начале запроса, сразу после применения временного фильтра.</span><span class="sxs-lookup"><span data-stu-id="f23a8-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="f23a8-114">При поиске полных маркеров нужно использовать оператор `has` вместо `contains`.</span><span class="sxs-lookup"><span data-stu-id="f23a8-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="f23a8-115">Вместо полнотекстового поиска во всех столбцах рекомендуется осуществлять поиск в определенном столбце.</span><span class="sxs-lookup"><span data-stu-id="f23a8-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="f23a8-116">При объединении таблиц сначала нужно указать таблицу с меньшим количеством строк.</span><span class="sxs-lookup"><span data-stu-id="f23a8-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="f23a8-117">Использовать оператор`project` следует только для необходимых столбцов объединенных таблиц.</span><span class="sxs-lookup"><span data-stu-id="f23a8-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="f23a8-118">Дополнительные руководства по повышению производительности запросов см. в статье [Рекомендации по использованию запросов Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="f23a8-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="f23a8-119">Подсказки и ловушки, связанные с запросами</span><span class="sxs-lookup"><span data-stu-id="f23a8-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="f23a8-120">Запросы с идентификаторами процессов</span><span class="sxs-lookup"><span data-stu-id="f23a8-120">Queries with process IDs</span></span>
<span data-ttu-id="f23a8-121">Идентификаторы процессов (PID) в Windows перерабатываются и используются для новых процессов.</span><span class="sxs-lookup"><span data-stu-id="f23a8-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="f23a8-122">Они не могут служить уникальными идентификаторами для определенных процессов сами по себе.</span><span class="sxs-lookup"><span data-stu-id="f23a8-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="f23a8-123">Чтобы создать уникальный идентификатор для процесса на определенном компьютере, идентификатор процесса нужно использовать вместе со временем создания процесса.</span><span class="sxs-lookup"><span data-stu-id="f23a8-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="f23a8-124">При объединении или обобщении данных по процессам рекомендуется включать столбцы для идентификатора компьютера (либо `DeviceId`, либо`DeviceName`), идентификатора процесса (`ProcessId` или `InitiatingProcessId`) и времени создания процесса (`ProcessCreationTime` или `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="f23a8-124">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="f23a8-125">В приведенном ниже примере запроса обнаружены процессы, имеющие доступ к более чем 10 IP-адресам через порт 445 (SMB) с одновременным возможным сканированием файловых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f23a8-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="f23a8-126">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="f23a8-126">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="f23a8-127">В запросе указаны одновременно и `InitiatingProcessId`, и `InitiatingProcessCreationTime`. Благодаря этому запрос относится к одному единственному процессу, и при этом исключаются многочисленные другие процессы с аналогичным идентификатором процесса.</span><span class="sxs-lookup"><span data-stu-id="f23a8-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="f23a8-128">Запросы с командными строками</span><span class="sxs-lookup"><span data-stu-id="f23a8-128">Queries with command lines</span></span>

<span data-ttu-id="f23a8-129">Существует множество разнообразных командных строк.</span><span class="sxs-lookup"><span data-stu-id="f23a8-129">Command lines can vary.</span></span> <span data-ttu-id="f23a8-130">При необходимости можно выполнить фильтрацию по названиям файлов и осуществить поиск нечетких соответствий.</span><span class="sxs-lookup"><span data-stu-id="f23a8-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="f23a8-131">Создать командную строку для выполнения задачи можно разными способами.</span><span class="sxs-lookup"><span data-stu-id="f23a8-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="f23a8-132">Например, злоумышленник может создать ссылку на файл с изображением с путем или без него, без расширения файла, используя переменные среды, или с кавычками.</span><span class="sxs-lookup"><span data-stu-id="f23a8-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="f23a8-133">Кроме того, злоумышленник может изменить порядок параметров или добавить несколько кавычек и пробелов.</span><span class="sxs-lookup"><span data-stu-id="f23a8-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="f23a8-134">Ниже приводятся рекомендации для создания более устойчивых запросов с помощью командных строк.</span><span class="sxs-lookup"><span data-stu-id="f23a8-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="f23a8-135">Указывать известные процессы (такие как *net.exe* или*psexec.exe*) нужно, используя соответствия полей имен файлов вместо применения фильтра для поля командной строки.</span><span class="sxs-lookup"><span data-stu-id="f23a8-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="f23a8-136">При запросе аргументов командной строки искать точное совпадение для нескольких несвязанных аргументов в определенном порядке не имеет смысла.</span><span class="sxs-lookup"><span data-stu-id="f23a8-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="f23a8-137">Вместо этого используются регулярные выражения или несколько отдельных аргументов, содержащих операторы.</span><span class="sxs-lookup"><span data-stu-id="f23a8-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="f23a8-138">Совпадения используются без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="f23a8-138">Use case insensitive matches.</span></span> <span data-ttu-id="f23a8-139">Например, следует использовать `=~`, `in~`, и`contains` вместо `==`, `in`, и `contains_cs`.</span><span class="sxs-lookup"><span data-stu-id="f23a8-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="f23a8-140">Чтобы предотвратить случаи сокрытия назначения командной строки в DOS, можно удалить кавычки, заменив их пробелами и заменив несколько пробелов одним.</span><span class="sxs-lookup"><span data-stu-id="f23a8-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="f23a8-141">Нужно помнить о том, что существуют более сложные методы маскирования в DOS, для борьбы с которыми требуются другие подходы, но вышеуказанные способы обычно помогают в наиболее распространенных случаях.</span><span class="sxs-lookup"><span data-stu-id="f23a8-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="f23a8-142">В приведенных ниже примерах предлагаются различные способы создания запроса для поиска файла *net.exe* для остановки службы брандмауэра Защитника Windows.</span><span class="sxs-lookup"><span data-stu-id="f23a8-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```
## <a name="related-topics"></a><span data-ttu-id="f23a8-143">См. также</span><span class="sxs-lookup"><span data-stu-id="f23a8-143">Related topics</span></span>
- [<span data-ttu-id="f23a8-144">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="f23a8-144">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f23a8-145">Сведения о языке запросов</span><span class="sxs-lookup"><span data-stu-id="f23a8-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f23a8-146">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="f23a8-146">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f23a8-147">Выслеживание угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="f23a8-147">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f23a8-148">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="f23a8-148">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
