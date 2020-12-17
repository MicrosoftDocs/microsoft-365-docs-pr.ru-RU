---
title: Обзор "Опыт работы с разделами" (предварительная версия)
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
description: Обзор работы с разделами.
ms.openlocfilehash: 9321f349056c1c4df36b6bd725214f3c6758cf6a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699043"
---
# <a name="topic-experiences-overview-preview"></a><span data-ttu-id="9e0ef-103">Обзор "Опыт работы с разделами" (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="9e0ef-103">Topic Experiences overview (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="9e0ef-104">Содержимое этой статьи для Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="9e0ef-105">[Узнайте больше о работе с Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="9e0ef-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="9e0ef-106">В разделе используются технологии Microsoft AI, Microsoft 365, Delve, Microsoft Graph, Поиск и другие компоненты и службы для создания сети знаний в среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-106">Topic experiences uses Microsoft AI technology, Microsoft 365, Delve, Microsoft Graph, Search, and other components and services to build a knowledge network in your Microsoft 365 environment.</span></span> 

   ![Поток управления знаниями](../media/knowledge-management/knowledge-management-flowchart.png) </br> 

<span data-ttu-id="9e0ef-108">Ее цель — преобразовывать информацию в знания и доставлять ее пользователям в приложениях, которые они используют каждый день, таких как современные страницы SharePoint и Поиск (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="9e0ef-108">Its goal is to convert information into knowledge and deliver it to your users in apps they use everyday, such as SharePoint modern pages and Microsoft Search.</span></span>

<span data-ttu-id="9e0ef-109">Темы помогают решить ключевую бизнес-проблему во многих компаниях, предоставляя информацию пользователям, когда они в ней нуждаются.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-109">Topic experiences helps to address a key business issue in many companies - providing the information to users when they need it.</span></span> <span data-ttu-id="9e0ef-110">Например, новым сотрудникам необходимо быстро изучить большое количество новых сведений и столкнуться с терминами, о которым они ничего не знают при чтении сведений о компании.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-110">For example, new employees need to learn a lot of new information quickly, and encounter terms they know nothing about when reading through company information.</span></span> <span data-ttu-id="9e0ef-111">Чтобы получить дополнительные сведения, пользователю может потребоваться отойти от того, что он делает, и тратить ценное время на поиск сведений, таких как сведения о том, что такое термин, кто в организации является экспертом по теме, а также сайты и документы, связанные с этим термином.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-111">To learn more, the user might need to step away from what they are doing and spend valuable time searching for details, such as information about what the term is, who in the organization is a subject matter expert, and maybe sites and documents that are related to the term.</span></span>

<span data-ttu-id="9e0ef-112">В разделе используется ИИ для автоматического поиска и **определения** тем в организации.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-112">Topic experiences uses AI to automatically search for and identify **topics** in your organization.</span></span> <span data-ttu-id="9e0ef-113">Он компилирует сведения о них, такие как краткое описание, эксперты по теме, а также сайты, файлы и страницы, связанные с ним.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-113">It compiles information about them, such as a short description, subject matter experts on the topic, and sites, files, and pages that are related to it.</span></span> <span data-ttu-id="9e0ef-114">Менеджер по знаниям или участник может выбрать обновление сведений о теме по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-114">A knowledge manager or contributor can choose to update the topic information as needed.</span></span> <span data-ttu-id="9e0ef-115">Разделы доступны для пользователей, что означает, что для каждого экземпляра темы, которая отображается на современном сайте SharePoint в новостей и на страницах, текст будет выделен.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-115">The topics are available to your users, which means that for every instance of the topic that appears in a modern SharePoint site in news and pages, the text will be highlighted.</span></span> <span data-ttu-id="9e0ef-116">Пользователи могут выбрать раздел, чтобы получить дополнительные сведения о нем в разделе.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-116">Users can choose to select the topic to learn more about it through the topic details.</span></span> <span data-ttu-id="9e0ef-117">Разделы также можно найти в поиске SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-117">Topics can also be found in SharePoint Search.</span></span>


## <a name="how-topics-are-displayed-to-users"></a><span data-ttu-id="9e0ef-118">Отображение тем для пользователей</span><span class="sxs-lookup"><span data-stu-id="9e0ef-118">How topics are displayed to users</span></span>

<span data-ttu-id="9e0ef-119">Если тема упоминается в контенте новостей и страниц SharePoint, она будет выделена.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-119">When a topic is mentioned in content on SharePoint news and pages, you'll see it highlighted.</span></span> <span data-ttu-id="9e0ef-120">Вы можете открыть сводку темы из выделения.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-120">You can open the topic summary from the highlight.</span></span> <span data-ttu-id="9e0ef-121">Откройте раздел сведений из заголовка сводки.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-121">Open the topic details from the title of the summary.</span></span> <span data-ttu-id="9e0ef-122">Упомянутый раздел может быть определен автоматически или добавлен на страницу с прямой ссылкой на раздел автором страницы.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-122">The mentioned topic could be identified automatically or have been added to the page with a direct reference to the topic by the page author.</span></span> 

   ![Основные темы](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a><span data-ttu-id="9e0ef-124">Индексация знаний</span><span class="sxs-lookup"><span data-stu-id="9e0ef-124">Knowledge indexing</span></span>

<span data-ttu-id="9e0ef-125">В темах используется технология Microsoft AI для определения тем **в** среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-125">Topic experiences uses Microsoft AI technology to identify **topics** in your Microsoft 365 environment.</span></span>

<span data-ttu-id="9e0ef-126">Тема — это фраза или термин, которые важны или важны для организации.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-126">A topic is a phrase or term that is organizationally significant or important.</span></span> <span data-ttu-id="9e0ef-127">Она имеет определенное значение для организации и имеет связанные с ней ресурсы, которые помогут людям понять, что это такое, и найти дополнительные сведения о ней.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-127">It has a specific meaning to the organization, and has resources related to it that can help people understand what it is and find more information about it.</span></span>

<span data-ttu-id="9e0ef-128">Если идентифицированный раздел и ИИ определяет, что в нем достаточно  сведений, чтобы стать рекомендуемой темой, для него создается страница темы, содержаная сведения, собранные с помощью индексации тем, например:</span><span class="sxs-lookup"><span data-stu-id="9e0ef-128">When a topic is identified and AI determines that it has enough information for it to be a suggested topic, a **topic page** is created for it that contains information that was gathered through topic indexing, such as:</span></span>

- <span data-ttu-id="9e0ef-129">Альтернативные имена и/или акронимы.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-129">Alternate names and/or acronyms.</span></span>
- <span data-ttu-id="9e0ef-130">Краткое описание этой темы.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-130">A short description of the topic.</span></span>
- <span data-ttu-id="9e0ef-131">Пользователи, которые могут быть осведомлены о теме.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-131">Users who might be knowledgeable about the topic.</span></span>
- <span data-ttu-id="9e0ef-132">Файлы, страницы и сайты, связанные с этой темой.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-132">Files, pages, and sites that are related to the topic.</span></span>

<span data-ttu-id="9e0ef-133">Администраторы знаний могут выбрать обход всех сайтов SharePoint в клиенте для разделов или выбрать только некоторые из них.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-133">Your knowledge admins can choose to crawl all SharePoint sites in your tenant for topics, or to just select certain ones.</span></span>

## <a name="roles"></a><span data-ttu-id="9e0ef-134">Роли</span><span class="sxs-lookup"><span data-stu-id="9e0ef-134">Roles</span></span>

<span data-ttu-id="9e0ef-135">При использовании разделов в среде Microsoft 365 ваши пользователи будут иметь следующие роли:</span><span class="sxs-lookup"><span data-stu-id="9e0ef-135">When you use Topic experiences in you Microsoft 365 environment, your users will have the following roles:</span></span>

- <span data-ttu-id="9e0ef-136">Просмотр темы: пользователи, которые смогут просматривать основные темы на современных  сайтах SharePoint, к которым у них есть по крайней мере доступ на чтение, и в Поиске (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="9e0ef-136">Topic viewer: Users who will be able to see topic highlights on SharePoint modern sites that they have at least *Read* access to, and in Microsoft Search.</span></span> <span data-ttu-id="9e0ef-137">Они смогут выбрать основные разделы тем, чтобы увидеть сведения о теме на страницах тем.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-137">They will be able to select topic highlights to see topic details in topic pages.</span></span> <span data-ttu-id="9e0ef-138">Посетители тем смогут предоставлять отзывы о полезности темы.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-138">Topic viewers will be able to provide feedback on how useful a topic is to them.</span></span>

- <span data-ttu-id="9e0ef-139">Авторы: пользователи с правами на редактирование существующих разделов или создание новых.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-139">Contributors: Users who have rights to edit existing topics or create new ones.</span></span> <span data-ttu-id="9e0ef-140">Администраторы знаний назначают пользователям разрешения участников с помощью параметров работы с разделами в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-140">Knowledge admins assign contributor permissions to users through the Topic experiences settings in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9e0ef-141">Обратите внимание, что вы также можете предоставить всем читателям тем разрешение на редактирование и создание тем, чтобы они также могли вносить свой вклад в просмотримые темы.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-141">Note that you can also choose to give all topic viewers the permission to edit and create topics so that they can also contribute to topics that they see.</span></span>

- <span data-ttu-id="9e0ef-142">Менеджеры знаний: пользователи, которые направляют разделы в течение жизненного цикла темы.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-142">Knowledge managers: Users who guide topics through the topic lifecycle.</span></span> <span data-ttu-id="9e0ef-143">Менеджеры по  знаниям используют страницу "Управление разделами" в Центре тем для подтверждения или удаления тем, предлагаемых ИИ, а также для редактирования существующих разделов или создания новых. К ним имеют доступ только пользователи.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-143">Knowledge managers use the **Manage Topics** page in the Topic center to confirm or remove AI-suggested topics, as well as edit existing topics or create new ones, and are the only users who have access to it.</span></span> <span data-ttu-id="9e0ef-144">Администраторы знаний назначают пользователям разрешения диспетчера знаний с помощью параметров администрирования "Раздел" в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-144">Knowledge admins assign knowledge manager permissions to users through the Topic experiences admin settings in the Microsoft 365 admin center.</span></span> 

- <span data-ttu-id="9e0ef-145">Администраторы знаний: администраторы знаний устанавливают интерфейсы раздела и управляют ими с помощью элементов управления администратора в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-145">Knowledge admins: Knowledge admins set up Topic experiences and manage it through the admin controls in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9e0ef-146">В настоящее время глобальный администратор Microsoft 365 или администратор SharePoint может выступать в качестве администратора знаний.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-146">Currently, a Microsoft 365 global or SharePoint administrator can serve as a knowledge admin.</span></span>

<span data-ttu-id="9e0ef-147">Дополнительные [сведения см. в](topic-experiences-roles.md) разделах "Опыт работы".</span><span class="sxs-lookup"><span data-stu-id="9e0ef-147">See [Topic Experiences roles](topic-experiences-roles.md) for more information.</span></span>

## <a name="topic-management"></a><span data-ttu-id="9e0ef-148">Управление темами</span><span class="sxs-lookup"><span data-stu-id="9e0ef-148">Topic management</span></span>

<span data-ttu-id="9e0ef-149">Управление темами можно сделать на странице "Управление **темами"** в Центре тем **организации.**</span><span class="sxs-lookup"><span data-stu-id="9e0ef-149">Topic management is done in the **Manage topics** page in your organization's **Topic center**.</span></span> <span data-ttu-id="9e0ef-150">Центр тем создается во время настройки и служит центром знаний для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-150">The Topic center is created during setup and serves as your center of knowledge for your organization.</span></span> 

<span data-ttu-id="9e0ef-151">Хотя все лицензированные пользователи смогут просматривать разделы, с которые они  связаны, в Центре тем, только пользователи с разрешениями на управление темами (менеджеры по знаниям) смогут просматривать и использовать страницу "Управление темами".</span><span class="sxs-lookup"><span data-stu-id="9e0ef-151">While all licensed users will be able to see topics they are connected with in the Topic center, only users with *Manage topics* permissions (knowledge managers) will be able to view and use the Manage topics page.</span></span>

<span data-ttu-id="9e0ef-152">Менеджеры по знаниям смогут:</span><span class="sxs-lookup"><span data-stu-id="9e0ef-152">Knowledge managers will be able to:</span></span>

- <span data-ttu-id="9e0ef-153">Подтвердите или отклонить разделы, обнаруженные в клиенте.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-153">Confirm or reject topics that were discovered in your tenant.</span></span>
- <span data-ttu-id="9e0ef-154">Создайте новые разделы вручную по мере необходимости (например, если было предоставлено недостаточно сведений, чтобы их можно было обнаружить с помощью ИИ).</span><span class="sxs-lookup"><span data-stu-id="9e0ef-154">Create new topics manually as needed (for example, if not enough information was provided for it to be discovered through AI).</span></span>
- <span data-ttu-id="9e0ef-155">Изменение существующих страниц тем.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-155">Edit existing topic pages.</span></span></br>

<span data-ttu-id="9e0ef-156">Дополнительные [сведения см. в разделах "Управление"](manage-topics.md) в Центре тем.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-156">See [Manage topics in the Topic center](manage-topics.md) for more information.</span></span>  


## <a name="admin-controls"></a><span data-ttu-id="9e0ef-157">Элементы управления для администраторов</span><span class="sxs-lookup"><span data-stu-id="9e0ef-157">Admin controls</span></span>

<span data-ttu-id="9e0ef-158">Элементы управления администратора в Центре администрирования Microsoft 365 позволяют управлять сетью знаний.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-158">Admin controls in the Microsoft 365 admin center allow you to manage your knowledge network.</span></span> <span data-ttu-id="9e0ef-159">Они позволяют глобальному администратору Microsoft 365 или SharePoint:</span><span class="sxs-lookup"><span data-stu-id="9e0ef-159">They allow a Microsoft 365 global or SharePoint administrator to:</span></span>

- <span data-ttu-id="9e0ef-160">У контролировать, какие пользователи в организации могут видеть разделы на современных страницах SharePoint или в результатах поиска SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-160">Control which users in your organization are allowed to see topics in SharePoint modern pages or in SharePoint search results.</span></span>
- <span data-ttu-id="9e0ef-161">Управление темами для обхода сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-161">Control which SharePoint sites will be crawled to search for topics.</span></span>
- <span data-ttu-id="9e0ef-162">Настройте обнаружение тем, чтобы исключить определенные разделы из найденных.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-162">Configure topic discovery to exclude specific topics from being found.</span></span>
- <span data-ttu-id="9e0ef-163">Управляйте темами в центре тем.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-163">Control which users can manage topics in the topic center.</span></span>
- <span data-ttu-id="9e0ef-164">Управление темами, которые могут создавать и редактировать пользователи в центре тем.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-164">Control which users can create and edit topics in the topic center.</span></span>
- <span data-ttu-id="9e0ef-165">Управление темами, которые пользователи смогут просматривать.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-165">Control which user will be able to view topics.</span></span>

<span data-ttu-id="9e0ef-166">Дополнительные [сведения об административных средствах](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions)управления см. в разделах "Назначение разрешений пользователям", "Управление видимостью тем" и "Управление обнаружением тем". [](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules) [](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery)</span><span class="sxs-lookup"><span data-stu-id="9e0ef-166">See [assign user permissions](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions), [manage topic visibility](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules), and [manage topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery) for more information about admin controls.</span></span>

## <a name="topic-curation--feedback"></a><span data-ttu-id="9e0ef-167">Отзывы о курсоре & тем</span><span class="sxs-lookup"><span data-stu-id="9e0ef-167">Topic curation & feedback</span></span>

<span data-ttu-id="9e0ef-168">ИИ будет постоянно работать над предоставлением предложений по улучшению тем по мере изменения среды.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-168">AI will continually work to provide you suggestions to improve your topics as changes occur in your environment.</span></span> 

<span data-ttu-id="9e0ef-169">Пользователям, которым вы разрешаете доступ к темам в повседневной работе, может быть задан вопрос о том, была ли эта тема полезной для них.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-169">Users who you allow access to see topics in their daily work might be asked if the topic was useful to them.</span></span> <span data-ttu-id="9e0ef-170">ИИ рассматривает эти ответы и использует их для определения того, что отображается в сводных и подробных разделах.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-170">AI looks at these responses and use them to help determine what's shown on topic summaries and in topic details.</span></span>

<span data-ttu-id="9e0ef-171">Пользователи с разрешениями на редактирование или создание тем могут обновлять страницы тем напрямую, если они хотят внести исправления или добавить дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-171">Users with edit or create topics permissions can make updates to topic pages directly if they want to make corrections or add additional information.</span></span> 

<span data-ttu-id="9e0ef-172">Кроме того, пользователи с соответствующими разрешениями могут отмечать элементы, например беседы Yammer, релевантные для темы, и добавлять их к определенному разделу.</span><span class="sxs-lookup"><span data-stu-id="9e0ef-172">Additionally, users with proper permissions can tag items such as Yammer conversation that are relevant to a topic, and add them to a specific topic.</span></span> 


## <a name="see-also"></a><span data-ttu-id="9e0ef-173">См. также</span><span class="sxs-lookup"><span data-stu-id="9e0ef-173">See also</span></span>

