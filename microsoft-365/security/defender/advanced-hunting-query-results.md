---
title: Работа с расширенным запросом на охоту приводит к microsoft 365 Defender
description: Сделайте большую часть результатов запроса, возвращенных расширенным поиском в Microsoft 365 Defender
keywords: передовая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, настраиваемые обнаружения, схема, кусто, Microsoft 365, Microsoft Threat Protection, визуализация, диаграмма, фильтры, сверла
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
ms.openlocfilehash: dd25d021d04dc5e8a831e327fedb16d28e32b32a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076309"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="b1453-104">Работа с расширенными результатами запроса на охоту</span><span class="sxs-lookup"><span data-stu-id="b1453-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b1453-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b1453-105">**Applies to:**</span></span>
- <span data-ttu-id="b1453-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1453-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b1453-107">В то время [](advanced-hunting-overview.md) как вы можете создавать расширенные запросы для получения очень точных сведений, вы также можете работать с результатами запроса, чтобы получить дополнительные сведения и изучить конкретные действия и индикаторы.</span><span class="sxs-lookup"><span data-stu-id="b1453-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="b1453-108">В результатах запроса можно принять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b1453-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="b1453-109">Просмотр результатов в таблице или диаграмме</span><span class="sxs-lookup"><span data-stu-id="b1453-109">View results as a table or chart</span></span>
- <span data-ttu-id="b1453-110">Экспорт таблиц и диаграмм</span><span class="sxs-lookup"><span data-stu-id="b1453-110">Export tables and charts</span></span>
- <span data-ttu-id="b1453-111">Детализация подробных сведений об объектах</span><span class="sxs-lookup"><span data-stu-id="b1453-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="b1453-112">Настройка запросов непосредственно из результатов или применение фильтров</span><span class="sxs-lookup"><span data-stu-id="b1453-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="b1453-113">Просмотр результатов запроса в таблице или диаграмме</span><span class="sxs-lookup"><span data-stu-id="b1453-113">View query results as a table or chart</span></span>
<span data-ttu-id="b1453-114">По умолчанию расширенный режим охоты отображает результаты запроса в качестве табулярных данных.</span><span class="sxs-lookup"><span data-stu-id="b1453-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="b1453-115">Вы также можете отобразить те же данные, что и диаграмма.</span><span class="sxs-lookup"><span data-stu-id="b1453-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="b1453-116">Расширенный поиск поддерживает следующие представления:</span><span class="sxs-lookup"><span data-stu-id="b1453-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="b1453-117">Тип представления</span><span class="sxs-lookup"><span data-stu-id="b1453-117">View type</span></span> | <span data-ttu-id="b1453-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b1453-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="b1453-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="b1453-119">**Table**</span></span> | <span data-ttu-id="b1453-120">Отображает результаты запроса в табулярном формате</span><span class="sxs-lookup"><span data-stu-id="b1453-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="b1453-121">**Диаграмма столбца**</span><span class="sxs-lookup"><span data-stu-id="b1453-121">**Column chart**</span></span> | <span data-ttu-id="b1453-122">Отрисовка ряда уникальных элементов на оси x-axis в качестве вертикальных баров, высоты которых представляют числимые значения из другого поля</span><span class="sxs-lookup"><span data-stu-id="b1453-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="b1453-123">**Сложенная диаграмма столбцов**</span><span class="sxs-lookup"><span data-stu-id="b1453-123">**Stacked column chart**</span></span> | <span data-ttu-id="b1453-124">Отрисовка ряда уникальных элементов на x-axis в качестве сложенных вертикальных баров, высоты которых представляют числовые значения из одного или более других полей.</span><span class="sxs-lookup"><span data-stu-id="b1453-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="b1453-125">**Диаграмма пирога**</span><span class="sxs-lookup"><span data-stu-id="b1453-125">**Pie chart**</span></span> | <span data-ttu-id="b1453-126">Отрисовка раздельных пирогов, представляющих уникальные элементы.</span><span class="sxs-lookup"><span data-stu-id="b1453-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="b1453-127">Размер каждого пирога представляет численное значение из другого поля.</span><span class="sxs-lookup"><span data-stu-id="b1453-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="b1453-128">**Пончиная диаграмма**</span><span class="sxs-lookup"><span data-stu-id="b1453-128">**Donut chart**</span></span> | <span data-ttu-id="b1453-129">Отрисовка раздельных дуг, представляющих уникальные элементы.</span><span class="sxs-lookup"><span data-stu-id="b1453-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="b1453-130">Длина каждой дуги представляет численное значение из другого поля.</span><span class="sxs-lookup"><span data-stu-id="b1453-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="b1453-131">**График**</span><span class="sxs-lookup"><span data-stu-id="b1453-131">**Line chart**</span></span> | <span data-ttu-id="b1453-132">Графики числимые значения для ряда уникальных элементов и соединяет замещенные значения</span><span class="sxs-lookup"><span data-stu-id="b1453-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="b1453-133">**Диаграмма scatter**</span><span class="sxs-lookup"><span data-stu-id="b1453-133">**Scatter chart**</span></span> | <span data-ttu-id="b1453-134">Графики числимые значения для ряда уникальных элементов</span><span class="sxs-lookup"><span data-stu-id="b1453-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="b1453-135">**Диаграмма области**</span><span class="sxs-lookup"><span data-stu-id="b1453-135">**Area chart**</span></span> | <span data-ttu-id="b1453-136">Графики числимых значений для ряда уникальных элементов и заполняют разделы ниже замещенных значений</span><span class="sxs-lookup"><span data-stu-id="b1453-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="b1453-137">Создание запросов для эффективных диаграмм</span><span class="sxs-lookup"><span data-stu-id="b1453-137">Construct queries for effective charts</span></span>
<span data-ttu-id="b1453-138">При отрисовывии диаграмм передовая охота автоматически определяет столбцы, интересующие, и числимые значения для совокупного значения.</span><span class="sxs-lookup"><span data-stu-id="b1453-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="b1453-139">Чтобы получить значимые диаграммы, состройте запросы для возврата определенных значений, которые необходимо увидеть визуализированными.</span><span class="sxs-lookup"><span data-stu-id="b1453-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="b1453-140">Вот некоторые примеры запросов и итоговая диаграмма.</span><span class="sxs-lookup"><span data-stu-id="b1453-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="b1453-141">Оповещений по строгости</span><span class="sxs-lookup"><span data-stu-id="b1453-141">Alerts by severity</span></span>
<span data-ttu-id="b1453-142">С помощью `summarize` оператора можно получить числовую цифру значений, которые необходимо наметить.</span><span class="sxs-lookup"><span data-stu-id="b1453-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="b1453-143">В приведенной ниже области запрос использует оператора для получения количества предупреждений `summarize` по строгости.</span><span class="sxs-lookup"><span data-stu-id="b1453-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="b1453-144">При отрисовывии результатов диаграмма столбца отображает каждое значение серьезности в качестве отдельного столбца:</span><span class="sxs-lookup"><span data-stu-id="b1453-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="b1453-145">![Изображение результатов расширенных запросов охоты, отображаемого в качестве результатов запроса диаграммы столбцов для оповещений по степени серьезности, отображаемой ](../../media/advanced-hunting-column-chart.jpg)
 *в качестве диаграммы столбца*</span><span class="sxs-lookup"><span data-stu-id="b1453-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="b1453-146">Серьезность оповещений с помощью операционной системы</span><span class="sxs-lookup"><span data-stu-id="b1453-146">Alert severity by operating system</span></span>
<span data-ttu-id="b1453-147">Можно также использовать оператора для подготовки `summarize` результатов для наметки значений из нескольких полей.</span><span class="sxs-lookup"><span data-stu-id="b1453-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="b1453-148">Например, вам может потребоваться понять, как распределяются степени серьезности оповещения по операционным системам (ОС).</span><span class="sxs-lookup"><span data-stu-id="b1453-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="b1453-149">В приведенной ниже области запрос использует оператора для получения сведений об ОС из таблицы, а затем для подсчета значений как в столбцах, так `join` `DeviceInfo` и в `summarize` `OSPlatform` `Severity` столбцах:</span><span class="sxs-lookup"><span data-stu-id="b1453-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="b1453-150">Эти результаты лучше всего визуализировать с помощью диаграммы сложенных столбцов:</span><span class="sxs-lookup"><span data-stu-id="b1453-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="b1453-151">![Изображение результатов расширенных запросов охоты, отображаемого в качестве сложенных результатов запроса диаграммы для оповещений оси и строгости, отображаемой в качестве ](../../media/advanced-hunting-stacked-chart.jpg)
 *сложенной диаграммы*</span><span class="sxs-lookup"><span data-stu-id="b1453-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="b1453-152">Фишинговые сообщения электронной почты в десяти доменах отправитель</span><span class="sxs-lookup"><span data-stu-id="b1453-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="b1453-153">Если вы имеете дело со списком значений, который не является конечным, оператор может использовать для диаграммы только значения с `Top` большинством экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b1453-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="b1453-154">Например, чтобы получить десять доменов отправитель с самыми фишинговыми электронными письмами, используйте запрос ниже:</span><span class="sxs-lookup"><span data-stu-id="b1453-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
<span data-ttu-id="b1453-155">Используйте представление диаграммы пирога, чтобы эффективно показывать распределение по верхним доменам:</span><span class="sxs-lookup"><span data-stu-id="b1453-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="b1453-156">![Изображение результатов расширенных запросов на охоту, отображаемого в диаграмме пирога, показывающая распространение фишинговых сообщений электронной почты в ](../../media/advanced-hunting-pie-chart.jpg)
 *верхних доменах отправитель*</span><span class="sxs-lookup"><span data-stu-id="b1453-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="b1453-157">Действия файла со временем</span><span class="sxs-lookup"><span data-stu-id="b1453-157">File activities over time</span></span>
<span data-ttu-id="b1453-158">С помощью оператора с функцией можно проверить события, связанные с определенным `summarize` `bin()` индикатором с течением времени.</span><span class="sxs-lookup"><span data-stu-id="b1453-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="b1453-159">В нижеупромянутом запросе учитываются события, связанные с файлом с интервалом в 30 минут, чтобы показать всплески активности, связанные `invoice.doc` с этим файлом:</span><span class="sxs-lookup"><span data-stu-id="b1453-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="b1453-160">На приведенной ниже строке четко выделены периоды времени с дополнительными действиями с `invoice.doc` участием:</span><span class="sxs-lookup"><span data-stu-id="b1453-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="b1453-161">![Изображение расширенных результатов запроса охоты, отображаемого в качестве диаграммы строки line, показывающая количество событий, связанных ](../../media/advanced-hunting-line-chart.jpg)
 *с файлом с течением времени*</span><span class="sxs-lookup"><span data-stu-id="b1453-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="b1453-162">Экспорт таблиц и диаграмм</span><span class="sxs-lookup"><span data-stu-id="b1453-162">Export tables and charts</span></span>
<span data-ttu-id="b1453-163">После выполнения запроса выберите **Экспорт,** чтобы сохранить результаты в локальном файле.</span><span class="sxs-lookup"><span data-stu-id="b1453-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="b1453-164">Выбранное представление определяет, как экспортируются результаты:</span><span class="sxs-lookup"><span data-stu-id="b1453-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="b1453-165">**Представление таблицы** — результаты запроса экспортируются в табулярной форме в виде книги Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="b1453-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="b1453-166">**Любая диаграмма** — результаты запроса экспортируются как изображение JPEG отрисовки диаграммы</span><span class="sxs-lookup"><span data-stu-id="b1453-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="b1453-167">Сверлить из результатов запроса</span><span class="sxs-lookup"><span data-stu-id="b1453-167">Drill down from query results</span></span>
<span data-ttu-id="b1453-168">Чтобы быстро проверить запись в результатах запроса, выберите соответствующую строку, чтобы открыть панель **записей Inspect.**</span><span class="sxs-lookup"><span data-stu-id="b1453-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="b1453-169">Панель предоставляет следующую информацию на основе выбранной записи:</span><span class="sxs-lookup"><span data-stu-id="b1453-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="b1453-170">**Активы** — краткое представление основных активов (почтовых ящиков, устройств и пользователей), найденных в записи, обогащенных доступной информацией, например уровнями риска и экспозиции.</span><span class="sxs-lookup"><span data-stu-id="b1453-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="b1453-171">**Дерево процесса** — создается для записей с информацией о процессе и обогащено с помощью доступной контекстной информации; как правило, запросы, возвращая больше столбцов, могут привести к более богатым деревьям процесса.</span><span class="sxs-lookup"><span data-stu-id="b1453-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="b1453-172">**Все сведения** — все значения столбцов в записи</span><span class="sxs-lookup"><span data-stu-id="b1453-172">**All details** — all the values from the columns in the record</span></span>  

![Изображение выбранной записи с панелью для проверки записи](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="b1453-174">Чтобы просмотреть дополнительные сведения о конкретном объекте в результатах запроса, таких как машина, файл, пользователь, IP-адрес или URL-адрес, выберите идентификатор сущности, чтобы открыть страницу подробного профиля для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="b1453-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="b1453-175">Регулирование запросов на основе результатов</span><span class="sxs-lookup"><span data-stu-id="b1453-175">Tweak your queries from the results</span></span>
<span data-ttu-id="b1453-176">Чтобы оперативно улучшить свой запрос, нужно щелкнуть правой кнопкой мыши одно из значений в полученном наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="b1453-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="b1453-177">Предлагаемые варианты можно использовать для</span><span class="sxs-lookup"><span data-stu-id="b1453-177">You can use the options to:</span></span>

- <span data-ttu-id="b1453-178">открытого поиска избранного значения (`==`)</span><span class="sxs-lookup"><span data-stu-id="b1453-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="b1453-179">исключения избранного значения из запроса (`!=`)</span><span class="sxs-lookup"><span data-stu-id="b1453-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="b1453-180">Чтобы добавить к своему запросу определенное значение, можно использовать дополнительные операторы, например, `contains`, `starts with` и`ends with`</span><span class="sxs-lookup"><span data-stu-id="b1453-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Изображение набора расширенных результатов охоты](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="b1453-182">Фильтрация результатов запроса</span><span class="sxs-lookup"><span data-stu-id="b1453-182">Filter the query results</span></span>
<span data-ttu-id="b1453-183">Используя отображаемые справа фильтры, можно сформировать сводку о полученном наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="b1453-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="b1453-184">В каждом столбце есть раздел, в котором приводятся уникальные обнаруженные для этого столбца значения и количество экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b1453-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="b1453-185">Уточнение запроса путем выбора кнопок или значений, которые необходимо включить или исключить, а затем выбрать `+` `-` запрос **Run**.</span><span class="sxs-lookup"><span data-stu-id="b1453-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Изображение фильтра расширенного выслеживания](../../media/advanced-hunting-filter.png)

<span data-ttu-id="b1453-187">Использование фильтра с целью изменения запроса и отправка этого запроса позволяют получить новые соответствующие результаты.</span><span class="sxs-lookup"><span data-stu-id="b1453-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1453-188">См. также</span><span class="sxs-lookup"><span data-stu-id="b1453-188">Related topics</span></span>
- [<span data-ttu-id="b1453-189">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="b1453-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b1453-190">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="b1453-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b1453-191">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="b1453-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b1453-192">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="b1453-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b1453-193">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="b1453-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b1453-194">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="b1453-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b1453-195">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="b1453-195">Custom detections overview</span></span>](custom-detections-overview.md)
