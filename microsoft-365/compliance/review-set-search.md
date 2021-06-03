---
title: Запрос контента в наборе обзоров
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как создать и запустить запрос в наборе обзоров для организации контента для более эффективного рассмотрения в Advanced eDiscovery случае.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736459"
---
# <a name="query-and-filter-content-in-a-review-set"></a><span data-ttu-id="0c029-103">Запрос и фильтрация контента в наборе обзоров</span><span class="sxs-lookup"><span data-stu-id="0c029-103">Query and filter content in a review set</span></span>

<span data-ttu-id="0c029-104">В большинстве случаев будет полезно углубиться в содержимое в наборе обзоров и организовать его, чтобы облегчить более эффективный обзор.</span><span class="sxs-lookup"><span data-stu-id="0c029-104">In most cases, it will be useful to dig deeper into the content in a review set and organize it to facilitate a more efficient review.</span></span> <span data-ttu-id="0c029-105">Использование фильтров и запросов в наборе обзоров позволяет сосредоточиться на подмножество документов, которые соответствуют критериям проверки.</span><span class="sxs-lookup"><span data-stu-id="0c029-105">Using filters and queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="default-filters"></a><span data-ttu-id="0c029-106">Фильтры по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0c029-106">Default filters</span></span>

<span data-ttu-id="0c029-107">В наборе обзоров есть пять фильтров по умолчанию, предварительно загруженных в наборе обзоров:</span><span class="sxs-lookup"><span data-stu-id="0c029-107">In a review set, there are five default filters that are pre-loaded in the review set:</span></span>

- <span data-ttu-id="0c029-108">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="0c029-108">Keywords</span></span>
- <span data-ttu-id="0c029-109">Дата</span><span class="sxs-lookup"><span data-stu-id="0c029-109">Date</span></span>
- <span data-ttu-id="0c029-110">Отправитель/автор</span><span class="sxs-lookup"><span data-stu-id="0c029-110">Sender/Author</span></span>
- <span data-ttu-id="0c029-111">Subject/Title</span><span class="sxs-lookup"><span data-stu-id="0c029-111">Subject/Title</span></span>
- <span data-ttu-id="0c029-112">Теги</span><span class="sxs-lookup"><span data-stu-id="0c029-112">Tags</span></span>

![Типы фильтров по умолчанию](../media/DefaultFilterTypes.png)

<span data-ttu-id="0c029-114">Щелкните каждый фильтр, чтобы расширить его и назначить значение.</span><span class="sxs-lookup"><span data-stu-id="0c029-114">Click each filter to expand it and assign a value.</span></span> <span data-ttu-id="0c029-115">Щелкните вне фильтра, чтобы автоматически применить фильтр к набору отзывов.</span><span class="sxs-lookup"><span data-stu-id="0c029-115">Click outside the filter to automatically apply the filter to the review set.</span></span> <span data-ttu-id="0c029-116">На следующем скриншоте показан фильтр Date, настроенный для показа документов в диапазоне дат.</span><span class="sxs-lookup"><span data-stu-id="0c029-116">The following screenshot shows the Date filter configured to show documents within a date range.</span></span>

![Расширенный фильтр по умолчанию](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a><span data-ttu-id="0c029-118">Добавление или удаление фильтров</span><span class="sxs-lookup"><span data-stu-id="0c029-118">Add or remove filters</span></span>

<span data-ttu-id="0c029-119">Чтобы добавить или удалить фильтры, отображаемые для набора отзывов, выберите **Фильтры** для открытия панели фильтров, которая отображается на странице вылетов.</span><span class="sxs-lookup"><span data-stu-id="0c029-119">To add or remove filters that are displayed for the review set, select **Filters** to open the filter panel, which is displayed on a flyout page.</span></span> 

![Панель фильтров](../media/FilterPanel.png)

<span data-ttu-id="0c029-121">Доступные фильтры организованы в четырех разделах:</span><span class="sxs-lookup"><span data-stu-id="0c029-121">The available filters are organized in four sections:</span></span>

- <span data-ttu-id="0c029-122">**Поиск.** Фильтры, которые предоставляют различные возможности поиска.</span><span class="sxs-lookup"><span data-stu-id="0c029-122">**Search**: Filters that provide different search capabilities.</span></span>

- <span data-ttu-id="0c029-123">**Аналитика &** программирования: фильтры свойств, созданных и добавленных в документы  при запуске & задания аналитики электронной почты или использования моделей прогностического кодирования.</span><span class="sxs-lookup"><span data-stu-id="0c029-123">**Analytics & predictive coding**: Filters for properties generated and added to documents when you run the **Document & email analytic** job or use predictive coding models.</span></span>

- <span data-ttu-id="0c029-124">**ID:** Фильтры для всех свойств документов.</span><span class="sxs-lookup"><span data-stu-id="0c029-124">**IDs**: Filters for all ID properties of documents.</span></span>

- <span data-ttu-id="0c029-125">**Свойства элемента:** фильтры для свойств документов.</span><span class="sxs-lookup"><span data-stu-id="0c029-125">**Item properties**: Filters for document properties.</span></span> 

<span data-ttu-id="0c029-126">Расширите каждый раздел и выберите или отфильтруйте фильтры, чтобы добавить или удалить их в наборе фильтров.</span><span class="sxs-lookup"><span data-stu-id="0c029-126">Expand each section and select or deselect filters to add or remove them in the filter set.</span></span> <span data-ttu-id="0c029-127">При добавлении фильтра он отображается в наборе фильтров.</span><span class="sxs-lookup"><span data-stu-id="0c029-127">When you add a filter, it's displayed in the filter set.</span></span> 

![Список разделов и свойств фильтра в панели фильтров](../media/FilterPanel2.png)

> [!NOTE]
> <span data-ttu-id="0c029-129">При расширении раздела на панели фильтров вы заметите, что выбраны типы фильтров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0c029-129">When you expand a section in the filter panel, you'll notice that the default filter types are selected.</span></span> <span data-ttu-id="0c029-130">Вы можете сохранить выбранные или отобрать их и удалить из набора фильтров.</span><span class="sxs-lookup"><span data-stu-id="0c029-130">You can keep these selected or deselect them and removed them from the filter set.</span></span> 

## <a name="filter-types"></a><span data-ttu-id="0c029-131">Типы фильтров</span><span class="sxs-lookup"><span data-stu-id="0c029-131">Filter types</span></span>

<span data-ttu-id="0c029-132">Каждое поле для поиска в наборе обзоров имеет соответствующий фильтр, который можно использовать для элементов фильтрации на основе определенного поля.</span><span class="sxs-lookup"><span data-stu-id="0c029-132">Every searchable field in a review set has a corresponding filter that you can use for filter items based on a specific field.</span></span>

<span data-ttu-id="0c029-133">Существует несколько типов фильтров:</span><span class="sxs-lookup"><span data-stu-id="0c029-133">There are multiple types of filters:</span></span>

- <span data-ttu-id="0c029-134">**Freetext:** фильтр freetext применяется к текстовым полям, таким как "Subject".</span><span class="sxs-lookup"><span data-stu-id="0c029-134">**Freetext**: A freetext filter is applied to text fields such as "Subject".</span></span> <span data-ttu-id="0c029-135">Можно перечислить несколько терминов поиска, разделив их с запятой.</span><span class="sxs-lookup"><span data-stu-id="0c029-135">You can list multiple search terms by separating them with a comma.</span></span>

- <span data-ttu-id="0c029-136">**Дата.** Фильтр даты используется для полей дат, таких как "Последняя измененная дата".</span><span class="sxs-lookup"><span data-stu-id="0c029-136">**Date**: A date filter is used for date fields such as "Last modified date".</span></span>

- <span data-ttu-id="0c029-137">**Параметры** поиска. Фильтр параметров поиска предоставляет список возможных значений (каждое значение отображается с помощью выбранного вами почтового ящика) для определенных полей в обзоре.</span><span class="sxs-lookup"><span data-stu-id="0c029-137">**Search options**: A search options filter provides a list of possible values (each value is displayed with a checkbox that you can select) for particular fields in the review.</span></span> <span data-ttu-id="0c029-138">Этот фильтр используется для полей, таких как "Отправитель", где в наборе отзывов имеется конечное число возможных значений.</span><span class="sxs-lookup"><span data-stu-id="0c029-138">This filter is used for fields, such as "Sender", where there is a finite number of possible values in the review set.</span></span>

- <span data-ttu-id="0c029-139">**Ключевое** слово. Условие ключевого слова — это определенный экземпляр условия freetext, который можно использовать для поиска терминов.</span><span class="sxs-lookup"><span data-stu-id="0c029-139">**Keyword**: A keyword condition is a specific instance of freetext condition that you can use to search for terms.</span></span> <span data-ttu-id="0c029-140">В этом типе фильтра можно также использовать язык запросов, похожий на KQL.</span><span class="sxs-lookup"><span data-stu-id="0c029-140">You can also use KQL-like query language in this type of filter.</span></span> <span data-ttu-id="0c029-141">Дополнительные сведения см. в разделах Язык запроса и Расширенный строитель запросов в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0c029-141">For more information, see the Query language and Advanced query builder sections in this topic.</span></span>

## <a name="include-and-exclude-filter-relationships"></a><span data-ttu-id="0c029-142">Включить и исключить отношения фильтра</span><span class="sxs-lookup"><span data-stu-id="0c029-142">Include and exclude filter relationships</span></span>

<span data-ttu-id="0c029-143">У вас есть возможность изменить включить и исключить связь для определенного фильтра.</span><span class="sxs-lookup"><span data-stu-id="0c029-143">You have the option to change the include and exclude relationship for a particular filter.</span></span> <span data-ttu-id="0c029-144">Например, в фильтре тегов можно исключить элементы, помеченные определенным тегом, выбрав **Equals none of** in the dropdown filter.</span><span class="sxs-lookup"><span data-stu-id="0c029-144">For example, in the Tag filter, you can exclude items that are tagged with a particular tag by selecting **Equals none of** in the dropdown filter.</span></span> 

![Исключение фильтра тегов](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a><span data-ttu-id="0c029-146">Сохранение фильтров в качестве запросов</span><span class="sxs-lookup"><span data-stu-id="0c029-146">Save filters as queries</span></span>

<span data-ttu-id="0c029-147">После выполнения фильтров можно сохранить комбинацию фильтров в качестве запроса фильтра.</span><span class="sxs-lookup"><span data-stu-id="0c029-147">After you are satisfied with your filters, you can save the filter combination as a filter query.</span></span> <span data-ttu-id="0c029-148">Это позволяет применять фильтр в будущих сеансах проверки.</span><span class="sxs-lookup"><span data-stu-id="0c029-148">This lets you apply the filter in the future review sessions.</span></span>

<span data-ttu-id="0c029-149">Чтобы сохранить фильтр, **выберите Сохранить запрос и** назовите его.</span><span class="sxs-lookup"><span data-stu-id="0c029-149">To save a filter, select **Save the query** and name it.</span></span> <span data-ttu-id="0c029-150">Вы или другие рецензенты могут запускать ранее  сохраненные запросы фильтра, выбрав отсев сохраненных запросов фильтра и выбрав запрос фильтра, который будет применяться для проверки установленных документов.</span><span class="sxs-lookup"><span data-stu-id="0c029-150">You or other reviewers can run previously saved filter queries by selecting the **Saved filter queries** dropdown and selecting a filter query to apply to review set documents.</span></span> 

![Сохранение запроса фильтра](../media/SaveFilterQuery.png)

<span data-ttu-id="0c029-152">Чтобы удалить запрос фильтра, откройте панель фильтров и выберите значок корзины рядом с запросом.</span><span class="sxs-lookup"><span data-stu-id="0c029-152">To delete a filter query, open the filter panel and select the trashcan icon next to the query.</span></span>

![Удаление запроса фильтра](../media/DeleteFilterQuery.png)

## <a name="query-language"></a><span data-ttu-id="0c029-154">Язык запросов</span><span class="sxs-lookup"><span data-stu-id="0c029-154">Query language</span></span>

<span data-ttu-id="0c029-155">В дополнение к использованию фильтров можно также использовать язык запросов, похожий на KQL, в фильтре "Ключевые слова", чтобы создать поисковый запрос набора отзывов.</span><span class="sxs-lookup"><span data-stu-id="0c029-155">In addition to using filters, you can also use a KQL-like query language in the Keywords filter to build your review set search query.</span></span> <span data-ttu-id="0c029-156">Язык запросов для запросов набора отзывов поддерживает стандартные операторы boolean, такие как **AND,** **OR,** **NOT** и **NEAR.**</span><span class="sxs-lookup"><span data-stu-id="0c029-156">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="0c029-157">Он также поддерживает под диктовую карточку с одним и несколькими символами (\*).</span><span class="sxs-lookup"><span data-stu-id="0c029-157">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="advanced-query-builder"></a><span data-ttu-id="0c029-158">Расширенный строитель запросов</span><span class="sxs-lookup"><span data-stu-id="0c029-158">Advanced query builder</span></span>

<span data-ttu-id="0c029-159">Кроме того, можно создавать дополнительные запросы для поиска документов в наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="0c029-159">You can also build more advanced queries to search for documents in a review set.</span></span>

1. <span data-ttu-id="0c029-160">Откройте панель фильтров, **выберите Фильтры** и расширь раздел **Поиск.**</span><span class="sxs-lookup"><span data-stu-id="0c029-160">Open the filter panel, select **Filters**, and expand the **Search** section.</span></span>

  ![Добавление фильтра KQL](../media/AddKQLFilter.png)

2. <span data-ttu-id="0c029-162">Выберите фильтр **KQL** и нажмите кнопку **Открыть строитель запросов.**</span><span class="sxs-lookup"><span data-stu-id="0c029-162">Select the **KQL** filter and click **Open query builder**.</span></span>

   <span data-ttu-id="0c029-163">На этой панели можно создавать сложные запросы KQL с помощью конструктора запросов.</span><span class="sxs-lookup"><span data-stu-id="0c029-163">In this panel, you can create complex KQL queries by using the query builder.</span></span> <span data-ttu-id="0c029-164">Можно добавить условия или добавить группы условий, которые состоит из нескольких условий, логически связанных **отношениями AND** или **OR.**</span><span class="sxs-lookup"><span data-stu-id="0c029-164">You can add conditions or add condition groups that are made up of multiple conditions that are logically connected by **AND** or **OR** relationships.</span></span>

   ![Использование конструктора запросов для настройки сложных запросов фильтра](../media/ComplexQuery.png)
