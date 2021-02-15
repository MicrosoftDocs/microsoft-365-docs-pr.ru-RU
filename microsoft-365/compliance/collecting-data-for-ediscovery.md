---
title: Сбор данных для дела в Advanced eDiscovery
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
description: Узнайте, как определить набор документов для проверки при анализе с помощью средства поиска в Advanced eDiscovery.
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751275"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="da0d8-103">Сбор данных для дела в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="da0d8-103">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="da0d8-104">После того как вы определили хранителей и источники данных, которые будут интересны для вашего дела, пора определить набор документов, в которые необходимо ввести сведения.</span><span class="sxs-lookup"><span data-stu-id="da0d8-104">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="da0d8-105">Средство поиска в Advanced eDiscovery можно использовать для идентификации соответствующих документов из мест, не в которые они находятся, в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="da0d8-105">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="da0d8-106">После выполнения поиска можно просмотреть статистику по полученным элементов, например расположения, в которые больше всего элементов, которые соответствуют поисковому запросу.</span><span class="sxs-lookup"><span data-stu-id="da0d8-106">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="da0d8-107">Вы также можете просмотреть подмножество результатов.</span><span class="sxs-lookup"><span data-stu-id="da0d8-107">You can also preview a subset of the results.</span></span> <span data-ttu-id="da0d8-108">После того как вы определили набор документов, которые необходимо дополнительно изучить, вы можете добавить результаты поиска в набор для сбора и обработки.</span><span class="sxs-lookup"><span data-stu-id="da0d8-108">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="da0d8-109">Создание поискового запроса</span><span class="sxs-lookup"><span data-stu-id="da0d8-109">Create a search</span></span>

<span data-ttu-id="da0d8-110">При выборе **нового поиска** на вкладке **"Поиск"** запустится мастер, который поможет вам создать поиск.</span><span class="sxs-lookup"><span data-stu-id="da0d8-110">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="da0d8-111">Подробные сведения о создании поиска см. в описании [создания поиска для сбора данных.](create-search-to-collect-data.md)</span><span class="sxs-lookup"><span data-stu-id="da0d8-111">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="da0d8-112">После создания поиска отображается страница с подробными сведениями.</span><span class="sxs-lookup"><span data-stu-id="da0d8-112">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="da0d8-113">Кнопки **"Статистика"** и **"Предварительный** просмотр" изначально недоступны, так как поиск еще не завершен.</span><span class="sxs-lookup"><span data-stu-id="da0d8-113">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="da0d8-114">Вы можете отслеживать ход поиска на вкладке **"Поиск".**</span><span class="sxs-lookup"><span data-stu-id="da0d8-114">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="da0d8-115">Просмотр результатов и статистики поиска</span><span class="sxs-lookup"><span data-stu-id="da0d8-115">View search results and statistics</span></span>

<span data-ttu-id="da0d8-116">Существует два компонента поиска контента: статистика (оценка) и предварительная версия.</span><span class="sxs-lookup"><span data-stu-id="da0d8-116">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="da0d8-117">По мере завершения каждого из этих компонентов состояние, отображаемого в  соответствующих столбцах на  вкладке "Поиск", изменится с "Отправлено" на "Выполняется" на **"Завершено".** </span><span class="sxs-lookup"><span data-stu-id="da0d8-117">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="da0d8-118">После завершения оценки поиска выберите поиск, на котором будет отображаться эта страница, на которой будут отображаться высокоуровневые статистические данные о результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="da0d8-118">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="da0d8-119">На этом этапе **кнопка "Статистика"** будет активной.</span><span class="sxs-lookup"><span data-stu-id="da0d8-119">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="da0d8-120">Вы можете выбрать его, чтобы увидеть статистику поиска, например:</span><span class="sxs-lookup"><span data-stu-id="da0d8-120">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="da0d8-121">Аннотация</span><span class="sxs-lookup"><span data-stu-id="da0d8-121">Summary</span></span>
- <span data-ttu-id="da0d8-122">Лучшие расположения</span><span class="sxs-lookup"><span data-stu-id="da0d8-122">Top locations</span></span>
- <span data-ttu-id="da0d8-123">Запросы</span><span class="sxs-lookup"><span data-stu-id="da0d8-123">Queries</span></span>

<span data-ttu-id="da0d8-124">Дополнительные сведения о статистике поиска см. в [статистике поиска.](search-statistics-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="da0d8-124">For more information about search statistics, see [Search statistics](search-statistics-in-advanced-ediscovery.md).</span></span>

<span data-ttu-id="da0d8-125">После завершения предварительного просмотра **кнопка "Предварительный** просмотр" станет активной.</span><span class="sxs-lookup"><span data-stu-id="da0d8-125">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="da0d8-126">Выберите его для предварительного просмотра выборки подмножество результатов.</span><span class="sxs-lookup"><span data-stu-id="da0d8-126">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="da0d8-127">Добавление результатов поиска в набор для проверки</span><span class="sxs-lookup"><span data-stu-id="da0d8-127">Add search results to a review set</span></span>

<span data-ttu-id="da0d8-128">Когда вы будете готовы собрать и обработать все результаты поиска, вы можете сделать это, добавив его в набор для проверки.</span><span class="sxs-lookup"><span data-stu-id="da0d8-128">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="da0d8-129">Дополнительные сведения [см. в подстройки "Добавление данных в набор для проверки".](add-data-to-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="da0d8-129">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="da0d8-130">Добавление данных, не в microsoft 365, в набор для проверки</span><span class="sxs-lookup"><span data-stu-id="da0d8-130">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="da0d8-131">В рамках процесса сбора для дела вы также можете добавить данные, не относящемся к Office 365, в набор для проверки, а также просмотреть и проанализировать вместе с данными Office 365, собранными с помощью средства поиска.</span><span class="sxs-lookup"><span data-stu-id="da0d8-131">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="da0d8-132">При добавлении office 365, не относя к Office 365, необходимо связать его с определенным хранителями в этом случае.</span><span class="sxs-lookup"><span data-stu-id="da0d8-132">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="da0d8-133">Дополнительные сведения см. в подстройки "Загрузка данных, не относяхся к [Microsoft 365".](load-non-Office-365-data-into-a-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="da0d8-133">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
