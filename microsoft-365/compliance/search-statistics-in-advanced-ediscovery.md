---
title: Статистика поиска в авансовом обнаружении электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: esclee
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Проверяйте результаты поиска, просмотрев статистику, созданную после выполнения поиска коллекции в Advanced eDiscovery.
ms.openlocfilehash: ef5653a76d94272ba5f608149648f1421198929a
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286085"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="3c838-103">Статистика поиска в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3c838-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="3c838-104">Одним из способов проверки результатов поиска является просмотр статистики по результатам, чтобы убедиться, что они соответствуют ожиданиям.</span><span class="sxs-lookup"><span data-stu-id="3c838-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="3c838-105">После завершения поиска в всплывающем окне со сведениями поиска отображается статистика высокого уровня:</span><span class="sxs-lookup"><span data-stu-id="3c838-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="3c838-106">Количество и количество элементов, получаемых при поиске</span><span class="sxs-lookup"><span data-stu-id="3c838-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="3c838-107">Количество частично индексированных или неиндексированных элементов, найденных в расположениях поиска</span><span class="sxs-lookup"><span data-stu-id="3c838-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="3c838-108">Количество искомых почтовых ящиков и расположений.</span><span class="sxs-lookup"><span data-stu-id="3c838-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="3c838-109">Чтобы просмотреть более подробную статистику, нажмите кнопку "Статистика" из всплывающего меню сведений о поиске.</span><span class="sxs-lookup"><span data-stu-id="3c838-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="3c838-110">Представление сводки</span><span class="sxs-lookup"><span data-stu-id="3c838-110">Summary view</span></span>

<span data-ttu-id="3c838-111">В представлении сводки можно просмотреть результаты поиска, разбитые по типу расположения (например, Exchange).</span><span class="sxs-lookup"><span data-stu-id="3c838-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="3c838-112">Для каждого типа расположения можно увидеть следующее:</span><span class="sxs-lookup"><span data-stu-id="3c838-112">For each location type, you can see:</span></span>

- <span data-ttu-id="3c838-113">Количество местоположений, в которых были элементы, соответствующие условиям поиска</span><span class="sxs-lookup"><span data-stu-id="3c838-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="3c838-114">Количество элементов из этих расположений, соответствующих условиям поиска</span><span class="sxs-lookup"><span data-stu-id="3c838-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="3c838-115">Общий объем элементов, которые отвечают условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="3c838-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="3c838-116">Представление "основные расположения"</span><span class="sxs-lookup"><span data-stu-id="3c838-116">Top locations view</span></span>

<span data-ttu-id="3c838-117">В представлении "основные места" отображаются отдельные расположения с наиболее совпадениями.</span><span class="sxs-lookup"><span data-stu-id="3c838-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="3c838-118">Для каждого расположения вы увидите следующее:</span><span class="sxs-lookup"><span data-stu-id="3c838-118">For each location, you will see:</span></span>

- <span data-ttu-id="3c838-119">Имя расположения (например, URL-адрес SharePoint)</span><span class="sxs-lookup"><span data-stu-id="3c838-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="3c838-120">Тип расположения</span><span class="sxs-lookup"><span data-stu-id="3c838-120">Location type</span></span>

- <span data-ttu-id="3c838-121">Количество элементов, которые отвечают условиям поиска</span><span class="sxs-lookup"><span data-stu-id="3c838-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="3c838-122">Общий объем элементов, которые отвечают условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="3c838-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="3c838-123">Представление "запросы"</span><span class="sxs-lookup"><span data-stu-id="3c838-123">Queries view</span></span>

<span data-ttu-id="3c838-124">Если в запросе используются ключевые слова (к:с) или ключевые слова, можно увидеть разделение запроса в представлении запросы по типу расположения.</span><span class="sxs-lookup"><span data-stu-id="3c838-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="3c838-125">Для каждого типа расположения вы увидите следующее:</span><span class="sxs-lookup"><span data-stu-id="3c838-125">For each location type, you will see:</span></span>

- <span data-ttu-id="3c838-126">Часть: в этом столбце будет либо слово "Primary", либо "ключевое слово".</span><span class="sxs-lookup"><span data-stu-id="3c838-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="3c838-127">"Primary" означает, что строка содержит статистику для всего запроса, а "ключевое слово" означает один из компонентов запроса.</span><span class="sxs-lookup"><span data-stu-id="3c838-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="3c838-128">Запрос: фактический компонент запроса, на который ссылается строка.</span><span class="sxs-lookup"><span data-stu-id="3c838-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="3c838-129">Если часть "основная", это будет весь запрос; Если часть — "ключевое слово", вы увидите один из компонентов запроса здесь.</span><span class="sxs-lookup"><span data-stu-id="3c838-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="3c838-130">При поиске всех почтовых ящиков (без указания ключевых слов) фактическим запросом является (Size >= 0), чтобы возвращались все элементы</span><span class="sxs-lookup"><span data-stu-id="3c838-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="3c838-131">При поиске на сайтах SharePoint Online и OneDrive для бизнеса добавляются два следующих компонента:</span><span class="sxs-lookup"><span data-stu-id="3c838-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="3c838-132">NOT IsExternalContent: 1 — исключение любого контента из локальной организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="3c838-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="3c838-133">NOT Исоненотепаже: 1-исключает все файлы OneNote, так как они будут дублироваться любого документа, который соответствует поисковому запросу.</span><span class="sxs-lookup"><span data-stu-id="3c838-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="3c838-134">Количество расположений, для которых были получены элементы, соответствующие условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="3c838-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="3c838-135">Количество элементов из этих расположений, соответствующих условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="3c838-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="3c838-136">Общий объем элементов, которые отвечают условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="3c838-136">Total volume of items that matched the search conditions.</span></span>
