---
title: Обрезка безопасности Microsoft Viva Topics
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
description: Обзор использования безопасности для просмотра тем.
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939627"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="06673-103">Обрезка безопасности Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="06673-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="06673-104">Пользователи Viva Topics не могут просматривать сведения в темах, которые им мешают существующие разрешения Office 365.</span><span class="sxs-lookup"><span data-stu-id="06673-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="06673-105">Все, что пользователь видит на странице темы (например, сайты SharePoint, документы, файлы), будет информацией, которую им уже разрешено видеть.</span><span class="sxs-lookup"><span data-stu-id="06673-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="06673-106">Viva Topics не изменяет существующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="06673-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="06673-107">Почему два пользователя могут иметь разные представления одной и той же темы</span><span class="sxs-lookup"><span data-stu-id="06673-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="06673-108">Когда тема создается с помощью AI или вручную, она может содержать описание темы, альтернативных имен, людей, связанных с этой темой, а также сайтов, страниц и файлов, связанных с этой темой.</span><span class="sxs-lookup"><span data-stu-id="06673-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="06673-109">Когда эта информация просматривается на странице темы, не исключено, что два пользователя, которые просматривают один и тот же раздел, не видят одинаковые сведения.</span><span class="sxs-lookup"><span data-stu-id="06673-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="06673-110">Например, когда пользователь 1 просматривает страницу темы Neptune, он может увидеть это представление страницы темы.</span><span class="sxs-lookup"><span data-stu-id="06673-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Тема Neptune для пользователя 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="06673-112">Однако, когда пользователь 2 смотрит на ту же страницу темы Neptune, их представление отличается от пользовательского 1.</span><span class="sxs-lookup"><span data-stu-id="06673-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="06673-113">Пользователь 2 может видеть файл обзор продукта *DG-2000* в разделе **Pinned files and pages** страницы темы, который не появляется для пользователя 1.</span><span class="sxs-lookup"><span data-stu-id="06673-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Тема Neptune для пользователя 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="06673-115">Разница в том, что пользователи могут видеть в одной и той же теме, поскольку у пользователей может не быть разрешений Office 365 на просмотр связанного сайта или файла.</span><span class="sxs-lookup"><span data-stu-id="06673-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="06673-116">Viva Topics уважает разрешения, заданной для элементов в теме, и не может изменить доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="06673-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="06673-117">В нашем примере пользователь 1 не может просматривать файл обзор продуктов *DG-2000* на своей странице темы для Neptune, так как у пользователя 1 нет разрешений Office 365 для просмотра файла.</span><span class="sxs-lookup"><span data-stu-id="06673-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="06673-118">Если пользователь не может видеть достаточно сведений в теме, чтобы она была полезной, эта тема будет недоступна пользователю.</span><span class="sxs-lookup"><span data-stu-id="06673-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="06673-119">Когда это произойдет, пользователь не увидит выделенную тему.</span><span class="sxs-lookup"><span data-stu-id="06673-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="06673-120">Другой пользователь, у которого есть разрешения на дополнительные сведения в этой теме, чтобы она была полезной, сможет увидеть эту тему.</span><span class="sxs-lookup"><span data-stu-id="06673-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="06673-121">Разрешения по темам для руководителей знаний и участников тем</span><span class="sxs-lookup"><span data-stu-id="06673-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="06673-122">Пользователи, на которые назначены разрешения на управление темами , — менеджеры знаний — смогут просматривать только сведения, которые они могут просматривать в рамках тем.</span><span class="sxs-lookup"><span data-stu-id="06673-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="06673-123">Кроме того, пользователи, у которых есть разрешения на создание и редактирование тем , — участники темы, — смогут просматривать только сведения, которые они могут просматривать в рамках тем.</span><span class="sxs-lookup"><span data-stu-id="06673-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="06673-124">Сведения об ИИ и сведения о теме вручную</span><span class="sxs-lookup"><span data-stu-id="06673-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="06673-125">Темы могут содержать сведения, созданные ИИ, а также сведения, добавленные или отредактированы участниками или руководителями знаний.</span><span class="sxs-lookup"><span data-stu-id="06673-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="06673-126">Сведения в теме, добавленной ИИ, видны только людям, которые имеют доступ к контенту источника.</span><span class="sxs-lookup"><span data-stu-id="06673-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="06673-127">Описание темы и сведения о пользователях, которые были вручную добавлены или отредактированы участником темы или менеджером знаний, видны всем, кто может видеть эту тему.</span><span class="sxs-lookup"><span data-stu-id="06673-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="06673-128">Файлы, страницы и сайты видны только пользователям, у которых есть разрешения на исходный контент, независимо от того, добавляется или добавляется ИИ вручную.</span><span class="sxs-lookup"><span data-stu-id="06673-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="06673-129">В следующей таблице описывается, что пользователи — зрители темы, вкладчики и менеджеры знаний — могут видеть в данной теме на основе их разрешений.</span><span class="sxs-lookup"><span data-stu-id="06673-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="06673-130">Элемент Topic</span><span class="sxs-lookup"><span data-stu-id="06673-130">Topic item</span></span>|<span data-ttu-id="06673-131">Что видят пользователи</span><span class="sxs-lookup"><span data-stu-id="06673-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="06673-132">Имя темы</span><span class="sxs-lookup"><span data-stu-id="06673-132">Topic name</span></span>|<span data-ttu-id="06673-133">Пользователи могут видеть имя темы в центре темы.</span><span class="sxs-lookup"><span data-stu-id="06673-133">Users can see the topic name of topics in the topic center.</span></span> <span data-ttu-id="06673-134">Некоторые темы могут быть не видны, если у пользователей нет разрешений на исходный контент или они имеют низкую емкость для пользователя.</span><span class="sxs-lookup"><span data-stu-id="06673-134">Some topics may not be visible if users don't have permissions to the source content or have a low relevancy to the user.</span></span>|
|<span data-ttu-id="06673-135">Описание темы</span><span class="sxs-lookup"><span data-stu-id="06673-135">Topic description</span></span>|<span data-ttu-id="06673-136">Описания, созданные с использованием ИИ, видны только пользователям, у которых есть разрешения на исходный контент.</span><span class="sxs-lookup"><span data-stu-id="06673-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="06673-137">Описания, внося или отредактированы вручную, видны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="06673-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="06673-138">Люди</span><span class="sxs-lookup"><span data-stu-id="06673-138">People</span></span>|<span data-ttu-id="06673-139">Закрепленные люди видны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="06673-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="06673-140">Предложенные люди видны только пользователям, у которых есть разрешения на исходный контент.</span><span class="sxs-lookup"><span data-stu-id="06673-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="06673-141">Files</span><span class="sxs-lookup"><span data-stu-id="06673-141">Files</span></span>|<span data-ttu-id="06673-142">Файлы видны только пользователям, у которых есть разрешения на исходный контент.</span><span class="sxs-lookup"><span data-stu-id="06673-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="06673-143">Страницы</span><span class="sxs-lookup"><span data-stu-id="06673-143">Pages</span></span>|<span data-ttu-id="06673-144">Страницы видны только пользователям, у которых есть разрешения на исходный контент.</span><span class="sxs-lookup"><span data-stu-id="06673-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="06673-145">Сайты</span><span class="sxs-lookup"><span data-stu-id="06673-145">Sites</span></span>|<span data-ttu-id="06673-146">Сайты видны только пользователям, у которых есть разрешения на исходный контент.</span><span class="sxs-lookup"><span data-stu-id="06673-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="06673-147">См. также</span><span class="sxs-lookup"><span data-stu-id="06673-147">See also</span></span>

