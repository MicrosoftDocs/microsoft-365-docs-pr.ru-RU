---
title: Trimming topic Experiences security trimming (Preview)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Обзор использования системы безопасности для просмотра разделов.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699061"
---
# <a name="topic-experiences-security-trimming-preview"></a><span data-ttu-id="dd79a-103">Trimming topic Experiences security trimming (Preview)</span><span class="sxs-lookup"><span data-stu-id="dd79a-103">Topic Experiences security trimming (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="dd79a-104">Содержимое этой статьи для Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="dd79a-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="dd79a-105">[Узнайте больше о работе с Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="dd79a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="dd79a-106">Темы, которые пользователи не смогут просматривать в разделах, которые не видят существующие разрешения Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd79a-106">Topic experiences users will not be able to view information in topics that their existing Office 365 permissions prevents them from seeing.</span></span> <span data-ttu-id="dd79a-107">Все, что пользователь видит на странице темы (например, сайты SharePoint, документы, файлы), будет информацией, которую он уже может видеть.</span><span class="sxs-lookup"><span data-stu-id="dd79a-107">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="dd79a-108">Темы не внося изменений в существующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="dd79a-108">Topic experiences does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="dd79a-109">Почему два пользователя могут иметь разные представления одного и того же раздела</span><span class="sxs-lookup"><span data-stu-id="dd79a-109">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="dd79a-110">Когда тема создается с помощью ИИ или ручного курсирования, она может содержать описание темы, альтернативные имена, людей, связанных с темой, а также сайты, страницы и файлы, связанные с этой темой.</span><span class="sxs-lookup"><span data-stu-id="dd79a-110">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="dd79a-111">Если эти сведения просматриваются на странице темы, возможно, что два пользователя, просматривая один и тот же раздел, не видят одинаковые сведения.</span><span class="sxs-lookup"><span data-stu-id="dd79a-111">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="dd79a-112">Например, когда пользователь 1 просмотрит страницу темы Neptune, он может увидеть это.</span><span class="sxs-lookup"><span data-stu-id="dd79a-112">For example, when User 1 views the Neptune topic page, this is what they might see.</span></span>

![Тема Neptune для пользователя 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="dd79a-114">Однако когда пользователь 2 просматривает ту же страницу темы Neptune, ее представление отличается от "Пользователь 1".</span><span class="sxs-lookup"><span data-stu-id="dd79a-114">However, when User 2 looks at the same Neptune topic page, her view differs from User 1.</span></span>  <span data-ttu-id="dd79a-115">Пользователь 2 может видеть файл "Обзор продукта *DG-2000"* в разделе "Закрепленные файлы и страницы" на странице темы, который не появляется для пользователя 1. </span><span class="sxs-lookup"><span data-stu-id="dd79a-115">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Тема Neptune для пользователя 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="dd79a-117">Разница в том, что пользователи могут видеть в одной теме, заключается в том, что у пользователей могут не быть разрешений Office 365 на просмотр связанного сайта или файла.</span><span class="sxs-lookup"><span data-stu-id="dd79a-117">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="dd79a-118">В теме соблюдаются разрешения, установленные для элементов в теме, и они не могут изменять доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="dd79a-118">Topic experiences respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="dd79a-119">В нашем примере пользователь 1 не может просматривать файл "Обзор продукта *DG-2000"* на своей странице темы для Neptune, так как у пользователя User 1 нет разрешений Office 365 на просмотр файла.</span><span class="sxs-lookup"><span data-stu-id="dd79a-119">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="dd79a-120">Если пользователь не может увидеть достаточно информации в теме, чтобы она была полезной, она будет недоступна для пользователя.</span><span class="sxs-lookup"><span data-stu-id="dd79a-120">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="dd79a-121">В этом случае пользователь не увидит выделенную тему.</span><span class="sxs-lookup"><span data-stu-id="dd79a-121">In this instance, the user will not see the highlighted topic.</span></span> <span data-ttu-id="dd79a-122">Тем не менее, другой пользователь, у которого есть разрешения на дополнительные сведения в этой теме, чтобы он был полезен, сможет увидеть этот раздел.</span><span class="sxs-lookup"><span data-stu-id="dd79a-122">However, a different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="dd79a-123">Разрешения для руководителей знаний и участников тем</span><span class="sxs-lookup"><span data-stu-id="dd79a-123">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="dd79a-124">Пользователи с разрешениями на управление темами ( менеджеры знаний) смогут просматривать только те сведения, которые им назначены.</span><span class="sxs-lookup"><span data-stu-id="dd79a-124">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="dd79a-125">Аналогичным образом, пользователи с разрешениями на создание и редактирование тем (участники тем) смогут просматривать только те сведения, которые у них есть разрешения на просмотр в разделах.</span><span class="sxs-lookup"><span data-stu-id="dd79a-125">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="dd79a-126">Сведения об ИИ в сравнении с информацией о теме вручную</span><span class="sxs-lookup"><span data-stu-id="dd79a-126">AI versus manually curated topic information</span></span>

<span data-ttu-id="dd79a-127">Разделы могут содержать сведения, созданные ИИ, а также сведения, добавляемые или редактируемые участниками тем или менеджерами знаний.</span><span class="sxs-lookup"><span data-stu-id="dd79a-127">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="dd79a-128">Сведения в теме, добавленной ИИ, видны только тем, у которых есть доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="dd79a-128">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="dd79a-129">Сведения, которые были вручную добавлены или изменены участником темы или руководителем знаний, видны всем, кто может видеть тему.</span><span class="sxs-lookup"><span data-stu-id="dd79a-129">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="dd79a-130">В следующей таблице описывается, какие пользователи — читатели тем, участники и менеджеры знаний — могут видеть в заданной теме на основе их разрешений.</span><span class="sxs-lookup"><span data-stu-id="dd79a-130">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="dd79a-131">Элемент темы</span><span class="sxs-lookup"><span data-stu-id="dd79a-131">Topic item</span></span>|<span data-ttu-id="dd79a-132">Что могут видеть пользователи</span><span class="sxs-lookup"><span data-stu-id="dd79a-132">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="dd79a-133">Имя раздела</span><span class="sxs-lookup"><span data-stu-id="dd79a-133">Topic name</span></span>|<span data-ttu-id="dd79a-134">Пользователи могут видеть название всех разделов в центре тем.</span><span class="sxs-lookup"><span data-stu-id="dd79a-134">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="dd79a-135">Некоторые разделы могут быть не видны, если они имеют низкую заметную для пользователя тему.</span><span class="sxs-lookup"><span data-stu-id="dd79a-135">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="dd79a-136">Описание темы</span><span class="sxs-lookup"><span data-stu-id="dd79a-136">Topic description</span></span>|<span data-ttu-id="dd79a-137">Описания, созданные ИИ, видны только пользователям, у которых есть разрешения на доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="dd79a-137">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="dd79a-138">Вручную введенное или измененное описание видно всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="dd79a-138">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="dd79a-139">Люди</span><span class="sxs-lookup"><span data-stu-id="dd79a-139">People</span></span>|<span data-ttu-id="dd79a-140">Закрепленные люди видны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="dd79a-140">Pinned people are visible to all users.</span></span> <span data-ttu-id="dd79a-141">Предлагаемые пользователи видны только пользователям с разрешениями на доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="dd79a-141">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="dd79a-142">Files</span><span class="sxs-lookup"><span data-stu-id="dd79a-142">Files</span></span>|<span data-ttu-id="dd79a-143">Файлы видны только пользователям с разрешениями на доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="dd79a-143">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="dd79a-144">Страницы</span><span class="sxs-lookup"><span data-stu-id="dd79a-144">Pages</span></span>|<span data-ttu-id="dd79a-145">Страницы видны только пользователям с разрешениями на доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="dd79a-145">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="dd79a-146">Сайты</span><span class="sxs-lookup"><span data-stu-id="dd79a-146">Sites</span></span>|<span data-ttu-id="dd79a-147">Сайты видны только пользователям с разрешениями на доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="dd79a-147">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="dd79a-148">См. также</span><span class="sxs-lookup"><span data-stu-id="dd79a-148">See also</span></span>

