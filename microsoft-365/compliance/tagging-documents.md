---
title: Добавление тегов к документам в наборе для проверки
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
description: Пометка документов в наборе обзоров помогает удалить ненужный контент и определить релевантный контент в Advanced eDiscovery случае.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736270"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="5f19a-103">Тег документов в наборе обзоров в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5f19a-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="5f19a-104">Организация контента в наборе обзоров имеет важное значение для завершения различных процессов в процессе электронного разбора.</span><span class="sxs-lookup"><span data-stu-id="5f19a-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="5f19a-105">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="5f19a-105">This includes:</span></span>

- <span data-ttu-id="5f19a-106">Вычисливание ненужного контента</span><span class="sxs-lookup"><span data-stu-id="5f19a-106">Culling unnecessary content</span></span>

- <span data-ttu-id="5f19a-107">Определение соответствующего контента</span><span class="sxs-lookup"><span data-stu-id="5f19a-107">Identifying relevant content</span></span>

- <span data-ttu-id="5f19a-108">Определение контента, которое должно быть рассмотрено экспертом или адвокатом</span><span class="sxs-lookup"><span data-stu-id="5f19a-108">Identifying content that must be reviewed by an expert or attorney</span></span>

<span data-ttu-id="5f19a-109">Когда эксперты, адвокаты или другие пользователи проверяют содержимое в наборе отзывов, их мнения, связанные с содержимым, могут быть запечатлены с помощью тегов.</span><span class="sxs-lookup"><span data-stu-id="5f19a-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="5f19a-110">Например, если цель состоит в том, чтобы отослать ненужный контент, пользователь может тегировать документы тегом "не реагируя".</span><span class="sxs-lookup"><span data-stu-id="5f19a-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="5f19a-111">После проверки и метки контента можно создать поиск набора обзоров, чтобы исключить любой контент, помеченный как "не отзывчивый".</span><span class="sxs-lookup"><span data-stu-id="5f19a-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive".</span></span> <span data-ttu-id="5f19a-112">Этот процесс устраняет неотвратимый контент из следующих действий рабочего процесса eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="5f19a-112">This process eliminates the non-responsive content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="5f19a-113">Панель тегов в наборе отзывов может быть настроена для каждого случая, чтобы теги поддержали предполагаемый рабочий процесс проверки для этого случая.</span><span class="sxs-lookup"><span data-stu-id="5f19a-113">The tagging panel in a review set can be customized for every case so that the tags support the intended review workflow for the case.</span></span>

> [!NOTE]
> <span data-ttu-id="5f19a-114">Область тегов — это Advanced eDiscovery случае.</span><span class="sxs-lookup"><span data-stu-id="5f19a-114">The scope of tags is an Advanced eDiscovery case.</span></span> <span data-ttu-id="5f19a-115">Это означает, что в случае может быть только один набор тегов, которые рецензенты могут использовать для тегов документов набора обзоров.</span><span class="sxs-lookup"><span data-stu-id="5f19a-115">That means a case can only have one set of tags that reviewers can use to tag review set documents.</span></span> <span data-ttu-id="5f19a-116">Вы не можете настроить другой набор тегов для использования в различных наборах отзывов в одном случае.</span><span class="sxs-lookup"><span data-stu-id="5f19a-116">You can't set up a different set of tags for use in different review sets in the same case.</span></span>

## <a name="tag-types"></a><span data-ttu-id="5f19a-117">Типы тегов</span><span class="sxs-lookup"><span data-stu-id="5f19a-117">Tag types</span></span>

<span data-ttu-id="5f19a-118">Advanced eDiscovery содержит два типа тегов:</span><span class="sxs-lookup"><span data-stu-id="5f19a-118">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="5f19a-119">**Теги выбора:** ограничивает рецензентов выбором одного тега в группе.</span><span class="sxs-lookup"><span data-stu-id="5f19a-119">**Single choice tags**: Restricts reviewers to selecting a single tag within a group.</span></span> <span data-ttu-id="5f19a-120">Эти типы тегов могут быть полезны для того, чтобы рецензенты не выбирали конфликтующие теги, такие как "отзывчивый" и "не отзывчивый".</span><span class="sxs-lookup"><span data-stu-id="5f19a-120">These types of tags can be useful to ensure that reviewers don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="5f19a-121">Отдельные теги выбора отображаются в качестве кнопок радио.</span><span class="sxs-lookup"><span data-stu-id="5f19a-121">Single choice tags appear as radio buttons.</span></span>

- <span data-ttu-id="5f19a-122">**Несколько тегов выбора.** Разрешить просмотрениям выбирать несколько тегов в группе.</span><span class="sxs-lookup"><span data-stu-id="5f19a-122">**Multiple choice tags**: Allow reviews to select multiple tags within a group.</span></span> <span data-ttu-id="5f19a-123">Эти типы тегов отображаются как почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="5f19a-123">These types of tags appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="5f19a-124">Структура тегов</span><span class="sxs-lookup"><span data-stu-id="5f19a-124">Tag structure</span></span>

<span data-ttu-id="5f19a-125">Помимо типов тегов можно использовать структуру организации тегов в панели тегов, чтобы сделать документы тегов более понятными.</span><span class="sxs-lookup"><span data-stu-id="5f19a-125">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="5f19a-126">Теги сгруппировали по разделам.</span><span class="sxs-lookup"><span data-stu-id="5f19a-126">Tags are grouped by sections.</span></span> <span data-ttu-id="5f19a-127">Набор просмотреть поиск поддерживает возможность поиска по тегам и по разделу тегов.</span><span class="sxs-lookup"><span data-stu-id="5f19a-127">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="5f19a-128">Это означает, что вы можете создать поиск набора отзывов для получения документов с тегами любого тега в разделе.</span><span class="sxs-lookup"><span data-stu-id="5f19a-128">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Разделы тегов в панели тегов](../media/TagTypes.png)

<span data-ttu-id="5f19a-130">Далее можно организовать теги, вложенные в раздел.</span><span class="sxs-lookup"><span data-stu-id="5f19a-130">You can further organize tags by nesting them within a section.</span></span> <span data-ttu-id="5f19a-131">Например, если цель заключается в определении и теге привилегированного контента, вложение можно использовать, чтобы понять, что рецензент может пометить документ как "Привилегированный" и выбрать тип привилегии, проверив соответствующий вложенный тег.</span><span class="sxs-lookup"><span data-stu-id="5f19a-131">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a reviewer can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Вложенные теги в разделе тегов](../media/NestingTags.png)

## <a name="create-tags"></a><span data-ttu-id="5f19a-133">Создание тегов</span><span class="sxs-lookup"><span data-stu-id="5f19a-133">Create tags</span></span>

<span data-ttu-id="5f19a-134">Прежде чем применять теги к документам в наборе отзывов, необходимо создать структуру тегов.</span><span class="sxs-lookup"><span data-stu-id="5f19a-134">Before applying tags to documents in the review set, you need to create a tag structure.</span></span>

1. <span data-ttu-id="5f19a-135">Откройте набор отзывов и перейдите к панели команд и выберите **Тег по запросу.**</span><span class="sxs-lookup"><span data-stu-id="5f19a-135">Open a review set and navigate to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="5f19a-136">В панели тегов выберите **Параметры Управления тегами**</span><span class="sxs-lookup"><span data-stu-id="5f19a-136">In the tagging panel, select **Manage tag options**</span></span>

3. <span data-ttu-id="5f19a-137">Выберите **раздел Добавить тег**.</span><span class="sxs-lookup"><span data-stu-id="5f19a-137">Select **Add tag section**.</span></span>

4. <span data-ttu-id="5f19a-138">Введите название группы тегов и необязательный описание, а затем нажмите **кнопку Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5f19a-138">Type a tag group title and an optional description, and then click **Save**.</span></span>

5. <span data-ttu-id="5f19a-139">Выберите тройное меню выпадаемой точки рядом с заголовком группы тегов и нажмите **кнопку Добавить шажок** или **добавить параметр**.</span><span class="sxs-lookup"><span data-stu-id="5f19a-139">Select the triple dot dropdown menu next to the tag group title and click **Add check box** or **Add option button**.</span></span>

6. <span data-ttu-id="5f19a-140">Введите имя и описание для почтового ящика или кнопки параметра.</span><span class="sxs-lookup"><span data-stu-id="5f19a-140">Type a name and description for the checkbox or option button.</span></span>

7. <span data-ttu-id="5f19a-141">Повторите этот процесс, чтобы создать новые разделы тегов, параметры тегов и почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="5f19a-141">Repeat this process to create new tag sections, tag options, and checkboxes.</span></span>

   ![Настройка структуры тегов](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a><span data-ttu-id="5f19a-143">Применение тегов</span><span class="sxs-lookup"><span data-stu-id="5f19a-143">Applying tags</span></span>

<span data-ttu-id="5f19a-144">С помощью структуры тегов рецензенты могут применять теги к документам в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="5f19a-144">With the tag structure in place, reviewers can apply tags to documents in a review set.</span></span> <span data-ttu-id="5f19a-145">Существует два различных способа применения тегов:</span><span class="sxs-lookup"><span data-stu-id="5f19a-145">There are two different ways to apply tags:</span></span>

- <span data-ttu-id="5f19a-146">Файлы тегов</span><span class="sxs-lookup"><span data-stu-id="5f19a-146">Tag files</span></span>

- <span data-ttu-id="5f19a-147">Тег по запросу</span><span class="sxs-lookup"><span data-stu-id="5f19a-147">Tag by query</span></span>

### <a name="tag-files"></a><span data-ttu-id="5f19a-148">Файлы тегов</span><span class="sxs-lookup"><span data-stu-id="5f19a-148">Tag files</span></span>

<span data-ttu-id="5f19a-149">Выберите один элемент или несколько элементов в наборе отзывов, вы можете применить теги к их выбору, щелкнув файлы **тегов** в панели команд.</span><span class="sxs-lookup"><span data-stu-id="5f19a-149">Whether you select a single item or several items in a review set, you can apply tags to their selection by clicking **Tag files** in the command bar.</span></span> <span data-ttu-id="5f19a-150">На панели тегов можно выбрать тег, который автоматически применяется к выбранным документам.</span><span class="sxs-lookup"><span data-stu-id="5f19a-150">In the tagging panel, you can select a tag and it is automatically applied to the selected documents.</span></span>

![Тег выбранных файлов](../media/TagFile2.png)

> [!NOTE]
> <span data-ttu-id="5f19a-152">Теги будут применяться только к выбранным пунктам в списке элементов.</span><span class="sxs-lookup"><span data-stu-id="5f19a-152">Tags will be applied only to selected items in the list of items.</span></span>

### <a name="tag-by-query"></a><span data-ttu-id="5f19a-153">Тег по запросу</span><span class="sxs-lookup"><span data-stu-id="5f19a-153">Tag by query</span></span>

<span data-ttu-id="5f19a-154">Пометка по запросу позволяет применять теги для всех элементов, отображающихся в фильтровом запросе, который в настоящее время применяется в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="5f19a-154">Tagging by query lets you apply tags to all items displayed by a filter query that's currently applied in the review set.</span></span>

1. <span data-ttu-id="5f19a-155">Отойдите от всех элементов в наборе отзывов и перейдите в командную планку и выберите **Тег по запросу.**</span><span class="sxs-lookup"><span data-stu-id="5f19a-155">Unselect all items in the review set and go to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="5f19a-156">На панели тегов выберите тег, который необходимо применить.</span><span class="sxs-lookup"><span data-stu-id="5f19a-156">In the tagging panel, select the tag that you want to apply.</span></span>

3. <span data-ttu-id="5f19a-157">В **отсеве выбора тегов** существует три параметра, которые диктуют, к как можно применить тег.</span><span class="sxs-lookup"><span data-stu-id="5f19a-157">Under the **Tag selection** dropdown, there are three options that dictate which items to apply the tag to.</span></span>

   - <span data-ttu-id="5f19a-158">**Элементы, которые соответствуют прикладному запросу.** Применяет теги к определенным пунктам, которые соответствуют условиям запроса фильтра.</span><span class="sxs-lookup"><span data-stu-id="5f19a-158">**Items that match applied query**: Applies tags to specific items that match the filter query conditions.</span></span>

   - <span data-ttu-id="5f19a-159">**Включайте** связанные элементы семейства: применяет теги к определенным пунктам, которые соответствуют условиям запроса фильтра и связанным с ними семейным элементам.</span><span class="sxs-lookup"><span data-stu-id="5f19a-159">**Include associated family items**: Applies tags to specific items that match the filter query conditions and their associated family items.</span></span> <span data-ttu-id="5f19a-160">*Элементы семейства* — это элементы с одинаковым значением метаданных FamilyId.</span><span class="sxs-lookup"><span data-stu-id="5f19a-160">*Family items* are items that share the same FamilyId metadata value.</span></span>  

   - <span data-ttu-id="5f19a-161">**Включайте** связанные элементы беседы: применяет теги к пунктам, которые соответствуют условиям запроса фильтра и связанным с ними предметам беседы.</span><span class="sxs-lookup"><span data-stu-id="5f19a-161">**Include associated conversation items**: Applies tags to items that match the filter query conditions and their associated conversation items.</span></span> <span data-ttu-id="5f19a-162">*Элементы беседы* — это элементы, которые имеют одинаковые значения метаданных ConversationId.</span><span class="sxs-lookup"><span data-stu-id="5f19a-162">*Conversation items* are items that share the same ConversationId metadata values.</span></span>

   ![Выбор тегов](../media/TagByQuery2.png)

4. <span data-ttu-id="5f19a-164">Нажмите **кнопку Пуск пометки задания,** чтобы вызвать задание пометки.</span><span class="sxs-lookup"><span data-stu-id="5f19a-164">Click **Start tagging job** to trigger the tagging job.</span></span>

## <a name="tag-filter"></a><span data-ttu-id="5f19a-165">Фильтр тегов</span><span class="sxs-lookup"><span data-stu-id="5f19a-165">Tag filter</span></span>

<span data-ttu-id="5f19a-166">Используйте фильтр тегов в наборе обзоров, чтобы быстро найти или исключить элементы из результатов запроса в зависимости от того, как помечен элемент.</span><span class="sxs-lookup"><span data-stu-id="5f19a-166">Use the tag filter in review set to quickly find or exclude items from the query results based on how an item is tagged.</span></span> 

1. <span data-ttu-id="5f19a-167">Выберите **фильтры** для расширения панели фильтров.</span><span class="sxs-lookup"><span data-stu-id="5f19a-167">Select **Filters** to expand the filter panel.</span></span>

2. <span data-ttu-id="5f19a-168">Выберите и **расширь свойства Item.**</span><span class="sxs-lookup"><span data-stu-id="5f19a-168">Select and expand **Item properties**.</span></span>

3. <span data-ttu-id="5f19a-169">Прокрутите вниз, чтобы найти фильтр с именем **Тег,** выберите почтовый ящик, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5f19a-169">Scroll down to find the filter named **Tag**, select the checkbox, and then click **Done**.</span></span>

4. <span data-ttu-id="5f19a-170">Чтобы включить или исключить элементы с определенным тегом из запроса, сделайте одно из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="5f19a-170">To include or exclude items with a specific tag from a query, do one of the following:</span></span>

   - <span data-ttu-id="5f19a-171">**Включите** элементы: Выберите значение тега и **выберите Равное любое из** в меню отсев.</span><span class="sxs-lookup"><span data-stu-id="5f19a-171">**Include items**: Select the tag value and select **Equal any of** in the dropdown menu.</span></span>

      <span data-ttu-id="5f19a-172">Или</span><span class="sxs-lookup"><span data-stu-id="5f19a-172">Or</span></span>

   - <span data-ttu-id="5f19a-173">**Исключить элементы.** Выберите значение тега и выберите **Равно ни одного из** в выпадаемом меню.</span><span class="sxs-lookup"><span data-stu-id="5f19a-173">**Exclude items**: Select the tag value and select **Equals none of** in dropdown menu.</span></span>

     ![Фильтр тегов исключает элементы](../media/TagFilterExclude.png)

> [!NOTE]
> <span data-ttu-id="5f19a-175">Обязательно обновите страницу, чтобы фильтр тегов отображал последние изменения в структуре тегов.</span><span class="sxs-lookup"><span data-stu-id="5f19a-175">Be sure to refresh the page to ensure that the tag filter displays the latest changes to the tag structure.</span></span>
