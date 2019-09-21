---
title: Запрос данных в наборе для проверки
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
description: ''
ms.openlocfilehash: 446f3f2588a79cb328476db490f1f555448b5ce7
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091375"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="41c19-102">Запрос данных в наборе для проверки</span><span class="sxs-lookup"><span data-stu-id="41c19-102">Query the data in a review set</span></span>

<span data-ttu-id="41c19-103">В большинстве случаев полезно иметь возможность глубже проанализировать, что есть в наборе рецензирования, и упорядочить их для более эффективного просмотра.</span><span class="sxs-lookup"><span data-stu-id="41c19-103">In most cases, it will be useful to be able to dig deeper into what is there in a review set and organize them to review more efficiently.</span></span> <span data-ttu-id="41c19-104">Запросы в наборе проверки позволяют сделать это, позволяя сосредоточиться на подмножестве документов, которые удовлетворяют критериям, определенным вами одновременно.</span><span class="sxs-lookup"><span data-stu-id="41c19-104">Queries within a review set enables you to do so by letting you focus on a subset of documents that meet the criteria defined by you at once.</span></span>

## <a name="creating-and-running-a-query-within-a-review-set"></a><span data-ttu-id="41c19-105">Создание и выполнение запроса в наборе проверки</span><span class="sxs-lookup"><span data-stu-id="41c19-105">Creating and running a query within a review set</span></span>

<span data-ttu-id="41c19-106">Чтобы создать и запустить запрос в наборе рецензирования, щелкните "создать запрос" в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="41c19-106">In order to create and run a query within your review set, click on "New Query" in your review set.</span></span> <span data-ttu-id="41c19-107">После задания имени запроса и определения условий нажмите кнопку Save (сохранить), чтобы выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="41c19-107">After you name your query and define the conditions, click "Save" to run the query.</span></span> <span data-ttu-id="41c19-108">Чтобы выполнить сохраненный ранее запрос, просто щелкните сохраненный запрос.</span><span class="sxs-lookup"><span data-stu-id="41c19-108">To run a query that has been previously saved, simply click on the saved query.</span></span> <span data-ttu-id="41c19-109">Ссылки на [поля метаданных документа](document-metadata-fields.md) для списка метаданных, по которым можно выполнять поиск.</span><span class="sxs-lookup"><span data-stu-id="41c19-109">Refer to [Document metadata fields](document-metadata-fields.md) for a list of metadata you can search by.</span></span>

## <a name="building-your-query"></a><span data-ttu-id="41c19-110">Создание запроса</span><span class="sxs-lookup"><span data-stu-id="41c19-110">Building your query</span></span>

<span data-ttu-id="41c19-111">Вы можете создать запрос, используя сочетание карточек условий и языка запросов в карточке условия ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="41c19-111">You can build your query using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="41c19-112">Вы можете сгруппировать карточки условий в виде блока, чтобы создать более сложный запрос.</span><span class="sxs-lookup"><span data-stu-id="41c19-112">You can group condition cards together as a block to craft a more complex query.</span></span>

### <a name="condition-card"></a><span data-ttu-id="41c19-113">Карточка условия</span><span class="sxs-lookup"><span data-stu-id="41c19-113">Condition card</span></span>

<span data-ttu-id="41c19-114">Каждое поле поиска в наборе рецензирования имеет соответствующую карточку условия, которую можно использовать для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="41c19-114">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="41c19-115">Существует несколько типов карточек условий:</span><span class="sxs-lookup"><span data-stu-id="41c19-115">There are multiple types of condition cards:</span></span>
- <span data-ttu-id="41c19-116">FREETEXT: карточка условия FREETEXT используется для текстовых полей, таких как тема.</span><span class="sxs-lookup"><span data-stu-id="41c19-116">Freetext: freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="41c19-117">Вы можете перечислить несколько терминов поиска, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="41c19-117">You can list multiple search terms by separating them out with a comma.</span></span>
- <span data-ttu-id="41c19-118">Дата: Дата условия используется для полей даты, таких как Дата последнего изменения.</span><span class="sxs-lookup"><span data-stu-id="41c19-118">Date: date condition card is used for date fields such as last modified date.</span></span>
- <span data-ttu-id="41c19-119">Параметры поиска: в карточке с параметрами поиска в карточке будет представлен список возможных значений для определенного поля в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="41c19-119">Search options: search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="41c19-120">Используется для полей, таких как отправитель, где в наборе рецензирования имеется конечное число возможных значений.</span><span class="sxs-lookup"><span data-stu-id="41c19-120">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>
- <span data-ttu-id="41c19-121">Ключевое слово: карточка условия для ключевых слов — это определенный экземпляр карточки условия FREETEXT, который можно использовать для поиска терминов или использовать KQL на языке запросов, аналогичный языку запросов в.</span><span class="sxs-lookup"><span data-stu-id="41c19-121">Keyword: keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="41c19-122">Более подробную информацию можно найти ниже.</span><span class="sxs-lookup"><span data-stu-id="41c19-122">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="41c19-123">Язык запросов</span><span class="sxs-lookup"><span data-stu-id="41c19-123">Query language</span></span>

<span data-ttu-id="41c19-124">В дополнение к карточкам условий для создания запроса можно использовать язык запросов KQL в карточке ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="41c19-124">In addition to condition cards, you can use a KQL-like query language in the Keywords card to craft your query.</span></span> <span data-ttu-id="41c19-125">Язык запросов поддерживает стандартный синтаксис KQL, такой как AND, OR, NOT и NEAR (n).</span><span class="sxs-lookup"><span data-stu-id="41c19-125">The query language supports standard KQL syntax like AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="41c19-126">Он также поддерживает односимвольный подстановочный знак (?) и многозначный подстановочный знак (\*).</span><span class="sxs-lookup"><span data-stu-id="41c19-126">It also supports single-character wildcard (?) and multi-character wildcard (\*).</span></span>

## <a name="filter"></a><span data-ttu-id="41c19-127">Фильтр</span><span class="sxs-lookup"><span data-stu-id="41c19-127">Filter</span></span>

<span data-ttu-id="41c19-128">В дополнение к запросам, которые можно сохранять, можно накладывать дополнительные условия на лету к результатам запроса с помощью фильтров.</span><span class="sxs-lookup"><span data-stu-id="41c19-128">In addition to queries that you can save, you can overlay additional conditions on the fly to your query results using filters.</span></span> <span data-ttu-id="41c19-129">Фильтры отличаются от запросов несколькими существенными особенностями.</span><span class="sxs-lookup"><span data-stu-id="41c19-129">Filters differ from queries in a few significant ways:</span></span>
- <span data-ttu-id="41c19-130">Фильтры являются временными (то есть не сохраняются в разных сеансах), в то время как запросы сохраняются в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="41c19-130">Filters are transient (i.e. they do not persist over different sessions), whereas queries are saved to the review set.</span></span>
- <span data-ttu-id="41c19-131">Фильтры всегда аддитивны; фильтры будут применяться к началу запроса, в то время как при применении запроса он будет заменен на действующий запрос.</span><span class="sxs-lookup"><span data-stu-id="41c19-131">Filters are always additive; filters will apply on top of the query you have in effect at the moment, whereas applying a query will replace the query in effect.</span></span>