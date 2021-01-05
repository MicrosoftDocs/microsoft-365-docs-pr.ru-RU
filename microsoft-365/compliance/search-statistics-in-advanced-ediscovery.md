---
title: Статистика поиска в Advance eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: Проверьте результаты поиска, просмотрев статистику, которая создается после запуска поиска коллекции в Advanced eDiscovery.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750780"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="380e3-103">Статистика поиска в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="380e3-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="380e3-104">Один из способов проверить результаты поиска — проверить статистику результатов, чтобы убедиться, что они соответствуют вашим ожиданиям.</span><span class="sxs-lookup"><span data-stu-id="380e3-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="380e3-105">После завершения поиска высокоуровневая статистика отображается во flyout сведений о поиске:</span><span class="sxs-lookup"><span data-stu-id="380e3-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="380e3-106">Количество и объем элементов, полученных в ходе поиска</span><span class="sxs-lookup"><span data-stu-id="380e3-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="380e3-107">Количество и объем частично индексных или неиндексных элементов, найденных в расположениях поиска</span><span class="sxs-lookup"><span data-stu-id="380e3-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="380e3-108">Количество почтовых ящиков и местоположений, в которые был отправлен поиск.</span><span class="sxs-lookup"><span data-stu-id="380e3-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="380e3-109">Чтобы просмотреть более подробную статистику, щелкните "Статистика" во flyout сведений о поиске.</span><span class="sxs-lookup"><span data-stu-id="380e3-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="380e3-110">Сводное представление</span><span class="sxs-lookup"><span data-stu-id="380e3-110">Summary view</span></span>

<span data-ttu-id="380e3-111">В представлении сводки можно увидеть результаты поиска, разбитые по типу расположения (например, Exchange).</span><span class="sxs-lookup"><span data-stu-id="380e3-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="380e3-112">Для каждого типа расположения можно увидеть:</span><span class="sxs-lookup"><span data-stu-id="380e3-112">For each location type, you can see:</span></span>

- <span data-ttu-id="380e3-113">Количество местоположений, в которых элементы соответствуют условиям поиска</span><span class="sxs-lookup"><span data-stu-id="380e3-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="380e3-114">Количество элементов из этих местоположений, которые соответствуют условиям поиска</span><span class="sxs-lookup"><span data-stu-id="380e3-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="380e3-115">Общий объем элементов, которые соответствуют условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="380e3-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="380e3-116">Представление верхних местоположений</span><span class="sxs-lookup"><span data-stu-id="380e3-116">Top locations view</span></span>

<span data-ttu-id="380e3-117">В представлении "Лучшие расположения" вы увидите отдельные расположения с наиболее совпадениями.</span><span class="sxs-lookup"><span data-stu-id="380e3-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="380e3-118">Для каждого расположения вы увидите:</span><span class="sxs-lookup"><span data-stu-id="380e3-118">For each location, you will see:</span></span>

- <span data-ttu-id="380e3-119">Имя расположения (например, URL-адрес SharePoint)</span><span class="sxs-lookup"><span data-stu-id="380e3-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="380e3-120">Тип расположения</span><span class="sxs-lookup"><span data-stu-id="380e3-120">Location type</span></span>

- <span data-ttu-id="380e3-121">Количество элементов, которые соответствуют условиям поиска</span><span class="sxs-lookup"><span data-stu-id="380e3-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="380e3-122">Общий объем элементов, которые соответствуют условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="380e3-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="380e3-123">Представление "Запросы"</span><span class="sxs-lookup"><span data-stu-id="380e3-123">Queries view</span></span>

<span data-ttu-id="380e3-124">Если в запросе использовались строки ключевых слов или ключевых слов (c:s), вы можете просмотреть разбивку запроса в представлении "Запросы" для каждого типа расположения.</span><span class="sxs-lookup"><span data-stu-id="380e3-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="380e3-125">Для каждого типа расположения вы увидите:</span><span class="sxs-lookup"><span data-stu-id="380e3-125">For each location type, you will see:</span></span>

- <span data-ttu-id="380e3-126">Часть: в этом столбце будет слово "Primary" или "Keyword".</span><span class="sxs-lookup"><span data-stu-id="380e3-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="380e3-127">"Основной" означает, что строка представляет статистику по всему запросу, тогда как "Ключевое слово" означает один из компонентов запроса.</span><span class="sxs-lookup"><span data-stu-id="380e3-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="380e3-128">Запрос: фактический компонент запроса, на который ссылается строка.</span><span class="sxs-lookup"><span data-stu-id="380e3-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="380e3-129">Если часть имеет "Primary", это будет весь запрос; Если часть была "Keyword", здесь вы увидите один из компонентов запроса.</span><span class="sxs-lookup"><span data-stu-id="380e3-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="380e3-130">При поиске во всех почтовых ящиках контента (без указания ключевых слов) фактический запрос (размер >= 0), чтобы возвращались все элементы</span><span class="sxs-lookup"><span data-stu-id="380e3-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="380e3-131">При поиске на сайтах SharePoint Online и OneDrive для бизнеса добавляются два следующих компонента:</span><span class="sxs-lookup"><span data-stu-id="380e3-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="380e3-132">NOT IsExternalContent:1 — исключает любой контент из локальной организации SharePoint</span><span class="sxs-lookup"><span data-stu-id="380e3-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="380e3-133">NOT isOneNotePage: 1 — исключает все файлы OneNote, так как они будут дублировать любой документ, соответствующий поисковому запросу.</span><span class="sxs-lookup"><span data-stu-id="380e3-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="380e3-134">Количество местоположений, в которых элементы соответствуют условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="380e3-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="380e3-135">Количество элементов из этих местоположений, которые соответствуют условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="380e3-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="380e3-136">Общий объем элементов, которые соответствуют условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="380e3-136">Total volume of items that matched the search conditions.</span></span>
