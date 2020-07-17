---
title: Совместное использование сайтов и файлов с гостевыми пользователями
f1.keywords: NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 89502322-bfbb-43d6-9207-4030f8ce26e0
ROBOTS: NOINDEX
description: 'Узнайте, как предоставлять доступ к сайтам и файлам пользователям за презнакомыми пользователями организации. '
ms.openlocfilehash: 79760f662ec68d2ac9089586fd9cbf38b0bd9897
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780053"
---
# <a name="share-sites-and-files-with-guest-users"></a><span data-ttu-id="9b505-103">Совместное использование сайтов и файлов с гостевыми пользователями</span><span class="sxs-lookup"><span data-stu-id="9b505-103">Share sites and files with guest users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9b505-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="9b505-104">The admin center is changing.</span></span> <span data-ttu-id="9b505-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="9b505-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="9b505-106">Чтобы работать совместно с пользователями за пределами вашей организации, вы можете получить доступ ко всем сайтам или отдельным файлам извне.</span><span class="sxs-lookup"><span data-stu-id="9b505-106">To collaborate with people outside your organization, you can share entire sites or specific files externally.</span></span> <span data-ttu-id="9b505-107">Если вы хотите перейти непосредственно к настройке общего доступа, выберите нужный сценарий:</span><span class="sxs-lookup"><span data-stu-id="9b505-107">If you want to get straight to setting up sharing, choose the scenario you want to enable:</span></span>

- [<span data-ttu-id="9b505-108">Совместная работа с гостями над документом</span><span class="sxs-lookup"><span data-stu-id="9b505-108">Collaborate with guests on a document</span></span>](../../solutions/collaborate-on-documents.md)
- [<span data-ttu-id="9b505-109">Совместная работа с гостями на сайте</span><span class="sxs-lookup"><span data-stu-id="9b505-109">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="9b505-110">Совместная работа с гостями в команде</span><span class="sxs-lookup"><span data-stu-id="9b505-110">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)
  
## <a name="deciding-how-to-share-your-content"></a><span data-ttu-id="9b505-111">Предоставление доступа к контенту</span><span class="sxs-lookup"><span data-stu-id="9b505-111">Deciding how to share your content</span></span>

<span data-ttu-id="9b505-112">Принимая решение о необходимости и способе предоставления внешнего доступа к вашему контенту, обдумайте следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="9b505-112">When considering if and how you want to share content externally, think about the following:</span></span>
  
- <span data-ttu-id="9b505-113">Кому вы хотите предоставить доступ к контенту на сайте и всех его дочерних сайтах, а также о том, что нужно сделать?</span><span class="sxs-lookup"><span data-stu-id="9b505-113">To whom do you want to grant access to content on the site and any subsites, and what do you want them to be able to do?</span></span>
    
- <span data-ttu-id="9b505-114">Кому из сотрудников организации вы дадите разрешение на предоставление внешнего доступа к контенту?</span><span class="sxs-lookup"><span data-stu-id="9b505-114">To whom in your organization do you want to grant permission to share content externally?</span></span> 
    
- <span data-ttu-id="9b505-115">Хотите ли вы, чтобы какое-либо содержимое было недоступно для просмотра пользователями вне вашей организации?</span><span class="sxs-lookup"><span data-stu-id="9b505-115">Is there content you want to ensure is never available to be viewed by people external to your organization?</span></span>
    
<span data-ttu-id="9b505-116">Ответив на эти вопросы, вы сможете спланировать свою стратегию общего доступа к контенту.</span><span class="sxs-lookup"><span data-stu-id="9b505-116">The answers to these questions will help you plan your strategy for content sharing.</span></span>
  
|<span data-ttu-id="9b505-117">**Действие**</span><span class="sxs-lookup"><span data-stu-id="9b505-117">**Try this:**</span></span>|<span data-ttu-id="9b505-118">**Задача**</span><span class="sxs-lookup"><span data-stu-id="9b505-118">**If you need to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9b505-119">Добавление гостя в группу</span><span class="sxs-lookup"><span data-stu-id="9b505-119">Add a guest to a group</span></span>  <br/> |<span data-ttu-id="9b505-120">Предоставьте другому пользователю доступ к информации и контенту на сайте группы.</span><span class="sxs-lookup"><span data-stu-id="9b505-120">Provide someone outside your organization with ongoing access to information and content on a team site.</span></span> <span data-ttu-id="9b505-121">Им необходима возможность выполнять действия, такие как полный пользователь сайта, а также создание, редактирование и просмотр контента.</span><span class="sxs-lookup"><span data-stu-id="9b505-121">They need the ability to perform like a full user of your site and create, edit, and view content.</span></span>  <br/> |
|<span data-ttu-id="9b505-122">Предоставление общего доступа к документу и требование наличия проверки подлинности гостей.</span><span class="sxs-lookup"><span data-stu-id="9b505-122">Share a document and require guests to authenticate.</span></span>  <br/> |<span data-ttu-id="9b505-123">Предоставьте определенным пользователям за прев Организации пользователям безопасный доступ к документу для рецензирования и совместной работы, но эти пользователи не нуждаются в доступе к другому контенту на сайте.</span><span class="sxs-lookup"><span data-stu-id="9b505-123">Provide specific people outside your organization with secure access to a document for review or collaboration, but these people do not require access to other content on the site.</span></span>  <br/> |
|<span data-ttu-id="9b505-124">Предоставление общего доступа к документу без необходимости проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9b505-124">Share a document, but don't require authentication.</span></span>  <br/> |<span data-ttu-id="9b505-125">Дать ссылку на неконфиденциальный документ внешним пользователям, чтобы они могли просмотреть его или оставить свои отзывы.</span><span class="sxs-lookup"><span data-stu-id="9b505-125">Share a link to a non-sensitive or non-confidential document with people outside your organization so that they can either view it or update it with feedback.</span></span> <span data-ttu-id="9b505-126">Этим пользователям не требуется доступ к контенту на сайте.</span><span class="sxs-lookup"><span data-stu-id="9b505-126">These people do not require access to content on the site.</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="9b505-127">При отключении внешнего общего доступа пользователи за пределами Организации, имеющей доступ к сети, больше не будут иметь доступа.</span><span class="sxs-lookup"><span data-stu-id="9b505-127">When you disable external sharing, people outside the organization who currently have access will no longer have access.</span></span> <span data-ttu-id="9b505-128">Если позднее вы включите внешний общий доступ, для этих пользователей будет восстановлен доступ.</span><span class="sxs-lookup"><span data-stu-id="9b505-128">If you later turn external sharing back on, access will be restored for these people.</span></span> <span data-ttu-id="9b505-129">Чтобы запретить пользователю доступ к общему контенту, [удалите его из группы Microsoft 365](/office365/admin/create-groups/add-or-remove-members-from-groups), удалите их разрешения с сайта или [запретите общий доступ к файлу или папке](https://support.microsoft.com/office/0a36470f-d7fe-40a0-bd74-0ac6c1e13323).</span><span class="sxs-lookup"><span data-stu-id="9b505-129">To prevent a user from accessing a shared content, [remove them from the Microsoft 365 group](/office365/admin/create-groups/add-or-remove-members-from-groups), remove their permissions from the site, or [stop sharing the file or folder with them](https://support.microsoft.com/office/0a36470f-d7fe-40a0-bd74-0ac6c1e13323).</span></span> 
  
## <a name="enable-external-sharing-at-the-organization-level"></a><span data-ttu-id="9b505-130">Включение внешнего общего доступа на уровне Организации</span><span class="sxs-lookup"><span data-stu-id="9b505-130">Enable external sharing at the organization level</span></span>

<span data-ttu-id="9b505-131">Внешний общий доступ включается по умолчанию на уровне Организации, но не на всех новых сайтах.</span><span class="sxs-lookup"><span data-stu-id="9b505-131">External sharing is turned on by default at the organization level, but not for all new sites.</span></span> <span data-ttu-id="9b505-132">Сведения см. в статье [External Sharing Overview](/sharepoint/external-sharing-overview).</span><span class="sxs-lookup"><span data-stu-id="9b505-132">For info, see [External sharing overview](/sharepoint/external-sharing-overview).</span></span> 

> [!NOTE]
>  <span data-ttu-id="9b505-133">Чтобы разрешить внешний общий доступ для любого сайта, его необходимо разрешить на уровне Организации.</span><span class="sxs-lookup"><span data-stu-id="9b505-133">To allow external sharing for any site, you need to allow it at the organization level.</span></span> 
  
1. <span data-ttu-id="9b505-134">В [центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=2024339)введите "External" в поле поиска на домашней странице, а затем выберите **сайты с внешним общим доступом**.</span><span class="sxs-lookup"><span data-stu-id="9b505-134">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), type "external" in the search box on the Home page, and choose **Sites external sharing**.</span></span>
  
2. <span data-ttu-id="9b505-135">На открывшейся странице Укажите, могут ли пользователи предоставлять доступ только к существующим гостям, новым, существующим гостям или всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="9b505-135">On the page that opens, choose whether users can share with existing guests only, new and existing guests, or anyone.</span></span> 
    
3. <span data-ttu-id="9b505-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9b505-136">Select **Save**.</span></span>
    
<span data-ttu-id="9b505-137">После включения внешнего общего доступа на уровне Организации можно настроить параметры общего доступа, чтобы отключить внешний общий доступ для определенных сайтов.</span><span class="sxs-lookup"><span data-stu-id="9b505-137">After you enable external sharing at the organization level, you can fine tune your sharing settings to disable external sharing for particular sites.</span></span> <span data-ttu-id="9b505-138">Сведения о том, [как включить или отключить внешний общий доступ для сайта](/sharepoint/change-external-sharing-site).</span><span class="sxs-lookup"><span data-stu-id="9b505-138">For info, see [Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site).</span></span>
  

  

    

