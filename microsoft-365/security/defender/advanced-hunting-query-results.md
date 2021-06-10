---
title: Работа с расширенным запросом на охоту приводит к Microsoft 365 Defender
description: Сделайте большую часть результатов запроса, возвращаемого расширенным поиском в Microsoft 365 Defender
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, настраиваемые обнаружения, схема, кусто, визуализация, диаграмма, фильтры, сверла
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: eccf93b019baa240a46260a28f3f0bc109345dd4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952600"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="9b5fc-104">Работа с расширенными результатами запроса на охоту</span><span class="sxs-lookup"><span data-stu-id="9b5fc-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9b5fc-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9b5fc-105">**Applies to:**</span></span>
- <span data-ttu-id="9b5fc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b5fc-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="9b5fc-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9b5fc-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9b5fc-108">В то время [](advanced-hunting-overview.md) как вы можете создавать расширенные запросы для получения очень точных сведений, вы также можете работать с результатами запроса, чтобы получить дополнительные сведения и изучить конкретные действия и индикаторы.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-108">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="9b5fc-109">В результатах запроса можно принять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9b5fc-109">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="9b5fc-110">Просмотр результатов в таблице или диаграмме</span><span class="sxs-lookup"><span data-stu-id="9b5fc-110">View results as a table or chart</span></span>
- <span data-ttu-id="9b5fc-111">Экспорт таблиц и диаграмм</span><span class="sxs-lookup"><span data-stu-id="9b5fc-111">Export tables and charts</span></span>
- <span data-ttu-id="9b5fc-112">Детализация подробных сведений об объектах</span><span class="sxs-lookup"><span data-stu-id="9b5fc-112">Drill down to detailed entity information</span></span>
- <span data-ttu-id="9b5fc-113">Настройка запросов непосредственно из результатов или применение фильтров</span><span class="sxs-lookup"><span data-stu-id="9b5fc-113">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="9b5fc-114">Просмотр результатов запроса в таблице или диаграмме</span><span class="sxs-lookup"><span data-stu-id="9b5fc-114">View query results as a table or chart</span></span>
<span data-ttu-id="9b5fc-115">По умолчанию расширенный режим охоты отображает результаты запроса в качестве табулярных данных.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-115">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="9b5fc-116">Вы также можете отобразить те же данные, что и диаграмма.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-116">You can also display the same data as a chart.</span></span> <span data-ttu-id="9b5fc-117">Расширенный поиск поддерживает следующие представления:</span><span class="sxs-lookup"><span data-stu-id="9b5fc-117">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="9b5fc-118">Тип представления</span><span class="sxs-lookup"><span data-stu-id="9b5fc-118">View type</span></span> | <span data-ttu-id="9b5fc-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9b5fc-119">Description</span></span> |
| -- | -- |
| <span data-ttu-id="9b5fc-120">**Table**</span><span class="sxs-lookup"><span data-stu-id="9b5fc-120">**Table**</span></span> | <span data-ttu-id="9b5fc-121">Отображает результаты запроса в табулярном формате</span><span class="sxs-lookup"><span data-stu-id="9b5fc-121">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="9b5fc-122">**Диаграмма столбца**</span><span class="sxs-lookup"><span data-stu-id="9b5fc-122">**Column chart**</span></span> | <span data-ttu-id="9b5fc-123">Отрисовка ряда уникальных элементов на оси x-axis в качестве вертикальных баров, высоты которых представляют числимые значения из другого поля</span><span class="sxs-lookup"><span data-stu-id="9b5fc-123">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="9b5fc-124">**Сложенная диаграмма столбцов**</span><span class="sxs-lookup"><span data-stu-id="9b5fc-124">**Stacked column chart**</span></span> | <span data-ttu-id="9b5fc-125">Отрисовка ряда уникальных элементов на x-axis в качестве сложенных вертикальных баров, высоты которых представляют числовые значения из одного или более других полей.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-125">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="9b5fc-126">**Диаграмма пирога**</span><span class="sxs-lookup"><span data-stu-id="9b5fc-126">**Pie chart**</span></span> | <span data-ttu-id="9b5fc-127">Отрисовка раздельных пирогов, представляющих уникальные элементы.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-127">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="9b5fc-128">Размер каждого пирога представляет численное значение из другого поля.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-128">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="9b5fc-129">**Пончиная диаграмма**</span><span class="sxs-lookup"><span data-stu-id="9b5fc-129">**Donut chart**</span></span> | <span data-ttu-id="9b5fc-130">Отрисовка раздельных дуг, представляющих уникальные элементы.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-130">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="9b5fc-131">Длина каждой дуги представляет численное значение из другого поля.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-131">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="9b5fc-132">**График**</span><span class="sxs-lookup"><span data-stu-id="9b5fc-132">**Line chart**</span></span> | <span data-ttu-id="9b5fc-133">Графики числимые значения для ряда уникальных элементов и соединяет замещенные значения</span><span class="sxs-lookup"><span data-stu-id="9b5fc-133">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="9b5fc-134">**Диаграмма scatter**</span><span class="sxs-lookup"><span data-stu-id="9b5fc-134">**Scatter chart**</span></span> | <span data-ttu-id="9b5fc-135">Графики числимые значения для ряда уникальных элементов</span><span class="sxs-lookup"><span data-stu-id="9b5fc-135">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="9b5fc-136">**Диаграмма области**</span><span class="sxs-lookup"><span data-stu-id="9b5fc-136">**Area chart**</span></span> | <span data-ttu-id="9b5fc-137">Графики числимых значений для ряда уникальных элементов и заполняют разделы ниже замещенных значений</span><span class="sxs-lookup"><span data-stu-id="9b5fc-137">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="9b5fc-138">Создание запросов для эффективных диаграмм</span><span class="sxs-lookup"><span data-stu-id="9b5fc-138">Construct queries for effective charts</span></span>
<span data-ttu-id="9b5fc-139">При отрисовывии диаграмм передовая охота автоматически определяет столбцы, интересующие, и числимые значения для совокупного значения.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-139">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="9b5fc-140">Чтобы получить значимые диаграммы, состройте запросы для возврата определенных значений, которые необходимо увидеть визуализированными.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-140">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="9b5fc-141">Вот некоторые примеры запросов и итоговая диаграмма.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-141">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="9b5fc-142">Оповещений по строгости</span><span class="sxs-lookup"><span data-stu-id="9b5fc-142">Alerts by severity</span></span>
<span data-ttu-id="9b5fc-143">С помощью `summarize` оператора можно получить числовую цифру значений, которые необходимо наметить.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-143">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="9b5fc-144">В приведенной ниже области запрос использует оператора для получения количества предупреждений `summarize` по строгости.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-144">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="9b5fc-145">При отрисовывии результатов диаграмма столбца отображает каждое значение серьезности в качестве отдельного столбца:</span><span class="sxs-lookup"><span data-stu-id="9b5fc-145">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="9b5fc-146">![Изображение результатов расширенных запросов охоты, отображаемого в качестве результатов запроса диаграммы столбцов для оповещений по степени серьезности, отображаемой ](../../media/advanced-hunting-column-chart.jpg)
 *в качестве диаграммы столбца*</span><span class="sxs-lookup"><span data-stu-id="9b5fc-146">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="9b5fc-147">Серьезность оповещений с помощью операционной системы</span><span class="sxs-lookup"><span data-stu-id="9b5fc-147">Alert severity by operating system</span></span>
<span data-ttu-id="9b5fc-148">Можно также использовать оператора для подготовки `summarize` результатов для наметки значений из нескольких полей.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-148">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="9b5fc-149">Например, вам может потребоваться понять, как распределяются степени серьезности оповещения по операционным системам (ОС).</span><span class="sxs-lookup"><span data-stu-id="9b5fc-149">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="9b5fc-150">В приведенной ниже области запрос использует оператора для получения сведений об ОС из таблицы, а затем для подсчета значений как в столбцах, так `join` `DeviceInfo` и в `summarize` `OSPlatform` `Severity` столбцах:</span><span class="sxs-lookup"><span data-stu-id="9b5fc-150">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="9b5fc-151">Эти результаты лучше всего визуализировать с помощью диаграммы сложенных столбцов:</span><span class="sxs-lookup"><span data-stu-id="9b5fc-151">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="9b5fc-152">![Изображение результатов расширенных запросов охоты, отображаемого в качестве сложенных результатов запроса диаграммы для оповещений оси и строгости, отображаемой в качестве ](../../media/advanced-hunting-stacked-chart.jpg)
 *сложенной диаграммы*</span><span class="sxs-lookup"><span data-stu-id="9b5fc-152">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="9b5fc-153">Фишинговые сообщения электронной почты в десяти доменах отправитель</span><span class="sxs-lookup"><span data-stu-id="9b5fc-153">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="9b5fc-154">Если вы имеете дело со списком значений, который не является конечным, оператор может использовать для диаграммы только значения с `Top` большинством экземпляров.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-154">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="9b5fc-155">Например, чтобы получить десять доменов отправитель с самыми фишинговыми электронными письмами, используйте запрос ниже:</span><span class="sxs-lookup"><span data-stu-id="9b5fc-155">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
<span data-ttu-id="9b5fc-156">Используйте представление диаграммы пирога, чтобы эффективно показывать распределение по верхним доменам:</span><span class="sxs-lookup"><span data-stu-id="9b5fc-156">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="9b5fc-157">![Изображение результатов расширенных запросов на охоту, отображаемого в диаграмме пирога, показывающая распространение фишинговых сообщений электронной почты в ](../../media/advanced-hunting-pie-chart.jpg)
 *верхних доменах отправитель*</span><span class="sxs-lookup"><span data-stu-id="9b5fc-157">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="9b5fc-158">Действия файла со временем</span><span class="sxs-lookup"><span data-stu-id="9b5fc-158">File activities over time</span></span>
<span data-ttu-id="9b5fc-159">С помощью оператора с функцией можно проверить события, связанные с определенным `summarize` `bin()` индикатором с течением времени.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-159">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="9b5fc-160">В нижеупромянутом запросе учитываются события, связанные с файлом с интервалом в 30 минут, чтобы показать всплески активности, связанные `invoice.doc` с этим файлом:</span><span class="sxs-lookup"><span data-stu-id="9b5fc-160">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="9b5fc-161">На приведенной ниже строке четко выделены периоды времени с дополнительными действиями с `invoice.doc` участием:</span><span class="sxs-lookup"><span data-stu-id="9b5fc-161">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="9b5fc-162">![Изображение расширенных результатов запроса охоты, отображаемого в качестве диаграммы строки line, показывающая количество событий, связанных ](../../media/advanced-hunting-line-chart.jpg)
 *с файлом с течением времени*</span><span class="sxs-lookup"><span data-stu-id="9b5fc-162">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="9b5fc-163">Экспорт таблиц и диаграмм</span><span class="sxs-lookup"><span data-stu-id="9b5fc-163">Export tables and charts</span></span>
<span data-ttu-id="9b5fc-164">После выполнения запроса выберите **Экспорт,** чтобы сохранить результаты в локальном файле.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-164">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="9b5fc-165">Выбранное представление определяет, как экспортируются результаты:</span><span class="sxs-lookup"><span data-stu-id="9b5fc-165">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="9b5fc-166">**Представление таблицы** — результаты запроса экспортируются в табулярной форме в виде Microsoft Excel книги</span><span class="sxs-lookup"><span data-stu-id="9b5fc-166">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="9b5fc-167">**Любая диаграмма** — результаты запроса экспортируются как изображение JPEG отрисовки диаграммы</span><span class="sxs-lookup"><span data-stu-id="9b5fc-167">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="9b5fc-168">Сверлить из результатов запроса</span><span class="sxs-lookup"><span data-stu-id="9b5fc-168">Drill down from query results</span></span>
<span data-ttu-id="9b5fc-169">Чтобы быстро проверить запись в результатах запроса, выберите соответствующую строку, чтобы открыть панель **записей Inspect.**</span><span class="sxs-lookup"><span data-stu-id="9b5fc-169">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="9b5fc-170">Панель предоставляет следующую информацию на основе выбранной записи:</span><span class="sxs-lookup"><span data-stu-id="9b5fc-170">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="9b5fc-171">**Активы** — краткое представление основных активов (почтовых ящиков, устройств и пользователей), найденных в записи, обогащенных доступной информацией, например уровнями риска и экспозиции.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-171">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="9b5fc-172">**Дерево процесса** — создается для записей с информацией о процессе и обогащено с помощью доступной контекстной информации; как правило, запросы, возвращая больше столбцов, могут привести к более богатым деревьям процесса.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-172">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="9b5fc-173">**Все сведения** — все значения столбцов в записи</span><span class="sxs-lookup"><span data-stu-id="9b5fc-173">**All details** — all the values from the columns in the record</span></span>  

![Изображение выбранной записи с панелью для проверки записи](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="9b5fc-175">Чтобы просмотреть дополнительные сведения о конкретном объекте в результатах запроса, таких как машина, файл, пользователь, IP-адрес или URL-адрес, выберите идентификатор сущности, чтобы открыть страницу подробного профиля для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-175">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="9b5fc-176">Регулирование запросов на основе результатов</span><span class="sxs-lookup"><span data-stu-id="9b5fc-176">Tweak your queries from the results</span></span>
<span data-ttu-id="9b5fc-177">Чтобы оперативно улучшить свой запрос, нужно щелкнуть правой кнопкой мыши одно из значений в полученном наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-177">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="9b5fc-178">Предлагаемые варианты можно использовать для</span><span class="sxs-lookup"><span data-stu-id="9b5fc-178">You can use the options to:</span></span>

- <span data-ttu-id="9b5fc-179">открытого поиска избранного значения (`==`)</span><span class="sxs-lookup"><span data-stu-id="9b5fc-179">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="9b5fc-180">исключения избранного значения из запроса (`!=`)</span><span class="sxs-lookup"><span data-stu-id="9b5fc-180">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="9b5fc-181">Чтобы добавить к своему запросу определенное значение, можно использовать дополнительные операторы, например, `contains`, `starts with` и`ends with`</span><span class="sxs-lookup"><span data-stu-id="9b5fc-181">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Изображение набора расширенных результатов охоты](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="9b5fc-183">Фильтрация результатов запроса</span><span class="sxs-lookup"><span data-stu-id="9b5fc-183">Filter the query results</span></span>
<span data-ttu-id="9b5fc-184">Используя отображаемые справа фильтры, можно сформировать сводку о полученном наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-184">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="9b5fc-185">В каждом столбце есть раздел, в котором приводятся уникальные обнаруженные для этого столбца значения и количество экземпляров.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-185">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="9b5fc-186">Уточнение запроса путем выбора кнопок или значений, которые необходимо включить или исключить, а затем выбрать `+` `-` запрос **Run**.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-186">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Изображение фильтра расширенного выслеживания](../../media/advanced-hunting-filter.png)

<span data-ttu-id="9b5fc-188">Использование фильтра с целью изменения запроса и отправка этого запроса позволяют получить новые соответствующие результаты.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-188">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

>[!NOTE]
><span data-ttu-id="9b5fc-189">Некоторые таблицы в этой статье могут быть недоступны в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9b5fc-190">[Включи Microsoft 365 Defender,](m365d-enable.md) чтобы искать угрозы с помощью дополнительных источников данных.</span><span class="sxs-lookup"><span data-stu-id="9b5fc-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="9b5fc-191">Вы можете переместить расширенные процессы охоты из Microsoft Defender для endpoint в Microsoft 365 Defender, следуя шагам в миграции расширенных запросов охоты из [Microsoft Defender для конечной точки](advanced-hunting-migrate-from-mde.md).</span><span class="sxs-lookup"><span data-stu-id="9b5fc-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9b5fc-192">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9b5fc-192">Related topics</span></span>
- [<span data-ttu-id="9b5fc-193">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="9b5fc-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9b5fc-194">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="9b5fc-194">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9b5fc-195">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="9b5fc-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9b5fc-196">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="9b5fc-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9b5fc-197">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="9b5fc-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9b5fc-198">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="9b5fc-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="9b5fc-199">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="9b5fc-199">Custom detections overview</span></span>](custom-detections-overview.md)
