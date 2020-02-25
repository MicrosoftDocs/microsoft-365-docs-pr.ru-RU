---
title: Обзор сведений о расширенном выслеживании угроз в службе Защиты от угроз (Майкрософт)
description: В статье рассказывается о запросах расширенного выслеживания в Microsoft 365 и о том, как их использовать для профилактического обнаружения угроз и слабых мест в своей сети.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, пользовательские обнаружения, схема, Кусто, Microsoft 365, защита от угроз Майкрософт
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
ms.openlocfilehash: 598ef669e95081ef098dfa9cfdb5473b21b28306
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234758"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="afad4-104">Защита от угроз (Майкрософт) позволяет осуществлять их расширенное выслеживание на профилактической основе</span><span class="sxs-lookup"><span data-stu-id="afad4-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="afad4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="afad4-105">**Applies to:**</span></span>
- <span data-ttu-id="afad4-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="afad4-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="afad4-107">Расширенное выслеживание— это средство для выслеживания угроз на основе запросов, которое позволяет изучать необработанные данные за период до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="afad4-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="afad4-108">Оно дает возможность проводить инспекцию событий в своей сети для поиска интересных индикаторов и объектов на профилактической основе.</span><span class="sxs-lookup"><span data-stu-id="afad4-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="afad4-109">Гибкое управление доступом к данным позволяет выслеживать как известные, так и потенциальные угрозы без ограничений.</span><span class="sxs-lookup"><span data-stu-id="afad4-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="afad4-110">В центре безопасности Microsoft 365 Расширенный поиск поддерживает запросы, которые проверяют данные из пакета ATP для защитника Майкрософт, охватывают данные с подключенных устройств и Office 365 ATP, предоставляя данные из электронных писем.</span><span class="sxs-lookup"><span data-stu-id="afad4-110">In the Microsoft 365 security center, advanced hunting supports queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span> <span data-ttu-id="afad4-111">Воспользоваться расширенным выслеживанием можно, [включив Защиту от угроз (Майкрософт)](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="afad4-111">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="afad4-112">Начало работы с расширенным выслеживанием</span><span class="sxs-lookup"><span data-stu-id="afad4-112">Get started with advanced hunting</span></span>

<span data-ttu-id="afad4-113">Чтобы быстро приступить к работе с расширенным выслеживанием и освоиться с ним, нужно выполнить несколько действий.</span><span class="sxs-lookup"><span data-stu-id="afad4-113">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="afad4-114">Цель обучения</span><span class="sxs-lookup"><span data-stu-id="afad4-114">Learning goal</span></span> | <span data-ttu-id="afad4-115">Описание</span><span class="sxs-lookup"><span data-stu-id="afad4-115">Description</span></span> | <span data-ttu-id="afad4-116">Ресурс</span><span class="sxs-lookup"><span data-stu-id="afad4-116">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="afad4-117">**Освоение языка**</span><span class="sxs-lookup"><span data-stu-id="afad4-117">**Get a feel for the language**</span></span> | <span data-ttu-id="afad4-118">Расширенное выслеживание основано на [языке запросов Kusto](https://docs.microsoft.com/azure/kusto/query/) с поддержкой аналогичного синтаксиса и аналогичных операторов.</span><span class="sxs-lookup"><span data-stu-id="afad4-118">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="afad4-119">Начать изучение языка запросов можно, выполнив свой первый запрос.</span><span class="sxs-lookup"><span data-stu-id="afad4-119">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="afad4-120">Сведения о языке запросов</span><span class="sxs-lookup"><span data-stu-id="afad4-120">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="afad4-121">**Сведения о схеме**</span><span class="sxs-lookup"><span data-stu-id="afad4-121">**Understand the schema**</span></span> | <span data-ttu-id="afad4-122">Формирование четкого и глубокого представления о таблицах схемы и входящих в них столбцах.</span><span class="sxs-lookup"><span data-stu-id="afad4-122">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="afad4-123">Это поможет определять, где искать данные и как создавать запросы.</span><span class="sxs-lookup"><span data-stu-id="afad4-123">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="afad4-124">Справочник по схеме</span><span class="sxs-lookup"><span data-stu-id="afad4-124">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="afad4-125">**Использование предварительно настроенных запросов**</span><span class="sxs-lookup"><span data-stu-id="afad4-125">**Use predefined queries**</span></span> | <span data-ttu-id="afad4-126">Возможен поиск в коллекции предварительно настроенных запросов для использования при разных сценариев выслеживания угроз.</span><span class="sxs-lookup"><span data-stu-id="afad4-126">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="afad4-127">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="afad4-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
| <span data-ttu-id="afad4-128">**Оптимизация запросов**</span><span class="sxs-lookup"><span data-stu-id="afad4-128">**Optimize queries**</span></span> | <span data-ttu-id="afad4-129">Общие сведения о создании эффективных запросов и запросов с объединенными данными из сообщений электронной почты и c устройств.</span><span class="sxs-lookup"><span data-stu-id="afad4-129">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="afad4-130">[Рекомендации по примению запросов](advanced-hunting-shared-queries.md), [Выслеживание на устройствах и в сообщениях электронной почты](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="afad4-130">[Query best practices](advanced-hunting-shared-queries.md), [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="afad4-131">Помощь при написании запросов</span><span class="sxs-lookup"><span data-stu-id="afad4-131">Get help as you write queries</span></span>
<span data-ttu-id="afad4-132">Ниже перечислены функции, благодаря которым запросы можно создавать быстрее.</span><span class="sxs-lookup"><span data-stu-id="afad4-132">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="afad4-133">**Автозаполнение** — отображение по мере ввода текста запроса вариантов, имеющихся в системе расширенного выслеживания.</span><span class="sxs-lookup"><span data-stu-id="afad4-133">**Autosuggest** — as you write queries, advanced hunting provides suggestions.</span></span> 
- <span data-ttu-id="afad4-134">**Справочник по схеме** — справочник по схеме со списком таблиц и их столбцов, расположенный рядом с рабочей областью.</span><span class="sxs-lookup"><span data-stu-id="afad4-134">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="afad4-135">Чтобы получить об элементе дополнительные сведения, нужно навести на него указатель мыши.</span><span class="sxs-lookup"><span data-stu-id="afad4-135">For more information, hover over an item.</span></span> <span data-ttu-id="afad4-136">Чтобы вставить элемент в редактор запросов, нужно дважды щелкнуть по нему.</span><span class="sxs-lookup"><span data-stu-id="afad4-136">Double-click an item to insert it to the query editor.</span></span>

## <a name="drilldown-from-query-results"></a><span data-ttu-id="afad4-137">Детализация результатов запроса</span><span class="sxs-lookup"><span data-stu-id="afad4-137">Drilldown from query results</span></span>
<span data-ttu-id="afad4-138">Чтобы просмотреть дополнительные сведения об объектах в результатах поиска по запросу, например, компьютерах, файлах, пользователях, IP-адресах и URL-адресах, нужно просто щелкнуть идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="afad4-138">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="afad4-139">Открывается страница c данными профиля выбранного объекта в центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="afad4-139">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="afad4-140">Регулирование запросов на основе результатов</span><span class="sxs-lookup"><span data-stu-id="afad4-140">Tweak your queries from the results</span></span>
<span data-ttu-id="afad4-141">Чтобы оперативно улучшить свой запрос, нужно щелкнуть правой кнопкой мыши одно из значений в полученном наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="afad4-141">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="afad4-142">Предлагаемые варианты можно использовать для</span><span class="sxs-lookup"><span data-stu-id="afad4-142">You can use the options to:</span></span>

- <span data-ttu-id="afad4-143">открытого поиска избранного значения (`==`)</span><span class="sxs-lookup"><span data-stu-id="afad4-143">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="afad4-144">исключения избранного значения из запроса (`!=`)</span><span class="sxs-lookup"><span data-stu-id="afad4-144">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="afad4-145">Чтобы добавить к своему запросу определенное значение, можно использовать дополнительные операторы, например, `contains`, `starts with` и`ends with`</span><span class="sxs-lookup"><span data-stu-id="afad4-145">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Изображение набора результатов расширенного выслеживания в ATP в Microsoft Defender](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="afad4-147">Фильтрация результатов запроса</span><span class="sxs-lookup"><span data-stu-id="afad4-147">Filter the query results</span></span>
<span data-ttu-id="afad4-148">Используя отображаемые справа фильтры, можно сформировать сводку о полученном наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="afad4-148">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="afad4-149">В каждом столбце есть раздел, в котором приводятся уникальные обнаруженные для этого столбца значения и количество экземпляров.</span><span class="sxs-lookup"><span data-stu-id="afad4-149">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="afad4-150">С помощью кнопок "+" и "-" для значений, которые нужно включить или исключить, можно уточнить запрос и затем выбрать команду**Выполнить запрос**.</span><span class="sxs-lookup"><span data-stu-id="afad4-150">Refine your query by selecting the "+" or "-" buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Изображение фильтра расширенного выслеживания](../../media/advanced-hunting-filter.png)

<span data-ttu-id="afad4-152">Использование фильтра с целью изменения запроса и отправка этого запроса позволяют получить новые соответствующие результаты.</span><span class="sxs-lookup"><span data-stu-id="afad4-152">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="afad4-153">См. также</span><span class="sxs-lookup"><span data-stu-id="afad4-153">Related topics</span></span>
- [<span data-ttu-id="afad4-154">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="afad4-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="afad4-155">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="afad4-155">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="afad4-156">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="afad4-156">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="afad4-157">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="afad4-157">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="afad4-158">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="afad4-158">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
