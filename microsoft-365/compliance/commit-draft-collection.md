---
title: Фиксация коллекции черновиков в набор отзывов
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
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
description: После создания и итерации в черновике коллекции можно установить его в набор отзывов. При фиксации коллекции черновиков собранные элементы добавляются для проверки набора в случае. После того как собранные элементы находятся в наборе отзывов, их можно анализировать, анализировать и экспортировать.
ms.openlocfilehash: e28592e7aac289bfc0cc29d312963fa21d9f8fd4
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838890"
---
# <a name="commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="91be8-105">Фиксация черновика коллекции в набор обзоров в advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="91be8-105">Commit a draft collection to a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="91be8-106">Если вы удовлетворены элементами, собранными в коллекции черновиков, и готовы анализировать, теги и анализировать их, вы можете добавить коллекцию в набор отзывов в данном случае.</span><span class="sxs-lookup"><span data-stu-id="91be8-106">When you're satisfied with the items you've collected in a draft collection and are ready to analyze, tag, and review them, you can add a collection to a review set in the case.</span></span> <span data-ttu-id="91be8-107">При фиксации черновика коллекции в набор отзывов собранные элементы копируется из исходного расположения контента в Microsoft 365 в набор отзывов.</span><span class="sxs-lookup"><span data-stu-id="91be8-107">When you commit a draft collection to a review set, collected items are copied from their original content location in Microsoft 365 to a review set.</span></span> <span data-ttu-id="91be8-108">Набор отзывов — это безопасное хранилище Azure, предоставленное Майкрософт в облаке Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91be8-108">A review set is a secure, Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>

## <a name="commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="91be8-109">Фиксация коллекции черновиков в набор отзывов</span><span class="sxs-lookup"><span data-stu-id="91be8-109">Commit a draft collection to a review set</span></span>

1. <span data-ttu-id="91be8-110">В центре соответствия требованиям Microsoft 365 откройте дело Advanced eDiscovery, а затем выберите вкладку **Collections,** чтобы отобразить список коллекций в этом случае.</span><span class="sxs-lookup"><span data-stu-id="91be8-110">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, and then select the **Collections** tab to display a list of the collections in the case.</span></span>

   ![Список коллекций в случае](../media/CommitDraftCollections1.png)

   > [!TIP]
   > <span data-ttu-id="91be8-112">Значение в `Estimated` столбце **Состояние** определяет черновики коллекций, которые можно добавить в набор отзывов.</span><span class="sxs-lookup"><span data-stu-id="91be8-112">A value of `Estimated` in the **Status** column identifies the draft collections that can be added to a review set.</span></span> <span data-ttu-id="91be8-113">Состояние `Committed` указывает, что коллекция уже добавлена в набор отзывов.</span><span class="sxs-lookup"><span data-stu-id="91be8-113">A status of `Committed` indicates that a collection has already been added to a review set.</span></span>

2. <span data-ttu-id="91be8-114">На странице **Коллекции выберите** черновик коллекции, который необходимо зафиксировать в наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="91be8-114">On the **Collections** page, select the draft collection that you want to commit to a review set.</span></span>

3. <span data-ttu-id="91be8-115">В нижней части страницы вылетов выберите коллекцию **Действия**  >  **Редактирование**.</span><span class="sxs-lookup"><span data-stu-id="91be8-115">On the bottom of the flyout page, select **Actions** > **Edit collection**.</span></span>

4. <span data-ttu-id="91be8-116">В мастере редактирования коллекции нажмите **кнопку Далее,** пока не будет отображаться черновик **сохранения** или страница сбора.</span><span class="sxs-lookup"><span data-stu-id="91be8-116">In the edit collection wizard, click **Next** until the **Save draft or collect** page is displayed.</span></span>

5. <span data-ttu-id="91be8-117">Настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="91be8-117">Configure the following settings:</span></span>

   1. <span data-ttu-id="91be8-118">Выберите **элементов Сбор и добавить в набор отзывов**.</span><span class="sxs-lookup"><span data-stu-id="91be8-118">Select **Collect items and add to review set**.</span></span>

   2. <span data-ttu-id="91be8-119">Решите, следует ли добавлять коллекцию в новый набор отзывов (который создается после отправки коллекции) или в существующий набор отзывов.</span><span class="sxs-lookup"><span data-stu-id="91be8-119">Decide whether to add the collection to a new review set (which is created after you submit the collection) or to an existing review set.</span></span> <span data-ttu-id="91be8-120">Заполните этот раздел в соответствии с вашим решением.</span><span class="sxs-lookup"><span data-stu-id="91be8-120">Complete this section based on your decision.</span></span>

   3. <span data-ttu-id="91be8-121">Настройка дополнительных параметров коллекции:</span><span class="sxs-lookup"><span data-stu-id="91be8-121">Configure the additional collection settings:</span></span>

       - <span data-ttu-id="91be8-122">**Teams and Yammer messages:** Select this option to add conversation threads to the collection that include the chat items returned by the search query in the collection.</span><span class="sxs-lookup"><span data-stu-id="91be8-122">**Teams and Yammer messages**: Select this option to add conversation threads to the collection that include the chat items returned by the search query in the collection.</span></span> <span data-ttu-id="91be8-123">Это означает, что диалог чата, содержащий элементы, которые соответствуют критериям поиска, реконструирован.</span><span class="sxs-lookup"><span data-stu-id="91be8-123">This means that the chat conversation that contains items that match the search criteria is reconstructed.</span></span> <span data-ttu-id="91be8-124">Это позволяет просмотреть элементы чата в контексте беседы взад и вперед.</span><span class="sxs-lookup"><span data-stu-id="91be8-124">This lets you review chat items in the context of the back and forth conversation.</span></span> <span data-ttu-id="91be8-125">Дополнительные сведения см. в дополнительных сведениях в потоке [Conversation in Advanced eDiscovery.](conversation-review-sets.md)</span><span class="sxs-lookup"><span data-stu-id="91be8-125">For more information, see [Conversation threading in Advanced eDiscovery](conversation-review-sets.md).</span></span>

       - <span data-ttu-id="91be8-126">**Облачные вложения.** Выберите этот параметр, чтобы включить современные вложения или связанные файлы при добавлении результатов коллекции в набор отзывов.</span><span class="sxs-lookup"><span data-stu-id="91be8-126">**Cloud attachments**: Select this option to include modern attachments or linked files when the collection results are added to the review set.</span></span> <span data-ttu-id="91be8-127">Это означает, что целевой файл современного вложения или связанного файла добавляется в набор отзывов.</span><span class="sxs-lookup"><span data-stu-id="91be8-127">This means that the target file of a modern attachment or linked file is added to the review set.</span></span>

       - <span data-ttu-id="91be8-128">**Версии SharePoint.** Выберите этот параметр, чтобы включить коллекцию всех версий документа SharePoint в пределах версии и параметрах поиска коллекции.</span><span class="sxs-lookup"><span data-stu-id="91be8-128">**SharePoint versions**: Select this option to enable the collection of all version of a SharePoint document per the version limits and search parameters of the collection.</span></span> <span data-ttu-id="91be8-129">Выбор этого параметра значительно увеличит размер элементов, добавленных в набор отзывов.</span><span class="sxs-lookup"><span data-stu-id="91be8-129">Selecting this option will significantly increase the size of items that are added to the review set.</span></span>

   4. <span data-ttu-id="91be8-130">Настройка параметров для определения масштабов коллекции для добавления в набор отзывов:</span><span class="sxs-lookup"><span data-stu-id="91be8-130">Configure the settings to define the scale of the collection to add to the review set:</span></span>

      - <span data-ttu-id="91be8-131">**Добавьте все результаты** коллекции: Выберите этот параметр, чтобы добавить в набор отзывов все элементы, которые соответствуют критериям поиска коллекции.</span><span class="sxs-lookup"><span data-stu-id="91be8-131">**Add all collection results**: Select this option to add all the items that match the search criteria of the collection to the review set.</span></span>

      - <span data-ttu-id="91be8-132">**Добавьте пример результатов** коллекции: Выберите этот параметр, чтобы добавить пример результатов коллекции в набор отзывов вместо добавления всех результатов.</span><span class="sxs-lookup"><span data-stu-id="91be8-132">**Add a sample of the collection results**: Select this option to add a sample of the collection results to the review set instead of adding all results.</span></span> <span data-ttu-id="91be8-133">Если вы выбрали этот параметр, нажмите **кнопку Изменить параметры выборки** и выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="91be8-133">If you select this option, click **Edit sample parameters** and choose one of the following options:</span></span>

         - <span data-ttu-id="91be8-134">**Пример, основанный на** уверенности. Элементы из коллекции добавляются в набор отзывов, определяются по заданным статистическим параметрам.</span><span class="sxs-lookup"><span data-stu-id="91be8-134">**Sample based on confidence**: Items from the collection are added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="91be8-135">Если при отборе результатов выборки обычно используется уровень доверия и интервал, укажите их в выпадаемом поле.</span><span class="sxs-lookup"><span data-stu-id="91be8-135">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="91be8-136">В противном случае используйте параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="91be8-136">Otherwise, use the default settings.</span></span>

         - <span data-ttu-id="91be8-137">**Случайный пример.** Элементы из коллекции добавляются в набор отзывов на основе случайного выбора указанного процента от общего числа элементов, возвращаемого поиском.</span><span class="sxs-lookup"><span data-stu-id="91be8-137">**Randomly sample**: Items from the collection are added to the review set based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

6. <span data-ttu-id="91be8-138">На странице **Обзор коллекции** можно просмотреть параметры коллекции, настроенные на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="91be8-138">On the **Review your collection** page, you can review the collection settings that you configured on the previous page.</span></span> <span data-ttu-id="91be8-139">Нажмите **кнопку Изменить,** если вы хотите изменить их.</span><span class="sxs-lookup"><span data-stu-id="91be8-139">Click **Edit** if you want to change them.</span></span>

7. <span data-ttu-id="91be8-140">Нажмите **Кнопку Отправить,** чтобы создать коллекцию черновиков.</span><span class="sxs-lookup"><span data-stu-id="91be8-140">Click **Submit** to create the draft collection.</span></span> <span data-ttu-id="91be8-141">Отображается страница, подтверждая, что коллекция создана.</span><span class="sxs-lookup"><span data-stu-id="91be8-141">A page is displayed confirming that the collection was created.</span></span>

## <a name="what-happens-after-you-commit-a-draft-collection"></a><span data-ttu-id="91be8-142">Что происходит после фиксации коллекции черновиков</span><span class="sxs-lookup"><span data-stu-id="91be8-142">What happens after you commit a draft collection</span></span>

<span data-ttu-id="91be8-143">При фиксации черновика коллекции в набор отзывов происходят следующие вещи:</span><span class="sxs-lookup"><span data-stu-id="91be8-143">When you commit a draft collection to a review set, the following things happen:</span></span>

- <span data-ttu-id="91be8-144">Запрос поиска коллекции снова запустится.</span><span class="sxs-lookup"><span data-stu-id="91be8-144">The collection search query is run again.</span></span> <span data-ttu-id="91be8-145">Это означает, что фактические результаты поиска, скопированные в набор отзывов, могут быть иными, чем предполагаемые результаты, возвращенные при последнем запуске поиска коллекции.</span><span class="sxs-lookup"><span data-stu-id="91be8-145">This means the actual search results copied to the review set may be different than the estimated results that were returned when the collection search was last run.</span></span>

- <span data-ttu-id="91be8-146">Все элементы в результатах поиска копируется из исходного источника данных в живой службе и копируется в безопасное хранилище Azure в облаке Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91be8-146">All items in the search results are copied from the original data source in the live service, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="91be8-147">Все элементы (включая содержимое и метаданные), которые не находятся в источниках данных хранителя или не-хранителя, переиндексировать (в процессе, называемом глубокой индексализационной), чтобы все данные в наборе обзоров были полностью искомы во время проверки данных дела. </span><span class="sxs-lookup"><span data-stu-id="91be8-147">All items (including the content and metadata) that aren't located in custodian or non-custodian data sources are reindexed (in a process called *deep indexing*) so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="91be8-148">Повторное перенастройка контента в коллекции приводит к тщательному и быстрому поиску при поиске или фильтрации контента в обзоре, задамом во время расследования дела.</span><span class="sxs-lookup"><span data-stu-id="91be8-148">Reindexing the content in a collection results in thorough and fast searches when you search or filter the content in the review set during the case investigation.</span></span>

- <span data-ttu-id="91be8-149">Зашифрованные документы SharePoint и OneDrive, а также зашифрованные файлы, прикрепленные к сообщениям электронной почты, возвращаемой в результатах поиска, расшифровываются при фиксации коллекции в набор отзывов.</span><span class="sxs-lookup"><span data-stu-id="91be8-149">Encrypted SharePoint and OneDrive documents and encrypted files attached email messages that's returned in the search results are decrypted when you commit the collection to a review set.</span></span> <span data-ttu-id="91be8-150">Вы можете просмотреть и запросить расшифрованные файлы в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="91be8-150">You can review and query the decrypted files in the review set.</span></span> <span data-ttu-id="91be8-151">Дополнительные сведения см. [в веб-сайте Расшифровка в средствах электронного разокрытия Microsoft 365.](ediscovery-decryption.md)</span><span class="sxs-lookup"><span data-stu-id="91be8-151">For more information, see [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).</span></span>

- <span data-ttu-id="91be8-152">Функции распознавания символов (OCR) извлекают текст из изображений и включают текст изображения с контентом, добавленным в набор отзывов.</span><span class="sxs-lookup"><span data-stu-id="91be8-152">Optical character recognition (OCR) functionality extracts text from images, and includes the image text with the content that's added to a review set.</span></span> <span data-ttu-id="91be8-153">Дополнительные сведения см. в разделе [Оптическое распознавание](#optical-character-recognition) символов в этой статье.</span><span class="sxs-lookup"><span data-stu-id="91be8-153">For more information, see the [Optical character recognition](#optical-character-recognition) section in this article.</span></span>

- <span data-ttu-id="91be8-154">После успешного завершения фиксации значение столбца состояния на вкладке **Collections** будет изменено на `Committed` .</span><span class="sxs-lookup"><span data-stu-id="91be8-154">After the commit is successfully completed, the value of the status column of on the **Collections** tab is changed to `Committed`.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="91be8-155">Оптическое распознавание символов</span><span class="sxs-lookup"><span data-stu-id="91be8-155">Optical character recognition</span></span>

<span data-ttu-id="91be8-156">При фиксации коллекции на набор отзывов функции распознавания символов (OCR) в Advanced eDiscovery автоматически извлекают текст из изображений и включают текст изображения с контентом, добавленным в набор обзоров.</span><span class="sxs-lookup"><span data-stu-id="91be8-156">When you commit a collection to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the content that's added to a review set.</span></span> <span data-ttu-id="91be8-157">Извлеченный текст можно просмотреть в текстовом представлении выбранного файла изображения в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="91be8-157">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="91be8-158">Это позволяет проводить дополнительные проверки и анализ текста на изображениях.</span><span class="sxs-lookup"><span data-stu-id="91be8-158">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="91be8-159">OCR поддерживается для свободных файлов, вложений электронной почты и встроенных изображений.</span><span class="sxs-lookup"><span data-stu-id="91be8-159">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="91be8-160">Список форматов файлов изображений, поддерживаемых для OCR, см. в списке Поддерживаемые типы файлов [в advanced eDiscovery.](supported-filetypes-ediscovery20.md#image)</span><span class="sxs-lookup"><span data-stu-id="91be8-160">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="91be8-161">Необходимо включить функции OCR для каждого случая, который вы создаете в advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="91be8-161">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="91be8-162">Дополнительные сведения см. в настройках параметров поиска [и аналитики.](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)</span><span class="sxs-lookup"><span data-stu-id="91be8-162">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>