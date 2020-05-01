---
title: Работать с расширенными результатами запроса поиска при поиске в Microsoft Threat protection
description: Предоставление большей части результатов запроса, возвращаемых расширенным поиском в защите от угроз Майкрософт
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, пользовательские обнаружения, схема, Кусто, Microsoft 365, защита от угроз Майкрософт, визуализация, диаграмма, фильтры, детализация
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
ms.openlocfilehash: f9838908ca0dbfb498601c3509b920b064a2eb22
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929246"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="e40b6-104">Работать с расширенными результатами запроса поиска</span><span class="sxs-lookup"><span data-stu-id="e40b6-104">Work with advanced hunting query results</span></span>

<span data-ttu-id="e40b6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e40b6-105">**Applies to:**</span></span>
- <span data-ttu-id="e40b6-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="e40b6-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e40b6-107">Несмотря на то, что [Расширенные](advanced-hunting-overview.md) запросы поиска можно создавать для получения очень точной информации, вы также можете работать с результатами запроса, чтобы получить дополнительные сведения и исследовать конкретные действия и индикаторы.</span><span class="sxs-lookup"><span data-stu-id="e40b6-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="e40b6-108">В результатах запроса можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e40b6-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="e40b6-109">Просмотр результатов в виде таблицы или диаграммы</span><span class="sxs-lookup"><span data-stu-id="e40b6-109">View results as a table or chart</span></span>
- <span data-ttu-id="e40b6-110">Экспорт таблиц и диаграмм</span><span class="sxs-lookup"><span data-stu-id="e40b6-110">Export tables and charts</span></span>
- <span data-ttu-id="e40b6-111">Детализация подробных сведений об объекте</span><span class="sxs-lookup"><span data-stu-id="e40b6-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="e40b6-112">Настройка запросов непосредственно из результатов или применение фильтров</span><span class="sxs-lookup"><span data-stu-id="e40b6-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="e40b6-113">Просмотр результатов запроса в виде таблицы или диаграммы</span><span class="sxs-lookup"><span data-stu-id="e40b6-113">View query results as a table or chart</span></span>
<span data-ttu-id="e40b6-114">По умолчанию при расширенном поиске отображаются результаты запроса в виде табличных данных.</span><span class="sxs-lookup"><span data-stu-id="e40b6-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="e40b6-115">Вы также можете отображать одни и те же данные в виде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="e40b6-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="e40b6-116">Расширенный поиск поддерживает следующие представления:</span><span class="sxs-lookup"><span data-stu-id="e40b6-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="e40b6-117">Тип представления</span><span class="sxs-lookup"><span data-stu-id="e40b6-117">View type</span></span> | <span data-ttu-id="e40b6-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e40b6-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="e40b6-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="e40b6-119">**Table**</span></span> | <span data-ttu-id="e40b6-120">Отображает результаты запроса в табличном формате</span><span class="sxs-lookup"><span data-stu-id="e40b6-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="e40b6-121">**Гистограмма**</span><span class="sxs-lookup"><span data-stu-id="e40b6-121">**Column chart**</span></span> | <span data-ttu-id="e40b6-122">Отображает ряд уникальных элементов на оси x как вертикальные полосы, высота которых представляет числовые значения из другого поля</span><span class="sxs-lookup"><span data-stu-id="e40b6-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="e40b6-123">**Гистограмма с накоплением**</span><span class="sxs-lookup"><span data-stu-id="e40b6-123">**Stacked column chart**</span></span> | <span data-ttu-id="e40b6-124">Отрисовывает ряд уникальных элементов на оси x в виде вертикальных полос с накоплением, высота которых представляет числовые значения из одного или нескольких других полей</span><span class="sxs-lookup"><span data-stu-id="e40b6-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="e40b6-125">**Круговая диаграмма**</span><span class="sxs-lookup"><span data-stu-id="e40b6-125">**Pie chart**</span></span> | <span data-ttu-id="e40b6-126">Отображает секторы, представляющие уникальные элементы.</span><span class="sxs-lookup"><span data-stu-id="e40b6-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="e40b6-127">Размер каждого круга представляет числовые значения из другого поля.</span><span class="sxs-lookup"><span data-stu-id="e40b6-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="e40b6-128">**Кольцевой график**</span><span class="sxs-lookup"><span data-stu-id="e40b6-128">**Donut chart**</span></span> | <span data-ttu-id="e40b6-129">Отображает разделы, представляющие уникальные элементы.</span><span class="sxs-lookup"><span data-stu-id="e40b6-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="e40b6-130">Длина каждой дуги представляет числовые значения из другого поля.</span><span class="sxs-lookup"><span data-stu-id="e40b6-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="e40b6-131">**График**</span><span class="sxs-lookup"><span data-stu-id="e40b6-131">**Line chart**</span></span> | <span data-ttu-id="e40b6-132">Отображает числовые значения для ряда уникальных элементов и соединяет значения, которые отображаются на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="e40b6-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="e40b6-133">**Точечная диаграмма**</span><span class="sxs-lookup"><span data-stu-id="e40b6-133">**Scatter chart**</span></span> | <span data-ttu-id="e40b6-134">Отображает числовые значения для ряда уникальных элементов</span><span class="sxs-lookup"><span data-stu-id="e40b6-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="e40b6-135">**Диаграмма с областями**</span><span class="sxs-lookup"><span data-stu-id="e40b6-135">**Area chart**</span></span> | <span data-ttu-id="e40b6-136">Отображает числовые значения для ряда уникальных элементов и заполняет разделы под выводимыми значениями</span><span class="sxs-lookup"><span data-stu-id="e40b6-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="e40b6-137">Создание запросов для эффективных диаграмм</span><span class="sxs-lookup"><span data-stu-id="e40b6-137">Construct queries for effective charts</span></span>
<span data-ttu-id="e40b6-138">При отображении диаграмм Расширенный поиск автоматически определяет интересующие столбцы и числовые значения для статистической обработки.</span><span class="sxs-lookup"><span data-stu-id="e40b6-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="e40b6-139">Чтобы получить осмысленные диаграммы, создайте запросы для возврата определенных значений, которые необходимо отобразить в визуальном виде.</span><span class="sxs-lookup"><span data-stu-id="e40b6-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="e40b6-140">Ниже приведено несколько примеров запросов и результирующих диаграмм.</span><span class="sxs-lookup"><span data-stu-id="e40b6-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="e40b6-141">Оповещения по степени серьезности</span><span class="sxs-lookup"><span data-stu-id="e40b6-141">Alerts by severity</span></span>
<span data-ttu-id="e40b6-142">С помощью `summarize` оператора можно получить числовое количество значений, которые вы хотите создать в диаграмме.</span><span class="sxs-lookup"><span data-stu-id="e40b6-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="e40b6-143">В приведенном ниже запросе `summarize` используется оператор, чтобы получить количество оповещений по степени серьезности.</span><span class="sxs-lookup"><span data-stu-id="e40b6-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="e40b6-144">При отображении результатов на гистограмме значения степени серьезности отображаются как отдельный столбец.</span><span class="sxs-lookup"><span data-stu-id="e40b6-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="e40b6-145">![Изображение результатов запроса поиска с расширенным поиском в виде](../../media/advanced-hunting-column-chart.jpg)
гистограммы*результаты запроса для оповещений по уровню серьезности отображаются в виде* гистограммы</span><span class="sxs-lookup"><span data-stu-id="e40b6-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="e40b6-146">Серьезность оповещений по операционной системе</span><span class="sxs-lookup"><span data-stu-id="e40b6-146">Alert severity by operating system</span></span>
<span data-ttu-id="e40b6-147">Кроме того, можно использовать `summarize` оператор, чтобы подготовить результаты для значений диаграмм из нескольких полей.</span><span class="sxs-lookup"><span data-stu-id="e40b6-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="e40b6-148">Например, вам может потребоваться определить, как серьезность оповещений распределяется между операционными системами (ОС).</span><span class="sxs-lookup"><span data-stu-id="e40b6-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="e40b6-149">Приведенный ниже запрос использует `join` `DeviceInfo` оператор для получения сведений о ОС из таблицы, а затем использует `summarize` для подсчета значений в столбцах `Severity` `OSPlatform` и.</span><span class="sxs-lookup"><span data-stu-id="e40b6-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="e40b6-150">Эти результаты лучше всего подходят для наглядной гистограммы с накоплением:</span><span class="sxs-lookup"><span data-stu-id="e40b6-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="e40b6-151">![Изображение результатов запроса поиска с накоплением в виде диаграммы](../../media/advanced-hunting-stacked-chart.jpg)
с накоплением*результатов запроса для оповещений по операционной системе и уровню серьезности, отображаемым в виде диаграммы с накоплением*</span><span class="sxs-lookup"><span data-stu-id="e40b6-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="e40b6-152">Фишинговые сообщения через десять доменов отправителей</span><span class="sxs-lookup"><span data-stu-id="e40b6-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="e40b6-153">Если вы работаете со списком неконечных значений, вы можете использовать `Top` оператор, чтобы отобразить только значения с наибольшим количеством экземпляров.</span><span class="sxs-lookup"><span data-stu-id="e40b6-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="e40b6-154">Например, чтобы получить первые десять доменов отправителей с наиболее поддельными сообщениями, используйте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="e40b6-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="e40b6-155">Используйте представление круговой диаграммы для эффективного отображения распределения между верхними доменами:</span><span class="sxs-lookup"><span data-stu-id="e40b6-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="e40b6-156">![Изображение результатов расширенного поиска поиска, отображаемое в виде](../../media/advanced-hunting-pie-chart.jpg)
круговой диаграммы с*распределением фишинговых сообщений между верхними доменами отправителя*</span><span class="sxs-lookup"><span data-stu-id="e40b6-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="e40b6-157">Действия с файлами с течением времени</span><span class="sxs-lookup"><span data-stu-id="e40b6-157">File activities over time</span></span>
<span data-ttu-id="e40b6-158">С помощью `summarize` оператора с `bin()` функцией можно проверить наличие событий, связанных с определенным индикатором, с течением времени.</span><span class="sxs-lookup"><span data-stu-id="e40b6-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="e40b6-159">В запросе ниже показано, как подсчитывает события `invoice.doc` , связанные с файлом, с интервалом в 30 минут, чтобы показать пиковые действия, связанные с этим файлом:</span><span class="sxs-lookup"><span data-stu-id="e40b6-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="e40b6-160">На графике ниже показано, как четко выделить периоды времени с большим количеством действий, включающих `invoice.doc`в себя:</span><span class="sxs-lookup"><span data-stu-id="e40b6-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="e40b6-161">![Изображение результатов расширенного поиска поиска, отображаемое в виде](../../media/advanced-hunting-line-chart.jpg)
линейного графика, которое*показывает количество событий, связанных с файлом* , с течением времени</span><span class="sxs-lookup"><span data-stu-id="e40b6-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="e40b6-162">Экспорт таблиц и диаграмм</span><span class="sxs-lookup"><span data-stu-id="e40b6-162">Export tables and charts</span></span>
<span data-ttu-id="e40b6-163">После выполнения запроса нажмите кнопку **Экспорт** , чтобы сохранить результаты в локальный файл.</span><span class="sxs-lookup"><span data-stu-id="e40b6-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="e40b6-164">Выбранное представление определяет, как будут экспортироваться результаты.</span><span class="sxs-lookup"><span data-stu-id="e40b6-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="e40b6-165">**Представление таблицы** — результаты запроса экспортируются в табличную форму в виде книги Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="e40b6-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="e40b6-166">**Любая диаграмма** — результаты запроса экспортируются в виде изображения в формате JPEG для визуализированной диаграммы</span><span class="sxs-lookup"><span data-stu-id="e40b6-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="e40b6-167">Детализация результатов запроса</span><span class="sxs-lookup"><span data-stu-id="e40b6-167">Drill down from query results</span></span>
<span data-ttu-id="e40b6-168">Чтобы просмотреть дополнительные сведения об объектах в результатах поиска по запросу, например, компьютерах, файлах, пользователях, IP-адресах и URL-адресах, нужно просто щелкнуть идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="e40b6-168">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="e40b6-169">Открывается страница c данными профиля выбранного объекта в центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e40b6-169">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="e40b6-170">Регулирование запросов на основе результатов</span><span class="sxs-lookup"><span data-stu-id="e40b6-170">Tweak your queries from the results</span></span>
<span data-ttu-id="e40b6-171">Чтобы оперативно улучшить свой запрос, нужно щелкнуть правой кнопкой мыши одно из значений в полученном наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="e40b6-171">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="e40b6-172">Предлагаемые варианты можно использовать для</span><span class="sxs-lookup"><span data-stu-id="e40b6-172">You can use the options to:</span></span>

- <span data-ttu-id="e40b6-173">открытого поиска избранного значения (`==`)</span><span class="sxs-lookup"><span data-stu-id="e40b6-173">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="e40b6-174">исключения избранного значения из запроса (`!=`)</span><span class="sxs-lookup"><span data-stu-id="e40b6-174">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="e40b6-175">Чтобы добавить к своему запросу определенное значение, можно использовать дополнительные операторы, например, `contains`, `starts with` и`ends with`</span><span class="sxs-lookup"><span data-stu-id="e40b6-175">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Изображение расширенного набора результатов поиска](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="e40b6-177">Фильтрация результатов запроса</span><span class="sxs-lookup"><span data-stu-id="e40b6-177">Filter the query results</span></span>
<span data-ttu-id="e40b6-178">Используя отображаемые справа фильтры, можно сформировать сводку о полученном наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="e40b6-178">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="e40b6-179">В каждом столбце есть раздел, в котором приводятся уникальные обнаруженные для этого столбца значения и количество экземпляров.</span><span class="sxs-lookup"><span data-stu-id="e40b6-179">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="e40b6-180">Уточните свой запрос, нажав кнопку `+` или `-` на значения, которые нужно включить или исключить, а затем выбрав **выполнить запрос**.</span><span class="sxs-lookup"><span data-stu-id="e40b6-180">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Изображение фильтра расширенного выслеживания](../../media/advanced-hunting-filter.png)

<span data-ttu-id="e40b6-182">Использование фильтра с целью изменения запроса и отправка этого запроса позволяют получить новые соответствующие результаты.</span><span class="sxs-lookup"><span data-stu-id="e40b6-182">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e40b6-183">См. также</span><span class="sxs-lookup"><span data-stu-id="e40b6-183">Related topics</span></span>
- [<span data-ttu-id="e40b6-184">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="e40b6-184">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e40b6-185">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="e40b6-185">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e40b6-186">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="e40b6-186">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e40b6-187">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="e40b6-187">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e40b6-188">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="e40b6-188">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e40b6-189">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="e40b6-189">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e40b6-190">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="e40b6-190">Custom detections overview</span></span>](custom-detections-overview.md)
