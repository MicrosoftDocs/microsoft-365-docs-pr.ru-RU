---
title: Группирует взаимодействия служб
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Группирует взаимодействия служб
ms.openlocfilehash: 6d5681b11cdbd837f784b6c8364cce23f964b167
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613230"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="4b61d-103">Группирует взаимодействия служб</span><span class="sxs-lookup"><span data-stu-id="4b61d-103">Groups services interactions</span></span>

<span data-ttu-id="4b61d-104">Группы Microsoft 365 предоставляют общую структуру для ряда служб и рабочих нагрузок на платформе Microsoft 365, чтобы обеспечить подключение для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b61d-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="4b61d-105">В основном существует группа Microsoft 365, которая предоставляет следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="4b61d-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="4b61d-106">Способ управления членством (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="4b61d-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="4b61d-107">Место для обмена сообщениями и беседами (почтовый ящик Exchange, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="4b61d-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="4b61d-108">Место для хранения файлов (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="4b61d-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="4b61d-109">Календарь для планирования (Exchange)</span><span class="sxs-lookup"><span data-stu-id="4b61d-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="4b61d-110">Записная книжка для записи заметок (OneNote)</span><span class="sxs-lookup"><span data-stu-id="4b61d-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="4b61d-111">В момент создания группы также подготавливается ряд других ресурсов, но они не видны, пока не будут доступны в первый раз из службы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="4b61d-112">Доска для управления задачами групп (планировщик)</span><span class="sxs-lookup"><span data-stu-id="4b61d-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="4b61d-113">Рабочая область для отчетов (Power BI)</span><span class="sxs-lookup"><span data-stu-id="4b61d-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="4b61d-114">Область для общих видеороликов (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="4b61d-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="4b61d-115">Область для общих форм (форм)</span><span class="sxs-lookup"><span data-stu-id="4b61d-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="4b61d-116">В Microsoft 365 другие службы могут взаимодействовать с группами Microsoft 365, чтобы обеспечить дополнительные функции и возможности для групп.</span><span class="sxs-lookup"><span data-stu-id="4b61d-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="4b61d-117">В число таких примеров входят:</span><span class="sxs-lookup"><span data-stu-id="4b61d-117">Examples of this include:</span></span>

- <span data-ttu-id="4b61d-118">Приложения для опытных приложений</span><span class="sxs-lookup"><span data-stu-id="4b61d-118">Power Apps for apps</span></span>
- <span data-ttu-id="4b61d-119">Автоматизация управления для рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="4b61d-119">Power Automate for workflows</span></span>
- <span data-ttu-id="4b61d-120">Проект в Интернете и схема управления каскадным управлением проектами</span><span class="sxs-lookup"><span data-stu-id="4b61d-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="4b61d-121">Teams для бесед на основе каналов</span><span class="sxs-lookup"><span data-stu-id="4b61d-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="4b61d-122">Yammer — сообщества, представляющие интерес</span><span class="sxs-lookup"><span data-stu-id="4b61d-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="4b61d-123">Взаимодействие с пользователями с помощью групп</span><span class="sxs-lookup"><span data-stu-id="4b61d-123">User interactions with groups</span></span>

<span data-ttu-id="4b61d-124">Группы Microsoft 365 могут создаваться и управляться с помощью различных интерфейсов, как администраторов, так и конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b61d-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="4b61d-125">Административные возможности</span><span class="sxs-lookup"><span data-stu-id="4b61d-125">Administrative experiences</span></span>

<span data-ttu-id="4b61d-126">Администраторы могут создавать группы Microsoft 365 и управлять ими из нескольких центров администрирования рабочей нагрузки, интерфейсов командной строки, поддерживающих сценарии, а также пользовательских приложений, взаимодействующих с API Graph.</span><span class="sxs-lookup"><span data-stu-id="4b61d-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="4b61d-127">Единственным исключением являются группы Yammer, которые необходимо создать в веб-интерфейсе Yammer.</span><span class="sxs-lookup"><span data-stu-id="4b61d-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="4b61d-128">**Связанные параметры**</span><span class="sxs-lookup"><span data-stu-id="4b61d-128">**Related settings**</span></span>

<span data-ttu-id="4b61d-129">В различных административных интерфейсах, которые могут управлять параметрами групп, существует несколько перекрытий, о которых следует знать.</span><span class="sxs-lookup"><span data-stu-id="4b61d-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="4b61d-130">**Центр администрирования Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="4b61d-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="4b61d-131">В центре администрирования Microsoft 365 гостевой доступ к группам включен по умолчанию, как и в случае предоставления владельцам возможности добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="4b61d-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="4b61d-132">Для групп из этого центра администрирования не предусмотрены другие элементы управления уровня Организации.</span><span class="sxs-lookup"><span data-stu-id="4b61d-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="4b61d-133">**Центр администрирования Azure AD**</span><span class="sxs-lookup"><span data-stu-id="4b61d-133">**Azure AD admin center**</span></span>

<span data-ttu-id="4b61d-134">Центр администрирования Azure AD позволяет управлять тем, могут ли пользователи создавать группы или назначать владельцев в порталах Azure, а также параметры истечения срока действия и политики именования.</span><span class="sxs-lookup"><span data-stu-id="4b61d-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="4b61d-135">В центре администрирования также представлен ряд мер по управлению гостевыми приглашениями, которые выходят за рамки центра администрирования Microsoft 365, например возможность ограничения того, могут ли владельцы, не являющиеся владельцами, приглашать гостей.</span><span class="sxs-lookup"><span data-stu-id="4b61d-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="4b61d-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="4b61d-136">**SharePoint**</span></span>

<span data-ttu-id="4b61d-137">Сайты SharePoint создаются с помощью групп безопасности "владелец", "участник" и "Посетители", первые два из которых соответствуют их аналогам группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="4b61d-138">Несмотря на то, что членство в сайтах SharePoint Online обычно управляется связанной группой Microsoft 365, это не двунаправленное отношение.</span><span class="sxs-lookup"><span data-stu-id="4b61d-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="4b61d-139">Любые изменения, внесенные в членство на уровне группы Microsoft 365, отражаются в SharePoint, но при изменении членства в группе SharePoint это не отражается в группе Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="4b61d-140">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="4b61d-140">User experiences</span></span>

<span data-ttu-id="4b61d-141">Конечные пользователи могут создавать группы из нескольких служб в Microsoft 365, и в других случаях они могут предоставлять доступ только группе.</span><span class="sxs-lookup"><span data-stu-id="4b61d-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="4b61d-142">В следующих службах разрешается создание групп с помощью конечных пользователей:</span><span class="sxs-lookup"><span data-stu-id="4b61d-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="4b61d-143">Проект планировщика Outlook для потока веб-SharePoint в Yammer Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b61d-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="4b61d-144">**Ограничение создания групп**</span><span class="sxs-lookup"><span data-stu-id="4b61d-144">**Restriction of group creation**</span></span>

<span data-ttu-id="4b61d-145">Распространенный подход к управлению перемножеством Teams заключается в ограничении того, какие пользователи могут их создавать.</span><span class="sxs-lookup"><span data-stu-id="4b61d-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="4b61d-146">Это можно сделать только путем ограничения создания групп.</span><span class="sxs-lookup"><span data-stu-id="4b61d-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="4b61d-147">Это влияет на возможность создания групп из других служб, где это может потребоваться для конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b61d-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="4b61d-148">Группы Microsoft 365 не поддерживают возможность ограничения создания групп из некоторых приложений или служб, но разрешать их от других приложений.</span><span class="sxs-lookup"><span data-stu-id="4b61d-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="4b61d-149">Возможности ограничения создания групп могут различаться в зависимости от приложений и служб:</span><span class="sxs-lookup"><span data-stu-id="4b61d-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="4b61d-150">Приложение или служба</span><span class="sxs-lookup"><span data-stu-id="4b61d-150">App or service</span></span>|<span data-ttu-id="4b61d-151">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="4b61d-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="4b61d-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="4b61d-152">Outlook</span></span>|<span data-ttu-id="4b61d-153">Параметр " **создать группу** " удален из меню "создание" на странице "Пользователи"</span><span class="sxs-lookup"><span data-stu-id="4b61d-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="4b61d-154">Планировщик</span><span class="sxs-lookup"><span data-stu-id="4b61d-154">Planner</span></span>|<span data-ttu-id="4b61d-155">**Новый план** объясняет, что создание групп отключено и предлагает добавить план в существующую группу.</span><span class="sxs-lookup"><span data-stu-id="4b61d-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="4b61d-156">Проект для веб-сайта и плана</span><span class="sxs-lookup"><span data-stu-id="4b61d-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="4b61d-157">Меню " **создать группу** " объясняет, что создание группы ограничено и предлагает использовать существующую группу.</span><span class="sxs-lookup"><span data-stu-id="4b61d-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="4b61d-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4b61d-158">SharePoint</span></span>|<span data-ttu-id="4b61d-159">Все еще можно создать сайт группы, не подключенный к группе.</span><span class="sxs-lookup"><span data-stu-id="4b61d-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="4b61d-160">Stream</span><span class="sxs-lookup"><span data-stu-id="4b61d-160">Stream</span></span>|<span data-ttu-id="4b61d-161">Параметр **группы** не отображается в меню " **создать**".</span><span class="sxs-lookup"><span data-stu-id="4b61d-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="4b61d-162">Teams</span><span class="sxs-lookup"><span data-stu-id="4b61d-162">Teams</span></span>|<span data-ttu-id="4b61d-163">Пользователь не может создать команду с новой группой, но по-прежнему сможет создать команду, использующую существующую группу.</span><span class="sxs-lookup"><span data-stu-id="4b61d-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="4b61d-164">Кнопка " **создать** группу" заменяется на **команду Создать группу**.</span><span class="sxs-lookup"><span data-stu-id="4b61d-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="4b61d-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="4b61d-165">Yammer</span></span>|<span data-ttu-id="4b61d-166">Параметр " **создать группу** " удаляется из главной группы или структуры навигации.</span><span class="sxs-lookup"><span data-stu-id="4b61d-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="4b61d-167">Взаимодействие служб с группами</span><span class="sxs-lookup"><span data-stu-id="4b61d-167">Services interactions with groups</span></span>

<span data-ttu-id="4b61d-168">Сведения о различных типах групп, способах их создания и управления ими, а также рекомендации по управлению, можно найти в разделе группы в афише Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="4b61d-169">[![Эскиз инфографики групп](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="4b61d-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="4b61d-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="4b61d-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="4b61d-171">В следующей таблице представлен обзор групп Microsoft 365, взаимодействий с различными службами.</span><span class="sxs-lookup"><span data-stu-id="4b61d-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="4b61d-172">Продукт</span><span class="sxs-lookup"><span data-stu-id="4b61d-172">Product</span></span>|<span data-ttu-id="4b61d-173">Возможности</span><span class="sxs-lookup"><span data-stu-id="4b61d-173">Features</span></span>|<span data-ttu-id="4b61d-174">Служба</span><span class="sxs-lookup"><span data-stu-id="4b61d-174">Does the service</span></span><br><span data-ttu-id="4b61d-175">Существует без группы?</span><span class="sxs-lookup"><span data-stu-id="4b61d-175">exist without a group?</span></span>|<span data-ttu-id="4b61d-176">Может служба</span><span class="sxs-lookup"><span data-stu-id="4b61d-176">Can the service</span></span><br><span data-ttu-id="4b61d-177">создать группу?</span><span class="sxs-lookup"><span data-stu-id="4b61d-177">create a group?</span></span>|<span data-ttu-id="4b61d-178">После удаления</span><span class="sxs-lookup"><span data-stu-id="4b61d-178">Does deleting the</span></span><br><span data-ttu-id="4b61d-179">экземпляр удалить группу?</span><span class="sxs-lookup"><span data-stu-id="4b61d-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="4b61d-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="4b61d-180">Azure AD</span></span>|<span data-ttu-id="4b61d-181">Членство, элементы управления группы, гости</span><span class="sxs-lookup"><span data-stu-id="4b61d-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="4b61d-182">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-182">Yes</span></span>|<span data-ttu-id="4b61d-183">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-183">Yes</span></span>|<span data-ttu-id="4b61d-184">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-184">Yes</span></span>|
|<span data-ttu-id="4b61d-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="4b61d-185">Exchange</span></span>|<span data-ttu-id="4b61d-186">Календарь, почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="4b61d-186">Calendar, mailbox</span></span>|<span data-ttu-id="4b61d-187">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-187">Yes</span></span>|<span data-ttu-id="4b61d-188">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-188">Yes</span></span>|<span data-ttu-id="4b61d-189">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-189">Yes</span></span>|
|<span data-ttu-id="4b61d-190">Forms</span><span class="sxs-lookup"><span data-stu-id="4b61d-190">Forms</span></span>|<span data-ttu-id="4b61d-191">Form</span><span class="sxs-lookup"><span data-stu-id="4b61d-191">Form</span></span>|<span data-ttu-id="4b61d-192">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-192">Yes</span></span>|<span data-ttu-id="4b61d-193">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-193">No</span></span>|<span data-ttu-id="4b61d-194">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-194">No</span></span>|
|<span data-ttu-id="4b61d-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="4b61d-195">OneNote</span></span>|<span data-ttu-id="4b61d-196">Notebook</span><span class="sxs-lookup"><span data-stu-id="4b61d-196">Notebook</span></span>|<span data-ttu-id="4b61d-197">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-197">Yes</span></span>|<span data-ttu-id="4b61d-198">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-198">No</span></span>|<span data-ttu-id="4b61d-199">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-199">No</span></span>|
|<span data-ttu-id="4b61d-200">Планировщик</span><span class="sxs-lookup"><span data-stu-id="4b61d-200">Planner</span></span>|<span data-ttu-id="4b61d-201">Доска задач</span><span class="sxs-lookup"><span data-stu-id="4b61d-201">Task board</span></span>|<span data-ttu-id="4b61d-202">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-202">No</span></span>|<span data-ttu-id="4b61d-203">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-203">Yes</span></span>|<span data-ttu-id="4b61d-204">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-204">Yes</span></span>|
|<span data-ttu-id="4b61d-205">Приложение Power Apps</span><span class="sxs-lookup"><span data-stu-id="4b61d-205">Power Apps app</span></span>|<span data-ttu-id="4b61d-206">Приложение</span><span class="sxs-lookup"><span data-stu-id="4b61d-206">App</span></span>|<span data-ttu-id="4b61d-207">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-207">Yes</span></span>|<span data-ttu-id="4b61d-208">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-208">No</span></span>|<span data-ttu-id="4b61d-209">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-209">No</span></span>|
|<span data-ttu-id="4b61d-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="4b61d-210">Power Automate</span></span>|<span data-ttu-id="4b61d-211">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="4b61d-211">Workflow</span></span>|<span data-ttu-id="4b61d-212">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-212">Yes</span></span>|<span data-ttu-id="4b61d-213">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-213">No</span></span>|<span data-ttu-id="4b61d-214">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-214">No</span></span>|
|<span data-ttu-id="4b61d-215">Power BI (классическая)</span><span class="sxs-lookup"><span data-stu-id="4b61d-215">Power BI (classic)</span></span>|<span data-ttu-id="4b61d-216">Рабочая группа</span><span class="sxs-lookup"><span data-stu-id="4b61d-216">Workspace</span></span>|<span data-ttu-id="4b61d-217">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-217">No</span></span>|<span data-ttu-id="4b61d-218">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-218">Yes</span></span>|<span data-ttu-id="4b61d-219">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-219">Yes</span></span>|
|<span data-ttu-id="4b61d-220">Power BI (Новая)</span><span class="sxs-lookup"><span data-stu-id="4b61d-220">Power BI (new)</span></span>|<span data-ttu-id="4b61d-221">Рабочая группа</span><span class="sxs-lookup"><span data-stu-id="4b61d-221">Workspace</span></span>|<span data-ttu-id="4b61d-222">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-222">Yes</span></span>|<span data-ttu-id="4b61d-223">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-223">No</span></span>|<span data-ttu-id="4b61d-224">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-224">Yes</span></span>|
|<span data-ttu-id="4b61d-225">Project в Интернете</span><span class="sxs-lookup"><span data-stu-id="4b61d-225">Project for the web</span></span>|<span data-ttu-id="4b61d-226">План проекта</span><span class="sxs-lookup"><span data-stu-id="4b61d-226">Project plan</span></span>|<span data-ttu-id="4b61d-227">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-227">Yes</span></span>|<span data-ttu-id="4b61d-228">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-228">Yes</span></span>|<span data-ttu-id="4b61d-229">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-229">No</span></span>|
|<span data-ttu-id="4b61d-230">Стратегия</span><span class="sxs-lookup"><span data-stu-id="4b61d-230">Roadmap</span></span>|<span data-ttu-id="4b61d-231">Стратегия</span><span class="sxs-lookup"><span data-stu-id="4b61d-231">Roadmap</span></span>|<span data-ttu-id="4b61d-232">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-232">Yes</span></span>|<span data-ttu-id="4b61d-233">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-233">Yes</span></span>|<span data-ttu-id="4b61d-234">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-234">No</span></span>|
|<span data-ttu-id="4b61d-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4b61d-235">SharePoint</span></span>|<span data-ttu-id="4b61d-236">Site</span><span class="sxs-lookup"><span data-stu-id="4b61d-236">Site</span></span>|<span data-ttu-id="4b61d-237">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-237">Yes</span></span>|<span data-ttu-id="4b61d-238">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-238">Yes</span></span>|<span data-ttu-id="4b61d-239">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-239">Yes</span></span>|
|<span data-ttu-id="4b61d-240">Stream</span><span class="sxs-lookup"><span data-stu-id="4b61d-240">Stream</span></span>|<span data-ttu-id="4b61d-241">Канал, видео</span><span class="sxs-lookup"><span data-stu-id="4b61d-241">Channel, video</span></span>|<span data-ttu-id="4b61d-242">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-242">Yes</span></span>|<span data-ttu-id="4b61d-243">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-243">Yes</span></span>|<span data-ttu-id="4b61d-244">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-244">Yes</span></span>|
|<span data-ttu-id="4b61d-245">Teams</span><span class="sxs-lookup"><span data-stu-id="4b61d-245">Teams</span></span>|<span data-ttu-id="4b61d-246">Команда</span><span class="sxs-lookup"><span data-stu-id="4b61d-246">Team</span></span>|<span data-ttu-id="4b61d-247">Нет</span><span class="sxs-lookup"><span data-stu-id="4b61d-247">No</span></span>|<span data-ttu-id="4b61d-248">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-248">Yes</span></span>|<span data-ttu-id="4b61d-249">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-249">Yes</span></span>|
|<span data-ttu-id="4b61d-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="4b61d-250">Yammer</span></span>|<span data-ttu-id="4b61d-251">Group</span><span class="sxs-lookup"><span data-stu-id="4b61d-251">Group</span></span>|<span data-ttu-id="4b61d-252">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-252">Yes</span></span>|<span data-ttu-id="4b61d-253">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-253">Yes</span></span>|<span data-ttu-id="4b61d-254">Да</span><span class="sxs-lookup"><span data-stu-id="4b61d-254">Yes</span></span>|

<span data-ttu-id="4b61d-255">В приведенной выше таблице представлен высокоуровневый обзор групповых взаимодействий со службами Microsoft 365, и вы должны знать о некоторых нюансах и тонкостях.</span><span class="sxs-lookup"><span data-stu-id="4b61d-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="4b61d-256">В следующих разделах подробно рассматривается работа с определенными рабочими нагрузками и их взаимодействия с группами.</span><span class="sxs-lookup"><span data-stu-id="4b61d-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="4b61d-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="4b61d-257">Azure AD</span></span>

<span data-ttu-id="4b61d-258">Azure AD предоставляет базовые возможности управления удостоверениями в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="4b61d-259">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="4b61d-260">Участие в группе</span><span class="sxs-lookup"><span data-stu-id="4b61d-260">Group membership</span></span>
- <span data-ttu-id="4b61d-261">Политика именования</span><span class="sxs-lookup"><span data-stu-id="4b61d-261">Naming policy</span></span>
- <span data-ttu-id="4b61d-262">Политика прекращения действия</span><span class="sxs-lookup"><span data-stu-id="4b61d-262">Expiration policy</span></span>
- <span data-ttu-id="4b61d-263">Guests</span><span class="sxs-lookup"><span data-stu-id="4b61d-263">Guests</span></span>
- <span data-ttu-id="4b61d-264">Ограничение создания групп</span><span class="sxs-lookup"><span data-stu-id="4b61d-264">Restriction of Group creation</span></span>

<span data-ttu-id="4b61d-265">**Можно создать группу в Azure AD.**</span><span class="sxs-lookup"><span data-stu-id="4b61d-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="4b61d-266">Да, группы Microsoft 365 можно создавать из Azure AD с помощью веб-портала администрирования PowerShell или API Graph.</span><span class="sxs-lookup"><span data-stu-id="4b61d-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="4b61d-267">**Существует ли Azure AD без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="4b61d-268">Да, Azure AD выполняет очень много служб, не имеющих отношения к группам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="4b61d-269">Каждая группа Microsoft 365 представлена в виде объекта в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4b61d-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="4b61d-270">**Может ли быть несколько экземпляров Azure AD для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="4b61d-271">Нет, существует только один экземпляр Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4b61d-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="4b61d-272">**Можно ли связать Azure AD с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="4b61d-273">Да, так как Azure AD — это базовая платформа, предоставляющая службу членства в группах.</span><span class="sxs-lookup"><span data-stu-id="4b61d-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="4b61d-274">**Можно связать Azure AD с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="4b61d-275">Нет, Azure AD — это базовая платформа, в которой существуют группы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="4b61d-276">**Удаляет ли экземпляр эту группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="4b61d-277">Удаление группы в Azure AD приведет к удалению соответствующих служб и контента, связанных с группой.</span><span class="sxs-lookup"><span data-stu-id="4b61d-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="4b61d-278">Teams</span><span class="sxs-lookup"><span data-stu-id="4b61d-278">Teams</span></span>

<span data-ttu-id="4b61d-279">Teams — это Рабочая область для общения в чате, предназначенная для улучшения совместной работы путем предоставления единственного интерфейса для взаимодействия со множеством служб Майкрософт и сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="4b61d-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="4b61d-280">По умолчанию при создании команды почтовый ящик и календарь, связанный с группой Microsoft 365, скрыты как в глобальном списке адресов в Exchange, так и в Outlook.</span><span class="sxs-lookup"><span data-stu-id="4b61d-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="4b61d-281">Это может быть вручную переопределено администратором, если пользователь хочет использовать как Outlook, так и Microsoft Teams в одной и той же группе Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="4b61d-282">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="4b61d-283">Беседы</span><span class="sxs-lookup"><span data-stu-id="4b61d-283">Conversations</span></span>
- <span data-ttu-id="4b61d-284">Вкладки каналов &</span><span class="sxs-lookup"><span data-stu-id="4b61d-284">Channels & tabs</span></span>
- <span data-ttu-id="4b61d-285">Собрания</span><span class="sxs-lookup"><span data-stu-id="4b61d-285">Meetings</span></span>

<span data-ttu-id="4b61d-286">**Можно создать группу с помощью Teams?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="4b61d-287">Да, при создании новой команды будет создана новая группа Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="4b61d-288">Кроме того, можно создать команду для существующей группы, которая в настоящее время не существует.</span><span class="sxs-lookup"><span data-stu-id="4b61d-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="4b61d-289">**Существуют Teams без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="4b61d-290">Нет, команда не может существовать без группы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="4b61d-291">**Может ли быть несколько команд для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="4b61d-292">Нет, отношение между группой и группой равно 1:1.</span><span class="sxs-lookup"><span data-stu-id="4b61d-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="4b61d-293">**Может ли группа быть связана с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-294">Нет, сама команда может быть связана только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="4b61d-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="4b61d-295">**Может связь группы с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="4b61d-296">Нет, команда может быть связана только с группой, с которой она была изначально связана.</span><span class="sxs-lookup"><span data-stu-id="4b61d-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="4b61d-297">**Удаляет ли группа удаление группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="4b61d-298">Да, при удалении команды в Microsoft Teams будет удалена группа, связанные с группой службы и контент.</span><span class="sxs-lookup"><span data-stu-id="4b61d-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="4b61d-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="4b61d-299">Exchange</span></span>

<span data-ttu-id="4b61d-300">Exchange Online предоставляет функции обмена сообщениями, календаря, контактов и связанных с ними функций.</span><span class="sxs-lookup"><span data-stu-id="4b61d-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="4b61d-301">В контексте группы связывается только один ресурс — а не весь экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="4b61d-302">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="4b61d-303">Почтовый ящик и календарь</span><span class="sxs-lookup"><span data-stu-id="4b61d-303">Mailbox and calendar</span></span>
- <span data-ttu-id="4b61d-304">Возможность отправлять по электронной почте всех участников группы</span><span class="sxs-lookup"><span data-stu-id="4b61d-304">Ability to email all Group members</span></span>
- <span data-ttu-id="4b61d-305">Хранение бесед по каналам Teams для целей обнаружения электронных данных, комментариев в планировщике</span><span class="sxs-lookup"><span data-stu-id="4b61d-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="4b61d-306">**Может Exchange создать группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="4b61d-307">Да, можно создать группу из центра администрирования Exchange Online, а также из Outlook.</span><span class="sxs-lookup"><span data-stu-id="4b61d-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="4b61d-308">Вы также можете преобразовать списки рассылки Exchange в группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="4b61d-309">**Существует ли Exchange без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="4b61d-310">Да, Exchange Online предоставляет ряд служб, в том числе общие почтовые ящики и календари, без сопоставления групп.</span><span class="sxs-lookup"><span data-stu-id="4b61d-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="4b61d-311">**Можно ли использовать несколько экземпляров почтовых ящиков или календарей Exchange для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="4b61d-312">Нет, для группы может быть только один почтовый ящик Exchange Online и календарь.</span><span class="sxs-lookup"><span data-stu-id="4b61d-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="4b61d-313">**Могут ли почтовые ящики и календари Exchange быть связаны с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-314">Нет, почтовый ящик и календарь имеют связь 1:1 с группой.</span><span class="sxs-lookup"><span data-stu-id="4b61d-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="4b61d-315">Можно предоставить общий доступ к почтовому ящику другим пользователям или группам, но при этом не будет задана любая форма сопоставления служб.</span><span class="sxs-lookup"><span data-stu-id="4b61d-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="4b61d-316">**Можно ли изменить связь почтового ящика Exchange или календаря с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="4b61d-317">Нет, почтовый ящик и календарь нельзя изменить на другую группу.</span><span class="sxs-lookup"><span data-stu-id="4b61d-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="4b61d-318">Однако содержимое можно переместить из одного почтового ящика в другой в Outlook или с помощью стороннего средства.</span><span class="sxs-lookup"><span data-stu-id="4b61d-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="4b61d-319">**Удаляет ли почтовый ящик удаление группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="4b61d-320">Да, при удалении почтового ящика в Exchange будет удалена группа, а также связанные с группой службы и контент.</span><span class="sxs-lookup"><span data-stu-id="4b61d-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="4b61d-321">Forms</span><span class="sxs-lookup"><span data-stu-id="4b61d-321">Forms</span></span>

<span data-ttu-id="4b61d-322">С помощью форм вы найдете веб-опросы и контрольные опросы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="4b61d-323">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="4b61d-324">Владение формами</span><span class="sxs-lookup"><span data-stu-id="4b61d-324">Ownership of forms</span></span>

<span data-ttu-id="4b61d-325">**Могут создаваться формы группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="4b61d-326">Нет, формы не могут создавать группы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="4b61d-327">**Существуют формы без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="4b61d-328">Да, опросы и тесты можно создавать непосредственно в учетной записи конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b61d-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="4b61d-329">**Допускается ли несколько форм для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="4b61d-330">Да, может быть несколько форм, связанных с группой.</span><span class="sxs-lookup"><span data-stu-id="4b61d-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="4b61d-331">**Могут ли формы быть связаны с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-332">Нет, форма может быть связана только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="4b61d-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="4b61d-333">**Можно выполнить связь формы с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="4b61d-334">Нет, после того как форма связана с группой (созданной непосредственно в пределах или владельцем, передаваемой из отдельного пользователя), ее невозможно переместить в другую группу.</span><span class="sxs-lookup"><span data-stu-id="4b61d-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="4b61d-335">**Удаляется ли форма удалить группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="4b61d-336">Нет, невозможно удалить группу из интерфейса форм, а только отдельные формы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="4b61d-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="4b61d-337">OneNote</span></span>

<span data-ttu-id="4b61d-338">OneNote — это приложение для цифровых записных книжек.</span><span class="sxs-lookup"><span data-stu-id="4b61d-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="4b61d-339">Записная книжка OneNote, созданная с группой, это файл на связанном сайте SharePoint, а не в службе, подключенной к группе.</span><span class="sxs-lookup"><span data-stu-id="4b61d-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="4b61d-340">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="4b61d-341">Общая записная книжка (хранится в связанной с группой SharePoint библиотеке SharePoint)</span><span class="sxs-lookup"><span data-stu-id="4b61d-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="4b61d-342">**Можно создать группу в OneNote?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="4b61d-343">Нет, приложение OneNote не может создать группу.</span><span class="sxs-lookup"><span data-stu-id="4b61d-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="4b61d-344">**Существуют записные книжки OneNote без группы.**</span><span class="sxs-lookup"><span data-stu-id="4b61d-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="4b61d-345">Да, записные книжки можно создавать непосредственно в OneDrive или в других общих папках.</span><span class="sxs-lookup"><span data-stu-id="4b61d-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="4b61d-346">**Есть ли несколько записных книжек OneNote для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="4b61d-347">Да, записная книжка создается по умолчанию, и другие пользователи могут добавляться, однако все ссылки на OneNote из служб, связанных с группами, всегда заключаются в записную книжку по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b61d-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="4b61d-348">**Можно ли связать записную книжку OneNote с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-349">Нет, записная книжка хранится в библиотеке сайтов SharePoint, связанной с группами, и связана с различными интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="4b61d-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="4b61d-350">Тем не менее, они могут быть предоставлены другим группам тем же способом, что и пользователи.</span><span class="sxs-lookup"><span data-stu-id="4b61d-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="4b61d-351">**Может измениться связь записной книжки с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="4b61d-352">Нет, сама Записная книжка связана с группой и доступна напрямую из других служб, подключенных к группам, однако содержимое можно переместить из одной записной книжки в другую в приложении OneNote.</span><span class="sxs-lookup"><span data-stu-id="4b61d-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="4b61d-353">**Удаляется ли Записная книжка удалить группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="4b61d-354">Нет, однако если Записная книжка OneNote удалена, в некоторых службах, связанных с группами, могут быть разорваны ссылки.</span><span class="sxs-lookup"><span data-stu-id="4b61d-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="4b61d-355">Планировщик</span><span class="sxs-lookup"><span data-stu-id="4b61d-355">Planner</span></span>

<span data-ttu-id="4b61d-356">Планировщик — это облегченная служба управления групповыми задачами.</span><span class="sxs-lookup"><span data-stu-id="4b61d-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="4b61d-357">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="4b61d-358">Доска для управления задачами групп</span><span class="sxs-lookup"><span data-stu-id="4b61d-358">Board for managing group tasks</span></span>

<span data-ttu-id="4b61d-359">**Может создать группу с помощью планировщика?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="4b61d-360">Да, при создании плана будет создана новая группа.</span><span class="sxs-lookup"><span data-stu-id="4b61d-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="4b61d-361">**Существует ли доска планировщика без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="4b61d-362">Нет, план должен быть связан с группой.</span><span class="sxs-lookup"><span data-stu-id="4b61d-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="4b61d-363">**Допускается ли несколько планов для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="4b61d-364">Да, может быть несколько планов для каждой группы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="4b61d-365">**Может ли план быть связан с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-366">Нет, план использует только сведения о членстве в группе для определения доступа.</span><span class="sxs-lookup"><span data-stu-id="4b61d-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="4b61d-367">**Можно связать план с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="4b61d-368">Нет, но при копировании плана создается новая группа.</span><span class="sxs-lookup"><span data-stu-id="4b61d-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="4b61d-369">Группа, созданная любым другим приложением, не будет автоматически отображаться в планировщике для пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b61d-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="4b61d-370">Чтобы получить доступ к доске изначально, им потребуется открыть другой интерфейс на основе группы, например Outlook.</span><span class="sxs-lookup"><span data-stu-id="4b61d-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="4b61d-371">**Удаляет ли план удаление группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="4b61d-372">Да, при удалении плана удаляются группы и связанные с группами службы и контент.</span><span class="sxs-lookup"><span data-stu-id="4b61d-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="4b61d-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="4b61d-373">Power Apps</span></span>

<span data-ttu-id="4b61d-374">Power Apps — это холст для разработки приложений без кода.</span><span class="sxs-lookup"><span data-stu-id="4b61d-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="4b61d-375">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="4b61d-376">Доступ к приложениям можно предоставить группе для запуска и изменения</span><span class="sxs-lookup"><span data-stu-id="4b61d-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="4b61d-377">**Можно переключить приложение на группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="4b61d-378">Нет, Power Apps не удается создать группу Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="4b61d-379">**Существуют приложения для опытных приложений без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="4b61d-380">Да, приложения можно создавать в приложениях для управления питанием и хранить их в учетной записи Creators до предоставления общего доступа или публикации.</span><span class="sxs-lookup"><span data-stu-id="4b61d-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="4b61d-381">**Может ли быть несколько приложений для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="4b61d-382">Да, существует несколько приложений, которым можно предоставить доступ к группе.</span><span class="sxs-lookup"><span data-stu-id="4b61d-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="4b61d-383">**Могут ли приложения связываться с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-384">Да, к приложению можно предоставить доступ нескольким группам.</span><span class="sxs-lookup"><span data-stu-id="4b61d-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="4b61d-385">**Может быть связь приложения с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="4b61d-386">Да, так как Ассоциация между приложениями для управления питанием и группой Microsoft 365 доступна только для совместного использования — приложение по-прежнему находится у создателя.</span><span class="sxs-lookup"><span data-stu-id="4b61d-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b61d-387">Для [предоставления доступа к приложениям для групп необходимо включить систему безопасности](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="4b61d-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="4b61d-388">**Удаляет ли приложение группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="4b61d-389">Нет, приложения не подключаются к группе, кроме предоставления общего доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="4b61d-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="4b61d-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="4b61d-390">Power Automate</span></span>

<span data-ttu-id="4b61d-391">Автоматизация управления питанием (ранее известной как Microsoft Flow) предоставляет рабочие процессы и службы автоматизации.</span><span class="sxs-lookup"><span data-stu-id="4b61d-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="4b61d-392">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="4b61d-393">Рабочие процессы можно совместно использовать для запуска и изменения группы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="4b61d-394">**Можно автоматизировать создание группы**</span><span class="sxs-lookup"><span data-stu-id="4b61d-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="4b61d-395">Нет, Power Автоматизация не может создать группу Microsoft 365 в контексте, связанной с одной.</span><span class="sxs-lookup"><span data-stu-id="4b61d-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="4b61d-396">Однако можно создать процесс, выполняющий различные операции, такие как создание группы безопасности Azure AD или обновление сведений о членстве в группе Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="4b61d-397">**Существуют потоки без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="4b61d-398">Да, потоки можно создавать в автоматизированной среде и находиться в учетной записи Creators до предоставления общего доступа или публикации.</span><span class="sxs-lookup"><span data-stu-id="4b61d-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="4b61d-399">**Может ли быть несколько потоков для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="4b61d-400">Да, можно использовать несколько потоков совместно с группой.</span><span class="sxs-lookup"><span data-stu-id="4b61d-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="4b61d-401">**Может ли последовательность быть связана с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-402">Да, потоки могут совместно использоваться несколькими группами.</span><span class="sxs-lookup"><span data-stu-id="4b61d-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="4b61d-403">**Может связь с данным процессом с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="4b61d-404">Да, так как Ассоциация между автоматизированной автоматизацией и группой Microsoft 365 доступна только для совместного использования — этот процесс по-прежнему располагается у создателя.</span><span class="sxs-lookup"><span data-stu-id="4b61d-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="4b61d-405">**Удаляет ли группа удаление группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="4b61d-406">Нет, как и Power Apps, потоки не подключаются к группе, отличной от общего доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="4b61d-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="4b61d-407">Power BI (классическая)</span><span class="sxs-lookup"><span data-stu-id="4b61d-407">Power BI (classic)</span></span>

<span data-ttu-id="4b61d-408">Power BI предоставляет интерактивные панели мониторинга и отчеты, управляемые данными.</span><span class="sxs-lookup"><span data-stu-id="4b61d-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="4b61d-409">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="4b61d-410">Отчеты о данных</span><span class="sxs-lookup"><span data-stu-id="4b61d-410">Data reporting</span></span>

<span data-ttu-id="4b61d-411">**Можно Power BI создать группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="4b61d-412">Да, при создании классической рабочей области будет создана группа Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="4b61d-413">**Существует ли классическая Рабочая область Power BI без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="4b61d-414">Нет, [Классическая Рабочая область в Power BI должна быть связана с группой](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="4b61d-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="4b61d-415">**Можно ли использовать несколько рабочих областей Power BI для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="4b61d-416">Нет, отношение между классической рабочей областью и группой составляет 1:1.</span><span class="sxs-lookup"><span data-stu-id="4b61d-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="4b61d-417">**Может ли Рабочая область быть связана с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-418">С технической точки зрения, в то время как классическая Рабочая область создается вместе с группой, доступ к содержимому может осуществляться вне группы с пользователями и группами безопасности.</span><span class="sxs-lookup"><span data-stu-id="4b61d-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="4b61d-419">**Может измениться связь рабочей области с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="4b61d-420">Нет, сама классическая Рабочая область связана с группой, однако содержимое можно переместить из одной рабочей области в другую в интерфейсе Power BI или путем локального экспорта содержимого.</span><span class="sxs-lookup"><span data-stu-id="4b61d-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="4b61d-421">**Удаляется ли Рабочая область удалить группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="4b61d-422">Да, удаление рабочей области в Power BI приведет к удалению групп и служб, связанных с группами, и содержимым.</span><span class="sxs-lookup"><span data-stu-id="4b61d-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="4b61d-423">Power BI (Новая)</span><span class="sxs-lookup"><span data-stu-id="4b61d-423">Power BI (new)</span></span>

<span data-ttu-id="4b61d-424">Power BI предоставляет интерактивные панели мониторинга и отчеты, управляемые данными.</span><span class="sxs-lookup"><span data-stu-id="4b61d-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="4b61d-425">При создании рабочей области в Power BI не создается группа Microsoft 365, а создание группы по-другому означает создание новой (неклассической) рабочей области в Power BI.</span><span class="sxs-lookup"><span data-stu-id="4b61d-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="4b61d-426">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="4b61d-427">Отчеты о данных</span><span class="sxs-lookup"><span data-stu-id="4b61d-427">Data reporting</span></span>

<span data-ttu-id="4b61d-428">**Можно Power BI создать группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="4b61d-429">Нет, невозможно создать группу Microsoft 365 из нового интерфейса Power BI.</span><span class="sxs-lookup"><span data-stu-id="4b61d-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="4b61d-430">**Существует ли новая Рабочая область Power BI без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="4b61d-431">Да, отчеты и рабочие области можно создавать в Power BI, которые не связаны с группами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="4b61d-432">**Может ли использоваться несколько рабочих областей для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="4b61d-433">Да, [несколько рабочих областей, созданных Power BI, могут совместно использоваться одной группой](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span><span class="sxs-lookup"><span data-stu-id="4b61d-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="4b61d-434">**Может ли Рабочая область быть связана с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-435">Нет, Рабочая область, созданная Power BI, может быть связана только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="4b61d-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="4b61d-436">**Может измениться связь рабочей области с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="4b61d-437">Да и нет.</span><span class="sxs-lookup"><span data-stu-id="4b61d-437">Yes and no.</span></span> <span data-ttu-id="4b61d-438">Рабочая область, созданная Power BI, может быть связана только с одной группой в каждый момент времени, но может изменить связь в любое время.</span><span class="sxs-lookup"><span data-stu-id="4b61d-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="4b61d-439">Рабочая область, созданная в Power BI группой, будет навсегда связана с этой группой.</span><span class="sxs-lookup"><span data-stu-id="4b61d-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="4b61d-440">**Удаляется ли Рабочая область удалить группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="4b61d-441">Да, удаление рабочей области в Power BI приведет к удалению групп и служб, связанных с группами, и содержимым.</span><span class="sxs-lookup"><span data-stu-id="4b61d-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="4b61d-442">Project в Интернете</span><span class="sxs-lookup"><span data-stu-id="4b61d-442">Project for the web</span></span>

<span data-ttu-id="4b61d-443">Project for Web предоставляет возможность создания планов проектов, диаграмм Ганта и схем.</span><span class="sxs-lookup"><span data-stu-id="4b61d-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="4b61d-444">Основные функции, предоставляемые группам.</span><span class="sxs-lookup"><span data-stu-id="4b61d-444">Key features provided to groups.</span></span>

- <span data-ttu-id="4b61d-445">Планы проекта</span><span class="sxs-lookup"><span data-stu-id="4b61d-445">Project plans</span></span>

<span data-ttu-id="4b61d-446">**Можно выполнить Project для веб-создания группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="4b61d-447">Да, можно создать новую группу Microsoft 365 непосредственно из Project для Интернета.</span><span class="sxs-lookup"><span data-stu-id="4b61d-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="4b61d-448">**Существуют проекты без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="4b61d-449">Да, проекты могут существовать без связывания с группой Microsoft 365, однако для назначения задач требуется сопоставление групп.</span><span class="sxs-lookup"><span data-stu-id="4b61d-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="4b61d-450">**Допускается ли несколько проектов для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="4b61d-451">Да, можно подключить несколько проектов в одной группе.</span><span class="sxs-lookup"><span data-stu-id="4b61d-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="4b61d-452">**Можно ли связать Project с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-453">Нет, проект можно связать только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="4b61d-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="4b61d-454">**Может измениться связь проекта с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="4b61d-455">Нет, после того как связь с группой будет установлена, она не может измениться.</span><span class="sxs-lookup"><span data-stu-id="4b61d-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="4b61d-456">**Удаляет ли проект группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="4b61d-457">Нет, удаление проекта в Project для Интернета не приведет к удалению группы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="4b61d-458">Стратегия</span><span class="sxs-lookup"><span data-stu-id="4b61d-458">Roadmap</span></span>

<span data-ttu-id="4b61d-459">Схема позволяет создавать планы проектов в Project для веб-сайта и Project Online.</span><span class="sxs-lookup"><span data-stu-id="4b61d-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="4b61d-460">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="4b61d-461">Планы проекта</span><span class="sxs-lookup"><span data-stu-id="4b61d-461">Project roadmaps</span></span>

<span data-ttu-id="4b61d-462">**Может схема создать группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="4b61d-463">Да, вы можете создать новую группу Microsoft 365 непосредственно из плана.</span><span class="sxs-lookup"><span data-stu-id="4b61d-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="4b61d-464">**Существует ли план без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="4b61d-465">Да, планы могут существовать без связывания с группой Microsoft 365, однако для совместного использования этой схемы требуется сопоставление групп.</span><span class="sxs-lookup"><span data-stu-id="4b61d-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="4b61d-466">**Существует ли несколько планов для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="4b61d-467">Да, несколько планов можно подключить к одной группе.</span><span class="sxs-lookup"><span data-stu-id="4b61d-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="4b61d-468">**Может ли схема быть связана с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-469">Нет, схема может быть связана только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="4b61d-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="4b61d-470">**Может сопоставлена схема с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="4b61d-471">Нет, после того как связь с группой будет установлена, она не может измениться.</span><span class="sxs-lookup"><span data-stu-id="4b61d-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="4b61d-472">**Удаляется ли план с удалением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="4b61d-473">Нет, удаление схемы не приводит к удалению этой группы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="4b61d-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4b61d-474">SharePoint</span></span>

<span data-ttu-id="4b61d-475">SharePoint — это веб-платформа управления контентом, обеспечивающая помимо прочего, Услуги хранения для ряда служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="4b61d-476">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="4b61d-477">Библиотека документов</span><span class="sxs-lookup"><span data-stu-id="4b61d-477">Document library</span></span>
- <span data-ttu-id="4b61d-478">Библиотека для хранения записной книжки OneNote</span><span class="sxs-lookup"><span data-stu-id="4b61d-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="4b61d-479">Хранение файлов вики-сайта Teams</span><span class="sxs-lookup"><span data-stu-id="4b61d-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="4b61d-480">**Можно создать группу SharePoint?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="4b61d-481">Да, при создании сайта группы в SharePoint по умолчанию будет создана группа Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="4b61d-482">Кроме того, можно создать группу и (при необходимости) команду для существующего сайта.</span><span class="sxs-lookup"><span data-stu-id="4b61d-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="4b61d-483">**Существуют сайты SharePoint без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="4b61d-484">Да, SharePoint предоставляет ряд служб и сайтов, не связанных с группами, таких как информационные и центральные сайты.</span><span class="sxs-lookup"><span data-stu-id="4b61d-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="4b61d-485">**Может быть несколько сайтов для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="4b61d-486">Нет, может быть только один сайт для каждой группы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="4b61d-487">Частные каналы в Teams используют дополнительные сайты, не подключенные к группе.</span><span class="sxs-lookup"><span data-stu-id="4b61d-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="4b61d-488">**Могут ли сайты быть связаны с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-489">Технически нет, но пока сайт создан с помощью группы, доступ к контенту можно предоставлять другим группам.</span><span class="sxs-lookup"><span data-stu-id="4b61d-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="4b61d-490">**Может измениться связь сайта с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="4b61d-491">Нет, сам сайт связан с группой, но контент можно переместить с одного сайта на другой в интерфейсе SharePoint, экспортировав содержимое локально или с помощью стороннего средства.</span><span class="sxs-lookup"><span data-stu-id="4b61d-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="4b61d-492">**Удаляет ли сайт эту группу?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="4b61d-493">Да, удаление сайта в SharePoint приведет к удалению служб и контента, связанных с группами и группами.</span><span class="sxs-lookup"><span data-stu-id="4b61d-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="4b61d-494">Stream</span><span class="sxs-lookup"><span data-stu-id="4b61d-494">Stream</span></span>

<span data-ttu-id="4b61d-495">Microsoft Stream — это платформа для хранения и совместного использования видео.</span><span class="sxs-lookup"><span data-stu-id="4b61d-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="4b61d-496">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="4b61d-497">Хранилище видео</span><span class="sxs-lookup"><span data-stu-id="4b61d-497">Video storage</span></span>
- <span data-ttu-id="4b61d-498">Запись собрания Teams</span><span class="sxs-lookup"><span data-stu-id="4b61d-498">Teams meeting recording</span></span>
- <span data-ttu-id="4b61d-499">Видеоканалы</span><span class="sxs-lookup"><span data-stu-id="4b61d-499">Video channels</span></span>

<span data-ttu-id="4b61d-500">**Может Потокировать создание группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="4b61d-501">Да, можно создать новую группу Microsoft 365 непосредственно из потока.</span><span class="sxs-lookup"><span data-stu-id="4b61d-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="4b61d-502">**Существует ли потоковая передача без группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="4b61d-503">Да, видеоканалы и видеоролики могут находиться в потоке без связывания с группой.</span><span class="sxs-lookup"><span data-stu-id="4b61d-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="4b61d-504">**Можно ли использовать несколько видеороликов и каналов для каждой группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="4b61d-505">Да, в каждой группе может быть несколько видеороликов и каналов.</span><span class="sxs-lookup"><span data-stu-id="4b61d-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="4b61d-506">**Может ли видео или канал быть связаны с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="4b61d-507">Да, несмотря на то, что видео или канал создается вместе с группой, к ним можно предоставить доступ другим группам.</span><span class="sxs-lookup"><span data-stu-id="4b61d-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="4b61d-508">**Можно выполнить связь с изменением группы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="4b61d-509">Да и нет; видео в потоке принадлежат исходному загрузчику или средству записи собраний, поэтому их можно связать с любой группой, но видеоканалы можно связать только с группой, в которой они были созданы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="4b61d-510">**Удаляет ли группа видеоролики или каналы?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="4b61d-511">Нет, удаление видео или каналов не приводит к удалению группы.</span><span class="sxs-lookup"><span data-stu-id="4b61d-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="4b61d-512">Однако удаление самой группы в потоке приведет к удалению связанных с группой служб и контента, за исключением реальных видеороликов.</span><span class="sxs-lookup"><span data-stu-id="4b61d-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="4b61d-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="4b61d-513">Yammer</span></span>

<span data-ttu-id="4b61d-514">Yammer — это корпоративная социальная платформа, предназначенная для ИТ-взаимодействия в организациях и между организациями.</span><span class="sxs-lookup"><span data-stu-id="4b61d-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="4b61d-515">Создание сообщества (прежнее название "Группа") в Yammer создает почтовый ящик, но на данный момент он не используется.</span><span class="sxs-lookup"><span data-stu-id="4b61d-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="4b61d-516">Группа Microsoft 365, связанная с Yammer, не может использоваться совместно с командой в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4b61d-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="4b61d-517">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="4b61d-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="4b61d-518">Область беседы</span><span class="sxs-lookup"><span data-stu-id="4b61d-518">Conversation area</span></span>

<span data-ttu-id="4b61d-519">**Можно создать группу Microsoft 365 в Yammer?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="4b61d-520">Да, при создании новой группы в Yammer будет создана новая группа Microsoft 365, если платформы подключены и у пользователя есть возможность создать группу.</span><span class="sxs-lookup"><span data-stu-id="4b61d-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="4b61d-521">Группа Yammer с соответствующей группой Microsoft 365 не может быть создана ни в одном интерфейсе или службе, отличной от Yammer.</span><span class="sxs-lookup"><span data-stu-id="4b61d-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="4b61d-522">**Существует ли группа Yammer без группы Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="4b61d-523">Да, можно создать группу Yammer без группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="4b61d-524">Если платформа Yammer не подключена к группам Microsoft 365 или пользователи не имеют возможности создавать группу Microsoft 365, группы Yammer создаются без сопоставления групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="4b61d-525">**Может ли быть несколько групп Yammer для каждой группы Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="4b61d-526">Нет, отношение между группой Yammer и группой Microsoft 365 — 1:1.</span><span class="sxs-lookup"><span data-stu-id="4b61d-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="4b61d-527">**Можно ли связать группу Yammer с несколькими группами Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="4b61d-528">Нет, Группа Yammer может быть связана только с одной группой Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b61d-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="4b61d-529">Записи можно предоставлять в другие группы Yammer или перемещать в нее.</span><span class="sxs-lookup"><span data-stu-id="4b61d-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="4b61d-530">**Может связь группы Yammer с изменением группы Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="4b61d-531">Нет, Группа Yammer может быть связана только с группой Microsoft 365, к которой она была изначально связана.</span><span class="sxs-lookup"><span data-stu-id="4b61d-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="4b61d-532">**Удаляет ли группа Yammer удаление группы Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="4b61d-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="4b61d-533">Да, удаление группы в Yammer приведет к удалению связанных групп и связанных с группами служб и контента Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4b61d-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4b61d-534">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="4b61d-534">Related topics</span></span>

[<span data-ttu-id="4b61d-535">Планирование управления совместной работой — пошаговое руководство</span><span class="sxs-lookup"><span data-stu-id="4b61d-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="4b61d-536">Создание плана по управлению совместной работой</span><span class="sxs-lookup"><span data-stu-id="4b61d-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

