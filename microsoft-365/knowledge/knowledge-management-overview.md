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
ms.openlocfilehash: 27ce6457f2329ccaa4738d6868b4f2051c0c0a51
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988846"
---
# <a name="knowledge-management-overview-preview"></a><span data-ttu-id="c3f47-103">Обзор управления знаниями (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c3f47-103">Knowledge management Overview (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="c3f47-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="c3f47-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c3f47-105">[Узнайте больше о работе с Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="c3f47-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="c3f47-106">Управление знаниями использует технологию Microsoft AI, Microsoft 365, delve, Поиск и другие компоненты и службы для создания сети знаний в среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3f47-106">Knowledge management uses Microsoft AI technology, Microsoft 365, Delve, Search, and other components and services to build a knowledge network in your Microsoft 365 environment.</span></span> 

   ![Процесс управления знаниями](../media/content-understanding/knowledge-management-flowchart.png) </br> 

<span data-ttu-id="c3f47-108">Цель состоит в том, чтобы предоставить пользователям сведения в приложениях, которые используются ежедневно, например Outlook, Teams и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c3f47-108">It's goal is to deliver information to you users in apps they use everyday, such as Outlook, Teams, and SharePoint.</span></span>

<span data-ttu-id="c3f47-109">Например, пользователи видят незнакомые термины в своих электронных письмах, сайтах SharePoint или в беседах Teams, которые им нужно знать.</span><span class="sxs-lookup"><span data-stu-id="c3f47-109">For example, users see unfamiliar terms in their emails, SharePoint sites, or in Teams conversations, that they want to know more about.</span></span> <span data-ttu-id="c3f47-110">Элемент управления знаниями использует AI для автоматического поиска и идентификации этих **разделов** , а также для компиляции сведений о них, таких как краткое описание темы и сайтов, файлов и связанных с ними страниц.</span><span class="sxs-lookup"><span data-stu-id="c3f47-110">Knowledge management uses AI to automatically searches for and identifies these **topics** , and compiles information about them, such as a short description, subject matter experts on the topic, and sites, files, and pages that are related to it.</span></span> <span data-ttu-id="c3f47-111">При необходимости можно выбрать обновление сведений о разделах.</span><span class="sxs-lookup"><span data-stu-id="c3f47-111">You can choose to update the topic information as needed.</span></span> <span data-ttu-id="c3f47-112">После этого можно сделать доступными для пользователей темы, что означает, что для каждого экземпляра раздела, который отображается в приложениях, таких как Outlook, Teams и SharePoint, текст будет выделен.</span><span class="sxs-lookup"><span data-stu-id="c3f47-112">You can then make the topics available to your users, which means that for every instance of the topic that appears in apps such as Outlook, Teams, and SharePoint, the text will be highlighted.</span></span> <span data-ttu-id="c3f47-113">Пользователи могут выбрать раздел, чтобы узнать больше о нем с помощью подробных сведений о теме.</span><span class="sxs-lookup"><span data-stu-id="c3f47-113">Users can choose to select the topic to learn more about it through the topic details.</span></span>


## <a name="topic-indexing"></a><span data-ttu-id="c3f47-114">Индексирование разделов</span><span class="sxs-lookup"><span data-stu-id="c3f47-114">Topic indexing</span></span>

<span data-ttu-id="c3f47-115">Управление знаниями использует технологию Microsoft AI для определения **тем** в вашей среде Office 365.</span><span class="sxs-lookup"><span data-stu-id="c3f47-115">Knowledge Management uses Microsoft AI technology to identify **topics** in your Office 365 environment.</span></span>

<span data-ttu-id="c3f47-116">Тема — это фраза или термин, который является важным или важным для Организации.</span><span class="sxs-lookup"><span data-stu-id="c3f47-116">A topic is a phrase or term that is organizationally significant or important.</span></span> <span data-ttu-id="c3f47-117">Он имеет определенное значение для Организации и имеет связанные с ней ресурсы, которые помогут людям узнать, что это такое, и получить дополнительные сведения о ней.</span><span class="sxs-lookup"><span data-stu-id="c3f47-117">It has a specific meaning to the organization, and has resources related to it that can help people understand what it is and find more information about it.</span></span>

<span data-ttu-id="c3f47-118">При указании темы создается **страница раздела** , содержащая сведения, собранные по индексированию разделов, например:</span><span class="sxs-lookup"><span data-stu-id="c3f47-118">When a topic is identified, a **topic page** is created for it that contains information that was gathered through topic indexing, such as:</span></span>

- <span data-ttu-id="c3f47-119">Альтернативные имена и/или акронимы.</span><span class="sxs-lookup"><span data-stu-id="c3f47-119">Alternate names and/or acronyms.</span></span>
- <span data-ttu-id="c3f47-120">Краткое описание статьи.</span><span class="sxs-lookup"><span data-stu-id="c3f47-120">A short description of the topic.</span></span>
- <span data-ttu-id="c3f47-121">Пользователи, которые могут быть знаниями о теме.</span><span class="sxs-lookup"><span data-stu-id="c3f47-121">Users who might be knowledgeable about the topic.</span></span>
- <span data-ttu-id="c3f47-122">Файлы, страницы и сайты, связанные с темой.</span><span class="sxs-lookup"><span data-stu-id="c3f47-122">Files, pages, and sites that are related to the topic.</span></span>


## <a name="topic-discovery"></a><span data-ttu-id="c3f47-123">Обнаружение разделов</span><span class="sxs-lookup"><span data-stu-id="c3f47-123">Topic discovery</span></span>
<span data-ttu-id="c3f47-124">Если раздел упоминается в контенте новостей и страницах SharePoint, он будет выделен.</span><span class="sxs-lookup"><span data-stu-id="c3f47-124">When a topic is mentioned in content on SharePoint news and pages, you'll see it highlighted.</span></span> <span data-ttu-id="c3f47-125">Откройте сводку разделов из выделения.</span><span class="sxs-lookup"><span data-stu-id="c3f47-125">Open the topic summary from the highlight.</span></span> <span data-ttu-id="c3f47-126">Откройте раздел сведения в заголовке сводки.</span><span class="sxs-lookup"><span data-stu-id="c3f47-126">Open the topic details from the title of the summary.</span></span> <!--(msg for Efren: not sure if I should use discovery for this; we use discovered in-product for indexing?)--> <span data-ttu-id="c3f47-127">Упомянутый раздел можно автоматически определить или добавить на страницу, указав прямую ссылку на раздел автора страницы.</span><span class="sxs-lookup"><span data-stu-id="c3f47-127">The mentioned topic could be identified automatically or have been added to the page with a direct reference to the topic by the page author.</span></span>

<span data-ttu-id="c3f47-128">Кроме того, вы можете обнаруживать темы в Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="c3f47-128">You can also discover topics through Microsoft Search.</span></span>


## <a name="topic-management"></a><span data-ttu-id="c3f47-129">Управление разделами</span><span class="sxs-lookup"><span data-stu-id="c3f47-129">Topic management</span></span>

<span data-ttu-id="c3f47-130">Управление разделами выполняется в **центре темы** Организации.</span><span class="sxs-lookup"><span data-stu-id="c3f47-130">Topic management is done in your organization's **topic center**.</span></span> <span data-ttu-id="c3f47-131">Сайт центра разделов создается во время установки и выступает в качестве центра знаний для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c3f47-131">The topic center site is created during setup and serves as your center of knowledge for your organization.</span></span> <span data-ttu-id="c3f47-132">Он будет содержать список всех разделов, обнаруженных в вашей среде, а также все темы, созданные для этих разделов.</span><span class="sxs-lookup"><span data-stu-id="c3f47-132">It will contain a list of all topics that were discovered in your environment, as well as all topic pages that were created for these topics.</span></span> 

<span data-ttu-id="c3f47-133">Пользователи, которым предоставлены правильные разрешения, смогут выполнять указанные ниже действия в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="c3f47-133">Users who are provided the correct permissions will be able to do the following in the topic center:</span></span>

- <span data-ttu-id="c3f47-134">Подтвердите или отклоните темы, обнаруженные в клиенте.</span><span class="sxs-lookup"><span data-stu-id="c3f47-134">Confirm or reject topics that were discovered in your tenant.</span></span>
- <span data-ttu-id="c3f47-135">При необходимости создайте новые разделы вручную (например, если было предоставлено недостаточно сведений для обнаружения с помощью AI).</span><span class="sxs-lookup"><span data-stu-id="c3f47-135">Create new topics manually as needed (for example, if not enough information was provided for it to be discovered through AI).</span></span>
- <span data-ttu-id="c3f47-136">Редактирование существующих тематических страниц.</span><span class="sxs-lookup"><span data-stu-id="c3f47-136">Edit existing topic pages.</span></span></br>

<span data-ttu-id="c3f47-137">Для получения дополнительных сведений ознакомьтесь со статьей ["работать с темой" в центре справки](work-with-topics.md) .</span><span class="sxs-lookup"><span data-stu-id="c3f47-137">See [Work with topic in the topic center](work-with-topics.md) for more information.</span></span>  


## <a name="admin-controls"></a><span data-ttu-id="c3f47-138">Элементы управления администратора</span><span class="sxs-lookup"><span data-stu-id="c3f47-138">Admin controls</span></span>

<span data-ttu-id="c3f47-139">Элементы управления администратора в центре администрирования Microsoft 365 позволяют управлять сетью знаний.</span><span class="sxs-lookup"><span data-stu-id="c3f47-139">Admin controls in the Microsoft 365 admin center  allow you to manage your knowledge network.</span></span> <span data-ttu-id="c3f47-140">Они позволяют глобальному администратору Microsoft 365 или администратору SharePoint:</span><span class="sxs-lookup"><span data-stu-id="c3f47-140">They allow a Microsoft 365 global or SharePoint admin to:</span></span>

- <span data-ttu-id="c3f47-141">Управление тем, какие пользователи в организации могут просматривать темы в своих клиентских приложениях или в результатах поиска SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c3f47-141">Control which users in your organization are allowed to see topics in their client apps or in SharePoint search results.</span></span>
- <span data-ttu-id="c3f47-142">Управление тем, какие сайты SharePoint будут обходиться при поиске разделов.</span><span class="sxs-lookup"><span data-stu-id="c3f47-142">Control which SharePoint sites will be crawled to search for topics.</span></span>
- <span data-ttu-id="c3f47-143">Настройка обнаружения разделов для исключения определенных терминов, которые не должны быть темой.</span><span class="sxs-lookup"><span data-stu-id="c3f47-143">Configure topic discovery to exclude specific terms that you don't want to be a topic.</span></span>
- <span data-ttu-id="c3f47-144">Определять, какие пользователи могут подтверждать или отклонять темы в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="c3f47-144">Control which users can to confirm or reject topics in the topic center.</span></span>
- <span data-ttu-id="c3f47-145">Определять, какие пользователи могут создавать и редактировать темы в центре разделов.</span><span class="sxs-lookup"><span data-stu-id="c3f47-145">Control which users can create and edit topics in the topic center.</span></span>

<span data-ttu-id="c3f47-146">Для [получения](topic-experiences-discovery.md) дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="c3f47-146">See [Manage your knowledge network](topic-experiences-discovery.md) for more information.</span></span> 

## <a name="topic-curation--feedback"></a><span data-ttu-id="c3f47-147">Тема куратион & отзывов</span><span class="sxs-lookup"><span data-stu-id="c3f47-147">Topic curation & feedback</span></span>

<span data-ttu-id="c3f47-148">AI постоянно работает над предоставлением предложений по улучшению тем, как в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="c3f47-148">AI will continually work to provide you suggestions to improve your topics as changes occur in your environment.</span></span>

<span data-ttu-id="c3f47-149">Пользователи, которым разрешен доступ к, видят темы в повседневной работе, могут делать предложения по их улучшению.</span><span class="sxs-lookup"><span data-stu-id="c3f47-149">Users who you allow access to see topics in their daily work are allowed to make suggestions to improve them.</span></span> <span data-ttu-id="c3f47-150">Например, если пользователь просматривает страницу темы и видит неправильные сведения или необходимо добавить, ссылка на странице темы позволяет им редактировать информацию напрямую.</span><span class="sxs-lookup"><span data-stu-id="c3f47-150">For example, if a user views the topic page and sees information that is incorrect or needs to be added, a link on the topic page allows them to edit the information directly.</span></span> <span data-ttu-id="c3f47-151">Другой пример: Если пользователь просматривает страницу "Новости SharePoint", вы найдете вопросы, предлагающие, подходит ли Подчеркните или подходит ли предлагаемый раздел для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c3f47-151">Another example, if a user views a a highlight on a SharePoint news page, you will find questions asking whether or not the highlight is appropriate or the suggested topic is appropriate for your organization.</span></span> <span data-ttu-id="c3f47-152">Ваш ответ поможет определить, что отображается в сводных сведениях о разделах и в разделах.</span><span class="sxs-lookup"><span data-stu-id="c3f47-152">Your answer will help determine what's shown on topic summaries and in topic details.</span></span>

<span data-ttu-id="c3f47-153">Кроме того, пользователи с соответствующими разрешениями могут замечать такие элементы, как беседа Yammer, которые относятся к теме, и добавлять их в конкретный раздел.</span><span class="sxs-lookup"><span data-stu-id="c3f47-153">Additionally, users with proper permissions can tag items such as Yammer conversation that are relevant to a topic, and add them to a specific topic.</span></span> <!--(msg for Efren: changed to Yammer, because we will not have shipped Teams yet)-->


## <a name="see-also"></a><span data-ttu-id="c3f47-154">См. также</span><span class="sxs-lookup"><span data-stu-id="c3f47-154">See also</span></span>
[<span data-ttu-id="c3f47-155">Настройка управления знаниями</span><span class="sxs-lookup"><span data-stu-id="c3f47-155">Set up knowledge management</span></span>](set-up-topic-experiences.md)</br>
[<span data-ttu-id="c3f47-156">Обзор центра разделов</span><span class="sxs-lookup"><span data-stu-id="c3f47-156">Topic center overview</span></span>](topic-center-overview.md)
