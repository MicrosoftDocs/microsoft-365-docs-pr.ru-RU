---
title: Работа с результатами запросов на расширенный поиск в Microsoft 365 Defender
description: Как получить большую часть результатов запроса, возвращаемого расширенным поиском в Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, microsoft 365, Microsoft Threat Protection, visualization, chart, filters, drill-down
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932326"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="61a45-104">Работа с результатами запросов на расширенный поиск</span><span class="sxs-lookup"><span data-stu-id="61a45-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="61a45-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="61a45-105">**Applies to:**</span></span>
- <span data-ttu-id="61a45-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61a45-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="61a45-107">Вы можете создавать [](advanced-hunting-overview.md) расширенные поисковые запросы для получения очень точной информации, но вы также можете работать с результатами запроса, чтобы получить дополнительную информацию и изучить конкретные действия и индикаторы.</span><span class="sxs-lookup"><span data-stu-id="61a45-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="61a45-108">С результатами запроса можно воспользоваться следующими действиями:</span><span class="sxs-lookup"><span data-stu-id="61a45-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="61a45-109">Просмотр результатов в таблице или диаграмме</span><span class="sxs-lookup"><span data-stu-id="61a45-109">View results as a table or chart</span></span>
- <span data-ttu-id="61a45-110">Экспорт таблиц и диаграмм</span><span class="sxs-lookup"><span data-stu-id="61a45-110">Export tables and charts</span></span>
- <span data-ttu-id="61a45-111">Детализация до подробных сведений об объектах</span><span class="sxs-lookup"><span data-stu-id="61a45-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="61a45-112">Настройка запросов непосредственно из результатов или применение фильтров</span><span class="sxs-lookup"><span data-stu-id="61a45-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="61a45-113">Просмотр результатов запроса в таблице или диаграмме</span><span class="sxs-lookup"><span data-stu-id="61a45-113">View query results as a table or chart</span></span>
<span data-ttu-id="61a45-114">По умолчанию расширенный поиск отображает результаты запроса в качестве табличные данные.</span><span class="sxs-lookup"><span data-stu-id="61a45-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="61a45-115">Вы также можете отобразить те же данные, что и диаграмму.</span><span class="sxs-lookup"><span data-stu-id="61a45-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="61a45-116">Расширенный поиск поддерживает следующие представления:</span><span class="sxs-lookup"><span data-stu-id="61a45-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="61a45-117">Тип представления</span><span class="sxs-lookup"><span data-stu-id="61a45-117">View type</span></span> | <span data-ttu-id="61a45-118">Описание</span><span class="sxs-lookup"><span data-stu-id="61a45-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="61a45-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="61a45-119">**Table**</span></span> | <span data-ttu-id="61a45-120">Отображает результаты запроса в табулярном формате</span><span class="sxs-lookup"><span data-stu-id="61a45-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="61a45-121">**Диаграмма столбца**</span><span class="sxs-lookup"><span data-stu-id="61a45-121">**Column chart**</span></span> | <span data-ttu-id="61a45-122">Отрисовка ряда уникальных элементов на оси X в качестве вертикальных полос, высота которых представляет числимые значения из другого поля</span><span class="sxs-lookup"><span data-stu-id="61a45-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="61a45-123">**Диаграмма с стопкой столбца**</span><span class="sxs-lookup"><span data-stu-id="61a45-123">**Stacked column chart**</span></span> | <span data-ttu-id="61a45-124">Отрисовка ряда уникальных элементов на оси X в качестве стеков вертикальных полос, высоты которых представляют числовые значения из одного или более других полей</span><span class="sxs-lookup"><span data-stu-id="61a45-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="61a45-125">**Круговая диаграмма**</span><span class="sxs-lookup"><span data-stu-id="61a45-125">**Pie chart**</span></span> | <span data-ttu-id="61a45-126">Отрисовка секциональных кругов, представляющих уникальные элементы.</span><span class="sxs-lookup"><span data-stu-id="61a45-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="61a45-127">Размер каждого кругового поля представляет числимые значения из другого поля.</span><span class="sxs-lookup"><span data-stu-id="61a45-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="61a45-128">**Диаграмма Donut**</span><span class="sxs-lookup"><span data-stu-id="61a45-128">**Donut chart**</span></span> | <span data-ttu-id="61a45-129">Отрисовка секциональных дуг, представляющих уникальные элементы.</span><span class="sxs-lookup"><span data-stu-id="61a45-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="61a45-130">Длина каждой дуги представляет числимые значения из другого поля.</span><span class="sxs-lookup"><span data-stu-id="61a45-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="61a45-131">**График**</span><span class="sxs-lookup"><span data-stu-id="61a45-131">**Line chart**</span></span> | <span data-ttu-id="61a45-132">Строит числимые значения для ряда уникальных элементов и связывает их</span><span class="sxs-lookup"><span data-stu-id="61a45-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="61a45-133">**Точечная диаграмма**</span><span class="sxs-lookup"><span data-stu-id="61a45-133">**Scatter chart**</span></span> | <span data-ttu-id="61a45-134">Строит числимые значения для ряда уникальных элементов</span><span class="sxs-lookup"><span data-stu-id="61a45-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="61a45-135">**Диаграмма области**</span><span class="sxs-lookup"><span data-stu-id="61a45-135">**Area chart**</span></span> | <span data-ttu-id="61a45-136">Занося числимые значения для ряда уникальных элементов и заполняя разделы под замещенными значениями</span><span class="sxs-lookup"><span data-stu-id="61a45-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="61a45-137">Создание запросов для эффективных диаграмм</span><span class="sxs-lookup"><span data-stu-id="61a45-137">Construct queries for effective charts</span></span>
<span data-ttu-id="61a45-138">При отрисовки диаграмм расширенный поиск автоматически определяет интересующие столбцы и числовую сумму значений.</span><span class="sxs-lookup"><span data-stu-id="61a45-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="61a45-139">Чтобы получить осмысленные диаграммы, соберите запросы, чтобы получить конкретные значения, которые вы хотите увидеть в визуализации.</span><span class="sxs-lookup"><span data-stu-id="61a45-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="61a45-140">Вот несколько примеров запросов и итогов диаграмм.</span><span class="sxs-lookup"><span data-stu-id="61a45-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="61a45-141">Оповещения по степени серьезности</span><span class="sxs-lookup"><span data-stu-id="61a45-141">Alerts by severity</span></span>
<span data-ttu-id="61a45-142">Используйте `summarize` оператор, чтобы получить числовую сумму значений, которые вы хотите отметить.</span><span class="sxs-lookup"><span data-stu-id="61a45-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="61a45-143">В приведенной ниже запросе используется оператор для получения количества оповещений `summarize` по степени серьезности.</span><span class="sxs-lookup"><span data-stu-id="61a45-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="61a45-144">При отрисовки результатов диаграмма столбца отображает каждое значение серьезности как отдельный столбец:</span><span class="sxs-lookup"><span data-stu-id="61a45-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="61a45-145">![Изображение результатов запроса на расширенный поиск, отображаемого в качестве результатов запроса диаграммы столбца для оповещений по степени серьезности, отображаемого ](../../media/advanced-hunting-column-chart.jpg)
 *в качестве диаграммы столбца*</span><span class="sxs-lookup"><span data-stu-id="61a45-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="61a45-146">Серьезность оповещений операционной системой</span><span class="sxs-lookup"><span data-stu-id="61a45-146">Alert severity by operating system</span></span>
<span data-ttu-id="61a45-147">Оператор также можно использовать для подготовки результатов для значений диаграммы `summarize` из нескольких полей.</span><span class="sxs-lookup"><span data-stu-id="61a45-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="61a45-148">Например, вам может потребоваться понять, как уровень серьезности оповещений распространяется между операционными системами (ОС).</span><span class="sxs-lookup"><span data-stu-id="61a45-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="61a45-149">В приведенного ниже запросе используется оператор для получения сведений об ОС из таблицы, а затем используется для подсчета значений как в столбцах, так и `join` `DeviceInfo` в `summarize` `OSPlatform` `Severity` столбцах:</span><span class="sxs-lookup"><span data-stu-id="61a45-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="61a45-150">Эти результаты лучше всего визуализируются с помощью диаграммы с стопкой:</span><span class="sxs-lookup"><span data-stu-id="61a45-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="61a45-151">![Изображение результатов запроса на расширенный поиск, отображаемого в качестве стека результатов запроса диаграммы для оповещений по ОС и степени серьезности, отображаемой в качестве ](../../media/advanced-hunting-stacked-chart.jpg)
 *стека диаграммы*</span><span class="sxs-lookup"><span data-stu-id="61a45-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="61a45-152">Фишинговые сообщения электронной почты в десяти верхних доменах отправитель</span><span class="sxs-lookup"><span data-stu-id="61a45-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="61a45-153">Если вы имеете дело со списком значений, который не является конечным, можно использовать оператор для диаграммы только значения с большинством `Top` экземпляров.</span><span class="sxs-lookup"><span data-stu-id="61a45-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="61a45-154">Например, чтобы получить десять доменов отправитель с наиболее фишинговыми электронными письмами, используйте запрос ниже:</span><span class="sxs-lookup"><span data-stu-id="61a45-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="61a45-155">Используйте круговую диаграмму для эффективного показа распределения по верхним доменам:</span><span class="sxs-lookup"><span data-stu-id="61a45-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="61a45-156">![Изображение результатов запроса на расширенный поиск в круговой диаграмме с распределением фишинговых сообщений по доменам ](../../media/advanced-hunting-pie-chart.jpg)
 *отправитель*</span><span class="sxs-lookup"><span data-stu-id="61a45-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="61a45-157">Действия с файлами со временем</span><span class="sxs-lookup"><span data-stu-id="61a45-157">File activities over time</span></span>
<span data-ttu-id="61a45-158">Используя оператор с функцией, вы можете проверять события, включающие `summarize` `bin()` определенный индикатор, с течением времени.</span><span class="sxs-lookup"><span data-stu-id="61a45-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="61a45-159">В приведенного ниже запросе учитываются события, включающие файл с 30-минутными интервалами, для показа пиков активности, связанных `invoice.doc` с этим файлом:</span><span class="sxs-lookup"><span data-stu-id="61a45-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="61a45-160">На приведенной ниже графике четко выделены периоды времени с дополнительными действиями, связанными `invoice.doc` с:</span><span class="sxs-lookup"><span data-stu-id="61a45-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="61a45-161">![Изображение результатов запроса на расширенный поиск, отображаемая в качестве графиковой графики, показывающая количество событий, связанных ](../../media/advanced-hunting-line-chart.jpg)
 *с файлом с течением времени*</span><span class="sxs-lookup"><span data-stu-id="61a45-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="61a45-162">Экспорт таблиц и диаграмм</span><span class="sxs-lookup"><span data-stu-id="61a45-162">Export tables and charts</span></span>
<span data-ttu-id="61a45-163">После выполнения запроса выберите **"Экспорт",** чтобы сохранить результаты в локальный файл.</span><span class="sxs-lookup"><span data-stu-id="61a45-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="61a45-164">Выбранное вами представление определяет, как экспортируются результаты:</span><span class="sxs-lookup"><span data-stu-id="61a45-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="61a45-165">**Представление таблицы** — результаты запроса экспортируются в виде табулярной книги Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="61a45-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="61a45-166">**Любая диаграмма** — результаты запроса экспортируются в формате JPEG отрисовки диаграммы</span><span class="sxs-lookup"><span data-stu-id="61a45-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="61a45-167">Drill down from query results</span><span class="sxs-lookup"><span data-stu-id="61a45-167">Drill down from query results</span></span>
<span data-ttu-id="61a45-168">Чтобы быстро проверить запись в результатах запроса, выберите соответствующую строку, чтобы открыть панель записей **inspect.**</span><span class="sxs-lookup"><span data-stu-id="61a45-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="61a45-169">Панель предоставляет следующие сведения на основе выбранной записи:</span><span class="sxs-lookup"><span data-stu-id="61a45-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="61a45-170">**Ресурсы —** обзор основных активов (почтовых ящиков, устройств и пользователей), найденных в записи, доставка доступной информации, например уровней риска и экспозиции</span><span class="sxs-lookup"><span data-stu-id="61a45-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="61a45-171">**Дерево процессов** — создается для записей с информацией о процессе и обогащено с использованием доступной контекстной информации; Как правило, запросы, возвращая больше столбцов, могут привести к более богатым деревьям процессов.</span><span class="sxs-lookup"><span data-stu-id="61a45-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="61a45-172">**Все сведения** — все значения из столбцов в записи</span><span class="sxs-lookup"><span data-stu-id="61a45-172">**All details** — all the values from the columns in the record</span></span>  

![Изображение выбранной записи с панелью для проверки записи](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="61a45-174">Чтобы просмотреть дополнительные сведения об определенной сущности в результатах запроса, например компьютере, файле, пользователе, IP-адресе или URL-адресе, выберите идентификатор сущности, чтобы открыть подробную страницу профиля для этой сущности.</span><span class="sxs-lookup"><span data-stu-id="61a45-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="61a45-175">Регулирование запросов на основе результатов</span><span class="sxs-lookup"><span data-stu-id="61a45-175">Tweak your queries from the results</span></span>
<span data-ttu-id="61a45-176">Чтобы оперативно улучшить свой запрос, нужно щелкнуть правой кнопкой мыши одно из значений в полученном наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="61a45-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="61a45-177">Предлагаемые варианты можно использовать для</span><span class="sxs-lookup"><span data-stu-id="61a45-177">You can use the options to:</span></span>

- <span data-ttu-id="61a45-178">открытого поиска избранного значения (`==`)</span><span class="sxs-lookup"><span data-stu-id="61a45-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="61a45-179">исключения избранного значения из запроса (`!=`)</span><span class="sxs-lookup"><span data-stu-id="61a45-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="61a45-180">Чтобы добавить к своему запросу определенное значение, можно использовать дополнительные операторы, например, `contains`, `starts with` и`ends with`</span><span class="sxs-lookup"><span data-stu-id="61a45-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Изображение набора результатов "Расширенный поиск"](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="61a45-182">Фильтрация результатов запроса</span><span class="sxs-lookup"><span data-stu-id="61a45-182">Filter the query results</span></span>
<span data-ttu-id="61a45-183">Используя отображаемые справа фильтры, можно сформировать сводку о полученном наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="61a45-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="61a45-184">В каждом столбце есть раздел, в котором приводятся уникальные обнаруженные для этого столбца значения и количество экземпляров.</span><span class="sxs-lookup"><span data-stu-id="61a45-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="61a45-185">Уточните запрос, выбрав кнопки или кнопки для значений, которые вы хотите включить или исключить, а затем выбрав запрос `+` `-` **"Выполнить".**</span><span class="sxs-lookup"><span data-stu-id="61a45-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Изображение фильтра расширенного выслеживания](../../media/advanced-hunting-filter.png)

<span data-ttu-id="61a45-187">Использование фильтра с целью изменения запроса и отправка этого запроса позволяют получить новые соответствующие результаты.</span><span class="sxs-lookup"><span data-stu-id="61a45-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="61a45-188">См. также</span><span class="sxs-lookup"><span data-stu-id="61a45-188">Related topics</span></span>
- [<span data-ttu-id="61a45-189">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="61a45-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="61a45-190">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="61a45-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="61a45-191">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="61a45-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="61a45-192">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="61a45-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="61a45-193">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="61a45-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="61a45-194">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="61a45-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="61a45-195">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="61a45-195">Custom detections overview</span></span>](custom-detections-overview.md)
