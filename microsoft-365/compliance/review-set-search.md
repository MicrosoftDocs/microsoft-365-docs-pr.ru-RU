---
title: Запрос данных в наборе для проверки
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как создать и запустить запрос в наборе обзоров для организации данных для более эффективного анализа в Advanced eDiscovery случае.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345804"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="3a5ff-103">Запрос данных в наборе для проверки</span><span class="sxs-lookup"><span data-stu-id="3a5ff-103">Query the data in a review set</span></span>

<span data-ttu-id="3a5ff-104">В большинстве случаев будет полезно углубиться в данные в наборе обзоров и организовать эти данные для более эффективного анализа.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="3a5ff-105">Использование запросов в наборе обзоров позволяет сосредоточиться на подмножество документов, которые соответствуют критериям проверки.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="3a5ff-106">Создание и запуск запроса в наборе обзоров</span><span class="sxs-lookup"><span data-stu-id="3a5ff-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="3a5ff-107">Чтобы создать и запустить запрос по документам в наборе отзывов, выберите **Новый** запрос в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="3a5ff-108">После имени запроса и определения условий выберите **Сохранить** для сохранения и запуска запроса.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="3a5ff-109">Чтобы выполнить ранее сохраненный запрос, выберите сохраненный запрос.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-109">To run a query that has been previously saved, select a saved query.</span></span>

![Просмотр запросов набора](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="3a5ff-111">Создание запроса набора обзоров</span><span class="sxs-lookup"><span data-stu-id="3a5ff-111">Building a review set query</span></span>

<span data-ttu-id="3a5ff-112">Вы можете создать запрос с помощью сочетания ключевых слов, свойств и условий в состоянии Keywords.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="3a5ff-113">Можно также сгруппить условия в качестве блока (называемого группой условий), чтобы создать более сложный запрос.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-113">You can also group conditions as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="3a5ff-114">Список и описание свойств метаданных, по которым можно искать, см. в статье [Поля метаданных документа в Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="3a5ff-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="3a5ff-115">Условия</span><span class="sxs-lookup"><span data-stu-id="3a5ff-115">Conditions</span></span>

<span data-ttu-id="3a5ff-116">Каждое поле для поиска в наборе отзывов имеет соответствующее условие, которое можно использовать для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="3a5ff-117">Существует несколько типов условий:</span><span class="sxs-lookup"><span data-stu-id="3a5ff-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="3a5ff-118">Freetext. Условие freetext используется для текстовых полей, таких как тема.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="3a5ff-119">Можно перечислить несколько терминов поиска, разделив их с запятой.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="3a5ff-120">Дата. Условие даты используется для полей дат, таких как последняя измененная дата.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="3a5ff-121">Параметры поиска. Условие параметра поиска предоставит список возможных значений для определенного поля в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="3a5ff-122">Это используется для полей, таких как отправитель, где в наборе отзывов имеется конечное число возможных значений.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="3a5ff-123">Ключевое слово. Условие ключевого слова — это определенный экземпляр условия freetext, который можно использовать для поиска терминов или языка запросов, похожих на KQL.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="3a5ff-124">Дополнительные подробности см. ниже.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="3a5ff-125">Язык запросов</span><span class="sxs-lookup"><span data-stu-id="3a5ff-125">Query language</span></span>

<span data-ttu-id="3a5ff-126">Помимо условий, для создания запроса можно использовать язык запросов, похожий на KQL, в состоянии Keywords.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="3a5ff-127">Язык запросов для запросов набора отзывов поддерживает стандартные операторы boolean, такие как **AND,** **OR,** **NOT** и **NEAR.**</span><span class="sxs-lookup"><span data-stu-id="3a5ff-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="3a5ff-128">Он также поддерживает под диктовую карточку с одним и несколькими символами (\*).</span><span class="sxs-lookup"><span data-stu-id="3a5ff-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="3a5ff-129">Фильтры</span><span class="sxs-lookup"><span data-stu-id="3a5ff-129">Filters</span></span>

<span data-ttu-id="3a5ff-130">Помимо запросов, которые можно сохранить, можно использовать фильтры набора обзоров для быстрого применения дополнительных условий к запросу набора обзоров.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="3a5ff-131">Использование фильтров поможет вам дополнительно уточнить результаты, отображаемые запросом набора отзывов.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![Просмотр фильтров набора](../media/AeDReviewSetFilters.png)

<span data-ttu-id="3a5ff-133">Фильтры отличаются от запросов двумя значительными способами:</span><span class="sxs-lookup"><span data-stu-id="3a5ff-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="3a5ff-134">Фильтры являются временными.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-134">Filters are transient.</span></span> <span data-ttu-id="3a5ff-135">Они не сохраняются за пределами существующего сеанса.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="3a5ff-136">Другими словами, не удалось сохранить фильтр.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="3a5ff-137">Запросы сохраняются в наборе отзывов и к ним при открываемом наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-137">Queries are saved to the review set, and access them whenever you open the review set.</span></span>

- <span data-ttu-id="3a5ff-138">Фильтры всегда являются добавками.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-138">Filters are always additive.</span></span> <span data-ttu-id="3a5ff-139">Фильтры применяются в дополнение к текущему запросу набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="3a5ff-140">Применение другого запроса заменит результаты, возвращенные текущим запросом.</span><span class="sxs-lookup"><span data-stu-id="3a5ff-140">Applying a different query will replace the results returned by the current query.</span></span>
