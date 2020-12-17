---
title: 'Обнаружение и курсирование тем "Опыт работы с разделами" (предварительная версия) '
description: Обзор того, как обнаруживаются разделы.
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 2d885d841b280e345d90742fe003bb443160c21f
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699058"
---
# <a name="topic-experiences-discovery-and-curation-preview"></a><span data-ttu-id="c3353-103">Обнаружение и курсор "Опыт работы с разделами" (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c3353-103">Topic Experiences discovery and curation (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="c3353-104">Содержимое этой статьи для Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="c3353-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c3353-105">[Узнайте больше о работе с Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="c3353-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="c3353-106">Раздел "Опыт" преобразует сведения знаний в знания в среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3353-106">Topic Experiences converts knowledge information to knowledge in your Microsoft 365 environment.</span></span> <span data-ttu-id="c3353-107">Все мы считываем документы и страницы сайтов, с которыми мы сталкивались с незнакомыми терминами.</span><span class="sxs-lookup"><span data-stu-id="c3353-107">We've all experienced reading through documents and site pages where we encounter terms we are unfamiliar with.</span></span> <span data-ttu-id="c3353-108">Мы много раз останавливаем то, что делаем, чтобы тратить время на поиск дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="c3353-108">Many times we stop what we are doing to spend precious time searching for more information.</span></span>

<span data-ttu-id="c3353-109">В разделе "Опыт" используется Microsoft Graph и ИИ **для** определения тем в организации.</span><span class="sxs-lookup"><span data-stu-id="c3353-109">What Topic Experiences does is use Microsoft Graph and AI to identify **topics** in your organization.</span></span>  <span data-ttu-id="c3353-110">Тема — это фраза или термин, которые имеют определенное значение для организации, где пользователям будет полезно просматривать вики-страницу о ней.</span><span class="sxs-lookup"><span data-stu-id="c3353-110">A topic is a phrase or term that has a specific meaning to an organization, where users would benefit by being able to view a wiki page about it.</span></span> <span data-ttu-id="c3353-111">ИИ выполняет поиск людей и контента, связанных с разделом, и если его достаточно, он становится рекомендуемым разделом.</span><span class="sxs-lookup"><span data-stu-id="c3353-111">AI searches for people and content connected to the topic, and if enough it discovered, it becomes a suggested topic.</span></span>

<span data-ttu-id="c3353-112">Сведения о теме, созданные ИИ, добавляются на страницу **"Тема",** которая может содержать:</span><span class="sxs-lookup"><span data-stu-id="c3353-112">The AI generated topic information is added to a **Topic page**, which can contain:</span></span>
- <span data-ttu-id="c3353-113">Краткое описание этой темы.</span><span class="sxs-lookup"><span data-stu-id="c3353-113">A short description of the topic.</span></span>
- <span data-ttu-id="c3353-114">Альтернативные имена для темы.</span><span class="sxs-lookup"><span data-stu-id="c3353-114">Alternate names for the topic.</span></span>
- <span data-ttu-id="c3353-115">Люди, которые могут узнать больше об этой теме.</span><span class="sxs-lookup"><span data-stu-id="c3353-115">People who might know more about the topic.</span></span>
- <span data-ttu-id="c3353-116">Сайты, файлы и страницы, которые могут быть связаны с темой.</span><span class="sxs-lookup"><span data-stu-id="c3353-116">Sites, files, and pages that might be related to the topic.</span></span>

<span data-ttu-id="c3353-117">В этом случае каждый экземпляр темы выделяется на всех современных страницах сайтов SharePoint в клиенте.</span><span class="sxs-lookup"><span data-stu-id="c3353-117">Topic experiences then makes sure that every instance of a topic is highlighted on all SharePoint modern site pages in your tenant.</span></span> <span data-ttu-id="c3353-118">Если пользователю интересно узнать больше о теме, он может выбрать  выделенную тему, чтобы просмотреть сводную карточку "Тема", которая содержит краткое описание.</span><span class="sxs-lookup"><span data-stu-id="c3353-118">When a user is curious to learn more about a topic, they can select the highlighted topic to view a **Topic summary** card that provides a short description.</span></span> <span data-ttu-id="c3353-119">Если они хотят получить дополнительные сведения, они могут выбрать ссылку "Сведения о разделе" в сводке, чтобы открыть страницу с подробными сведениями. </span><span class="sxs-lookup"><span data-stu-id="c3353-119">And if they want to learn more, they can select a **Topic details** link in the summary to open the detailed topic page.</span></span>

![Основные темы](../media/knowledge-management/saturn.png) </br>

<span data-ttu-id="c3353-121">Кроме того, пользователи также смогут найти разделы с помощью Поиска (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="c3353-121">Additionally, users will also be able to find topics through Microsoft Search.</span></span>


## <a name="topic-curation"></a><span data-ttu-id="c3353-122">Курсор темы</span><span class="sxs-lookup"><span data-stu-id="c3353-122">Topic curation</span></span>

<span data-ttu-id="c3353-123">Раздел "Опыт" приветствует "курсор" человека для улучшения качества ваших разделов.</span><span class="sxs-lookup"><span data-stu-id="c3353-123">Topic Experiences welcomes human "curation" to improve the quality of your topics.</span></span> <span data-ttu-id="c3353-124">Хотя ИИ изначально определяет и предлагает темы, обновления контента от участников вручную, подтверждение от пользователей на содержимое, созданный ИИ, и отзывы о полезности тем очень важны.</span><span class="sxs-lookup"><span data-stu-id="c3353-124">While AI initially identifies and suggests topics, manually made updates to content from contributors, confirmation from users for AI generated content, and feedback on the usefulness of topics are all essential.</span></span>

- <span data-ttu-id="c3353-125">Разделы, созданные ИИ (рекомендуемые темы), могут просмотреть **менеджеры по анализу** в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c3353-125">AI generated topics ("suggested topics") can be reviewed by **knowledge managers** in your organization.</span></span> <span data-ttu-id="c3353-126">На странице "Управление разделами" в центре тем можно подтвердить их как допустимые или отклонить, чтобы запретить их просмотр.</span><span class="sxs-lookup"><span data-stu-id="c3353-126">In the Manage Topics page in the Topic Center, they can choose to confirm them as valid, or reject them to prevent them from being viewed.</span></span>

- <span data-ttu-id="c3353-127">Вы можете *назначить* разрешения на создание и редактирование разделов любому из лицензированных пользователей, чтобы они могли вносить изменения в существующие разделы или при необходимости создавать новые темы.</span><span class="sxs-lookup"><span data-stu-id="c3353-127">You can assign *Create and edit topics* permissions to any of your licensed users so that they can make changes to existing topics or create new topics when needed.</span></span> 

- <span data-ttu-id="c3353-128">Даже пользователям, у которых есть только доступ на чтение тем (читателям тем), будет предложено проверить полезность определенных разделов.</span><span class="sxs-lookup"><span data-stu-id="c3353-128">Even users who only have read access to topic (topic viewers) will be asked to verify the usefulness of specific topics.</span></span>

<span data-ttu-id="c3353-129">Даже при нацелии на человека ИИ будет постоянно искать дополнительные сведения о темах и искать проверку человека.</span><span class="sxs-lookup"><span data-stu-id="c3353-129">Even with human curation, AI will continually look for more information about topics, and will look for human verification.</span></span> <span data-ttu-id="c3353-130">Например, если ИИ считает, что вы человек, которого следует закрепить в качестве эксперта по теме, он попросит вас подтвердить это.</span><span class="sxs-lookup"><span data-stu-id="c3353-130">For example, if AI thinks you are a person that should be pinned as an expert on a topic, it will ask you to confirm this.</span></span> 

















## <a name="see-also"></a><span data-ttu-id="c3353-131">См. также</span><span class="sxs-lookup"><span data-stu-id="c3353-131">See also</span></span>



  






