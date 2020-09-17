---
title: Обзор управления знаниями (Предварительная версия)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Обзор управления знаниями в Project кортекс.
ms.openlocfilehash: 80750ee94248b21b8ac7bd3869830a7986de34b9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949376"
---
# <a name="knowledge-management-0verview-preview"></a><span data-ttu-id="1c345-103">Центр управления знаниями 0verview (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="1c345-103">Knowledge management 0verview (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="1c345-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="1c345-104">The content in this article is for Project Cortex Private Preview.</span></span> [<span data-ttu-id="1c345-105">Узнайте больше о Project Кортекс</span><span class="sxs-lookup"><span data-stu-id="1c345-105">Find out more about Project Cortex</span></span>](https://aka.ms/projectcortex) 

<span data-ttu-id="1c345-106">Управление знаниями использует технологию Microsoft AI, Microsoft 365, delve, Поиск и другие компоненты и службы для создания сети знаний в среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c345-106">Knowledge management uses Microsoft AI technology, Microsoft 365, Delve, Search, and other components and services to build a knowledge network in your Microsoft 365 environment.</span></span> 

   ![Процесс управления знаниями](../media/content-understanding/knowledge-management-flowchart.png) </br> 

<span data-ttu-id="1c345-108">Цель состоит в том, чтобы предоставить пользователям сведения в приложениях, которые используются ежедневно, например Outlook, Teams и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1c345-108">It's goal is to deliver information to you users in apps they use everyday, such as Outlook, Teams, and SharePoint.</span></span>

<span data-ttu-id="1c345-109">Например, пользователи видят незнакомые термины в своих электронных письмах, сайтах SharePoint или в беседах Teams, которые им нужно знать.</span><span class="sxs-lookup"><span data-stu-id="1c345-109">For example, users see unfamiliar terms in their emails, SharePoint sites, or in Teams conversations, that they want to know more about.</span></span> <span data-ttu-id="1c345-110">Элемент управления знаниями использует AI для автоматического поиска и идентификации этих **разделов**, а также для компиляции сведений о них, таких как краткое описание темы и сайтов, файлов и связанных с ними страниц.</span><span class="sxs-lookup"><span data-stu-id="1c345-110">Knowledge management uses AI to automatically searches for and identifies these **topics**, and compiles information about them, such as a short description, subject matter experts on the topic, and sites, files, and pages that are related to it.</span></span> <span data-ttu-id="1c345-111">При необходимости можно выбрать обновление сведений о разделах.</span><span class="sxs-lookup"><span data-stu-id="1c345-111">You can choose to update the topic information as needed.</span></span> <span data-ttu-id="1c345-112">После этого можно сделать доступными для пользователей темы, что означает, что для каждого экземпляра раздела, который отображается в приложениях, таких как Outlook, Teams и SharePoint, текст будет выделен.</span><span class="sxs-lookup"><span data-stu-id="1c345-112">You can then make the topics available to your users, which means that for every instance of the topic that appears in apps such as Outlook, Teams, and SharePoint, the text will be highlighted.</span></span> <span data-ttu-id="1c345-113">Пользователи могут выбрать раздел, чтобы узнать больше о нем с помощью подробных сведений о теме.</span><span class="sxs-lookup"><span data-stu-id="1c345-113">Users can choose to select the topic to learn more about it through the topic details.</span></span>


## <a name="topic-discovery"></a><span data-ttu-id="1c345-114">Обнаружение разделов</span><span class="sxs-lookup"><span data-stu-id="1c345-114">Topic discovery</span></span>

<span data-ttu-id="1c345-115">Управление знаниями использует технологию Microsoft AI для поиска **разделов** в среде Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c345-115">Knowledge Management uses Microsoft AI technology to search for **topics** in your Office 365 environment.</span></span>

<span data-ttu-id="1c345-116">Тема — это фраза или термин, который является важным или важным для Организации.</span><span class="sxs-lookup"><span data-stu-id="1c345-116">A topic is a phrase or term that is organizationally significant or important.</span></span> <span data-ttu-id="1c345-117">Он имеет определенное значение для Организации и имеет связанные с ней ресурсы, которые помогут людям узнать, что это такое, и получить дополнительные сведения о ней.</span><span class="sxs-lookup"><span data-stu-id="1c345-117">It has a specific meaning to the organization, and has resources related to it that can help people understand what it is and find more information about it.</span></span>

<span data-ttu-id="1c345-118">При обнаружении раздела создается **страница раздела** , содержащая сведения, собранные по обнаружению разделов, например:</span><span class="sxs-lookup"><span data-stu-id="1c345-118">When a topic is discovered, a **topic page** is created for it that contains information that was gathered through topic discovery, such as:</span></span>

- <span data-ttu-id="1c345-119">Краткое описание статьи.</span><span class="sxs-lookup"><span data-stu-id="1c345-119">A short description of the topic.</span></span>
- <span data-ttu-id="1c345-120">Пользователи, которые могут быть знаниями о теме.</span><span class="sxs-lookup"><span data-stu-id="1c345-120">Users who might be knowledgeable about the topic.</span></span>
- <span data-ttu-id="1c345-121">Файлы, страницы и сайты, связанные с темой.</span><span class="sxs-lookup"><span data-stu-id="1c345-121">Files, pages, and sites that are related to the topic.</span></span>


## <a name="topic-management"></a><span data-ttu-id="1c345-122">Управление разделами</span><span class="sxs-lookup"><span data-stu-id="1c345-122">Topic management</span></span>

<span data-ttu-id="1c345-123">Управление разделами выполняется в **центре темы**Организации.</span><span class="sxs-lookup"><span data-stu-id="1c345-123">Topic management is done in your organization's **topic center**.</span></span> <span data-ttu-id="1c345-124">Сайт центра разделов создается во время установки и выступает в качестве центра знаний для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1c345-124">The topic center site is created during setup and serves as your center of knowledge for your organization.</span></span> <span data-ttu-id="1c345-125">Он будет содержать список всех разделов, обнаруженных в вашей среде, а также все темы, созданные для этих разделов.</span><span class="sxs-lookup"><span data-stu-id="1c345-125">It will contain a list of all topics that were discovered in your environment, as well as all topic pages that were created for these topics.</span></span> 

<span data-ttu-id="1c345-126">Пользователи, которым предоставлены правильные разрешения, смогут выполнять указанные ниже действия в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="1c345-126">Users who are provided the correct permissions will be able to do the following in the topic center:</span></span>

- <span data-ttu-id="1c345-127">Подтвердите или отклоните темы, обнаруженные в клиенте.</span><span class="sxs-lookup"><span data-stu-id="1c345-127">Confirm or reject topics that were discovered in your tenant.</span></span>
- <span data-ttu-id="1c345-128">При необходимости создайте новые разделы вручную (например, если было предоставлено недостаточно сведений для обнаружения с помощью AI).</span><span class="sxs-lookup"><span data-stu-id="1c345-128">Create new topics manually as needed (for example, if not enough information was provided for it to be discovered through AI).</span></span>
- <span data-ttu-id="1c345-129">Редактирование существующих тематических страниц.</span><span class="sxs-lookup"><span data-stu-id="1c345-129">Edit existing topic pages.</span></span></br>

<span data-ttu-id="1c345-130">Для получения дополнительных сведений ознакомьтесь со статьей ["работать с темой" в центре справки](work-with-topics.md) .</span><span class="sxs-lookup"><span data-stu-id="1c345-130">See [Work with topic in the topic center](work-with-topics.md) for more information.</span></span>  


## <a name="admin-controls"></a><span data-ttu-id="1c345-131">Элементы управления администратора</span><span class="sxs-lookup"><span data-stu-id="1c345-131">Admin controls</span></span>

<span data-ttu-id="1c345-132">Элементы управления администратора в центре администрирования Microsoft 365 позволяют управлять сетью знаний.</span><span class="sxs-lookup"><span data-stu-id="1c345-132">Admin controls in the Microsoft 365 admin center  allow you to manage your knowledge network.</span></span> <span data-ttu-id="1c345-133">Они позволяют глобальному администратору Microsoft 365 или администратору SharePoint:</span><span class="sxs-lookup"><span data-stu-id="1c345-133">They allow a Microsoft 365 global or SharePoint admin to:</span></span>

- <span data-ttu-id="1c345-134">Управление тем, какие пользователи в организации могут просматривать темы в своих клиентских приложениях или в результатах поиска SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1c345-134">Control which users in your organization are allowed to see topics in their client apps or in SharePoint search results.</span></span>
- <span data-ttu-id="1c345-135">Управление тем, какие сайты SharePoint будут обходиться при поиске разделов.</span><span class="sxs-lookup"><span data-stu-id="1c345-135">Control which SharePoint sites will be crawled to search for topics.</span></span>
- <span data-ttu-id="1c345-136">Настройка обнаружения разделов для исключения определенных терминов, которые не должны быть темой.</span><span class="sxs-lookup"><span data-stu-id="1c345-136">Configure topic discovery to exclude specific terms that you don't want to be a topic.</span></span>
- <span data-ttu-id="1c345-137">Определять, какие пользователи могут подтверждать или отклонять темы в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="1c345-137">Control which users can to confirm or reject topics in the topic center.</span></span>
- <span data-ttu-id="1c345-138">Определять, какие пользователи могут создавать и редактировать темы в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="1c345-138">Control which users can create and edit topics in the topic center.</span></span>

<span data-ttu-id="1c345-139">Для [получения](manage-knowledge-network.md) дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="1c345-139">See [Manage your knowledge network](manage-knowledge-network.md) for more information.</span></span> 

## <a name="topic-curation"></a><span data-ttu-id="1c345-140">Раздел куратион</span><span class="sxs-lookup"><span data-stu-id="1c345-140">Topic curation</span></span>

<span data-ttu-id="1c345-141">AI постоянно работает над предоставлением предложений по улучшению тем, как в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="1c345-141">AI will continually work to provide you suggestions to improve your topics as changes occur in your environment.</span></span>

<span data-ttu-id="1c345-142">Пользователи, которым разрешен доступ к, видят темы в повседневной работе, могут делать предложения по их улучшению.</span><span class="sxs-lookup"><span data-stu-id="1c345-142">Users who you allow access to see topics in their daily work are allowed to make suggestions to improve them.</span></span> <span data-ttu-id="1c345-143">Например, если пользователь просматривает страницу темы и видит неправильные сведения или необходимо добавить, ссылка на странице темы позволяет отправить запрос на обновление сведений.</span><span class="sxs-lookup"><span data-stu-id="1c345-143">For example, if a user views the topic page and sees information that is incorrect or needs to be added, a link on the topic page allows them to submit a request to update the information.</span></span>

<span data-ttu-id="1c345-144">Кроме того, пользователи с соответствующими разрешениями могут замечать такие элементы, как беседа в Teams, которые относятся к теме, и добавлять их в определенный раздел.</span><span class="sxs-lookup"><span data-stu-id="1c345-144">Additionally, users with proper permissions can tag items such as Teams conversation that are relevant to a topic, and add them to a specific topic.</span></span>




## <a name="see-also"></a><span data-ttu-id="1c345-145">См. также</span><span class="sxs-lookup"><span data-stu-id="1c345-145">See also</span></span>
[<span data-ttu-id="1c345-146">Настройка управления знаниями</span><span class="sxs-lookup"><span data-stu-id="1c345-146">Set up knowledge management</span></span>](set-up-knowledge-network.md)</br>
[<span data-ttu-id="1c345-147">Обзор центра разделов</span><span class="sxs-lookup"><span data-stu-id="1c345-147">Topic center overview</span></span>](topic-center-overview.md)
