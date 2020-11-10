---
title: 'Работать с подразделами в центре справки (Предварительная версия) '
description: Работа со статьями в центре справки.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 464a926b99cceeb652756ad6d1456c5e17d2a925
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988742"
---
# <a name="work-with-topics-in-the-topic-center-preview"></a><span data-ttu-id="fbc5f-103">Работать с подразделами в центре справки (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fbc5f-103">Work with topics in the topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="fbc5f-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="fbc5f-105">[Узнайте больше о работе с Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="fbc5f-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="fbc5f-106">В центре знаний руководитель может просматривать темы, которые были mined и обнаружены в указанных исходных расположениях SharePoint, а также либо подтверждать их, либо отклонять.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-106">In the topic center, a knowledge manager can review topics that have been mined and discovered in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="fbc5f-107">Диспетчер базы знаний также может создавать и публиковать новые темы, если они не были найдены в ходе обнаружения разделов, или редактировать существующие, если их необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-107">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="requirements"></a><span data-ttu-id="fbc5f-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="fbc5f-108">Requirements</span></span>

<span data-ttu-id="fbc5f-109">Для работы в центре разделов необходимы необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-109">In order to work in the topic center, you need to have the required permissions.</span></span> <span data-ttu-id="fbc5f-110">Администратор может добавить вас во время [установки управления знаниями](set-up-topic-experiences.md)или добавить новых пользователей [позже](give-user-permissions-to-the-topic-center.md).</span><span class="sxs-lookup"><span data-stu-id="fbc5f-110">Your admin can add you during [knowledge management setup](set-up-topic-experiences.md), or new users can be [added afterwards](give-user-permissions-to-the-topic-center.md).</span></span>

<span data-ttu-id="fbc5f-111">Пользователям центра разделов могут быть предоставлены два набора разрешений:</span><span class="sxs-lookup"><span data-stu-id="fbc5f-111">Topic center users can be given two sets of permissions:</span></span>

- <span data-ttu-id="fbc5f-112">Создание и редактирование разделов: создание новых разделов или обновление содержимого разделов, таких как описание, документы и связанные лица.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-112">Create and edit topics: Create new topics or update topic content such as the description, documents and associated persons.</span></span>

- <span data-ttu-id="fbc5f-113">Управление разделами: использование панели управления разделами для просмотра тем в Организации.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-113">Manage topics: Use the Topic management dashboard to review topics across the organization.</span></span> <span data-ttu-id="fbc5f-114">Пользователи могут выполнять такие действия, как "подтвердить" и "отклонить".</span><span class="sxs-lookup"><span data-stu-id="fbc5f-114">Users can perform actions such as confirm and reject topics.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="fbc5f-115">Обзор предлагаемых разделов</span><span class="sxs-lookup"><span data-stu-id="fbc5f-115">Review suggested topics</span></span>

<span data-ttu-id="fbc5f-116">На домашней странице центра разделов темы, обнаруженные в указанных исходных расположениях SharePoint, будут перечислены на **предлагаемой** вкладке. Пользователь с разрешениями на управление разделами может проверить неподтвержденные разделы и подтвердить или отклонить их.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-116">On the topic center home page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A user with permissions to manage topics can review unconfirmed topics and choose to confirm or reject them.</span></span>


<span data-ttu-id="fbc5f-117">Чтобы просмотреть предлагаемый раздел:</span><span class="sxs-lookup"><span data-stu-id="fbc5f-117">To review a suggested topic:</span></span>

1. <span data-ttu-id="fbc5f-118">На вкладке **предлагаемые** выберите раздел, чтобы открыть страницу раздела.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-118">On the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="fbc5f-119">На странице темы изучите страницу раздела и нажмите кнопку **изменить** , если необходимо внести какие-либо изменения на страницу.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-119">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="fbc5f-120">На домашней странице центра знаний для выбранного раздела можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fbc5f-120">On the Knowledge Center home page, for the selected topic, you can:</span></span>

    1. <span data-ttu-id="fbc5f-121">Выберите проверку, чтобы подтвердить, что вы хотите сохранить раздел.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-121">Select the check to confirm that you want to keep the topic.</span></span>
    
    1. <span data-ttu-id="fbc5f-122">Если вы хотите отклонить тему, выберите значение " **x** ".</span><span class="sxs-lookup"><span data-stu-id="fbc5f-122">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="fbc5f-123">Подтвержденные темы будут удалены из **неподтвержденного** списка и теперь будут отображаться на вкладке **подтверждено** .</span><span class="sxs-lookup"><span data-stu-id="fbc5f-123">Confirmed topics will be removed from the **Unconfirmed** list and will now display in the **Confirmed** tab.</span></span>

    <span data-ttu-id="fbc5f-124">Отклоненные разделы будут удалены из **неподтвержденного** списка и теперь будут отображаться на вкладке **отклонено или исключено** .</span><span class="sxs-lookup"><span data-stu-id="fbc5f-124">Rejected topics will be removed from the **Unconfirmed** list and will now display in the **Rejected or Excluded** tab.</span></span>

## <a name="review-confirmed-topics"></a><span data-ttu-id="fbc5f-125">Просмотр подтвержденных разделов</span><span class="sxs-lookup"><span data-stu-id="fbc5f-125">Review confirmed topics</span></span>

<span data-ttu-id="fbc5f-126">На домашней странице центра разделов находятся разделы, обнаруженные в указанных исходных расположениях SharePoint и подтвержденные диспетчером знаний или кровдсаурцед, подтвержденные 2 или более людьми через механизм обратной связи карты, будут перечислены на вкладке **подтверждено** . Пользователь с разрешениями на управление разделами может просматривать подтвержденные темы и отклонять их.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-126">On the topic center home page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or crowdsourced confirmed by 2 or more people through the card feedback mechanism will be listed in the **Confirmed** tab. A user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>


<span data-ttu-id="fbc5f-127">Чтобы просмотреть подтвержденный раздел, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-127">To review a confirmed topic:</span></span>

1. <span data-ttu-id="fbc5f-128">На вкладке **подтвержденные** выберите раздел, чтобы открыть страницу раздела.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-128">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="fbc5f-129">На странице темы изучите страницу раздела и нажмите кнопку **изменить** , если необходимо внести какие-либо изменения на страницу.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-129">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="fbc5f-130">Вы можете отклонить его.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-130">You can reject it too</span></span>

## <a name="review-published-topics"></a><span data-ttu-id="fbc5f-131">Обзор опубликованных разделов</span><span class="sxs-lookup"><span data-stu-id="fbc5f-131">Review published topics</span></span>
<span data-ttu-id="fbc5f-132">Опубликованные разделы были изменены таким образом, что конкретные сведения всегда будут отображаться на странице.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-132">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="fbc5f-133">Здесь показаны разделы, созданные вручную.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-133">Manually created topics show here.</span></span>

   
## <a name="create-a-new-topic"></a><span data-ttu-id="fbc5f-134">Создание раздела</span><span class="sxs-lookup"><span data-stu-id="fbc5f-134">Create a new topic</span></span>

<span data-ttu-id="fbc5f-135">При необходимости пользователь с разрешениями на создание или изменение темы может создать новый раздел.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-135">A user with create or edit topic permissions can create a new topic if needed.</span></span> <span data-ttu-id="fbc5f-136">Это может потребоваться, если тема не была обнаружена с помощью обнаружения, или если не удалось найти достаточное свидетельство для создания темы в результате использования AI-технологии.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-136">You might need to do this if the topic was not discovered through discovery or if the AI technology did not find enough evidence to establish it as a topic.</span></span>

<span data-ttu-id="fbc5f-137">Чтобы создать новый раздел, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-137">To create a new topic:</span></span>

1. <span data-ttu-id="fbc5f-138">На странице "центр разделов" выберите **создать** , а затем выберите **раздел страница**.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-138">On the topic center page, select **New** , then select **Topic Page**.</span></span>

    ![Новый раздел](../media/content-understanding/k-new-topic.png)

2. <span data-ttu-id="fbc5f-140">На странице новый раздел вы можете ввести сведения о новом шаблоне раздела:</span><span class="sxs-lookup"><span data-stu-id="fbc5f-140">On the new topic page, you can fill in the information on the new topic template:</span></span>

    1. <span data-ttu-id="fbc5f-141">В разделе **имя этого раздела** введите имя нового раздела.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-141">In the **Name this topic** section, type the name of the new topic.</span></span>
    
    1. <span data-ttu-id="fbc5f-142">В разделе **альтернативные имена** введите имена или акронимы, которые также используются для ссылки на раздел.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-142">In the **Alternate names** section, type names or acronyms that are also used to refer to the topic.</span></span>
    
    1. <span data-ttu-id="fbc5f-143">В разделе **Краткое описание** введите описание раздела с одним или двумя предложениями.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-143">In the **Short description** section, type a one or two sentence description of the topic.</span></span> <span data-ttu-id="fbc5f-144">Этот текст будет использоваться для связанной карточки с темой.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-144">This text will be used for the associated topic card.</span></span>
    
    1. <span data-ttu-id="fbc5f-145">В разделе **люди** введите имена экспертов для темы.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-145">In the **People** section, type the names of subject matter experts for the topic.</span></span>
    
    1. <span data-ttu-id="fbc5f-146">В разделе **файлы и страницы** выберите **Добавить** , а затем на следующей странице можно выбрать связанные файлы OneDrive или страницы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-146">In the **Files and pages** section, select **Add** and then on the next page you can select associated OneDrive files or SharePoint Online pages.</span></span>
    
    1. <span data-ttu-id="fbc5f-147">В разделе **сайты** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-147">In the **Sites** section, select **Add**.</span></span> <span data-ttu-id="fbc5f-148">В области  **сайты** , которая отображается, выберите сайты, связанные с этим разделом.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-148">In the  **Sites** pane that displays, select the sites that are associated to the topic.</span></span>

    ![Страница новой темы](../media/content-understanding/k-new-topic-page.png)
    
3. <span data-ttu-id="fbc5f-150">Если необходимо добавить на страницу другие компоненты, например текст, изображения, веб-части, ссылки и т. д., выберите значок холст в центре страницы, чтобы нахождение и добавление элементов.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-150">If you need to add other components to the page, such as text, images, web parts, links, etc., select the canvas icon in the middle of the page to locate and add them.</span></span>

    ![Добавление элементов на страницу](../media/content-understanding/static-icon.png)

4. <span data-ttu-id="fbc5f-152">Когда все будет готово, нажмите кнопку **опубликовать** , чтобы опубликовать страницу темы.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-152">When you are done, select **Publish** to publish the topic page.</span></span> <span data-ttu-id="fbc5f-153">Опубликованные темы страницы будут отображаться на вкладке **страницы** .</span><span class="sxs-lookup"><span data-stu-id="fbc5f-153">Published topic pages will display in the **Pages** tab.</span></span>

> [!Note] 
> <span data-ttu-id="fbc5f-154">Новая страница темы состоит из веб-частей, которые представляют собой *сведения о сети*.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-154">The new topic page is made up of web parts that are *knowledge network aware*.</span></span> <span data-ttu-id="fbc5f-155">Это означает, что как AI собирает дополнительные сведения о теме, сведения в этих веб-частях будут обновлены с помощью предложений, чтобы сделать страницу более полезной для пользователей.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-155">This means that as AI gathers more information on the topic, the information in these web parts will be updated with suggestions to make the page more useful to users.</span></span>


## <a name="edit-an-existing-topic-page"></a><span data-ttu-id="fbc5f-156">Изменение существующей страницы раздела</span><span class="sxs-lookup"><span data-stu-id="fbc5f-156">Edit an existing topic page</span></span>

<span data-ttu-id="fbc5f-157">Имеющиеся страницы разделов можно найти на странице **страницы** .</span><span class="sxs-lookup"><span data-stu-id="fbc5f-157">Existing topic pages can be found in the **Pages** page.</span></span> 

1. <span data-ttu-id="fbc5f-158">На странице "центр разделов" выберите **страницы**.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-158">On the Topic Center page, select **Pages**.</span></span>

2. <span data-ttu-id="fbc5f-159">На странице **страницы** отображается список тематических страниц.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-159">On the **Pages** page, you will see a list of topic pages.</span></span> <span data-ttu-id="fbc5f-160">Используйте поле поиска, чтобы найти страницу темы, которую необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-160">Use the Search box to find the topic page you want to update.</span></span> <span data-ttu-id="fbc5f-161">Щелкните имя страницы темы, которую нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-161">Click on the name of the topic page that you want to edit.</span></span>

3. <span data-ttu-id="fbc5f-162">На странице раздел нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-162">On the topic page, select **Edit**.</span></span>

4. <span data-ttu-id="fbc5f-163">Внесите необходимые изменения на странице.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-163">Make the changes you need to the page.</span></span> <span data-ttu-id="fbc5f-164">Сюда входят обновления следующих полей:</span><span class="sxs-lookup"><span data-stu-id="fbc5f-164">This includes updates to the following fields:</span></span>

    1. <span data-ttu-id="fbc5f-165">Альтернативные имена</span><span class="sxs-lookup"><span data-stu-id="fbc5f-165">Alternate names</span></span>
    1. <span data-ttu-id="fbc5f-166">Описание</span><span class="sxs-lookup"><span data-stu-id="fbc5f-166">Description</span></span>
    1. <span data-ttu-id="fbc5f-167">Люди</span><span class="sxs-lookup"><span data-stu-id="fbc5f-167">People</span></span>
    1. <span data-ttu-id="fbc5f-168">Файлы и страницы</span><span class="sxs-lookup"><span data-stu-id="fbc5f-168">Files and pages</span></span>
    1. <span data-ttu-id="fbc5f-169">Сайты</span><span class="sxs-lookup"><span data-stu-id="fbc5f-169">Sites</span></span>
    1. <span data-ttu-id="fbc5f-170">Кроме того, можно добавить статические элементы на страницу, например текст, изображения или ссылку, выбрав значок холст.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-170">You can also add static items to the page—such as text, images, or link—by selecting the canvas icon.</span></span>

5. <span data-ttu-id="fbc5f-171">Нажмите кнопку **повторно опубликовать** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="fbc5f-171">Select **Republish** to save your changes.</span></span>

<!--## See also-->


