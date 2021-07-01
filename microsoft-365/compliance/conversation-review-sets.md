---
title: Просмотр бесед в Advanced eDiscovery
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
ms.assetid: ''
description: Узнайте о функции восстановления беседы в Advanced eDiscovery (так называемая потоковая беседа) для восстановления, просмотра и экспорта бесед в Microsoft Teams и Yammer группах.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9848280a7d6dbcbd6128fff06f150c8458f09701
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227191"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a><span data-ttu-id="5224b-103">Потоковая беседа в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5224b-103">Conversation threading in Advanced eDiscovery</span></span>

<span data-ttu-id="5224b-104">Мгновенные сообщения — это удобный способ задавать вопросы, обмениваться идеями или быстро общаться в больших аудиториях.</span><span class="sxs-lookup"><span data-stu-id="5224b-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="5224b-105">Поскольку платформы обмена мгновенными сообщениями, такие как группы Microsoft Teams и Yammer, становятся ключевыми для совместной работы предприятий, организации должны оценить, как их рабочий процесс по обнаружению электронных данных решает эти новые формы взаимодействия и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="5224b-105">As instant messaging platforms, like Microsoft Teams and Yammer groups, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span>

<span data-ttu-id="5224b-106">Функция реконструкции беседы в Advanced eDiscovery предназначена для определения контекстного контента и создания различных представлений беседы.</span><span class="sxs-lookup"><span data-stu-id="5224b-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="5224b-107">Эта возможность позволяет эффективно и быстро просмотреть полные беседы мгновенных сообщений (также называемые беседами с потоками), которые создаются на таких платформах, как Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5224b-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="5224b-108">С помощью conversation Reconstruction можно использовать встроенные возможности для восстановления, просмотра и экспорта потоковой беседы.</span><span class="sxs-lookup"><span data-stu-id="5224b-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="5224b-109">Использование Advanced eDiscovery реконструкции беседы для:</span><span class="sxs-lookup"><span data-stu-id="5224b-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="5224b-110">Сохранение уникальных метаданных на уровне сообщений во всех сообщениях в ходе беседы.</span><span class="sxs-lookup"><span data-stu-id="5224b-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="5224b-111">Сбор контекстных сообщений вокруг результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="5224b-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="5224b-112">Обзор, аннотации и отредактировать потоковые беседы.</span><span class="sxs-lookup"><span data-stu-id="5224b-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="5224b-113">Экспорт отдельных сообщений или потоковой беседы</span><span class="sxs-lookup"><span data-stu-id="5224b-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="5224b-114">Терминология</span><span class="sxs-lookup"><span data-stu-id="5224b-114">Terminology</span></span>

<span data-ttu-id="5224b-115">Вот несколько определений, которые помогут приступить к использованию реконструкции беседы.</span><span class="sxs-lookup"><span data-stu-id="5224b-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="5224b-116">**Сообщения:** Представляет наименьший блок беседы.</span><span class="sxs-lookup"><span data-stu-id="5224b-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="5224b-117">Сообщения могут отличаться по размеру, структуре и метаданным.</span><span class="sxs-lookup"><span data-stu-id="5224b-117">Messages may vary in size, structure, and metadata.</span></span>

- <span data-ttu-id="5224b-118">**Беседа:** Представляет группу одного или более сообщений.</span><span class="sxs-lookup"><span data-stu-id="5224b-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="5224b-119">В различных приложениях беседы могут быть представлены разными способами.</span><span class="sxs-lookup"><span data-stu-id="5224b-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="5224b-120">В некоторых приложениях существует явное действие, которое приводит к ответу на существующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="5224b-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="5224b-121">Беседы формируются явно в результате этого действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="5224b-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="5224b-122">Например, вот снимок экрана беседы канала в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5224b-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teams Разговор на канале](../media/threadedchat.png)

   <span data-ttu-id="5224b-124">В других приложениях (например, сообщения чата 1xN в Teams) нет официальной цепочки ответов, а сообщения отображаются как "плоская река сообщений" в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="5224b-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="5224b-125">В приложениях этих типов беседы высвечены из группы сообщений, которые происходят в течение определенного времени.</span><span class="sxs-lookup"><span data-stu-id="5224b-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="5224b-126">Эта "мягкая группировка" сообщений (в отличие от цепочки ответов) представляет беседу "назад и вперед" на определенную интересуемую тему.</span><span class="sxs-lookup"><span data-stu-id="5224b-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span>

## <a name="step-1-create-a-draft-collection"></a><span data-ttu-id="5224b-127">Шаг 1. Создание коллекции черновиков</span><span class="sxs-lookup"><span data-stu-id="5224b-127">Step 1: Create a draft collection</span></span>

<span data-ttu-id="5224b-128">После того как вы определили соответствующие хранители и расположения контента, можно создать поиск, чтобы найти потенциально релевантный контент.</span><span class="sxs-lookup"><span data-stu-id="5224b-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="5224b-129">На **вкладке Коллекции** в Advanced eDiscovery можно создать коллекцию, щелкнув **новую** коллекцию и следуя за мастером.</span><span class="sxs-lookup"><span data-stu-id="5224b-129">On the **Collections** tab in the Advanced eDiscovery case, you can create a collection by clicking **New collection** and following the wizard.</span></span> <span data-ttu-id="5224b-130">Сведения о том, как создать коллекцию, создать запрос поиска и просмотреть результаты поиска, см. в статью [Создание коллекции черновиков.](create-draft-collection.md)</span><span class="sxs-lookup"><span data-stu-id="5224b-130">For information about how you can create a collection, build a search query, and preview the search results, see [Create a draft collection](create-draft-collection.md).</span></span>

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="5224b-131">Шаг 2. Совершение набора черновиков в набор отзывов</span><span class="sxs-lookup"><span data-stu-id="5224b-131">Step 2: Commit a draft collection to a review set</span></span>

<span data-ttu-id="5224b-132">После проверки и завершения поиска в коллекции можно добавить результаты поиска в набор отзывов.</span><span class="sxs-lookup"><span data-stu-id="5224b-132">After you have reviewed and finalized the search query in a collection, you can add the search results to a review set.</span></span> <span data-ttu-id="5224b-133">При добавлении результатов поиска в набор отзывов исходные данные копируется в область служба хранилища Azure для облегчения процесса проверки и анализа.</span><span class="sxs-lookup"><span data-stu-id="5224b-133">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="5224b-134">Дополнительные сведения о добавлении результатов поиска в набор отзывов см. в документе [Commit a draft collection to a review set.](commit-draft-collection.md)</span><span class="sxs-lookup"><span data-stu-id="5224b-134">For more information about adding search results to a review set, see [Commit a draft collection to a review set](commit-draft-collection.md).</span></span>

<span data-ttu-id="5224b-135">При добавлении элементов из бесед в набор отзывов можно использовать параметр threaded conversations для сбора контекстных сообщений из бесед, содержащих элементы, которые соответствуют критериям поиска коллекции.</span><span class="sxs-lookup"><span data-stu-id="5224b-135">When you add items from conversations to a review set, you can use the threaded conversations option to collect contextual messages from conversations that contain items that match the search criteria of the collection.</span></span> <span data-ttu-id="5224b-136">После выбора параметра беседы потоков могут произойти следующие вещи:</span><span class="sxs-lookup"><span data-stu-id="5224b-136">After you select the thread conversations option, the following things can happen:</span></span>

  ![Переоценка беседы](../media/messagesandconversations.png)

1. <span data-ttu-id="5224b-138">С помощью ключевого слова и запроса диапазона дат поиск возвращал хит в *Message 3.*</span><span class="sxs-lookup"><span data-stu-id="5224b-138">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="5224b-139">Это сообщение было частью более масштабной беседы, иллюстрированной *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="5224b-139">This message was part of a larger conversation, illustrated by *CRC1*.</span></span>

2. <span data-ttu-id="5224b-140">Если добавить данные в набор отзывов и включить параметры для иска беседы, Advanced eDiscovery будут возвращаться и собирать другие элементы в *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="5224b-140">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span>

3. <span data-ttu-id="5224b-141">После того как элементы были добавлены в набор отзывов, вы можете просмотреть все отдельные сообщения *из CRC1.*</span><span class="sxs-lookup"><span data-stu-id="5224b-141">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span>

<span data-ttu-id="5224b-142">Чтобы включить параметр threaded conversations, см. в рубке [Commit a draft collection to a review set.](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set)</span><span class="sxs-lookup"><span data-stu-id="5224b-142">To enabled the threaded conversations option, see [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span></span>

## <a name="step-3-review-and-export-threaded-conversations"></a><span data-ttu-id="5224b-143">Шаг 3. Просмотр и экспорт бесед с потоками</span><span class="sxs-lookup"><span data-stu-id="5224b-143">Step 3: Review and export threaded conversations</span></span>

<span data-ttu-id="5224b-144">После обработки и добавления контента в набор отзывов можно приступить к проверке данных в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="5224b-144">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="5224b-145">Возможности проверки отличаются в зависимости от того, был ли контент добавлен в стандартный набор обзоров или набор обзоров беседы.</span><span class="sxs-lookup"><span data-stu-id="5224b-145">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span>

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="5224b-146">Просмотр бесед в стандартном наборе обзоров</span><span class="sxs-lookup"><span data-stu-id="5224b-146">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="5224b-147">В стандартном наборе обзоров сообщения обрабатываются и отображаются как отдельные элементы, аналогичные тому, как они хранятся в папке почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="5224b-147">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="5224b-148">В этом рабочего процесса каждое сообщение обрабатывается как отдельный элемент.</span><span class="sxs-lookup"><span data-stu-id="5224b-148">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="5224b-149">В результате параметры потоковой сводки и экспорта недоступны в стандартном наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="5224b-149">As a result, the threaded summary and export options aren't available in a standard review set.</span></span>

  ![Стандартный набор обзоров](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="5224b-151">Просмотр бесед в наборе обзоров бесед</span><span class="sxs-lookup"><span data-stu-id="5224b-151">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="5224b-152">В наборе обзоров бесед отдельные сообщения совмещение и преподносясь как беседы.</span><span class="sxs-lookup"><span data-stu-id="5224b-152">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="5224b-153">Это позволяет просмотреть и экспортировать контекстные беседы.</span><span class="sxs-lookup"><span data-stu-id="5224b-153">This lets you review and export contextual conversations.</span></span>

  ![Набор обзоров беседы](../media/ConversationRSOptions.PNG)

<span data-ttu-id="5224b-155">В следующих разделах описаны обзор и экспорт бесед в наборе обзоров бесед.</span><span class="sxs-lookup"><span data-stu-id="5224b-155">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="5224b-156">Просмотр бесед</span><span class="sxs-lookup"><span data-stu-id="5224b-156">Reviewing conversations</span></span>

<span data-ttu-id="5224b-157">В наборе обзоров бесед можно использовать следующие параметры для облегчения процесса проверки.</span><span class="sxs-lookup"><span data-stu-id="5224b-157">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="5224b-158">**Группа по разговору:** Группировать сообщения в одной беседе вместе, чтобы помочь пользователям упростить и ускорить процесс проверки.</span><span class="sxs-lookup"><span data-stu-id="5224b-158">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span>

- <span data-ttu-id="5224b-159">**Сводное представление:** Отображает резьбовую беседу.</span><span class="sxs-lookup"><span data-stu-id="5224b-159">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="5224b-160">В этом представлении можно просмотреть весь разговор, а также получить доступ к метаданным для каждого отдельного сообщения.</span><span class="sxs-lookup"><span data-stu-id="5224b-160">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>

   - <span data-ttu-id="5224b-161">Просмотр метаданных для отдельных сообщений</span><span class="sxs-lookup"><span data-stu-id="5224b-161">View metadata for individual messages</span></span>

   - <span data-ttu-id="5224b-162">Скачивание отдельных сообщений</span><span class="sxs-lookup"><span data-stu-id="5224b-162">Download individual messages</span></span>

- <span data-ttu-id="5224b-163">**Представление текста:** Предоставляет извлеченный текст для всего разговора.</span><span class="sxs-lookup"><span data-stu-id="5224b-163">**Text view:** Provides the extracted text for the entire conversation.</span></span>

- <span data-ttu-id="5224b-164">**Аннотировать представление:** Позволяет разметку потокового представления беседы.</span><span class="sxs-lookup"><span data-stu-id="5224b-164">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="5224b-165">Все сообщения в беседе имеют один и тот же аннотированный документ.</span><span class="sxs-lookup"><span data-stu-id="5224b-165">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="5224b-166">**Теги:** При просмотре бесед в наборе обзоров можно просматривать и применять теги, щелкнув панель **Теги** в панели кодирования.</span><span class="sxs-lookup"><span data-stu-id="5224b-166">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="5224b-167">**Повторное преобразование беседы:** При добавлении сообщений в набор обзоров бесед автоматически запускается задание преобразования для создания потоковой сводки и аннотации представлений.</span><span class="sxs-lookup"><span data-stu-id="5224b-167">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="5224b-168">Если задание реконструкции беседы не удается, вы можете повторно использовать эту работу, нажав кнопку Action > Создать диалоговую **PDF в** наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="5224b-168">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="5224b-169">Экспорт разговоров</span><span class="sxs-lookup"><span data-stu-id="5224b-169">Exporting conversations</span></span>

<span data-ttu-id="5224b-170">В наборе обзоров бесед можно установить следующие параметры экспорта бесед:</span><span class="sxs-lookup"><span data-stu-id="5224b-170">In a conversation review set, you can set the following options to export conversations:</span></span>

![Экспорт вариантов для бесед](../media/export.png)

1. <span data-ttu-id="5224b-172">Параметры метаданных:</span><span class="sxs-lookup"><span data-stu-id="5224b-172">Metadata options:</span></span>
   - <span data-ttu-id="5224b-173">**Файл нагрузки:** Метаданные включены для каждого отдельного сообщения, электронной почты и документа.</span><span class="sxs-lookup"><span data-stu-id="5224b-173">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="5224b-174">Для каждого сообщения в беседе имеется одна строка.</span><span class="sxs-lookup"><span data-stu-id="5224b-174">There is one row for each message in a conversation.</span></span>
   - <span data-ttu-id="5224b-175">**Теги:** Теги из процесса проверки включены в файл метаданных.</span><span class="sxs-lookup"><span data-stu-id="5224b-175">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="5224b-176">Сообщения в беседе имеют одинаковые теги.</span><span class="sxs-lookup"><span data-stu-id="5224b-176">Messages in a conversation share the same tags.</span></span>

2. <span data-ttu-id="5224b-177">Параметры беседы:</span><span class="sxs-lookup"><span data-stu-id="5224b-177">Conversation options:</span></span>
   - <span data-ttu-id="5224b-178">**Файлы беседы:** При экспорте файлов беседы аннотированное представление преобразуется в файл PDF и загружается в папку экспорта.</span><span class="sxs-lookup"><span data-stu-id="5224b-178">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="5224b-179">Сообщения в одном файле беседы указывают на PDF-версию того же файла беседы.</span><span class="sxs-lookup"><span data-stu-id="5224b-179">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>
   - <span data-ttu-id="5224b-180">**Отдельные сообщения чата:** При экспорте отдельных сообщений каждое уникальное сообщение в беседе экспортируется в качестве отдельного элемента.</span><span class="sxs-lookup"><span data-stu-id="5224b-180">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="5224b-181">Файл экспортируется в том же формате, что и в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="5224b-181">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="5224b-182">Для определенного разговора вы получаете несколько файлов msg.</span><span class="sxs-lookup"><span data-stu-id="5224b-182">For a specific conversation, you receive multiple .msg files.</span></span>

     > [!NOTE]
     > <span data-ttu-id="5224b-183">Если вы применили аннотации к файлу беседы, эти аннотации не будут перенесены в отдельные сообщения.</span><span class="sxs-lookup"><span data-stu-id="5224b-183">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span>

3. <span data-ttu-id="5224b-184">Другие параметры:</span><span class="sxs-lookup"><span data-stu-id="5224b-184">Other options:</span></span>
   - <span data-ttu-id="5224b-185">**Создание текстовых файлов для всего экспортируемой содержимого:** Создает текстовый файл для каждого разговора, экспортируемой из набора отзывов.</span><span class="sxs-lookup"><span data-stu-id="5224b-185">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span>
   - <span data-ttu-id="5224b-186">**Замените экспортируемую контентную информацию на отредактировали PDF:** Если в процессе проверки создаются отредактированные файлы беседы, эти файлы доступны во время экспорта.</span><span class="sxs-lookup"><span data-stu-id="5224b-186">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="5224b-187">Можно определить, следует ли экспортировать только личные файлы (не выбрав этот параметр) или заменить личные файлы отредактными версиями родных файлов (выбрав этот параметр), экспорт которых экспортируется в формате PDF-файлов.</span><span class="sxs-lookup"><span data-stu-id="5224b-187">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="5224b-188">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="5224b-188">More information</span></span>

<span data-ttu-id="5224b-189">Дополнительные сведения о том, как просмотреть данные о Advanced eDiscovery, см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="5224b-189">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="5224b-190">Просмотр данных кейсов</span><span class="sxs-lookup"><span data-stu-id="5224b-190">View case data</span></span>](view-documents-in-review-set.md)
- [<span data-ttu-id="5224b-191">Анализ данных дела</span><span class="sxs-lookup"><span data-stu-id="5224b-191">Analyze case data</span></span>](analyzing-data-in-review-set.md)
- [<span data-ttu-id="5224b-192">Экспорт данных дела</span><span class="sxs-lookup"><span data-stu-id="5224b-192">Export case data</span></span>](exporting-data-ediscover20.md)
