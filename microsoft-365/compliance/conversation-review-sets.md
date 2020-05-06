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
description: Узнайте, как использовать функцию реконструкции беседы в Advanced eDiscovery для реорганизации, просмотра и экспорта связанных обсуждений.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 45cf4bdbf0956ee28e75878b7db5ec84b81c7230
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035497"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="1496a-103">Обзор бесед в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1496a-103">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="1496a-104">Обмен мгновенными сообщениями это удобный способ задать вопросы, обмениваться идеями или быстро общаться по большим группам.</span><span class="sxs-lookup"><span data-stu-id="1496a-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="1496a-105">Как платформы обмена мгновенными сообщениями, такие как Microsoft Teams, становятся основой для совместной работы в корпоративной среде, организациям необходимо оценить, как их рабочие процессы обнаружения электронных данных посвящены новым формам общения</span><span class="sxs-lookup"><span data-stu-id="1496a-105">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="1496a-106">Функция реконструкции беседы в Advanced eDiscovery предназначена для идентификации контекстного содержимого и создания отдельных представлений бесед.</span><span class="sxs-lookup"><span data-stu-id="1496a-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="1496a-107">Эта возможность позволяет эффективно и быстро просматривать полные беседы по обмену мгновенными сообщениями (также называемые *цепочки*обсуждений), которые создаются на таких платформах, как Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1496a-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="1496a-108">С помощью функции реконструкции бесед можно создавать, просматривать и экспортировать цепочки обсуждений с помощью встроенных возможностей.</span><span class="sxs-lookup"><span data-stu-id="1496a-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="1496a-109">Используйте расширенную реконструкции беседы обнаружения электронных данных, чтобы:</span><span class="sxs-lookup"><span data-stu-id="1496a-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="1496a-110">Сохранять уникальные метаданные уровня сообщения для всех сообщений в беседе.</span><span class="sxs-lookup"><span data-stu-id="1496a-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="1496a-111">Сбор контекстных сообщений для результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="1496a-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="1496a-112">Просмотр, комментирование и редактирование потоков обсуждений.</span><span class="sxs-lookup"><span data-stu-id="1496a-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="1496a-113">Экспорт отдельных сообщений или цепочки обсуждений</span><span class="sxs-lookup"><span data-stu-id="1496a-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="1496a-114">Терминология</span><span class="sxs-lookup"><span data-stu-id="1496a-114">Terminology</span></span>

<span data-ttu-id="1496a-115">Ниже приведено несколько определений, которые помогут начать работу с реконструкции бесед.</span><span class="sxs-lookup"><span data-stu-id="1496a-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="1496a-116">**Сообщения:** Представляет наименьшую единицу беседы.</span><span class="sxs-lookup"><span data-stu-id="1496a-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="1496a-117">Сообщения могут отличаться в зависимости от размера, структуры и метаданных.</span><span class="sxs-lookup"><span data-stu-id="1496a-117">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="1496a-118">**Беседа:** Представляет группу из одного или нескольких сообщений.</span><span class="sxs-lookup"><span data-stu-id="1496a-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="1496a-119">В разных приложениях беседы могут быть представлены различными способами.</span><span class="sxs-lookup"><span data-stu-id="1496a-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="1496a-120">В некоторых приложениях существует явное действие, которое вызывается при ответе на существующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="1496a-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="1496a-121">Беседы формируются в явном виде в результате этого действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="1496a-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="1496a-122">Например, ниже приведен снимок экрана беседы с каналом в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1496a-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Беседа с каналом Microsoft Teams](../media/threadedchat.png)

   <span data-ttu-id="1496a-124">В других приложениях (например, в 1xN сообщениях чата в Teams) не существует формальной цепочки ответа, а сообщения отображаются как "плоское Ривер сообщений" в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="1496a-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="1496a-125">В этих типах приложений беседы выводятся из группы сообщений, происходящих в течение определенного времени.</span><span class="sxs-lookup"><span data-stu-id="1496a-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="1496a-126">Это "мягкое" Группирование сообщений (в отличие от цепочки ответа) представляет собой обсуждение с определенной темой.</span><span class="sxs-lookup"><span data-stu-id="1496a-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="1496a-127">Шаг 1: выполнение поиска</span><span class="sxs-lookup"><span data-stu-id="1496a-127">Step 1: Run a search</span></span>

<span data-ttu-id="1496a-128">После определения соответствующих custodians и расположений содержимого можно создать поиск для поиска потенциально релевантного контента.</span><span class="sxs-lookup"><span data-stu-id="1496a-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="1496a-129">На вкладке **поиски** в расширенном случае обнаружения электронных данных можно создать поиск, нажав кнопку **Новый поиск** и следуя инструкциям мастера.</span><span class="sxs-lookup"><span data-stu-id="1496a-129">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="1496a-130">Сведения о том, как создавать поисковый запрос, создавать поисковый запрос и просматривать результаты поиска, можно узнать [в статье сбор данных для обращения](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="1496a-130">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="1496a-131">Шаг 2: создание набора проверки беседы</span><span class="sxs-lookup"><span data-stu-id="1496a-131">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="1496a-132">В наборе рецензирования можно искать, помечать, аннотировать и изменять документы, сообщения электронной почты и беседы в чате.</span><span class="sxs-lookup"><span data-stu-id="1496a-132">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="1496a-133">В Advanced eDiscovery вы можете настроить проверку бесед, используя отдельные сообщения или цепочки обсуждений.</span><span class="sxs-lookup"><span data-stu-id="1496a-133">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="1496a-134">Это определяется типом набора проверки, который добавляет результаты поиска, созданного на шаге 1, в.</span><span class="sxs-lookup"><span data-stu-id="1496a-134">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="1496a-135">Существует два вида наборов проверки:</span><span class="sxs-lookup"><span data-stu-id="1496a-135">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="1496a-136">**Стандартные наборы проверки:** Сообщения в беседах обрабатываются и отображаются как отдельные элементы.</span><span class="sxs-lookup"><span data-stu-id="1496a-136">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="1496a-137">**Наборы проверки беседы:** Сообщения в беседах обрабатываются по отдельности, но отображаются в представлении беседы.</span><span class="sxs-lookup"><span data-stu-id="1496a-137">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="1496a-138">В наборе проверки бесед можно закомментировать, пометить и исправить сообщения в связанном представлении беседы.</span><span class="sxs-lookup"><span data-stu-id="1496a-138">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="1496a-139">Дополнительные сведения о том, как просматривать контент в наборе рецензирования и управлять им, можно найти в разделе [Управление наборами проверки](managing-review-sets.md).</span><span class="sxs-lookup"><span data-stu-id="1496a-139">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="1496a-140">Шаг 3: включение параметров получения беседы</span><span class="sxs-lookup"><span data-stu-id="1496a-140">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="1496a-141">После просмотра и завершения запроса поиска можно добавить результаты поиска в набор проверки.</span><span class="sxs-lookup"><span data-stu-id="1496a-141">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="1496a-142">При добавлении результатов поиска в набор проверки исходные данные копируются в область хранилища Azure, чтобы упростить процесс просмотра и анализа.</span><span class="sxs-lookup"><span data-stu-id="1496a-142">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="1496a-143">Дополнительные сведения о добавлении результатов поиска в набор рецензирования можно найти в статье [Добавление результатов поиска в набор рецензирования](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="1496a-143">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="1496a-144">Когда вы добавляете данные из бесед в набор проверки, вы можете использовать параметры извлечения беседы для расширения поиска и включения контекстных сообщений.</span><span class="sxs-lookup"><span data-stu-id="1496a-144">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="1496a-145">После настройки параметров извлечения беседы могут происходить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1496a-145">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![Получение беседы](../media/messagesandconversations.png)
  
1. <span data-ttu-id="1496a-147">При использовании ключевого слова и запроса с диапазоном дат в *сообщении 3*будет возвращено совпадение поиска.</span><span class="sxs-lookup"><span data-stu-id="1496a-147">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="1496a-148">Это сообщение было частью большой беседы, которое проиллюстрировано *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="1496a-148">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="1496a-149">Когда вы добавляете данные в набор проверки и включаете параметры получения беседы, Расширенное обнаружение электронных данных перейдет назад и соберет другие элементы в *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="1496a-149">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="1496a-150">После добавления элементов в набор проверки можно просмотреть все отдельные сообщения из *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="1496a-150">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 

<span data-ttu-id="1496a-151">Чтобы включить извлечение бесед:</span><span class="sxs-lookup"><span data-stu-id="1496a-151">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="1496a-152">На вкладке **поиски** в расширенном случае обнаружения электронных данных выберите Поиск, а затем нажмите кнопку **Добавить, чтобы просмотреть набор** на всплывающей странице.</span><span class="sxs-lookup"><span data-stu-id="1496a-152">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="1496a-153">Выберите существующий набор рецензирования или создайте набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="1496a-153">Select an existing review set or create a review set.</span></span> <span data-ttu-id="1496a-154">Вы можете настроить параметры извлечения при добавлении результатов поиска в стандартный или в набор проверки беседы.</span><span class="sxs-lookup"><span data-stu-id="1496a-154">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="1496a-155">В разделе **Параметры коллекции**настройте параметры извлечения бесед для источников контента, которые необходимо расширить в поиске, а затем нажмите кнопку **Добавить** , чтобы запустить процесс.</span><span class="sxs-lookup"><span data-stu-id="1496a-155">Under **Collection options**, configure the conversation retrieval options for the content sources that you want to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="1496a-156">После завершения задания **Add to Review Set** на вкладке **задания** можно начать просмотр бесед.</span><span class="sxs-lookup"><span data-stu-id="1496a-156">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-and-export-conversations-in-a-review-set"></a><span data-ttu-id="1496a-157">Шаг 4: Просмотр и экспорт бесед в наборе рецензирования</span><span class="sxs-lookup"><span data-stu-id="1496a-157">Step 4: Review and export conversations in a review set</span></span>

<span data-ttu-id="1496a-158">После того как содержимое было обработано и Добавлено в набор рецензирования, можно начать просмотр данных в наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="1496a-158">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="1496a-159">Возможности рецензирования различаются в зависимости от того, было ли содержимое добавлено в стандартный набор проверки или в набор проверки беседы.</span><span class="sxs-lookup"><span data-stu-id="1496a-159">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="1496a-160">Просмотр бесед в стандартном наборе рецензирования</span><span class="sxs-lookup"><span data-stu-id="1496a-160">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="1496a-161">В стандартном наборе проверки сообщения обрабатываются и отображаются как отдельные элементы, аналогично тому, как они хранятся в папке почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="1496a-161">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="1496a-162">В этом рабочем процессе каждое сообщение обрабатывается как отдельный элемент.</span><span class="sxs-lookup"><span data-stu-id="1496a-162">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="1496a-163">В результате этого сводные данные и параметры экспорта недоступны в стандартном наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="1496a-163">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

  ![Стандартный набор проверки](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="1496a-165">Просмотр бесед в наборе проверки беседы</span><span class="sxs-lookup"><span data-stu-id="1496a-165">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="1496a-166">В наборе проверки беседы отдельные сообщения объединяются в цепочки и представляются как беседы.</span><span class="sxs-lookup"><span data-stu-id="1496a-166">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="1496a-167">Это позволяет просматривать и экспортировать контекстные беседы.</span><span class="sxs-lookup"><span data-stu-id="1496a-167">This lets you review and export contextual conversations.</span></span> 

  ![Набор проверки беседы](../media/ConversationRSOptions.PNG)

<span data-ttu-id="1496a-169">В следующих разделах описывается просмотр и экспорт бесед в наборе проверки беседы.</span><span class="sxs-lookup"><span data-stu-id="1496a-169">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="1496a-170">Рецензирование бесед</span><span class="sxs-lookup"><span data-stu-id="1496a-170">Reviewing conversations</span></span>

<span data-ttu-id="1496a-171">В наборе проверки беседы можно использовать следующие параметры для упрощения процесса проверки.</span><span class="sxs-lookup"><span data-stu-id="1496a-171">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="1496a-172">**Группировка по беседам:** Группирует сообщения в одном сеансе, чтобы упростить и ускорить процесс проверки.</span><span class="sxs-lookup"><span data-stu-id="1496a-172">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="1496a-173">**Представление сводки:** Отображает цепочку обсуждений.</span><span class="sxs-lookup"><span data-stu-id="1496a-173">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="1496a-174">В этом представлении вы можете видеть все беседы, а также получать доступ к метаданным для каждого отдельного сообщения.</span><span class="sxs-lookup"><span data-stu-id="1496a-174">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="1496a-175">Просмотр метаданных для отдельных сообщений</span><span class="sxs-lookup"><span data-stu-id="1496a-175">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="1496a-176">Загрузка отдельных сообщений</span><span class="sxs-lookup"><span data-stu-id="1496a-176">Download individual messages</span></span>

- <span data-ttu-id="1496a-177">**Представление текста:** Предоставляет извлеченный текст для всей беседы.</span><span class="sxs-lookup"><span data-stu-id="1496a-177">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="1496a-178">**Представление "Примечания":** Позволяет разметку обсуждения в потоковом представлении.</span><span class="sxs-lookup"><span data-stu-id="1496a-178">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="1496a-179">Все сообщения в беседе используют один и тот же документ с аннотациями.</span><span class="sxs-lookup"><span data-stu-id="1496a-179">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="1496a-180">**Маркировка:** При просмотре бесед в наборе рецензирования можно просматривать и применять теги, щелкая **панель маркировки** в панели "код".</span><span class="sxs-lookup"><span data-stu-id="1496a-180">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="1496a-181">**Повторное выполнение преобразования беседы:** При добавлении сообщений в набор проверки беседы автоматически запускается задание преобразования, чтобы создать потоковые представления сводки и примечаний.</span><span class="sxs-lookup"><span data-stu-id="1496a-181">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="1496a-182">Если не удается выполнить задачу реконструкции беседы, можно повторно запустить это задание, нажав кнопку **действие > создать документы PDF для беседы** в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="1496a-182">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="1496a-183">Экспорт бесед</span><span class="sxs-lookup"><span data-stu-id="1496a-183">Exporting conversations</span></span>

<span data-ttu-id="1496a-184">В наборе проверки беседы можно задать следующие параметры для экспорта бесед:</span><span class="sxs-lookup"><span data-stu-id="1496a-184">In a conversation review set, you can set the following options to export conversations:</span></span>

![Экспорт](../media/export.png)

<span data-ttu-id="1496a-186">а.</span><span class="sxs-lookup"><span data-stu-id="1496a-186">a.</span></span> <span data-ttu-id="1496a-187">Параметры метаданных</span><span class="sxs-lookup"><span data-stu-id="1496a-187">Metadata options</span></span>

   - <span data-ttu-id="1496a-188">**Загрузка файла:** Метаданные включены для каждого отдельного сообщения, электронной почты и документа.</span><span class="sxs-lookup"><span data-stu-id="1496a-188">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="1496a-189">Для каждого сообщения в беседе существует одна строка.</span><span class="sxs-lookup"><span data-stu-id="1496a-189">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="1496a-190">**Теги:** Теги из процесса проверки включены в файл метаданных.</span><span class="sxs-lookup"><span data-stu-id="1496a-190">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="1496a-191">Сообщения в беседе используют одни и те же теги.</span><span class="sxs-lookup"><span data-stu-id="1496a-191">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="1496a-192">б.</span><span class="sxs-lookup"><span data-stu-id="1496a-192">b.</span></span> <span data-ttu-id="1496a-193">Параметры беседы</span><span class="sxs-lookup"><span data-stu-id="1496a-193">Conversation options</span></span>
  
   - <span data-ttu-id="1496a-194">**Файлы беседы:** При экспорте файлов бесед представление с заметками преобразуется в PDF-файл и загружается в папку экспорта.</span><span class="sxs-lookup"><span data-stu-id="1496a-194">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="1496a-195">Сообщения в одном файле беседы указывает на PDF-версию того же файла беседы.</span><span class="sxs-lookup"><span data-stu-id="1496a-195">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="1496a-196">**Отдельные сообщения чата:** При экспорте отдельных сообщений каждое уникальное сообщение в беседе экспортируется как автономный элемент.</span><span class="sxs-lookup"><span data-stu-id="1496a-196">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="1496a-197">Файл экспортируется в том же формате, в котором он был сохранен, как в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="1496a-197">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="1496a-198">Для конкретной беседы вы получаете несколько файлов. MSG.</span><span class="sxs-lookup"><span data-stu-id="1496a-198">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="1496a-199">Если вы применили заметки к файлу беседы, эти заметки не будут передаваться в отдельные сообщения.</span><span class="sxs-lookup"><span data-stu-id="1496a-199">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="1496a-200">в.</span><span class="sxs-lookup"><span data-stu-id="1496a-200">c.</span></span> <span data-ttu-id="1496a-201">Другие варианты</span><span class="sxs-lookup"><span data-stu-id="1496a-201">Other options</span></span>

   - <span data-ttu-id="1496a-202">**Создание текстовых файлов для всего экспортированного контента:** Создает текстовый файл для каждого диалога, экспортированного из набора рецензирования.</span><span class="sxs-lookup"><span data-stu-id="1496a-202">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="1496a-203">**Замените экспортированный контент на отредактировал PDF:** Если в процессе проверки создаются файлы беседы отредактировал, эти файлы доступны во время экспорта.</span><span class="sxs-lookup"><span data-stu-id="1496a-203">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="1496a-204">Вы можете выбрать, следует ли экспортировать только собственные файлы (не выбрав этот параметр) или заменить собственные файлы версиями отредактировал (выбрав этот параметр), которые будут экспортированы в виде PDF-файлов.</span><span class="sxs-lookup"><span data-stu-id="1496a-204">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="1496a-205">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="1496a-205">More information</span></span>

<span data-ttu-id="1496a-206">Чтобы узнать больше о том, как просматривать данные о делах в Advanced eDiscovery, ознакомьтесь со следующими статьями:</span><span class="sxs-lookup"><span data-stu-id="1496a-206">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="1496a-207">Просмотр данных обращений</span><span class="sxs-lookup"><span data-stu-id="1496a-207">View case data</span></span>](view-documents-in-review-set.md)

- [<span data-ttu-id="1496a-208">Анализ данных дела</span><span class="sxs-lookup"><span data-stu-id="1496a-208">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="1496a-209">Экспорт данных дела</span><span class="sxs-lookup"><span data-stu-id="1496a-209">Export case data</span></span>](exporting-data-ediscover20.md)
