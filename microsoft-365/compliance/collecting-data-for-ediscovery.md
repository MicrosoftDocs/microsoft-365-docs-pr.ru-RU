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
ms.openlocfilehash: 4e0bc71071ecfe20a2141e72b1146e9688618faf
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633608"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="821a6-102">Сбор данных для обращения в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="821a6-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="821a6-103">Определив custodians и источники данных, представляющие интерес для вашего случая, можно определить набор документов для delve.</span><span class="sxs-lookup"><span data-stu-id="821a6-103">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="821a6-104">Вы можете использовать средство поиска в Advanced eDiscovery для идентификации этих кустодиал и расположений, не являющихся кустодиал в Office 365.</span><span class="sxs-lookup"><span data-stu-id="821a6-104">You can use the Search tool in Advanced eDiscovery to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="821a6-105">После выполнения поиска вы можете просмотреть статистику для извлеченных элементов, таких как расположения, в которых большинство элементов содержали поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="821a6-105">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="821a6-106">Кроме того, можно выполнить предварительный просмотр подмножества результатов.</span><span class="sxs-lookup"><span data-stu-id="821a6-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="821a6-107">После определения набора документов, которые вы хотите проанализировать, можно добавить результаты поиска в набор проверки для сбора и обработки.</span><span class="sxs-lookup"><span data-stu-id="821a6-107">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="821a6-108">Создание поискового запроса</span><span class="sxs-lookup"><span data-stu-id="821a6-108">Create a search</span></span>

<span data-ttu-id="821a6-109">При выборе **нового поиска** на вкладке **поиски** запустится мастер, который поможет создать поиск.</span><span class="sxs-lookup"><span data-stu-id="821a6-109">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="821a6-110">Подробную информацию о том, как создать поиск, можно узнать в статье [Создание поиска для сбора данных](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="821a6-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="821a6-111">После создания поиска отображается раскрывающаяся страница со сведениями.</span><span class="sxs-lookup"><span data-stu-id="821a6-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="821a6-112">Изначально кнопки **Статистика** и **Предварительный просмотр** изначально недоступны, так как поиск еще не завершен.</span><span class="sxs-lookup"><span data-stu-id="821a6-112">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="821a6-113">Вы можете следить за ходом выполнения поиска на вкладке **поиски** .</span><span class="sxs-lookup"><span data-stu-id="821a6-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="821a6-114">Просмотр результатов поиска и статистики</span><span class="sxs-lookup"><span data-stu-id="821a6-114">View search results and statistics</span></span>

<span data-ttu-id="821a6-115">Поиск контента состоит из двух компонентов: статистики (оценок) и предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="821a6-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="821a6-116">По мере завершения каждого из этих компонентов отображается состояние, отображаемое в соответствующих столбцах вкладки **поисковые запросы** изменяются с **отправленного** на **в состояние** **завершено**.</span><span class="sxs-lookup"><span data-stu-id="821a6-116">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="821a6-117">Когда оценка поиска будет завершена, выберите Поиск, чтобы отобразить всплывающую страницу, в которой будет отображена определенная высокоуровневая статистика о результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="821a6-117">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="821a6-118">На этом шаге кнопка **Статистика** будет активна.</span><span class="sxs-lookup"><span data-stu-id="821a6-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="821a6-119">Вы можете выбрать его для просмотра статистики поиска, например:</span><span class="sxs-lookup"><span data-stu-id="821a6-119">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="821a6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="821a6-120">Summary</span></span>
- <span data-ttu-id="821a6-121">Основные расположения</span><span class="sxs-lookup"><span data-stu-id="821a6-121">Top locations</span></span>
- <span data-ttu-id="821a6-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="821a6-122">Queries</span></span>

<span data-ttu-id="821a6-123">Дополнительные сведения о статистике поиска можно найти в статье [Статистика поиска](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="821a6-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="821a6-124">После завершения предварительного просмотра кнопка **Предварительный просмотр** будет активна.</span><span class="sxs-lookup"><span data-stu-id="821a6-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="821a6-125">Выберите его, чтобы просмотреть образец подмножества результатов.</span><span class="sxs-lookup"><span data-stu-id="821a6-125">Select it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-review-set"></a><span data-ttu-id="821a6-126">Добавление результатов поиска в набор проверки</span><span class="sxs-lookup"><span data-stu-id="821a6-126">Adding search results to a review set</span></span>

<span data-ttu-id="821a6-127">Когда вы будете готовы собирать и обрабатывать результаты поиска, вы можете сделать это, добавив его в набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="821a6-127">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="821a6-128">Дополнительные сведения см. в статье [Добавление данных в набор рецензирования](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="821a6-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>
