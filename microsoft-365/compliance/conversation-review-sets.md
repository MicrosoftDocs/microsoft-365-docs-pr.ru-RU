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
description: Узнайте, как использовать функцию реконструкции бесед в Advanced eDiscovery для восстановления, просмотра и экспорта бесед.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf5c39f567240b58546dbeb353e3e461e9b69e48
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358347"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="2c1f6-103">Просмотр бесед в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2c1f6-103">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="2c1f6-104">Обмен мгновенными сообщениями — это удобный способ задать вопросы, поделиться идеями или быстро обмениваться идеями с широкой аудиторией.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="2c1f6-105">По мере того как платформы обмена мгновенными сообщениями, такие как Microsoft Teams, становятся основными для совместной работы предприятия, организации должны оценить, как их рабочий процесс eDiscovery адресует эти новые формы взаимодействия и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-105">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="2c1f6-106">Функция реконструкции бесед в Advanced eDiscovery предназначена для определения контекстного содержимого и создания отдельных представлений бесед.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="2c1f6-107">Эта возможность позволяет эффективно и быстро просмотреть полные мгновенные сообщения (также называемые цепочками *бесед),* которые создаются на таких платформах, как Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="2c1f6-108">С помощью реконструкции бесед можно использовать встроенные возможности для воссоздание, просмотра и экспорта бесед.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="2c1f6-109">Использование реконструкции беседы Advanced eDiscovery для:</span><span class="sxs-lookup"><span data-stu-id="2c1f6-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="2c1f6-110">Сохранение уникальных метаданных на уровне сообщений во всех сообщениях в беседе.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="2c1f6-111">Сбор контекстных сообщений вокруг результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="2c1f6-112">Просмотр, аннотации и отредактировать беседы с потоками.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="2c1f6-113">Экспорт отдельных сообщений или бесед с цепочками</span><span class="sxs-lookup"><span data-stu-id="2c1f6-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="2c1f6-114">Терминология</span><span class="sxs-lookup"><span data-stu-id="2c1f6-114">Terminology</span></span>

<span data-ttu-id="2c1f6-115">Вот несколько определений, которые помогут вам приступить к использованию реконструкции беседы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="2c1f6-116">**Сообщения:** Представляет наименьшую единицу беседы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="2c1f6-117">Размер, структура и метаданные сообщений могут отличаться.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-117">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="2c1f6-118">**Беседа:** Представляет группировку одного или более сообщений.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="2c1f6-119">В разных приложениях беседы могут быть представлены различными способами.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="2c1f6-120">В некоторых приложениях существует явное действие, которое приводит к ответу на существующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="2c1f6-121">Беседы формируются явно в результате этого действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="2c1f6-122">Например, вот снимок экрана с беседой канала в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Беседа на канале Microsoft Teams](../media/threadedchat.png)

   <span data-ttu-id="2c1f6-124">В других приложениях (например, сообщениях чата 1xN в Teams) нет формальной цепочки ответов, а вместо этого сообщения отображаются как "плоская речка сообщений" в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="2c1f6-125">В приложениях этих типов беседы высмеяются из группы сообщений, которые происходят в течение определенного времени.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="2c1f6-126">Такая "мягкая группировка" сообщений (в отличие от цепочки ответов) представляет беседу "назад и вперед" по интересующих вас темах.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="2c1f6-127">Шаг 1. Запуск поиска</span><span class="sxs-lookup"><span data-stu-id="2c1f6-127">Step 1: Run a search</span></span>

<span data-ttu-id="2c1f6-128">После того как вы определили релевантные хранители и расположения контента, вы можете создать поиск потенциально релевантной информации.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="2c1f6-129">На **вкладке "Поиск"** в деле Advanced eDiscovery можно создать поиск, нажав кнопку **"Создать поиск"** и следуя за мастером.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-129">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="2c1f6-130">Сведения о том, как создать поиск, создать поисковый запрос и просмотреть результаты поиска, см. в подстройки ["Сбор данных для дела".](create-search-to-collect-data.md)</span><span class="sxs-lookup"><span data-stu-id="2c1f6-130">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="2c1f6-131">Шаг 2. Создание набора для проверки беседы</span><span class="sxs-lookup"><span data-stu-id="2c1f6-131">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="2c1f6-132">В наборе для проверки можно искать, помечать, примечать и редактировать документы, сообщения электронной почты и беседы чата.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-132">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="2c1f6-133">В Advanced eDiscovery можно настроить просмотр бесед на основе отдельных сообщений или бесед.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-133">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="2c1f6-134">Это определяется типом набора для проверки, в который добавляются результаты поиска, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-134">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="2c1f6-135">Существует два разных типа наборов для проверки:</span><span class="sxs-lookup"><span data-stu-id="2c1f6-135">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="2c1f6-136">**Стандартные наборы для проверки:** Сообщения в беседах обрабатываются и отображаются как отдельные элементы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-136">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="2c1f6-137">**Наборы для просмотра беседы:** Сообщения в беседах обрабатываются по отдельности, но отображаются в представлении беседы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-137">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="2c1f6-138">В наборе для проверки беседы можно отмечать, помечать и редактировать сообщения в потоковом представлении беседы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-138">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="2c1f6-139">Дополнительные сведения о том, как просмотреть контент в наборе для проверки и управлять им, см. в документе ["Управление наборами отзывов".](managing-review-sets.md)</span><span class="sxs-lookup"><span data-stu-id="2c1f6-139">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="2c1f6-140">Шаг 3. Включить параметры и получить беседу</span><span class="sxs-lookup"><span data-stu-id="2c1f6-140">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="2c1f6-141">После проверки и завершения поискового запроса вы можете добавить результаты поиска в набор для проверки.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-141">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="2c1f6-142">При добавлении результатов поиска в набор для проверки исходные данные копируется в хранилище Azure для упрощения процесса проверки и анализа.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-142">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="2c1f6-143">Дополнительные сведения о добавлении результатов поиска в набор для проверки см. в подстройки "Добавление результатов поиска [в набор для проверки".](add-data-to-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="2c1f6-143">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="2c1f6-144">При добавлении данных из бесед в набор для проверки вы можете использовать параметры ищите беседы для расширения поиска и добавления контекстных сообщений.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-144">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="2c1f6-145">После настройки параметров ирисовки беседы могут произойти следующие вещи:</span><span class="sxs-lookup"><span data-stu-id="2c1f6-145">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![Ирисовка беседы](../media/messagesandconversations.png)
  
1. <span data-ttu-id="2c1f6-147">С помощью запроса по ключевому слову и диапазону дат поиск вернул сообщение *3.*</span><span class="sxs-lookup"><span data-stu-id="2c1f6-147">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="2c1f6-148">Это сообщение было частью более крупной беседы, иллюстрированной *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="2c1f6-148">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="2c1f6-149">Когда вы добавляете данные в набор для проверки и включаете параметры иска беседы, Advanced eDiscovery возвращается и собирает другие элементы в *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="2c1f6-149">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="2c1f6-150">После того как элементы будут добавлены в набор для проверки, вы можете просмотреть все отдельные сообщения из *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="2c1f6-150">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 

<span data-ttu-id="2c1f6-151">Чтобы включить и получить беседу:</span><span class="sxs-lookup"><span data-stu-id="2c1f6-151">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="2c1f6-152">На **вкладке "Поиск"** в деле Advanced eDiscovery выберите поиск, а затем нажмите кнопку "Добавить для **проверки", задав** флажок на странице".</span><span class="sxs-lookup"><span data-stu-id="2c1f6-152">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="2c1f6-153">Выберите существующий набор для проверки или создайте набор для проверки.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-153">Select an existing review set or create a review set.</span></span> <span data-ttu-id="2c1f6-154">Параметры ищите можно настроить при добавлении результатов поиска в стандартный набор или набор для просмотра бесед.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-154">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="2c1f6-155">В **параметрах коллекции** настройте параметры и получения бесед для источников контента, которые нужно развернуть в поиске, а затем нажмите кнопку **"Добавить",** чтобы начать процесс.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-155">Under **Collection options**, configure the conversation retrieval options for the content sources that you want to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="2c1f6-156">После завершения **задания "Добавить для проверки"** на вкладке **"Задания"** можно начать просмотр бесед.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-156">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-and-export-conversations-in-a-review-set"></a><span data-ttu-id="2c1f6-157">Шаг 4. Просмотр и экспорт бесед в наборе для проверки</span><span class="sxs-lookup"><span data-stu-id="2c1f6-157">Step 4: Review and export conversations in a review set</span></span>

<span data-ttu-id="2c1f6-158">После обработки контента и его добавления в набор для проверки можно приступить к просмотру данных в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-158">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="2c1f6-159">Возможности проверки отличаются в зависимости от того, было ли содержимое добавлено в стандартный набор для проверки или набор анализа бесед.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-159">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="2c1f6-160">Просмотр бесед в стандартном наборе для проверки</span><span class="sxs-lookup"><span data-stu-id="2c1f6-160">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="2c1f6-161">В стандартном наборе для проверки сообщения обрабатываются и отображаются как отдельные элементы, аналогично хранимые в папке почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-161">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="2c1f6-162">В этом рабочий процесс каждое сообщение обрабатывается как отдельный элемент.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-162">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="2c1f6-163">В результате потоковые параметры сводки и экспорта недоступны в стандартном наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-163">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

  ![Стандартный набор для проверки](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="2c1f6-165">Просмотр бесед в наборе для проверки бесед</span><span class="sxs-lookup"><span data-stu-id="2c1f6-165">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="2c1f6-166">В наборе для просмотра бесед отдельные сообщения объединяется и представляются как беседы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-166">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="2c1f6-167">Это позволяет просмотреть и экспортировать контекстные беседы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-167">This lets you review and export contextual conversations.</span></span> 

  ![Набор для проверки беседы](../media/ConversationRSOptions.PNG)

<span data-ttu-id="2c1f6-169">В следующих разделах описывается просмотр и экспорт бесед в наборе для проверки бесед.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-169">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="2c1f6-170">Просмотр бесед</span><span class="sxs-lookup"><span data-stu-id="2c1f6-170">Reviewing conversations</span></span>

<span data-ttu-id="2c1f6-171">В наборе для проверки беседы можно использовать следующие параметры для упрощения процесса проверки.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-171">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="2c1f6-172">**Группировка по беседе:** Группировать сообщения в одной беседе, чтобы упростить и ускорить процесс проверки.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-172">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="2c1f6-173">**Сводное представление:** Отображает цепочку беседы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-173">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="2c1f6-174">В этом представлении можно просмотреть всю беседу, а также получить доступ к метаданным для каждого отдельного сообщения.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-174">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="2c1f6-175">Просмотр метаданных для отдельных сообщений</span><span class="sxs-lookup"><span data-stu-id="2c1f6-175">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="2c1f6-176">Скачивание отдельных сообщений</span><span class="sxs-lookup"><span data-stu-id="2c1f6-176">Download individual messages</span></span>

- <span data-ttu-id="2c1f6-177">**Текстовое представление:** Предоставляет извлеченный текст для всей беседы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-177">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="2c1f6-178">**Представление "Аннотировать":** Позволяет разметить потоковые представления беседы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-178">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="2c1f6-179">Все сообщения в беседе имеют один и тот же документ с заносями.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-179">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="2c1f6-180">**Добавление тегов:** При просмотре бесед в наборе для проверки можно просматривать и применять теги, щелкнув панель тегов **на** панели кодирования.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-180">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="2c1f6-181">**Повторное преобразование беседы:** При добавлении сообщений в набор для проверки бесед автоматически запускается задание преобразования для создания потоковой сводки и создания заносок в представления.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-181">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="2c1f6-182">Если задание реконструкции беседы не удается, вы можете повторно его перезапись, нажав кнопку **Action > Create conversation PDFs** in the review set.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-182">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="2c1f6-183">Экспорт бесед</span><span class="sxs-lookup"><span data-stu-id="2c1f6-183">Exporting conversations</span></span>

<span data-ttu-id="2c1f6-184">В наборе для проверки бесед можно настроить следующие параметры экспорта бесед:</span><span class="sxs-lookup"><span data-stu-id="2c1f6-184">In a conversation review set, you can set the following options to export conversations:</span></span>

![Параметры экспорта для бесед](../media/export.png)

<span data-ttu-id="2c1f6-186">а.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-186">a.</span></span> <span data-ttu-id="2c1f6-187">Параметры метаданных</span><span class="sxs-lookup"><span data-stu-id="2c1f6-187">Metadata options</span></span>

   - <span data-ttu-id="2c1f6-188">**Загрузим файл:** Метаданные включаются для каждого отдельного сообщения, электронной почты и документа.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-188">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="2c1f6-189">Для каждого сообщения в беседе есть одна строка.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-189">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="2c1f6-190">**Теги:** Теги из процесса проверки включаются в файл метаданных.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-190">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="2c1f6-191">Сообщения в беседе имеют одинаковые теги.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-191">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="2c1f6-192">б.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-192">b.</span></span> <span data-ttu-id="2c1f6-193">Параметры беседы</span><span class="sxs-lookup"><span data-stu-id="2c1f6-193">Conversation options</span></span>
  
   - <span data-ttu-id="2c1f6-194">**Файлы беседы:** При экспорте файлов бесед представление с заносом преобразуется в PDF-файл и загружается в папку экспорта.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-194">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="2c1f6-195">Сообщения в одном файле беседы указывают на PDF-версию того же файла беседы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-195">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="2c1f6-196">**Отдельные сообщения чата:** При экспорте отдельных сообщений каждое уникальное сообщение в беседе экспортируется как отдельный элемент.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-196">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="2c1f6-197">Файл экспортируется в том же формате, что и в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-197">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="2c1f6-198">Для конкретной беседы вы получаете несколько MSG-файлов.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-198">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="2c1f6-199">Если вы применили примечания к файлу беседы, эти примечания не будут перенесены в отдельные сообщения.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-199">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="2c1f6-200">в.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-200">c.</span></span> <span data-ttu-id="2c1f6-201">Другие параметры</span><span class="sxs-lookup"><span data-stu-id="2c1f6-201">Other options</span></span>

   - <span data-ttu-id="2c1f6-202">**Создание текстовых файлов для всего экспортируемой информации:** Создает текстовый файл для каждой беседы, экспортируемой из набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-202">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="2c1f6-203">**Замените экспортируемую информацию на отредактировали PDFs:** Если в процессе проверки создаются отредактные файлы бесед, то эти файлы доступны во время экспорта.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-203">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="2c1f6-204">Вы можете определить, следует ли экспортировать только встроенные файлы (не выбрав этот параметр) или заменить их на отредактировали версии встроенных файлов (выбрав этот параметр), которые экспортируются как PDF-файлы.</span><span class="sxs-lookup"><span data-stu-id="2c1f6-204">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="2c1f6-205">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="2c1f6-205">More information</span></span>

<span data-ttu-id="2c1f6-206">Дополнительные сведения о проверке данных дела в Advanced eDiscovery см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="2c1f6-206">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="2c1f6-207">Просмотр данных дела</span><span class="sxs-lookup"><span data-stu-id="2c1f6-207">View case data</span></span>](view-documents-in-review-set.md)

- [<span data-ttu-id="2c1f6-208">Анализ данных дела</span><span class="sxs-lookup"><span data-stu-id="2c1f6-208">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="2c1f6-209">Экспорт данных дела</span><span class="sxs-lookup"><span data-stu-id="2c1f6-209">Export case data</span></span>](exporting-data-ediscover20.md)
