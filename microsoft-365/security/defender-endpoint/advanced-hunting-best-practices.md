---
title: Запрос лучших методов для продвинутой охоты
description: В этой статье можно узнать о том, как формировать оперативные, эффективные и безошибочные запросы в ходе расширенного выслеживания.
keywords: передовая охота, охота на угрозы, охота на киберугрозы, mdatp, защита microsoft atp, поиск wdatp, запрос, телеметрия, настраиваемые обнаружения, схема, кусто, избегайте времени, командных строк, id процесса
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6259ac1c5804b244c825a1bb54401640fdefaf34
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072430"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="54e1c-104">Рекомендации по использованию запросов расширенного выслеживания</span><span class="sxs-lookup"><span data-stu-id="54e1c-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54e1c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="54e1c-105">**Applies to:**</span></span>
- [<span data-ttu-id="54e1c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="54e1c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="54e1c-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="54e1c-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="54e1c-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="54e1c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a><span data-ttu-id="54e1c-109">Оптимизация производительности запросов</span><span class="sxs-lookup"><span data-stu-id="54e1c-109">Optimize query performance</span></span>

<span data-ttu-id="54e1c-110">Применяем эти рекомендации, чтобы быстрее получать результаты и избегать периодов времени во время работы сложных запросов.</span><span class="sxs-lookup"><span data-stu-id="54e1c-110">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span>

- <span data-ttu-id="54e1c-111">Чтобы избежать чрезвычайно больших наборов результатов, при попытках ввода новых запросов нужно всегда использовать `limit`.</span><span class="sxs-lookup"><span data-stu-id="54e1c-111">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="54e1c-112">Кроме того, с помощью `count` можно заранее задать размеры набора результатов.</span><span class="sxs-lookup"><span data-stu-id="54e1c-112">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="54e1c-113">Временные фильтры рекомендуется применять в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="54e1c-113">Use time filters first.</span></span> <span data-ttu-id="54e1c-114">В идеале ограничьте запросы семи днями.</span><span class="sxs-lookup"><span data-stu-id="54e1c-114">Ideally, limit your queries to seven days.</span></span>
- <span data-ttu-id="54e1c-115">Рекомендуется устанавливать фильтры, предназначенные для удаления большей части данных в начале запроса, сразу после применения временного фильтра.</span><span class="sxs-lookup"><span data-stu-id="54e1c-115">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="54e1c-116">При поиске полных маркеров нужно использовать оператор `has` вместо `contains`.</span><span class="sxs-lookup"><span data-stu-id="54e1c-116">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="54e1c-117">Вместо полнотекстового поиска во всех столбцах рекомендуется осуществлять поиск в определенном столбце.</span><span class="sxs-lookup"><span data-stu-id="54e1c-117">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="54e1c-118">При объединении таблиц сначала нужно указать таблицу с меньшим количеством строк.</span><span class="sxs-lookup"><span data-stu-id="54e1c-118">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="54e1c-119">Использовать оператор`project` следует только для необходимых столбцов объединенных таблиц.</span><span class="sxs-lookup"><span data-stu-id="54e1c-119">`project` only the necessary columns from tables you've joined.</span></span>

>[!TIP]
><span data-ttu-id="54e1c-120">Дополнительные руководства по повышению производительности запросов см. в статье [Рекомендации по использованию запросов Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="54e1c-120">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="54e1c-121">Подсказки и ловушки, связанные с запросами</span><span class="sxs-lookup"><span data-stu-id="54e1c-121">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="54e1c-122">Запросы с идентификаторами процессов</span><span class="sxs-lookup"><span data-stu-id="54e1c-122">Queries with process IDs</span></span>

<span data-ttu-id="54e1c-123">Идентификаторы процессов (PID) в Windows перерабатываются и используются для новых процессов.</span><span class="sxs-lookup"><span data-stu-id="54e1c-123">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="54e1c-124">Они не могут служить уникальными идентификаторами для определенных процессов сами по себе.</span><span class="sxs-lookup"><span data-stu-id="54e1c-124">On their own, they can't serve as unique identifiers for specific processes.</span></span> <span data-ttu-id="54e1c-125">Чтобы получить уникальный идентификатор для процесса на определенном устройстве, используйте идентификатор процесса вместе с временем создания процесса.</span><span class="sxs-lookup"><span data-stu-id="54e1c-125">To get a unique identifier for a process on a specific device, use the process ID together with the process creation time.</span></span> <span data-ttu-id="54e1c-126">Когда вы присоединяется или суммируете данные вокруг процессов, включаем столбцы для идентификатора устройства (либо или), идентификатора процесса (или) и времени создания процесса `DeviceId` `DeviceName` `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` (или).</span><span class="sxs-lookup"><span data-stu-id="54e1c-126">When you join or summarize data around processes, include columns for the device identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`).</span></span>

<span data-ttu-id="54e1c-127">В приведенном ниже примере запроса обнаружены процессы, имеющие доступ к более чем 10 IP-адресам через порт 445 (SMB) с одновременным возможным сканированием файловых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="54e1c-127">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="54e1c-128">В запросе указаны одновременно и `InitiatingProcessId`, и `InitiatingProcessCreationTime`. Благодаря этому запрос относится к одному единственному процессу, и при этом исключаются многочисленные другие процессы с аналогичным идентификатором процесса.</span><span class="sxs-lookup"><span data-stu-id="54e1c-128">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="54e1c-129">Запросы с командными строками</span><span class="sxs-lookup"><span data-stu-id="54e1c-129">Queries with command lines</span></span>

<span data-ttu-id="54e1c-130">Существует множество разнообразных командных строк.</span><span class="sxs-lookup"><span data-stu-id="54e1c-130">Command lines can vary.</span></span> <span data-ttu-id="54e1c-131">При необходимости можно выполнить фильтрацию по названиям файлов и осуществить поиск нечетких соответствий.</span><span class="sxs-lookup"><span data-stu-id="54e1c-131">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="54e1c-132">Создать командную строку для выполнения задачи можно разными способами.</span><span class="sxs-lookup"><span data-stu-id="54e1c-132">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="54e1c-133">Например, злоумышленник может создать ссылку на файл с изображением с путем или без него, без расширения файла, используя переменные среды, или с кавычками.</span><span class="sxs-lookup"><span data-stu-id="54e1c-133">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="54e1c-134">Кроме того, злоумышленник может изменить порядок параметров или добавить несколько кавычек и пробелов.</span><span class="sxs-lookup"><span data-stu-id="54e1c-134">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="54e1c-135">Ниже приводятся рекомендации для создания более устойчивых запросов с помощью командных строк.</span><span class="sxs-lookup"><span data-stu-id="54e1c-135">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="54e1c-136">Указывать известные процессы (такие как *net.exe* или *psexec.exe*) нужно, используя соответствия полей имен файлов вместо применения фильтра для поля командной строки.</span><span class="sxs-lookup"><span data-stu-id="54e1c-136">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="54e1c-137">При запросе аргументов командной строки искать точное совпадение для нескольких несвязанных аргументов в определенном порядке не имеет смысла.</span><span class="sxs-lookup"><span data-stu-id="54e1c-137">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="54e1c-138">Вместо этого используются регулярные выражения или несколько отдельных аргументов, содержащих операторы.</span><span class="sxs-lookup"><span data-stu-id="54e1c-138">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="54e1c-139">Совпадения используются без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="54e1c-139">Use case insensitive matches.</span></span> <span data-ttu-id="54e1c-140">Например, используйте `=~` `in~` , и вместо , `contains` `==` `in` и `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="54e1c-140">For example, use `=~`, `in~`, and `contains` instead of `==`, `in` and `contains_cs`</span></span>
- <span data-ttu-id="54e1c-141">Чтобы предотвратить случаи сокрытия назначения командной строки в DOS, можно удалить кавычки, заменив их пробелами и заменив несколько пробелов одним.</span><span class="sxs-lookup"><span data-stu-id="54e1c-141">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="54e1c-142">Нужно помнить о том, что существуют более сложные методы маскирования в DOS, для борьбы с которыми требуются другие подходы, но вышеуказанные способы обычно помогают в наиболее распространенных случаях.</span><span class="sxs-lookup"><span data-stu-id="54e1c-142">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="54e1c-143">В приведенных ниже примерах предлагаются различные способы создания запроса для поиска файла *net.exe* для остановки службы брандмауэра Защитника Windows.</span><span class="sxs-lookup"><span data-stu-id="54e1c-143">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

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

> <span data-ttu-id="54e1c-144">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="54e1c-144">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="54e1c-145">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="54e1c-145">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="54e1c-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="54e1c-146">Related topics</span></span>

- [<span data-ttu-id="54e1c-147">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="54e1c-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="54e1c-148">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="54e1c-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="54e1c-149">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="54e1c-149">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="54e1c-150">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="54e1c-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="54e1c-151">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="54e1c-151">Custom detections overview</span></span>](overview-custom-detections.md)
