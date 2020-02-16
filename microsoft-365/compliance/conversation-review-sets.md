---
title: Обзор бесед в Advanced eDiscovery
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
description: ''
ms.openlocfilehash: 01f2e6f9ceccd1903f62e8661f2cfc8f4cc2b47e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078151"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="39b7b-102">Обзор бесед в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="39b7b-102">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="39b7b-103">Обмен мгновенными сообщениями это удобный способ задать вопросы, обмениваться идеями или быстро общаться по большим группам.</span><span class="sxs-lookup"><span data-stu-id="39b7b-103">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="39b7b-104">Как платформы обмена мгновенными сообщениями, такие как Microsoft Teams, становятся основой для совместной работы в корпоративной среде, организациям необходимо оценить, как их рабочие процессы обнаружения электронных данных посвящены новым формам общения</span><span class="sxs-lookup"><span data-stu-id="39b7b-104">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="39b7b-105">Функция реконструкции беседы в Advanced eDiscovery предназначена для идентификации контекстного содержимого и создания отдельных представлений бесед.</span><span class="sxs-lookup"><span data-stu-id="39b7b-105">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="39b7b-106">Эта возможность позволяет эффективно и быстро просматривать полные беседы по обмену мгновенными сообщениями (также называемые *цепочки*обсуждений), которые создаются на таких платформах, как Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="39b7b-106">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="39b7b-107">С помощью функции реконструкции бесед можно создавать, просматривать и экспортировать цепочки обсуждений с помощью встроенных возможностей.</span><span class="sxs-lookup"><span data-stu-id="39b7b-107">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="39b7b-108">Используйте расширенную реконструкции беседы обнаружения электронных данных, чтобы:</span><span class="sxs-lookup"><span data-stu-id="39b7b-108">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="39b7b-109">Сохранять уникальные метаданные уровня сообщения для всех сообщений в беседе.</span><span class="sxs-lookup"><span data-stu-id="39b7b-109">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="39b7b-110">Сбор контекстных сообщений для результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="39b7b-110">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="39b7b-111">Просмотр, комментирование и редактирование потоков обсуждений.</span><span class="sxs-lookup"><span data-stu-id="39b7b-111">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="39b7b-112">Экспорт отдельных сообщений или цепочки обсуждений</span><span class="sxs-lookup"><span data-stu-id="39b7b-112">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="39b7b-113">Терминология</span><span class="sxs-lookup"><span data-stu-id="39b7b-113">Terminology</span></span>

<span data-ttu-id="39b7b-114">Ниже приведено несколько определений, которые помогут начать работу с реконструкции бесед.</span><span class="sxs-lookup"><span data-stu-id="39b7b-114">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="39b7b-115">**Сообщения:** Представляет наименьшую единицу беседы.</span><span class="sxs-lookup"><span data-stu-id="39b7b-115">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="39b7b-116">Сообщения могут отличаться в зависимости от размера, структуры и метаданных.</span><span class="sxs-lookup"><span data-stu-id="39b7b-116">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="39b7b-117">**Беседа:** Представляет группу из одного или нескольких сообщений.</span><span class="sxs-lookup"><span data-stu-id="39b7b-117">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="39b7b-118">В разных приложениях беседы могут быть представлены различными способами.</span><span class="sxs-lookup"><span data-stu-id="39b7b-118">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="39b7b-119">В некоторых приложениях существует явное действие, которое вызывается при ответе на существующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="39b7b-119">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="39b7b-120">Беседы формируются в явном виде в результате этого действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="39b7b-120">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="39b7b-121">Например, ниже приведен снимок экрана беседы с каналом в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="39b7b-121">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Беседа с каналом Microsoft Teams](../media/threadedchat.png)

   <span data-ttu-id="39b7b-123">В других приложениях (например, в 1xN сообщениях чата в Teams) не существует формальной цепочки ответа, а сообщения отображаются как "плоское Ривер сообщений" в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="39b7b-123">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="39b7b-124">В этих типах приложений беседы выводятся из группы сообщений, происходящих в течение определенного времени.</span><span class="sxs-lookup"><span data-stu-id="39b7b-124">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="39b7b-125">Это "мягкое" Группирование сообщений (в отличие от цепочки ответа) представляет собой обсуждение с определенной темой.</span><span class="sxs-lookup"><span data-stu-id="39b7b-125">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="39b7b-126">Шаг 1: выполнение поиска</span><span class="sxs-lookup"><span data-stu-id="39b7b-126">Step 1: Run a search</span></span>

<span data-ttu-id="39b7b-127">После определения соответствующих custodians и расположений содержимого можно создать поиск для поиска потенциально релевантного контента.</span><span class="sxs-lookup"><span data-stu-id="39b7b-127">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="39b7b-128">На вкладке **поиски** в расширенном случае обнаружения электронных данных можно создать поиск, нажав кнопку **Новый поиск** и следуя инструкциям мастера.</span><span class="sxs-lookup"><span data-stu-id="39b7b-128">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="39b7b-129">Сведения о том, как создавать поисковый запрос, создавать поисковый запрос и просматривать результаты поиска, можно узнать [в статье сбор данных для обращения](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="39b7b-129">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="39b7b-130">Шаг 2: создание набора проверки беседы</span><span class="sxs-lookup"><span data-stu-id="39b7b-130">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="39b7b-131">В наборе рецензирования можно искать, помечать, аннотировать и изменять документы, сообщения электронной почты и беседы в чате.</span><span class="sxs-lookup"><span data-stu-id="39b7b-131">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="39b7b-132">В Advanced eDiscovery вы можете настроить проверку бесед, используя отдельные сообщения или цепочки обсуждений.</span><span class="sxs-lookup"><span data-stu-id="39b7b-132">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="39b7b-133">Это определяется типом набора проверки, который добавляет результаты поиска, созданного на шаге 1, в.</span><span class="sxs-lookup"><span data-stu-id="39b7b-133">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="39b7b-134">Существует два вида наборов проверки:</span><span class="sxs-lookup"><span data-stu-id="39b7b-134">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="39b7b-135">**Стандартные наборы проверки:** Сообщения в беседах обрабатываются и отображаются как отдельные элементы.</span><span class="sxs-lookup"><span data-stu-id="39b7b-135">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="39b7b-136">**Наборы проверки беседы:** Сообщения в беседах обрабатываются по отдельности, но отображаются в представлении беседы.</span><span class="sxs-lookup"><span data-stu-id="39b7b-136">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="39b7b-137">В наборе проверки бесед можно закомментировать, пометить и исправить сообщения в связанном представлении беседы.</span><span class="sxs-lookup"><span data-stu-id="39b7b-137">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="39b7b-138">Дополнительные сведения о том, как просматривать контент в наборе рецензирования и управлять им, можно найти в разделе [Управление наборами проверки](managing-review-sets.md).</span><span class="sxs-lookup"><span data-stu-id="39b7b-138">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="39b7b-139">Шаг 3: включение параметров получения беседы</span><span class="sxs-lookup"><span data-stu-id="39b7b-139">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="39b7b-140">После просмотра и завершения запроса поиска можно добавить результаты поиска в набор проверки.</span><span class="sxs-lookup"><span data-stu-id="39b7b-140">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="39b7b-141">При добавлении результатов поиска в набор проверки исходные данные копируются в область хранилища Azure, чтобы упростить процесс просмотра и анализа.</span><span class="sxs-lookup"><span data-stu-id="39b7b-141">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="39b7b-142">Дополнительные сведения о добавлении результатов поиска в набор рецензирования можно найти в статье [Добавление результатов поиска в набор рецензирования](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="39b7b-142">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="39b7b-143">Когда вы добавляете данные из бесед в набор проверки, вы можете использовать параметры извлечения беседы для расширения поиска и включения контекстных сообщений.</span><span class="sxs-lookup"><span data-stu-id="39b7b-143">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="39b7b-144">После настройки параметров извлечения беседы могут происходить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="39b7b-144">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![Получение беседы](../media/messagesandconversations.png)
  
1. <span data-ttu-id="39b7b-146">При использовании ключевого слова и запроса с диапазоном дат в *сообщении 3*будет возвращено совпадение поиска.</span><span class="sxs-lookup"><span data-stu-id="39b7b-146">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="39b7b-147">Это сообщение было частью большой беседы, которое проиллюстрировано *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="39b7b-147">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="39b7b-148">Когда вы добавляете данные в набор проверки и включаете параметры получения беседы, Расширенное обнаружение электронных данных перейдет назад и соберет другие элементы в *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="39b7b-148">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="39b7b-149">После добавления элементов в набор проверки можно просмотреть все отдельные сообщения из *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="39b7b-149">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 



<span data-ttu-id="39b7b-150">Чтобы включить извлечение бесед:</span><span class="sxs-lookup"><span data-stu-id="39b7b-150">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="39b7b-151">На вкладке **поиски** в расширенном случае обнаружения электронных данных выберите Поиск, а затем нажмите кнопку **Добавить, чтобы просмотреть набор** на всплывающей странице.</span><span class="sxs-lookup"><span data-stu-id="39b7b-151">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="39b7b-152">Выберите существующий набор рецензирования или создайте набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="39b7b-152">Select an existing review set or create a review set.</span></span> <span data-ttu-id="39b7b-153">Вы можете настроить параметры извлечения при добавлении результатов поиска в стандартный или в набор проверки беседы.</span><span class="sxs-lookup"><span data-stu-id="39b7b-153">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="39b7b-154">В разделе **Параметры коллекции**настройте параметры извлечения бесед для источников контента, которые необходимо расширить в поиске, а затем нажмите кнопку **Добавить** , чтобы запустить процесс.</span><span class="sxs-lookup"><span data-stu-id="39b7b-154">Under **Collection options**, configure the conversation retrieval options for the content sources that you want to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="39b7b-155">После завершения задания **Add to Review Set** на вкладке **задания** можно начать просмотр бесед.</span><span class="sxs-lookup"><span data-stu-id="39b7b-155">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-conversations-in-the-review-set"></a><span data-ttu-id="39b7b-156">Шаг 4: Проверка бесед в наборе рецензирования</span><span class="sxs-lookup"><span data-stu-id="39b7b-156">Step 4: Review conversations in the review set</span></span>

<span data-ttu-id="39b7b-157">После того как содержимое было обработано и Добавлено в набор рецензирования, можно начать просмотр данных в наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="39b7b-157">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="39b7b-158">Возможности рецензирования различаются в зависимости от того, было ли содержимое добавлено в стандартный набор проверки или в набор проверки беседы.</span><span class="sxs-lookup"><span data-stu-id="39b7b-158">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="39b7b-159">Просмотр бесед в стандартном наборе рецензирования</span><span class="sxs-lookup"><span data-stu-id="39b7b-159">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="39b7b-160">В стандартном наборе проверки сообщения обрабатываются и отображаются как отдельные элементы, аналогично тому, как они хранятся в папке почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="39b7b-160">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="39b7b-161">В этом рабочем процессе каждое сообщение обрабатывается как отдельный элемент.</span><span class="sxs-lookup"><span data-stu-id="39b7b-161">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="39b7b-162">В результате этого сводные данные и параметры экспорта недоступны в стандартном наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="39b7b-162">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

  ![Стандартный набор проверки](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="39b7b-164">Просмотр бесед в наборе проверки беседы</span><span class="sxs-lookup"><span data-stu-id="39b7b-164">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="39b7b-165">В наборе проверки беседы отдельные сообщения объединяются в цепочки и представляются как беседы.</span><span class="sxs-lookup"><span data-stu-id="39b7b-165">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="39b7b-166">Это позволяет просматривать и экспортировать контекстные беседы.</span><span class="sxs-lookup"><span data-stu-id="39b7b-166">This lets you review and export contextual conversations.</span></span> 

  ![Набор проверки беседы](../media/ConversationRSOptions.PNG)

<span data-ttu-id="39b7b-168">В следующих разделах описывается просмотр и экспорт бесед в наборе проверки беседы.</span><span class="sxs-lookup"><span data-stu-id="39b7b-168">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="39b7b-169">Рецензирование бесед</span><span class="sxs-lookup"><span data-stu-id="39b7b-169">Reviewing conversations</span></span>

<span data-ttu-id="39b7b-170">В наборе проверки беседы можно использовать следующие параметры для упрощения процесса проверки.</span><span class="sxs-lookup"><span data-stu-id="39b7b-170">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="39b7b-171">**Группировка по беседам:** Группирует сообщения в одном сеансе, чтобы упростить и ускорить процесс проверки.</span><span class="sxs-lookup"><span data-stu-id="39b7b-171">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="39b7b-172">**Представление сводки:** Отображает цепочку обсуждений.</span><span class="sxs-lookup"><span data-stu-id="39b7b-172">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="39b7b-173">В этом представлении вы можете видеть все беседы, а также получать доступ к метаданным для каждого отдельного сообщения.</span><span class="sxs-lookup"><span data-stu-id="39b7b-173">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="39b7b-174">Просмотр метаданных для отдельных сообщений</span><span class="sxs-lookup"><span data-stu-id="39b7b-174">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="39b7b-175">Загрузка отдельных сообщений</span><span class="sxs-lookup"><span data-stu-id="39b7b-175">Download individual messages</span></span>

- <span data-ttu-id="39b7b-176">**Представление текста:** Предоставляет извлеченный текст для всей беседы.</span><span class="sxs-lookup"><span data-stu-id="39b7b-176">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="39b7b-177">**Представление "Примечания":** Позволяет разметку обсуждения в потоковом представлении.</span><span class="sxs-lookup"><span data-stu-id="39b7b-177">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="39b7b-178">Все сообщения в беседе используют один и тот же документ с аннотациями.</span><span class="sxs-lookup"><span data-stu-id="39b7b-178">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="39b7b-179">**Маркировка:** При просмотре бесед в наборе рецензирования можно просматривать и применять теги, щелкая **панель маркировки** в панели "код".</span><span class="sxs-lookup"><span data-stu-id="39b7b-179">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="39b7b-180">**Повторное выполнение преобразования беседы:** При добавлении сообщений в набор проверки беседы автоматически запускается задание преобразования, чтобы создать потоковые представления сводки и примечаний.</span><span class="sxs-lookup"><span data-stu-id="39b7b-180">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="39b7b-181">Если не удается выполнить задачу реконструкции беседы, можно повторно запустить это задание, нажав кнопку **действие > создать документы PDF для беседы** в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="39b7b-181">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>


#### <a name="exporting-conversations"></a><span data-ttu-id="39b7b-182">Экспорт бесед</span><span class="sxs-lookup"><span data-stu-id="39b7b-182">Exporting conversations</span></span>

<span data-ttu-id="39b7b-183">В наборе проверки беседы можно задать следующие параметры для экспорта бесед:</span><span class="sxs-lookup"><span data-stu-id="39b7b-183">In a conversation review set, you can set the following options to export conversations:</span></span>

![Экспорт](../media/export.png)

<span data-ttu-id="39b7b-185">а.</span><span class="sxs-lookup"><span data-stu-id="39b7b-185">a.</span></span> <span data-ttu-id="39b7b-186">Параметры метаданных</span><span class="sxs-lookup"><span data-stu-id="39b7b-186">Metadata options</span></span>

   - <span data-ttu-id="39b7b-187">**Загрузка файла:** Метаданные включены для каждого отдельного сообщения, электронной почты и документа.</span><span class="sxs-lookup"><span data-stu-id="39b7b-187">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="39b7b-188">Для каждого сообщения в беседе существует одна строка.</span><span class="sxs-lookup"><span data-stu-id="39b7b-188">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="39b7b-189">**Теги:** Теги из процесса проверки включены в файл метаданных.</span><span class="sxs-lookup"><span data-stu-id="39b7b-189">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="39b7b-190">Сообщения в беседе используют одни и те же теги.</span><span class="sxs-lookup"><span data-stu-id="39b7b-190">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="39b7b-191">б.</span><span class="sxs-lookup"><span data-stu-id="39b7b-191">b.</span></span> <span data-ttu-id="39b7b-192">Параметры беседы</span><span class="sxs-lookup"><span data-stu-id="39b7b-192">Conversation options</span></span>
  
   - <span data-ttu-id="39b7b-193">**Файлы беседы:** При экспорте файлов бесед представление с заметками преобразуется в PDF-файл и загружается в папку экспорта.</span><span class="sxs-lookup"><span data-stu-id="39b7b-193">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="39b7b-194">Сообщения в одном файле беседы указывает на PDF-версию того же файла беседы.</span><span class="sxs-lookup"><span data-stu-id="39b7b-194">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="39b7b-195">**Отдельные сообщения чата:** При экспорте отдельных сообщений каждое уникальное сообщение в беседе экспортируется как автономный элемент.</span><span class="sxs-lookup"><span data-stu-id="39b7b-195">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="39b7b-196">Файл экспортируется в том же формате, в котором он был сохранен, как в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="39b7b-196">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="39b7b-197">Для конкретной беседы вы получаете несколько файлов. MSG.</span><span class="sxs-lookup"><span data-stu-id="39b7b-197">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="39b7b-198">Если вы применили заметки к файлу беседы, эти заметки не будут передаваться в отдельные сообщения.</span><span class="sxs-lookup"><span data-stu-id="39b7b-198">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="39b7b-199">в.</span><span class="sxs-lookup"><span data-stu-id="39b7b-199">c.</span></span> <span data-ttu-id="39b7b-200">Другие варианты</span><span class="sxs-lookup"><span data-stu-id="39b7b-200">Other options</span></span>

   - <span data-ttu-id="39b7b-201">**Создание текстовых файлов для всего экспортированного контента:** Создает текстовый файл для каждого диалога, экспортированного из набора рецензирования.</span><span class="sxs-lookup"><span data-stu-id="39b7b-201">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="39b7b-202">**Замените экспортированный контент на отредактировал PDF:** Если в процессе проверки создаются файлы беседы отредактировал, эти файлы доступны во время экспорта.</span><span class="sxs-lookup"><span data-stu-id="39b7b-202">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="39b7b-203">Вы можете выбрать, следует ли экспортировать только собственные файлы (не выбрав этот параметр) или заменить собственные файлы версиями отредактировал (выбрав этот параметр), которые будут экспортированы в виде PDF-файлов.</span><span class="sxs-lookup"><span data-stu-id="39b7b-203">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="39b7b-204">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="39b7b-204">More information</span></span>

<span data-ttu-id="39b7b-205">Чтобы узнать больше о том, как просматривать данные о делах в Advanced eDiscovery, ознакомьтесь со следующими статьями:</span><span class="sxs-lookup"><span data-stu-id="39b7b-205">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="39b7b-206">Просмотр данных обращений</span><span class="sxs-lookup"><span data-stu-id="39b7b-206">View case data</span></span>](view-documents-in-review-set.md) 

- [<span data-ttu-id="39b7b-207">Анализ данных дела</span><span class="sxs-lookup"><span data-stu-id="39b7b-207">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="39b7b-208">Экспорт данных дела</span><span class="sxs-lookup"><span data-stu-id="39b7b-208">Export case data</span></span>](exporting-data-ediscover20.md)
