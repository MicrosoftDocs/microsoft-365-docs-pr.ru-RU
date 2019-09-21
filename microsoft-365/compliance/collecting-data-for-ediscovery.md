---
title: Сбор данных для обращения в Advanced eDiscovery
ms.author: esclee
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
ms.openlocfilehash: 091d6f8835ae1aae2f075f0b510954255c3a6a5c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089840"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="e212f-102">Сбор данных для обращения в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e212f-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="e212f-103">Определив custodians и источники данных, представляющие интерес для вашего случая, можно определить набор документов для delve.</span><span class="sxs-lookup"><span data-stu-id="e212f-103">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="e212f-104">Вы можете использовать средство поиска в Advanced eDiscovery для идентификации этих кустодиал и расположений, не являющихся кустодиал в Office 365.</span><span class="sxs-lookup"><span data-stu-id="e212f-104">You can use the Search tool in Advanced eDiscovery to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="e212f-105">После выполнения поиска вы сможете просматривать статистику извлеченных элементов, таких как расположения, в которых большинство элементов содержали поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="e212f-105">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="e212f-106">Кроме того, можно выполнить предварительный просмотр подмножества результатов.</span><span class="sxs-lookup"><span data-stu-id="e212f-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="e212f-107">После определения набора документов, которые необходимо проанализировать, можно добавить результаты поиска в набор проверки для сбора и обработки.</span><span class="sxs-lookup"><span data-stu-id="e212f-107">When you've identified the set of documents that want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="e212f-108">Create a search</span><span class="sxs-lookup"><span data-stu-id="e212f-108">Create a search</span></span>

<span data-ttu-id="e212f-109">При нажатии кнопки **Новый поиск** на вкладке **поиски** запустится мастер, который поможет создать поиск.</span><span class="sxs-lookup"><span data-stu-id="e212f-109">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="e212f-110">Подробную информацию о том, как создать поиск, можно узнать в статье [Создание поиска для сбора данных](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="e212f-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="e212f-111">После создания поиска отображается раскрывающаяся страница со сведениями.</span><span class="sxs-lookup"><span data-stu-id="e212f-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="e212f-112">Обратите внимание, что кнопки **Статистика** и **Предварительный просмотр** изначально отображаются серым цветом, так как поиск еще не завершен.</span><span class="sxs-lookup"><span data-stu-id="e212f-112">Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet.</span></span> <span data-ttu-id="e212f-113">Вы можете следить за ходом выполнения поиска на вкладке **поиски** .</span><span class="sxs-lookup"><span data-stu-id="e212f-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="e212f-114">Просмотр результатов поиска и статистики</span><span class="sxs-lookup"><span data-stu-id="e212f-114">View search results and statistics</span></span>

<span data-ttu-id="e212f-115">Поиск контента состоит из двух компонентов: статистики (оценок) и предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="e212f-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="e212f-116">По мере завершения каждого из этих компонентов отображается состояние, отображаемое в соответствующих столбцах вкладки **поисковые запросы** изменяются с **отправленного** на **в состояние** **завершено**.</span><span class="sxs-lookup"><span data-stu-id="e212f-116">As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="e212f-117">После завершения оценки нажмите кнопку поиска, чтобы отобразить раскрывающуюся страницу, в которой будет отображена определенная высокоуровневая статистика о результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="e212f-117">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="e212f-118">На этом шаге кнопка **Статистика** будет активна.</span><span class="sxs-lookup"><span data-stu-id="e212f-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="e212f-119">Вы можете щелкнуть его, чтобы просмотреть статистику поиска, например:</span><span class="sxs-lookup"><span data-stu-id="e212f-119">You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="e212f-120">Сводка</span><span class="sxs-lookup"><span data-stu-id="e212f-120">Summary</span></span>
- <span data-ttu-id="e212f-121">Основные расположения</span><span class="sxs-lookup"><span data-stu-id="e212f-121">Top locations</span></span>
- <span data-ttu-id="e212f-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="e212f-122">Queries</span></span>

<span data-ttu-id="e212f-123">Дополнительные сведения о статистике поиска можно найти в статье [Статистика поиска](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="e212f-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="e212f-124">После завершения предварительного просмотра кнопка **Предварительный просмотр** будет активна.</span><span class="sxs-lookup"><span data-stu-id="e212f-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="e212f-125">Щелкните его, чтобы просмотреть образец подмножества результатов.</span><span class="sxs-lookup"><span data-stu-id="e212f-125">Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-review-set"></a><span data-ttu-id="e212f-126">Добавление результатов поиска в набор проверки</span><span class="sxs-lookup"><span data-stu-id="e212f-126">Adding search results to a review set</span></span>

<span data-ttu-id="e212f-127">Когда вы будете готовы собирать и обрабатывать результаты поиска, вы можете сделать это, добавив его в набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="e212f-127">When you are ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="e212f-128">Дополнительные сведения см. в статье [Добавление данных в набор рецензирования](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="e212f-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span> 