---
title: Запрос данных в наборе для проверки
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как создать и выполнить запрос в наборе проверки, чтобы упорядочить данные для более эффективной проверки в расширенном случае обнаружения электронных данных.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 871630af4b8b19e5fad1a062129782e36b9706f5
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527439"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="ef5dd-103">Запрос данных в наборе для проверки</span><span class="sxs-lookup"><span data-stu-id="ef5dd-103">Query the data in a review set</span></span>

<span data-ttu-id="ef5dd-104">В большинстве случаев будет полезна возможность более глубокого изучения данных в наборе проверки и систематизации этих данных для упрощения проверки.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="ef5dd-105">Использование запросов в наборе рецензирования помогает сосредоточиться на подмножестве документов, соответствующих критериям проверки.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="ef5dd-106">Создание и выполнение запроса в наборе рецензирования</span><span class="sxs-lookup"><span data-stu-id="ef5dd-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="ef5dd-107">Чтобы создать и выполнить запрос для документов в наборе рецензирования, щелкните **новый запрос** в наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-107">To create and run a query on the documents in a review set, click **New query** in the review set.</span></span> <span data-ttu-id="ef5dd-108">После задания имени запроса и определения условий нажмите кнопку **сохранить** , чтобы сохранить и запустить запрос.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-108">After you name your query and define the conditions, click **Save** to save and run the query.</span></span> <span data-ttu-id="ef5dd-109">Чтобы выполнить сохраненный ранее запрос, щелкните сохраненный запрос.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-109">To run a query that has been previously saved, click a saved query.</span></span>

![Просмотр запросов Set](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="ef5dd-111">Создание запроса на проверку набора</span><span class="sxs-lookup"><span data-stu-id="ef5dd-111">Building a review set query</span></span>

<span data-ttu-id="ef5dd-112">Вы можете создать запрос, используя сочетание карточек условий и языка запросов в карточке условия ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-112">You can build a query by using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="ef5dd-113">Вы также можете группировать карты условий как блок (называемый *группой условий*), чтобы создать более сложный запрос.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-113">You can also group condition cards together as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="ef5dd-114">Список и описание свойств метаданных, которые можно искать, приведены [в статье Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="ef5dd-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="condition-cards"></a><span data-ttu-id="ef5dd-115">Карточки условий</span><span class="sxs-lookup"><span data-stu-id="ef5dd-115">Condition cards</span></span>

<span data-ttu-id="ef5dd-116">Каждое поле поиска в наборе рецензирования имеет соответствующую карточку условия, которую можно использовать для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-116">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="ef5dd-117">Существует несколько типов карточек условий:</span><span class="sxs-lookup"><span data-stu-id="ef5dd-117">There are multiple types of condition cards:</span></span>

- <span data-ttu-id="ef5dd-118">FREETEXT: карточка условия FREETEXT используется для текстовых полей, таких как subject.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-118">Freetext: A freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="ef5dd-119">Вы можете перечислить несколько терминов поиска, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="ef5dd-120">Дата: карточка условия даты используется для полей даты, таких как Дата последнего изменения.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-120">Date: A date condition card is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="ef5dd-121">Параметры поиска: в карточке с параметрами поиска будет представлен список возможных значений для определенного поля в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-121">Search options: A search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="ef5dd-122">Используется для полей, таких как отправитель, где в наборе рецензирования имеется конечное число возможных значений.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="ef5dd-123">Ключевое слово: карточка условия для ключевых слов — это определенный экземпляр карточки условия FREETEXT, который можно использовать для поиска терминов или использовать KQL на языке запросов.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-123">Keyword: A keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="ef5dd-124">Более подробную информацию можно найти ниже.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="ef5dd-125">Язык запросов</span><span class="sxs-lookup"><span data-stu-id="ef5dd-125">Query language</span></span>

<span data-ttu-id="ef5dd-126">В дополнение к карточкам условий для создания запроса можно использовать язык запросов KQL в карточке ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-126">In addition to condition cards, you can use a KQL-like query language in the Keywords card to build your query.</span></span> <span data-ttu-id="ef5dd-127">Язык запросов для запросов Set проверки поддерживает стандартные логические операторы, такие как **and**, **or**, **Not**и **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="ef5dd-128">Он также поддерживает односимвольный подстановочный знак (?) и многозначный подстановочный знак (\*).</span><span class="sxs-lookup"><span data-stu-id="ef5dd-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="using-filters"></a><span data-ttu-id="ef5dd-129">Использование фильтров</span><span class="sxs-lookup"><span data-stu-id="ef5dd-129">Using filters</span></span>

<span data-ttu-id="ef5dd-130">В дополнение к запросам, которые можно сохранить, можно использовать проверку фильтров Set, чтобы быстро применить дополнительные условия к запросу набора проверки.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="ef5dd-131">Это поможет уточнить результаты, отображаемые запросом на проверку набора.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-131">This helps you further refine the results displayed by a review set query.</span></span>

![Обзор набора фильтров](../media/AeDReviewSetFilters.png)

<span data-ttu-id="ef5dd-133">Фильтры отличаются от запросов двумя существенными особенностями.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="ef5dd-134">Фильтры являются временными.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-134">Filters are transient.</span></span> <span data-ttu-id="ef5dd-135">Они не будут сохранены за пределами существующего сеанса.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="ef5dd-136">Другими словами, вы не можете сохранить фильтр.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="ef5dd-137">Запросы сохраняются в наборе проверки и обращаются к ним при открытии набора проверки.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-137">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="ef5dd-138">Фильтры всегда являются аддитивными.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-138">Filters are always additive.</span></span> <span data-ttu-id="ef5dd-139">Фильтры применяются в дополнение к текущему запросу набора проверки.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="ef5dd-140">При применении другого запроса будут заменены результаты, возвращенные текущим запросом.</span><span class="sxs-lookup"><span data-stu-id="ef5dd-140">Applying a different query will replace the results returned by the current query.</span></span>
