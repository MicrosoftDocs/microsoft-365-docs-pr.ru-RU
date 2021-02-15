---
title: Триммер безопасности Microsoft Viva Topics
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Обзор использования системы безопасности для просмотра разделов.
ms.openlocfilehash: fc8e2a08fcf9af266aee49eee878738f7f17aa59
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107522"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="68164-103">Триммер безопасности Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="68164-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="68164-104">Пользователи Viva Topics не могут просматривать сведения в темах, которые их существующие разрешения Office 365 не могут просматривать.</span><span class="sxs-lookup"><span data-stu-id="68164-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="68164-105">Все, что пользователь видит на странице темы (например, сайты SharePoint, документы, файлы), будет информацией, которую он уже может видеть.</span><span class="sxs-lookup"><span data-stu-id="68164-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="68164-106">Разделы Viva не внося изменений в существующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="68164-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="68164-107">Почему два пользователя могут иметь разные представления одного и того же раздела</span><span class="sxs-lookup"><span data-stu-id="68164-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="68164-108">Когда тема создается с помощью ИИ или ручного курсирования, она может содержать описание темы, альтернативные имена, людей, связанных с темой, а также сайты, страницы и файлы, связанные с этой темой.</span><span class="sxs-lookup"><span data-stu-id="68164-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="68164-109">Если эти сведения просматриваются на странице темы, возможно, что два пользователя, просматривая один и тот же раздел, не видят одинаковые сведения.</span><span class="sxs-lookup"><span data-stu-id="68164-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="68164-110">Например, когда пользователь 1 просматривает страницу темы Neptune, он может увидеть это представление страницы темы.</span><span class="sxs-lookup"><span data-stu-id="68164-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Тема Neptune для пользователя 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="68164-112">Однако если пользователь 2 просматривает ту же страницу темы Neptune, его представление отличается от "Пользователь 1".</span><span class="sxs-lookup"><span data-stu-id="68164-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="68164-113">Пользователь 2 может видеть файл "Обзор продукта *DG-2000"* в разделе закрепленных файлов и страниц на странице темы, который не появляется для пользователя 1. </span><span class="sxs-lookup"><span data-stu-id="68164-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Тема Neptune для пользователя 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="68164-115">Разница в том, что пользователи могут видеть в одной теме, заключается в том, что у пользователей могут не быть разрешений Office 365 на просмотр связанного сайта или файла.</span><span class="sxs-lookup"><span data-stu-id="68164-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="68164-116">Разделы Viva соблюдают разрешения, установленные для элементов в теме, и не могут изменять доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="68164-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="68164-117">В нашем примере пользователь 1 не может просматривать файл "Обзор продукта *DG-2000"* на своей странице темы для Neptune, так как у пользователя User 1 нет разрешений Office 365 на просмотр файла.</span><span class="sxs-lookup"><span data-stu-id="68164-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="68164-118">Если пользователь не может увидеть достаточно информации в теме, чтобы она была полезной, она будет недоступна для пользователя.</span><span class="sxs-lookup"><span data-stu-id="68164-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="68164-119">Когда это произойдет, пользователь не увидит выделенную тему.</span><span class="sxs-lookup"><span data-stu-id="68164-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="68164-120">Другой пользователь, у которого есть разрешения на дополнительные сведения в теме, чтобы он был полезен, сможет увидеть этот раздел.</span><span class="sxs-lookup"><span data-stu-id="68164-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="68164-121">Разрешения для руководителей знаний и участников тем</span><span class="sxs-lookup"><span data-stu-id="68164-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="68164-122">Пользователи с разрешениями на управление темами ( менеджеры знаний) смогут просматривать только те сведения, которые им назначены.</span><span class="sxs-lookup"><span data-stu-id="68164-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="68164-123">Аналогичным образом, пользователи с разрешениями на создание и редактирование тем (участники тем) смогут просматривать только те сведения, которые у них есть разрешения на просмотр в разделах.</span><span class="sxs-lookup"><span data-stu-id="68164-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="68164-124">Сведения об ИИ в сравнении с информацией о теме вручную</span><span class="sxs-lookup"><span data-stu-id="68164-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="68164-125">Разделы могут содержать сведения, созданные ИИ, а также сведения, добавляемые или редактируемые участниками тем или менеджерами знаний.</span><span class="sxs-lookup"><span data-stu-id="68164-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="68164-126">Сведения в теме, добавленной ИИ, видны только тем, у которых есть доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="68164-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="68164-127">Сведения, которые были вручную добавлены или изменены участником темы или руководителем знаний, видны всем, кто может видеть тему.</span><span class="sxs-lookup"><span data-stu-id="68164-127">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="68164-128">В следующей таблице описано, какие пользователи — посетители тем, участники и менеджеры знаний — могут видеть в заданной теме на основе их разрешений.</span><span class="sxs-lookup"><span data-stu-id="68164-128">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="68164-129">Элемент темы</span><span class="sxs-lookup"><span data-stu-id="68164-129">Topic item</span></span>|<span data-ttu-id="68164-130">Что могут видеть пользователи</span><span class="sxs-lookup"><span data-stu-id="68164-130">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="68164-131">Имя раздела</span><span class="sxs-lookup"><span data-stu-id="68164-131">Topic name</span></span>|<span data-ttu-id="68164-132">Пользователи могут видеть название всех разделов в центре тем.</span><span class="sxs-lookup"><span data-stu-id="68164-132">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="68164-133">Некоторые разделы могут быть не видны, если они имеют низкую заметную для пользователя тему.</span><span class="sxs-lookup"><span data-stu-id="68164-133">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="68164-134">Описание темы</span><span class="sxs-lookup"><span data-stu-id="68164-134">Topic description</span></span>|<span data-ttu-id="68164-135">Описания, созданные ИИ, видны только пользователям, у которых есть разрешения на доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="68164-135">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="68164-136">Введенное вручную или измененное описание видно всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="68164-136">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="68164-137">Люди</span><span class="sxs-lookup"><span data-stu-id="68164-137">People</span></span>|<span data-ttu-id="68164-138">Закрепленные люди видны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="68164-138">Pinned people are visible to all users.</span></span> <span data-ttu-id="68164-139">Предлагаемые пользователи видны только пользователям с разрешениями на доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="68164-139">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="68164-140">Файлы</span><span class="sxs-lookup"><span data-stu-id="68164-140">Files</span></span>|<span data-ttu-id="68164-141">Файлы видны только пользователям с разрешениями на доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="68164-141">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="68164-142">Страницы</span><span class="sxs-lookup"><span data-stu-id="68164-142">Pages</span></span>|<span data-ttu-id="68164-143">Страницы видны только пользователям с разрешениями на доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="68164-143">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="68164-144">Сайты</span><span class="sxs-lookup"><span data-stu-id="68164-144">Sites</span></span>|<span data-ttu-id="68164-145">Сайты видны только пользователям с разрешениями на доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="68164-145">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="68164-146">См. также</span><span class="sxs-lookup"><span data-stu-id="68164-146">See also</span></span>

