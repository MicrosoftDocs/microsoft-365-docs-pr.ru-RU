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
description: Узнайте, как создать и запустить запрос в наборе для проверки, чтобы упорядочат данные для более эффективного анализа в случае Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ead897d412af2356d8b57ab8494539a5ed9a019
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816572"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="3b096-103">Запрос данных в наборе для проверки</span><span class="sxs-lookup"><span data-stu-id="3b096-103">Query the data in a review set</span></span>

<span data-ttu-id="3b096-104">В большинстве случаев полезно иметь возможность углубиться в данные в наборе для проверки и упорядоывать эти данные, чтобы облегчить более эффективную проверку.</span><span class="sxs-lookup"><span data-stu-id="3b096-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="3b096-105">Использование запросов в наборе для проверки помогает сосредоточиться на подмножество документов, которые соответствуют критериям проверки.</span><span class="sxs-lookup"><span data-stu-id="3b096-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="3b096-106">Создание и запуск запроса в наборе для проверки</span><span class="sxs-lookup"><span data-stu-id="3b096-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="3b096-107">Чтобы создать и запустить запрос к документам в наборе для проверки, выберите новый **запрос** в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="3b096-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="3b096-108">После того как вы назовете запрос и определите условия, выберите  "Сохранить", чтобы сохранить и запустить запрос.</span><span class="sxs-lookup"><span data-stu-id="3b096-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="3b096-109">Чтобы выполнить ранее сохраненный запрос, выберите сохраненный запрос.</span><span class="sxs-lookup"><span data-stu-id="3b096-109">To run a query that has been previously saved, select a saved query.</span></span>

![Проверка запросов набора](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="3b096-111">Создание запроса набора для проверки</span><span class="sxs-lookup"><span data-stu-id="3b096-111">Building a review set query</span></span>

<span data-ttu-id="3b096-112">Вы можете создать запрос, используя сочетание ключевых слов, свойств и условий в условии Keywords.</span><span class="sxs-lookup"><span data-stu-id="3b096-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="3b096-113">Вы также можете сгруппить условия в качестве блока (называемого группой *условий),* чтобы создать более сложный запрос.</span><span class="sxs-lookup"><span data-stu-id="3b096-113">You can also group conditions as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="3b096-114">Список и описание свойств метаданных, которые можно искать, см. в полях метаданных документа [в Advanced eDiscovery.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="3b096-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="3b096-115">Условия</span><span class="sxs-lookup"><span data-stu-id="3b096-115">Conditions</span></span>

<span data-ttu-id="3b096-116">Каждое поле для поиска в наборе для проверки имеет соответствующее условие, которое можно использовать для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="3b096-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="3b096-117">Существует несколько типов условий:</span><span class="sxs-lookup"><span data-stu-id="3b096-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="3b096-118">Freetext: условие freetext используется для текстовых полей, таких как тема.</span><span class="sxs-lookup"><span data-stu-id="3b096-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="3b096-119">Можно перечислить несколько условий поиска, разделив их запятой.</span><span class="sxs-lookup"><span data-stu-id="3b096-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="3b096-120">Дата: условие даты используется для полей даты, таких как дата последнего изменения.</span><span class="sxs-lookup"><span data-stu-id="3b096-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="3b096-121">Параметры поиска: условие параметров поиска предоставляет список возможных значений для конкретного поля в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="3b096-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="3b096-122">Он используется для полей, таких как отправитель, где в наборе для проверки имеется ограниченное количество возможных значений.</span><span class="sxs-lookup"><span data-stu-id="3b096-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="3b096-123">Ключевое слово: условие ключевого слова — это особый экземпляр условия freetext, который можно использовать для поиска терминов или использования языка запросов, похожего на KQL.</span><span class="sxs-lookup"><span data-stu-id="3b096-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="3b096-124">Подробнее см. ниже.</span><span class="sxs-lookup"><span data-stu-id="3b096-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="3b096-125">Язык запросов</span><span class="sxs-lookup"><span data-stu-id="3b096-125">Query language</span></span>

<span data-ttu-id="3b096-126">Помимо условий для создания запроса можно использовать язык запросов, похожий на KQL, в условии Keywords.</span><span class="sxs-lookup"><span data-stu-id="3b096-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="3b096-127">Язык запросов для запросов набора для проверки поддерживает стандартные boolean операторы, такие как **AND**, **OR**, **NOT** и **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="3b096-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="3b096-128">Кроме того, он поддерживает поддереговные знаки (?) и многоядерные знаки (\*).</span><span class="sxs-lookup"><span data-stu-id="3b096-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="3b096-129">Фильтры</span><span class="sxs-lookup"><span data-stu-id="3b096-129">Filters</span></span>

<span data-ttu-id="3b096-130">В дополнение к запросам, которые можно сохранить, вы можете использовать фильтры набора для проверки, чтобы быстро применить дополнительные условия к запросу набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="3b096-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="3b096-131">Использование фильтров поможет вам уточнить результаты, отображаемую в запросе набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="3b096-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![Просмотр фильтров набора](../media/AeDReviewSetFilters.png)

<span data-ttu-id="3b096-133">Фильтры отличаются от запросов двумя значительными способами:</span><span class="sxs-lookup"><span data-stu-id="3b096-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="3b096-134">Фильтры являются временными.</span><span class="sxs-lookup"><span data-stu-id="3b096-134">Filters are transient.</span></span> <span data-ttu-id="3b096-135">Они не сохраняются после существующего сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b096-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="3b096-136">Другими словами, вы не можете сохранить фильтр.</span><span class="sxs-lookup"><span data-stu-id="3b096-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="3b096-137">Запросы сохраняются в наборе для проверки и к ним можно получить доступ всякий раз, когда открывается набор для проверки.</span><span class="sxs-lookup"><span data-stu-id="3b096-137">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="3b096-138">Фильтры всегда являются аддитивными.</span><span class="sxs-lookup"><span data-stu-id="3b096-138">Filters are always additive.</span></span> <span data-ttu-id="3b096-139">Фильтры применяются в дополнение к текущему запросу набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="3b096-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="3b096-140">Применение другого запроса заменит результаты, возвращенные текущим запросом.</span><span class="sxs-lookup"><span data-stu-id="3b096-140">Applying a different query will replace the results returned by the current query.</span></span>
