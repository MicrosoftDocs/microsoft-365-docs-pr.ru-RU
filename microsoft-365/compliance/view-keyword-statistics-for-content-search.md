---
title: Просмотр статистики результатов поиска электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Узнайте, как использовать функцию статистики поиска для отображения статистики поиска контента и поиска, связанного с делом об обнаружении основных данных в центре Microsoft 365 соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311117"
---
# <a name="view-statistics-for-ediscovery-search-results"></a><span data-ttu-id="d6229-103">Просмотр статистики результатов поиска электронных данных</span><span class="sxs-lookup"><span data-stu-id="d6229-103">View statistics for eDiscovery search results</span></span>

<span data-ttu-id="d6229-104">После создания и запуска поиска контента или поиска, связанного с делом об обнаружении основных данных, можно просмотреть статистику о предполагаемых результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="d6229-104">After you create and run a Content search or a search associated with a Core eDiscovery case, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="d6229-105">Это включает сводку результатов поиска (аналогичную сводке о предполагаемых результатах поиска, отображаемой на странице вылетов поиска), статистику запросов, например количество местоположений контента с элементами, которые соответствуют запросу поиска, и удостоверение расположения контента, которое имеет наиболее совпадающие элементы.</span><span class="sxs-lookup"><span data-stu-id="d6229-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed on the search flyout page), the query statistics such as the number of content locations with items that match the search query, and the identity of content locations that have the most matching items.</span></span>
  
<span data-ttu-id="d6229-106">Кроме того, вы можете использовать список ключевых слов для настройки поиска для возврата статистики по каждому ключевому слову в поисковом запросе.</span><span class="sxs-lookup"><span data-stu-id="d6229-106">Additionally, you can use the keywords list to configure a search to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="d6229-107">Это позволяет сравнить количество результатов, возвращаемого каждым ключевым словом в запросе.</span><span class="sxs-lookup"><span data-stu-id="d6229-107">This lets you compare the number of results returned by each keyword in a query.</span></span>
  
<span data-ttu-id="d6229-108">Вы также можете скачать статистику поиска в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="d6229-108">You can also download search statistics to a CSV file.</span></span> <span data-ttu-id="d6229-109">чтобы сравнить результаты с помощью функций фильтрации и сортировки в Excel или подготовить отчеты.</span><span class="sxs-lookup"><span data-stu-id="d6229-109">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-searches"></a><span data-ttu-id="d6229-110">Получить статистику для поиска</span><span class="sxs-lookup"><span data-stu-id="d6229-110">Get statistics for searches</span></span>

<span data-ttu-id="d6229-111">Отображение статистики поиска контента или поиска, связанного с делом об обнаружении основных данных.:</span><span class="sxs-lookup"><span data-stu-id="d6229-111">To display statistics for a Content search or a search associated with a Core eDiscovery case.:</span></span>
  
1. <span data-ttu-id="d6229-112">В центре Microsoft 365 нажмите кнопку **Показать все,** а затем сделайте одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="d6229-112">In the Microsoft 365 compliance center, click **Show all**, and then do one of the following:</span></span>

   - <span data-ttu-id="d6229-113">Щелкните **поиск контента** и выберите поиск, чтобы отобразить страницу вылетов.</span><span class="sxs-lookup"><span data-stu-id="d6229-113">Click **Content search** and then select a search to display the flyout page.</span></span>

     <span data-ttu-id="d6229-114">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="d6229-114">OR</span></span>

   - <span data-ttu-id="d6229-115">Щелкните **ядро электронного** поиска, выберите случай, а затем выберите поиск на вкладке Поиск, чтобы отобразить  >  страницу  вылетов.</span><span class="sxs-lookup"><span data-stu-id="d6229-115">Click **eDiscovery** > **Core**, select a case, and then select a search on the **Searches** tab to display the flyout page.</span></span>

2. <span data-ttu-id="d6229-116">На странице флажок выбранного поиска щелкните вкладку **Статистика поиска.**</span><span class="sxs-lookup"><span data-stu-id="d6229-116">On the flyout page of the selected search, click the **Search statistics** tab.</span></span>
  
   ![Вкладка Статистика поиска](../media/SearchStatistics1.png)

<span data-ttu-id="d6229-118">Вкладка **Статистика поиска** содержит следующие разделы, содержащие различные типы статистики поиска.</span><span class="sxs-lookup"><span data-stu-id="d6229-118">The **Search statistics** tab contains for following sections that contain different types of statistics about the search.</span></span>

### <a name="search-content"></a><span data-ttu-id="d6229-119">Содержимое поиска</span><span class="sxs-lookup"><span data-stu-id="d6229-119">Search content</span></span>

<span data-ttu-id="d6229-120">В этом разделе отображается графическое резюме предполагаемых элементов, возвращенных поиском.</span><span class="sxs-lookup"><span data-stu-id="d6229-120">This section displays a graphical summary of the estimated items returned by the search.</span></span> <span data-ttu-id="d6229-121">Это указывает количество элементов, которые соответствуют критериям поиска.</span><span class="sxs-lookup"><span data-stu-id="d6229-121">This indicates the number of items that match the search criteria.</span></span> <span data-ttu-id="d6229-122">Эти сведения дают представление о предполагаемом количестве элементов, возвращаемого поиском.</span><span class="sxs-lookup"><span data-stu-id="d6229-122">This information gives you an idea about the estimated number of items returned by the search.</span></span>

![Оценки поиска для поиска](../media/SearchContentReport.png)

- <span data-ttu-id="d6229-124">**Предполагаемые элементы по расположениям:** общее число предполагаемых элементов, возвращенных поиском.</span><span class="sxs-lookup"><span data-stu-id="d6229-124">**Estimated items by locations**: The total number of estimated items returned by the search.</span></span> <span data-ttu-id="d6229-125">Также отображается определенное количество элементов, расположенных в почтовых ящиках и расположенных на сайтах.</span><span class="sxs-lookup"><span data-stu-id="d6229-125">The specific number of items located in mailboxes and located in sites is also displayed.</span></span>

- <span data-ttu-id="d6229-126">**Предполагаемые расположения с хитами:** общее количество местоположений контента, содержащих элементы, возвращаемые поиском.</span><span class="sxs-lookup"><span data-stu-id="d6229-126">**Estimated locations with hits**: The total number of content locations that contain items returned by the search.</span></span> <span data-ttu-id="d6229-127">Также отображается определенное количество почтовых ящиков и расположения сайтов.</span><span class="sxs-lookup"><span data-stu-id="d6229-127">The specific number of mailbox and site locations is also displayed.</span></span>

- <span data-ttu-id="d6229-128">**Объем данных по расположению (в МБ)**: общий размер всех предполагаемых элементов, возвращаемого поиском.</span><span class="sxs-lookup"><span data-stu-id="d6229-128">**Data volume by location (in MB)**: The total size of all estimated items returned by the search.</span></span> <span data-ttu-id="d6229-129">Также отображается определенный размер элементов почтовых ящиков и элементов сайта.</span><span class="sxs-lookup"><span data-stu-id="d6229-129">The specific size of mailbox items and site items is also displayed.</span></span>

### <a name="condition-report"></a><span data-ttu-id="d6229-130">Отчет о состоянии</span><span class="sxs-lookup"><span data-stu-id="d6229-130">Condition report</span></span>

<span data-ttu-id="d6229-131">В этом разделе отображаются статистические данные о запросе поиска и количестве предполагаемых элементов, которые совпадают с различными частями поискового запроса.</span><span class="sxs-lookup"><span data-stu-id="d6229-131">This section displays statistics about the search query and the number of estimated items that matched different parts of the search query.</span></span> <span data-ttu-id="d6229-132">Эти статистические данные можно использовать для анализа количества элементов, которые соответствуют каждому компоненту поискового запроса.</span><span class="sxs-lookup"><span data-stu-id="d6229-132">You can use these statistics to analyze the number of items that match each component of search query.</span></span> <span data-ttu-id="d6229-133">Это поможет вам уточнить критерии поиска и при необходимости сузить область области.</span><span class="sxs-lookup"><span data-stu-id="d6229-133">This can help you refine the search criteria and if necessary narrow the scope of the scope.</span></span> <span data-ttu-id="d6229-134">Вы также можете скачать копию этого отчета в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="d6229-134">You can also download a copy of this report in CSV format.</span></span>

![Отчет о состоянии](../media/SearchContentReportNoKeywordList.png)

- <span data-ttu-id="d6229-136">**Тип расположения.** Тип расположения контента, к который применима статистика запросов.</span><span class="sxs-lookup"><span data-stu-id="d6229-136">**Location type**: The type of content location that the query statistics are applicable to.</span></span> <span data-ttu-id="d6229-137">Значение Exchange **указывает** расположение почтового ящика; значение **SharePoint** указывает расположение сайта.</span><span class="sxs-lookup"><span data-stu-id="d6229-137">The value of **Exchange** indicates a mailbox location; a value of **SharePoint** indicates a site location.</span></span>

- <span data-ttu-id="d6229-138">**Часть.** Часть поискового запроса, к которая применима статистика.</span><span class="sxs-lookup"><span data-stu-id="d6229-138">**Part**: The part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="d6229-139">**Основной** указывает на весь поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="d6229-139">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="d6229-140">**Ключевое** слово указывает, что статистика в строке для определенного ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="d6229-140">**Keyword** indicates the statistics in the row are for a specific keyword.</span></span> <span data-ttu-id="d6229-141">Если для поиска используется список ключевых слов, в эту таблицу включены статистические данные по каждому компоненту запроса.</span><span class="sxs-lookup"><span data-stu-id="d6229-141">If you use a keyword list for search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="d6229-142">Дополнительные сведения см. в [статье Получить статистику ключевых слов для поиска.](#get-keyword-statistics-for-searches)</span><span class="sxs-lookup"><span data-stu-id="d6229-142">For more information, see [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span></span>

- <span data-ttu-id="d6229-143">**Условие.** Фактический компонент (ключевое слово или условие) поискового запроса, возвращающий статистику, отображаемую в соответствующей строке.</span><span class="sxs-lookup"><span data-stu-id="d6229-143">**Condition**: The actual component (keyword or condition) of the search query that returned the statistics displayed in the corresponding row.</span></span>

- <span data-ttu-id="d6229-144">**Расположения с хитами:** количество расположений контента (заданных столбцом типа Location), содержащих элементы, которые соответствуют основному или ключевому запросу, указанному в столбце **Condition.** </span><span class="sxs-lookup"><span data-stu-id="d6229-144">**Locations with hits**: The number of the content locations (specified by the **Location type** column) that contain items that match the primary or keyword query listed in the **Condition** column.</span></span>

- <span data-ttu-id="d6229-145">**Элементы.** Количество элементов (из указанного расположения контента), которые соответствуют запросу, указанному в столбце **Condition.**</span><span class="sxs-lookup"><span data-stu-id="d6229-145">**Items**: The number of items (from the specified content location) that match the query listed in the **Condition** column.</span></span> <span data-ttu-id="d6229-146">Как было объяснено ранее, если элемент содержит несколько экземпляров ключевого слова, которое находится в поиске, он учитывается только один раз в этом столбце.</span><span class="sxs-lookup"><span data-stu-id="d6229-146">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in this column.</span></span>

- <span data-ttu-id="d6229-147">**Размер (МБ)**: общий размер всех найденных элементов (в указанном расположении контента), которые соответствуют запросу поиска в столбце **Condition.**</span><span class="sxs-lookup"><span data-stu-id="d6229-147">**Size (MB)**: The total size of all items that were found (in the specified content location) that match the search query in the **Condition** column.</span></span>

### <a name="top-locations"></a><span data-ttu-id="d6229-148">Верхние расположения</span><span class="sxs-lookup"><span data-stu-id="d6229-148">Top locations</span></span>

<span data-ttu-id="d6229-149">В этом разделе отображаются статистические данные о конкретных расположениях контента с большинством элементов, возвращенных поиском.</span><span class="sxs-lookup"><span data-stu-id="d6229-149">This section displays statistics about the specific content locations with the most items returned by the search.</span></span> <span data-ttu-id="d6229-150">Выводится первая 1000 расположений.</span><span class="sxs-lookup"><span data-stu-id="d6229-150">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="d6229-151">Вы также можете скачать копию этого отчета в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="d6229-151">You can also download a copy of this report in CSV format.</span></span>

- <span data-ttu-id="d6229-152">Имя имени расположения (адрес электронной почты почтовых ящиков и URL-адрес сайтов).</span><span class="sxs-lookup"><span data-stu-id="d6229-152">The name of the location name (the email address of mailboxes and the URL for sites).</span></span>

- <span data-ttu-id="d6229-153">Тип расположения (почтовый ящик или сайт).</span><span class="sxs-lookup"><span data-stu-id="d6229-153">Location type (a mailbox or site).</span></span>

- <span data-ttu-id="d6229-154">Предполагаемое количество элементов в расположении контента, возвращаемом поиском.</span><span class="sxs-lookup"><span data-stu-id="d6229-154">Estimated number of items in the content location returned by the search.</span></span>

- <span data-ttu-id="d6229-155">Общий размер предполагаемых элементов в каждом расположении контента.</span><span class="sxs-lookup"><span data-stu-id="d6229-155">The total size of estimated items in each content location.</span></span>

## <a name="get-keyword-statistics-for-searches"></a><span data-ttu-id="d6229-156">Получить статистику ключевых слов для поиска</span><span class="sxs-lookup"><span data-stu-id="d6229-156">Get keyword statistics for searches</span></span>

<span data-ttu-id="d6229-157">Как объяснялось ранее, в разделе **Отчет о** состоянии показан запрос поиска и число (и размер) элементов, которые соответствуют запросу.</span><span class="sxs-lookup"><span data-stu-id="d6229-157">As previous explained, the **Condition report** section shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="d6229-158">Если при создании или редактировании поискового запроса используется список ключевых слов, можно получить расширенную статистику, которая показывает, сколько элементов соответствует каждому ключевому слову или ключевому слову.</span><span class="sxs-lookup"><span data-stu-id="d6229-158">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="d6229-159">Это поможет быстро определить, какие части запроса являются наиболее (и наименее) эффективными.</span><span class="sxs-lookup"><span data-stu-id="d6229-159">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="d6229-160">Например, если ключевое слово возвращает большое количество элементов, можно уточнить запрос ключевого слова, чтобы сузить результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="d6229-160">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span>

<span data-ttu-id="d6229-161">Создание списка ключевых слов и просмотр статистики ключевых слов для поиска:</span><span class="sxs-lookup"><span data-stu-id="d6229-161">To create a keyword list and view keyword statistics for a search:</span></span>
  
1. <span data-ttu-id="d6229-162">В центре Microsoft 365 создайте новый поиск контента или поиск, связанный с делом об обнаружении основных данных.</span><span class="sxs-lookup"><span data-stu-id="d6229-162">In the Microsoft 365 compliance center, create a new Content search or a search associated with a Core eDiscovery case.</span></span>

2. <span data-ttu-id="d6229-163">На странице **Условия** мастера поиска.</span><span class="sxs-lookup"><span data-stu-id="d6229-163">On the **Conditions** page of the search wizard.</span></span> <span data-ttu-id="d6229-164">выберите **контрольный ящик списка ключевых** слов Show.</span><span class="sxs-lookup"><span data-stu-id="d6229-164">select the **Show keyword list** checkbox.</span></span>

   ![Показать поле списка ключевых слов](../media/SearchKeywordsList1.png)

3. <span data-ttu-id="d6229-166">Введите ключевое слово или этап ключевого слова в строке в таблице ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="d6229-166">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="d6229-167">Например, введите **бюджет** в первом  ряду, введите безопасность во втором ряду и введите **FY2021** в третьем ряду.</span><span class="sxs-lookup"><span data-stu-id="d6229-167">For example, type **budget** in the first row, type **security** in the second row, and type **FY2021** in the third row.</span></span>

   ![Введите до 20 ключевых слов или фраз в списке](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > <span data-ttu-id="d6229-169">Чтобы уменьшить проблемы, вызванные большими списками ключевых слов, в списке поисковых запросов не более 20 строк.</span><span class="sxs-lookup"><span data-stu-id="d6229-169">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

4. <span data-ttu-id="d6229-170">После добавления ключевых слов в список, для поиска и получения статистики, запустите поиск.</span><span class="sxs-lookup"><span data-stu-id="d6229-170">After adding the keywords to the list that you want to search and get statistics for, run the search.</span></span>

5. <span data-ttu-id="d6229-171">После завершения поиска выберите его, чтобы отобразить страницу вылетов.</span><span class="sxs-lookup"><span data-stu-id="d6229-171">When the search is completed, select it to display the flyout page.</span></span>

6. <span data-ttu-id="d6229-172">На **вкладке Статистика поиска** щелкните отчет **Condition,** чтобы отобразить статистику ключевых слов для поиска.</span><span class="sxs-lookup"><span data-stu-id="d6229-172">On the **Search statistics** tab, click the **Condition report** to display the keyword statistics for the search.</span></span>

    ![Отображаются статистические данные по каждому ключевому слову](../media/SearchKeywordsList3.png)
  
    <span data-ttu-id="d6229-174">Как показано на предыдущем скриншоте, отображаются статистические данные по каждому ключевому слову; это включает в себя:</span><span class="sxs-lookup"><span data-stu-id="d6229-174">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span>

    - <span data-ttu-id="d6229-175">Статистика ключевых слов для каждого типа расположения контента, включенного в поиск.</span><span class="sxs-lookup"><span data-stu-id="d6229-175">The keyword statistics for each type of content location included in the search.</span></span>

    - <span data-ttu-id="d6229-176">Количество элементов неиндексуальных почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="d6229-176">The number of unindexed mailbox items.</span></span>

    - <span data-ttu-id="d6229-177">Фактический запрос и результаты поиска по каждому ключевому слову (идентифицировано как **ключевое** слово в столбце **Часть),** которое включает любые условия из поискового запроса.</span><span class="sxs-lookup"><span data-stu-id="d6229-177">The actual search query and results for each keyword (identified as **Keyword** in the **Part** column), which includes any conditions from the search query.</span></span>

    - <span data-ttu-id="d6229-178">Полный поисковый запрос (определен как **Основной** в столбце **Часть)** и статистика для полного запроса для каждого типа расположения.</span><span class="sxs-lookup"><span data-stu-id="d6229-178">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query for each location type.</span></span> <span data-ttu-id="d6229-179">Обратите внимание, что это те же статистические данные, которые отображаются на **вкладке Сводка.**</span><span class="sxs-lookup"><span data-stu-id="d6229-179">Note these are the same statistics displayed on the **Summary** tab.</span></span>
