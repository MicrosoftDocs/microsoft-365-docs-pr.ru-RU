---
title: Добавление результатов поиска в набор для проверки
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
ms.openlocfilehash: 03328cfeada2e6bc493bfff0ee64f95904b8c9f8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089982"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="aeee1-102">Добавление результатов поиска в набор для проверки</span><span class="sxs-lookup"><span data-stu-id="aeee1-102">Add search results to a review set</span></span>

<span data-ttu-id="aeee1-103">При удовлетворении результатов поиска и готовности к просмотру и анализу этих результатов поиска их можно добавить в набор проверки в случае.</span><span class="sxs-lookup"><span data-stu-id="aeee1-103">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="aeee1-104">Копирование исходных данных в набор рецензирования также упрощает процесс анализа и анализа, предоставляя расширенные средства анализа, такие как обнаружение тем, обнаружение близких копий и идентификация цепочки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="aeee1-104">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="aeee1-105">Вы также можете добавлять данные из источников данных, отличных от Office 365, в набор проверки, чтобы вы могли просматривать эти данные в дополнение к данным, собранным из Office 365.</span><span class="sxs-lookup"><span data-stu-id="aeee1-105">You can also add data from non-Office 365 data sources to a review set so that you can review that data in addition to the data you collect from Office 365.</span></span> 

<span data-ttu-id="aeee1-106">При добавлении результатов поиска в набор рецензирования (наборы рецензирования находятся на вкладке " **наборы проверки** "), выполняются следующие действия:</span><span class="sxs-lookup"><span data-stu-id="aeee1-106">When you add the results of a search to a review set (review sets are on the **Review sets** tab of the case), the following things occur:</span></span>

- <span data-ttu-id="aeee1-107">Поиск выполняется повторно.</span><span class="sxs-lookup"><span data-stu-id="aeee1-107">The search is run again.</span></span> <span data-ttu-id="aeee1-108">Это означает, что фактические результаты поиска, скопированные в набор проверки, могут отличаться от предполагаемых результатов, возвращенных при последнем запуске поиска.</span><span class="sxs-lookup"><span data-stu-id="aeee1-108">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="aeee1-109">Все элементы в результатах поиска копируются из исходного источника данных в службы Live Office 365 и копируются в безопасное место хранения Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="aeee1-109">All items in the search results are copied from the original data source in the live Office 365 services, and copied to a secure Azure storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="aeee1-110">Все элементы (включая содержимое и метаданные) переиндексируются таким образом, чтобы все данные в наборе проверки были полностью доступны для поиска во время проверки данных регистра.</span><span class="sxs-lookup"><span data-stu-id="aeee1-110">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="aeee1-111">Повторное индексирование результатов данных выполняется при поиске в наборе проверки в ходе анализа.</span><span class="sxs-lookup"><span data-stu-id="aeee1-111">Re-indexing the data results in thorough and very fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="aeee1-112">Чтобы добавить данные в набор рецензирования, щелкните Поиск на вкладке **поиски** , а затем щелкните **Добавить результаты для проверки набора** на всплывающей странице.</span><span class="sxs-lookup"><span data-stu-id="aeee1-112">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

![Добавление данных в набор проверки](media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="aeee1-114">Вы можете добавить существующий набор рецензирования или создать новый.</span><span class="sxs-lookup"><span data-stu-id="aeee1-114">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="aeee1-115">При добавлении в новый набор проверки укажите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="aeee1-115">If adding to a new review set, specify the name and then click **Add**.</span></span>

![Выбор набора проверок](media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="aeee1-117">Добавление данных в набор проверки — длительный процесс.</span><span class="sxs-lookup"><span data-stu-id="aeee1-117">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="aeee1-118">Этот процесс включает сбор элементов из исходных источников данных в Office 365 (например, из почтовых ящиков и сайтов), копируя их в место хранения Azure (этот процесс копирования *также называется*приемом), а затем повторной индексации элементов.</span><span class="sxs-lookup"><span data-stu-id="aeee1-118">This process includes gathering items from the original data sources in Office 365 (for example, from mailboxes and sites), copying them to the Azure storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="aeee1-119">Отслеживать ход выполнения можно на вкладке " **задания** " или на вкладке " **поиски** ", отслеживая состояние **добавленных данных в столбце "просмотреть набор** ".</span><span class="sxs-lookup"><span data-stu-id="aeee1-119">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="aeee1-120">После завершения обработки набора проверки откройте вкладку **Рецензирование** и щелкните набор проверки, чтобы начать процесс фильтрации, проверки, маркировки и экспорта данных в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="aeee1-120">After the review set processing is completed, click the **Review sets** tab in the case, and click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="aeee1-121">Добавление примера в набор проверки</span><span class="sxs-lookup"><span data-stu-id="aeee1-121">Add a sample to a review set</span></span>

<span data-ttu-id="aeee1-122">Если требуется более тщательный поиск результатов поиска перед добавлением их в набор рецензирования, можно добавить образец результатов поиска в набор проверки, а не добавлять все.</span><span class="sxs-lookup"><span data-stu-id="aeee1-122">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="aeee1-123">Чтобы добавить пример в набор рецензирования, щелкните Поиск на вкладке **поиски** и выберите пункт **Пример** на всплывающей странице.</span><span class="sxs-lookup"><span data-stu-id="aeee1-123">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="aeee1-124">На странице " **Параметры выборки** " выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="aeee1-124">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="aeee1-125">**Уровень вероятности%** и **доверительный интервал%** — элементы, добавляемые в набор проверки, будут определяться заданными статистическими параметрами.</span><span class="sxs-lookup"><span data-stu-id="aeee1-125">**Confidence level %** and **Confidence interval %** – The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="aeee1-126">Если обычно используется уровень вероятности и интервал при выборке результатов, укажите их в раскрывающихся списках.</span><span class="sxs-lookup"><span data-stu-id="aeee1-126">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="aeee1-127">В противном случае используйте параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aeee1-127">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="aeee1-128">**Случайная выборка%** — элементы, добавляемые в набор проверки, основываются на случайном выборе указанного процента от общего числа элементов, возвращенных при поиске.</span><span class="sxs-lookup"><span data-stu-id="aeee1-128">**Random sample %** – The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="aeee1-129">Выбрав и настроив один из предыдущих вариантов, выберите набор проверки, чтобы добавить пример, а затем нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="aeee1-129">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="aeee1-130">Кроме того, вы можете отслеживать ход выполнения на вкладке **задания** или **поиска** , отслеживая состояние в **добавленных данных в столбце "просмотреть набор** ".</span><span class="sxs-lookup"><span data-stu-id="aeee1-130">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>