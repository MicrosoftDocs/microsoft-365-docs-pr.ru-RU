---
title: Работа с расширенными запросами на охоту приводит к atP Microsoft Defender
description: Сделайте большую часть результатов запроса, возвращаемого расширенным поиском в ATP Защитника Майкрософт
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, visualization, chart, filters, drill down
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4abec618a79704804b5e3349f5c4c5a4827d35ef
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499431"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="ca9e1-104">Работа с расширенными результатами запроса на охоту</span><span class="sxs-lookup"><span data-stu-id="ca9e1-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ca9e1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ca9e1-105">**Applies to:**</span></span>
- [<span data-ttu-id="ca9e1-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ca9e1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="ca9e1-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ca9e1-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ca9e1-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="ca9e1-109">В то время [](advanced-hunting-overview.md) как вы можете создавать расширенные запросы для получения очень точных сведений, вы также можете работать с результатами запроса, чтобы получить дополнительные сведения и изучить конкретные действия и индикаторы.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-109">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="ca9e1-110">В результатах запроса можно принять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ca9e1-110">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="ca9e1-111">Просмотр результатов в таблице или диаграмме</span><span class="sxs-lookup"><span data-stu-id="ca9e1-111">View results as a table or chart</span></span>
- <span data-ttu-id="ca9e1-112">Экспорт таблиц и диаграмм</span><span class="sxs-lookup"><span data-stu-id="ca9e1-112">Export tables and charts</span></span>
- <span data-ttu-id="ca9e1-113">Детализация подробных сведений об объектах</span><span class="sxs-lookup"><span data-stu-id="ca9e1-113">Drill down to detailed entity information</span></span>
- <span data-ttu-id="ca9e1-114">Настройка запросов непосредственно из результатов или применение фильтров</span><span class="sxs-lookup"><span data-stu-id="ca9e1-114">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="ca9e1-115">Просмотр результатов запроса в таблице или диаграмме</span><span class="sxs-lookup"><span data-stu-id="ca9e1-115">View query results as a table or chart</span></span>
<span data-ttu-id="ca9e1-116">По умолчанию расширенный режим охоты отображает результаты запроса в качестве табулярных данных.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-116">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="ca9e1-117">Вы также можете отобразить те же данные, что и диаграмма.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-117">You can also display the same data as a chart.</span></span> <span data-ttu-id="ca9e1-118">Расширенный поиск поддерживает следующие представления:</span><span class="sxs-lookup"><span data-stu-id="ca9e1-118">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="ca9e1-119">Тип представления</span><span class="sxs-lookup"><span data-stu-id="ca9e1-119">View type</span></span> | <span data-ttu-id="ca9e1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ca9e1-120">Description</span></span> |
| -- | -- |
| <span data-ttu-id="ca9e1-121">**Table**</span><span class="sxs-lookup"><span data-stu-id="ca9e1-121">**Table**</span></span> | <span data-ttu-id="ca9e1-122">Отображает результаты запроса в табулярном формате</span><span class="sxs-lookup"><span data-stu-id="ca9e1-122">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="ca9e1-123">**Диаграмма столбца**</span><span class="sxs-lookup"><span data-stu-id="ca9e1-123">**Column chart**</span></span> | <span data-ttu-id="ca9e1-124">Отрисовка ряда уникальных элементов на оси x-axis в качестве вертикальных баров, высоты которых представляют числимые значения из другого поля</span><span class="sxs-lookup"><span data-stu-id="ca9e1-124">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="ca9e1-125">**Сложенная диаграмма столбцов**</span><span class="sxs-lookup"><span data-stu-id="ca9e1-125">**Stacked column chart**</span></span> | <span data-ttu-id="ca9e1-126">Отрисовка ряда уникальных элементов на x-axis в качестве сложенных вертикальных баров, высоты которых представляют числовые значения из одного или более других полей.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-126">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="ca9e1-127">**Диаграмма пирога**</span><span class="sxs-lookup"><span data-stu-id="ca9e1-127">**Pie chart**</span></span> | <span data-ttu-id="ca9e1-128">Отрисовка раздельных пирогов, представляющих уникальные элементы.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-128">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="ca9e1-129">Размер каждого пирога представляет численное значение из другого поля.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-129">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="ca9e1-130">**Пончиная диаграмма**</span><span class="sxs-lookup"><span data-stu-id="ca9e1-130">**Donut chart**</span></span> | <span data-ttu-id="ca9e1-131">Отрисовка раздельных дуг, представляющих уникальные элементы.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-131">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="ca9e1-132">Длина каждой дуги представляет численное значение из другого поля.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-132">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="ca9e1-133">**График**</span><span class="sxs-lookup"><span data-stu-id="ca9e1-133">**Line chart**</span></span> | <span data-ttu-id="ca9e1-134">Графики числимые значения для ряда уникальных элементов и соединяет замещенные значения</span><span class="sxs-lookup"><span data-stu-id="ca9e1-134">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="ca9e1-135">**Диаграмма scatter**</span><span class="sxs-lookup"><span data-stu-id="ca9e1-135">**Scatter chart**</span></span> | <span data-ttu-id="ca9e1-136">Графики числимые значения для ряда уникальных элементов</span><span class="sxs-lookup"><span data-stu-id="ca9e1-136">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="ca9e1-137">**Диаграмма области**</span><span class="sxs-lookup"><span data-stu-id="ca9e1-137">**Area chart**</span></span> | <span data-ttu-id="ca9e1-138">Графики числимых значений для ряда уникальных элементов и заполняют разделы ниже замещенных значений</span><span class="sxs-lookup"><span data-stu-id="ca9e1-138">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="ca9e1-139">Создание запросов для эффективных диаграмм</span><span class="sxs-lookup"><span data-stu-id="ca9e1-139">Construct queries for effective charts</span></span>
<span data-ttu-id="ca9e1-140">При отрисовывии диаграмм передовая охота автоматически определяет столбцы, интересующие, и числимые значения для совокупного значения.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-140">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="ca9e1-141">Чтобы получить значимые диаграммы, состройте запросы для возврата определенных значений, которые необходимо увидеть визуализированными.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-141">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="ca9e1-142">Вот некоторые примеры запросов и итоговая диаграмма.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-142">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="ca9e1-143">Оповещений по строгости</span><span class="sxs-lookup"><span data-stu-id="ca9e1-143">Alerts by severity</span></span>
<span data-ttu-id="ca9e1-144">С помощью `summarize` оператора можно получить числовую цифру значений, которые необходимо наметить.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-144">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="ca9e1-145">В приведенной ниже области запрос использует оператора для получения количества предупреждений `summarize` по строгости.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-145">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
DeviceAlertEvents
| summarize Total = count() by Severity
```
<span data-ttu-id="ca9e1-146">При отрисовывии результатов диаграмма столбца отображает каждое значение серьезности в качестве отдельного столбца:</span><span class="sxs-lookup"><span data-stu-id="ca9e1-146">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="ca9e1-147">![Изображение результатов расширенных запросов охоты, отображаемого в качестве результатов запроса диаграммы столбцов для оповещений по степени серьезности, отображаемой ](images/advanced-hunting-column-chart.jpg)
 *в качестве диаграммы столбца*</span><span class="sxs-lookup"><span data-stu-id="ca9e1-147">![Image of advanced hunting query results displayed as a column chart](images/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="ca9e1-148">Серьезность оповещений с помощью операционной системы</span><span class="sxs-lookup"><span data-stu-id="ca9e1-148">Alert severity by operating system</span></span>
<span data-ttu-id="ca9e1-149">Можно также использовать оператора для подготовки `summarize` результатов для наметки значений из нескольких полей.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-149">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="ca9e1-150">Например, вам может потребоваться понять, как распределяются степени серьезности оповещения по операционным системам (ОС).</span><span class="sxs-lookup"><span data-stu-id="ca9e1-150">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="ca9e1-151">В приведенной ниже области запрос использует оператора для получения сведений об ОС из таблицы, а затем для подсчета значений как в столбцах, так `join` `DeviceInfo` и в `summarize` `OSPlatform` `Severity` столбцах:</span><span class="sxs-lookup"><span data-stu-id="ca9e1-151">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity
```
<span data-ttu-id="ca9e1-152">Эти результаты лучше всего визуализировать с помощью диаграммы сложенных столбцов:</span><span class="sxs-lookup"><span data-stu-id="ca9e1-152">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="ca9e1-153">![Изображение результатов расширенных запросов охоты, отображаемого в качестве сложенных результатов запроса диаграммы для оповещений оси и строгости, отображаемой в качестве ](images/advanced-hunting-stacked-chart.jpg)
 *сложенной диаграммы*</span><span class="sxs-lookup"><span data-stu-id="ca9e1-153">![Image of advanced hunting query results displayed as a stacked chart](images/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="top-ten-device-groups-with-alerts"></a><span data-ttu-id="ca9e1-154">Десять групп устройств с оповещениями</span><span class="sxs-lookup"><span data-stu-id="ca9e1-154">Top ten device groups with alerts</span></span>
<span data-ttu-id="ca9e1-155">Если вы имеете дело со списком значений, который не является конечным, оператор может использовать для диаграммы только значения с `Top` большинством экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-155">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="ca9e1-156">Например, чтобы получить десятку групп устройств с наибольшей частью оповещений, используйте запрос ниже:</span><span class="sxs-lookup"><span data-stu-id="ca9e1-156">For example, to get the top ten device groups with the most alerts, use the query below:</span></span>

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by MachineGroup
| top 10 by Count
```
<span data-ttu-id="ca9e1-157">Используйте представление диаграммы пирога, чтобы эффективно показывать распределение по верхним группам:</span><span class="sxs-lookup"><span data-stu-id="ca9e1-157">Use the pie chart view to effectively show distribution across the top groups:</span></span>

<span data-ttu-id="ca9e1-158">![Изображение результатов расширенных запросов на охоту, отображаемого в диаграмме пирога, показывающая распределение оповещений ](images/advanced-hunting-pie-chart.jpg)
 *по группам устройств*</span><span class="sxs-lookup"><span data-stu-id="ca9e1-158">![Image of advanced hunting query results displayed as a pie chart](images/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of alerts across device groups*</span></span>

#### <a name="malware-detections-over-time"></a><span data-ttu-id="ca9e1-159">Обнаружение вредоносных программ со временем</span><span class="sxs-lookup"><span data-stu-id="ca9e1-159">Malware detections over time</span></span>
<span data-ttu-id="ca9e1-160">С помощью оператора с функцией можно проверить события, связанные с определенным `summarize` `bin()` индикатором с течением времени.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-160">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="ca9e1-161">В нижеупромянутом запросе учитывается обнаружение тестового файла EICAR с интервалом в 30 минут, чтобы показать всплески обнаружения этого файла:</span><span class="sxs-lookup"><span data-stu-id="ca9e1-161">The query below counts detections of an EICAR test file at 30 minute intervals to show spikes in detections of that file:</span></span>

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| where SHA1 == "3395856ce81f2b7382dee72602f798b642f14140"
| summarize Detections = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="ca9e1-162">На приведенной ниже строке четко выделены периоды времени с дополнительными обнаружениями тестовой вредоносной программы:</span><span class="sxs-lookup"><span data-stu-id="ca9e1-162">The line chart below clearly highlights time periods with more detections of the test malware:</span></span> 

<span data-ttu-id="ca9e1-163">![Изображение результатов расширенных запросов на охоту, отображаемого в качестве диаграммы строки Line, показывающая количество обнаружения тестового вредоносного ПО ](images/advanced-hunting-line-chart.jpg)
 *со временем*</span><span class="sxs-lookup"><span data-stu-id="ca9e1-163">![Image of advanced hunting query results displayed as a line chart](images/advanced-hunting-line-chart.jpg)
*Line chart showing the number of detections of a test malware over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="ca9e1-164">Экспорт таблиц и диаграмм</span><span class="sxs-lookup"><span data-stu-id="ca9e1-164">Export tables and charts</span></span>
<span data-ttu-id="ca9e1-165">После выполнения запроса выберите **Экспорт,** чтобы сохранить результаты в локальном файле.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-165">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="ca9e1-166">Выбранное представление определяет, как экспортируются результаты:</span><span class="sxs-lookup"><span data-stu-id="ca9e1-166">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="ca9e1-167">**Представление таблицы** — результаты запроса экспортируются в табулярной форме в виде книги Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="ca9e1-167">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="ca9e1-168">**Любая диаграмма** — результаты запроса экспортируются как изображение JPEG отрисовки диаграммы</span><span class="sxs-lookup"><span data-stu-id="ca9e1-168">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="ca9e1-169">Сверлить из результатов запроса</span><span class="sxs-lookup"><span data-stu-id="ca9e1-169">Drill down from query results</span></span>
<span data-ttu-id="ca9e1-170">Чтобы просмотреть дополнительные сведения об объектах, таких как устройства, файлы, пользователи, IP-адреса и URL-адреса, в результатах запроса просто щелкните идентификатор сущности.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-170">To view more information about entities, such as devices, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="ca9e1-171">Это открывает страницу подробного профиля для выбранного объекта.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-171">This opens a detailed profile page for the selected entity.</span></span>

<span data-ttu-id="ca9e1-172">Чтобы быстро проверить запись в результатах запроса, выберите соответствующую строку, чтобы открыть панель записей Inspect.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-172">To quickly inspect a record in your query results, select the corresponding row to open the Inspect record panel.</span></span> <span data-ttu-id="ca9e1-173">Панель предоставляет следующую информацию на основе выбранной записи:</span><span class="sxs-lookup"><span data-stu-id="ca9e1-173">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="ca9e1-174">**Assets** — краткое представление основных активов (почтовых ящиков, устройств и пользователей), найденных в записи, обогащенных доступной информацией, например уровнями риска и экспозиции.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-174">**Assets** — A summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="ca9e1-175">**Дерево процесса** — диаграмма, созданная для записей с данными о процессе и обогащенная с помощью доступной контекстной информации; как правило, запросы, возвращая больше столбцов, могут привести к более богатым деревьям процесса.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-175">**Process tree** — A chart generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="ca9e1-176">**Все сведения** — списки всех значений из столбцов в записи</span><span class="sxs-lookup"><span data-stu-id="ca9e1-176">**All details** — Lists all the values from the columns in the record</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="ca9e1-177">Регулирование запросов на основе результатов</span><span class="sxs-lookup"><span data-stu-id="ca9e1-177">Tweak your queries from the results</span></span>
<span data-ttu-id="ca9e1-178">Чтобы оперативно улучшить свой запрос, нужно щелкнуть правой кнопкой мыши одно из значений в полученном наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-178">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="ca9e1-179">Предлагаемые варианты можно использовать для</span><span class="sxs-lookup"><span data-stu-id="ca9e1-179">You can use the options to:</span></span>

- <span data-ttu-id="ca9e1-180">открытого поиска избранного значения (`==`)</span><span class="sxs-lookup"><span data-stu-id="ca9e1-180">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="ca9e1-181">исключения избранного значения из запроса (`!=`)</span><span class="sxs-lookup"><span data-stu-id="ca9e1-181">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="ca9e1-182">Чтобы добавить к своему запросу определенное значение, можно использовать дополнительные операторы, например, `contains`, `starts with` и`ends with`</span><span class="sxs-lookup"><span data-stu-id="ca9e1-182">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Изображение набора расширенных результатов охоты](images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="ca9e1-184">Фильтрация результатов запроса</span><span class="sxs-lookup"><span data-stu-id="ca9e1-184">Filter the query results</span></span>
<span data-ttu-id="ca9e1-185">Фильтры, отображаемые в правой области, предоставляют сводку набора результатов.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-185">The filters displayed in the right pane provide a summary of the result set.</span></span> <span data-ttu-id="ca9e1-186">Каждый столбец имеет свой раздел в области, в каждом из которых перечислены значения, найденные в этом столбце, и количество экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-186">Every column has its own section in the pane, each of which lists the values found in that column, and the number of instances.</span></span>

<span data-ttu-id="ca9e1-187">Уточнение запроса путем выбора кнопок или значений, которые необходимо `+` `-` включить или исключить.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-187">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude.</span></span> <span data-ttu-id="ca9e1-188">Затем выберите **запрос Run**.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-188">Then select **Run query**.</span></span>

![Изображение фильтра расширенного выслеживания](images/advanced-hunting-filter.png)

<span data-ttu-id="ca9e1-190">Использование фильтра с целью изменения запроса и отправка этого запроса позволяют получить новые соответствующие результаты.</span><span class="sxs-lookup"><span data-stu-id="ca9e1-190">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ca9e1-191">См. также</span><span class="sxs-lookup"><span data-stu-id="ca9e1-191">Related topics</span></span>
- [<span data-ttu-id="ca9e1-192">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="ca9e1-192">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ca9e1-193">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="ca9e1-193">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ca9e1-194">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="ca9e1-194">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ca9e1-195">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="ca9e1-195">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="ca9e1-196">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="ca9e1-196">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ca9e1-197">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="ca9e1-197">Custom detections overview</span></span>](overview-custom-detections.md)
