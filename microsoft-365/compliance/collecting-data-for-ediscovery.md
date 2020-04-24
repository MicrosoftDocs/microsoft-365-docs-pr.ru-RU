---
title: Сбор данных для обращения в Advanced eDiscovery
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 462c58f8531265026b34fe3d8484736aefa4c5fa
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "43799942"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="ea851-102">Сбор данных для обращения в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ea851-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="ea851-103">Определив custodians и источники данных, представляющие интерес для вашего случая, можно определить набор документов для delve.</span><span class="sxs-lookup"><span data-stu-id="ea851-103">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="ea851-104">Вы можете использовать средство поиска в Advanced eDiscovery для определения релевантных документов из кустодиал и расположений, отличных от кустодиал, в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea851-104">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="ea851-105">После выполнения поиска вы можете просмотреть статистику для извлеченных элементов, таких как расположения, в которых большинство элементов содержали поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="ea851-105">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="ea851-106">Кроме того, можно выполнить предварительный просмотр подмножества результатов.</span><span class="sxs-lookup"><span data-stu-id="ea851-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="ea851-107">После определения набора документов, которые вы хотите проанализировать, можно добавить результаты поиска в набор проверки для сбора и обработки.</span><span class="sxs-lookup"><span data-stu-id="ea851-107">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="ea851-108">Создание поискового запроса</span><span class="sxs-lookup"><span data-stu-id="ea851-108">Create a search</span></span>

<span data-ttu-id="ea851-109">При выборе **нового поиска** на вкладке **поиски** запустится мастер, который поможет создать поиск.</span><span class="sxs-lookup"><span data-stu-id="ea851-109">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="ea851-110">Подробную информацию о том, как создать поиск, можно узнать в статье [Создание поиска для сбора данных](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="ea851-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="ea851-111">После создания поиска отображается раскрывающаяся страница со сведениями.</span><span class="sxs-lookup"><span data-stu-id="ea851-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="ea851-112">Изначально кнопки **Статистика** и **Предварительный просмотр** изначально недоступны, так как поиск еще не завершен.</span><span class="sxs-lookup"><span data-stu-id="ea851-112">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="ea851-113">Вы можете следить за ходом выполнения поиска на вкладке **поиски** .</span><span class="sxs-lookup"><span data-stu-id="ea851-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="ea851-114">Просмотр результатов поиска и статистики</span><span class="sxs-lookup"><span data-stu-id="ea851-114">View search results and statistics</span></span>

<span data-ttu-id="ea851-115">Поиск контента состоит из двух компонентов: статистики (оценок) и предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="ea851-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="ea851-116">По мере завершения каждого из этих компонентов отображается состояние, отображаемое в соответствующих столбцах вкладки **поисковые запросы** изменяются с **отправленного** на **в состояние** **завершено**.</span><span class="sxs-lookup"><span data-stu-id="ea851-116">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="ea851-117">Когда оценка поиска будет завершена, выберите Поиск, чтобы отобразить всплывающую страницу, в которой будет отображена определенная высокоуровневая статистика о результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="ea851-117">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="ea851-118">На этом шаге кнопка **Статистика** будет активна.</span><span class="sxs-lookup"><span data-stu-id="ea851-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="ea851-119">Вы можете выбрать его для просмотра статистики поиска, например:</span><span class="sxs-lookup"><span data-stu-id="ea851-119">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="ea851-120">Сводка</span><span class="sxs-lookup"><span data-stu-id="ea851-120">Summary</span></span>
- <span data-ttu-id="ea851-121">Основные расположения</span><span class="sxs-lookup"><span data-stu-id="ea851-121">Top locations</span></span>
- <span data-ttu-id="ea851-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="ea851-122">Queries</span></span>

<span data-ttu-id="ea851-123">Дополнительные сведения о статистике поиска можно найти в статье [Статистика поиска](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="ea851-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="ea851-124">После завершения предварительного просмотра кнопка **Предварительный просмотр** будет активна.</span><span class="sxs-lookup"><span data-stu-id="ea851-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="ea851-125">Выберите его, чтобы просмотреть образец подмножества результатов.</span><span class="sxs-lookup"><span data-stu-id="ea851-125">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="ea851-126">Добавление результатов поиска в набор для проверки</span><span class="sxs-lookup"><span data-stu-id="ea851-126">Add search results to a review set</span></span>

<span data-ttu-id="ea851-127">Когда вы будете готовы собирать и обрабатывать результаты поиска, вы можете сделать это, добавив его в набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="ea851-127">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="ea851-128">Дополнительные сведения см. в статье [Добавление данных в набор рецензирования](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="ea851-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="ea851-129">Добавление данных, отличных от Microsoft 365, в набор проверки</span><span class="sxs-lookup"><span data-stu-id="ea851-129">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="ea851-130">В рамках процесса сбора данных можно также добавить данные 365, не относящиеся к Office, в набор проверки и просмотреть и проанализировать вместе с данными Office 365, собранными с помощью средства поиска.</span><span class="sxs-lookup"><span data-stu-id="ea851-130">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="ea851-131">При добавлении приложения, отличного от Office 365, необходимо связать его с определенным хранитель в случае.</span><span class="sxs-lookup"><span data-stu-id="ea851-131">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="ea851-132">Дополнительные сведения см. [в статье Загрузка данных, отличных от Microsoft 365, в набор рецензирования](load-non-Office-365-data-into-a-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="ea851-132">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
