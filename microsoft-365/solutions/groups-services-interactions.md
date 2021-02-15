---
title: Взаимодействие служб групп
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
description: Взаимодействие служб групп
ms.openlocfilehash: 6d5681b11cdbd837f784b6c8364cce23f964b167
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613230"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="8ddfc-103">Взаимодействие служб групп</span><span class="sxs-lookup"><span data-stu-id="8ddfc-103">Groups services interactions</span></span>

<span data-ttu-id="8ddfc-104">Группы Microsoft 365 предоставляют общую структуру для ряда служб и рабочих нагрузок на платформе Microsoft 365, чтобы обеспечить единый опытом для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="8ddfc-105">По своей сути существует группа Microsoft 365, которая предоставляет:</span><span class="sxs-lookup"><span data-stu-id="8ddfc-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="8ddfc-106">Способ управления членством (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="8ddfc-107">Место для обмена сообщениями и бесед (почтовый ящик Exchange, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="8ddfc-108">Место хранения файлов (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="8ddfc-109">Календарь для планирования (Exchange)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="8ddfc-110">Записная книжка для записи заметок (OneNote)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="8ddfc-111">На момент создания группы также можно получить ряд других ресурсов, однако они будут видны только после первого доступа из службы:</span><span class="sxs-lookup"><span data-stu-id="8ddfc-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="8ddfc-112">Доска для управления групповыми задачами (Планировщик)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="8ddfc-113">Рабочее пространство для отчетов (Power BI)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="8ddfc-114">Область для общих видео (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="8ddfc-115">Область для общих форм (формы)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="8ddfc-116">В Microsoft 365 другие службы могут взаимодействовать с группами Microsoft 365, чтобы предоставлять участникам группы дополнительные функции и возможности.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="8ddfc-117">Примеры этого:</span><span class="sxs-lookup"><span data-stu-id="8ddfc-117">Examples of this include:</span></span>

- <span data-ttu-id="8ddfc-118">Power Apps для приложений</span><span class="sxs-lookup"><span data-stu-id="8ddfc-118">Power Apps for apps</span></span>
- <span data-ttu-id="8ddfc-119">Power Automate для рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="8ddfc-119">Power Automate for workflows</span></span>
- <span data-ttu-id="8ddfc-120">Project в Интернете и план управления проектами на основе каскадных проектов</span><span class="sxs-lookup"><span data-stu-id="8ddfc-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="8ddfc-121">Teams для бесед на основе каналов</span><span class="sxs-lookup"><span data-stu-id="8ddfc-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="8ddfc-122">Yammer для интересующие сообщества</span><span class="sxs-lookup"><span data-stu-id="8ddfc-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="8ddfc-123">Взаимодействие пользователей с группами</span><span class="sxs-lookup"><span data-stu-id="8ddfc-123">User interactions with groups</span></span>

<span data-ttu-id="8ddfc-124">Группы Microsoft 365 можно создавать и управлять с помощью различных интерфейсов, как администраторов, так и конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="8ddfc-125">Административные процедуры</span><span class="sxs-lookup"><span data-stu-id="8ddfc-125">Administrative experiences</span></span>

<span data-ttu-id="8ddfc-126">Администраторы могут создавать группы Microsoft 365 и управлять ими из нескольких центров администрирования рабочих нагрузок, интерфейсов командной строки, которые поддерживают сценарии, а также настраиваемые приложения, взаимодействующие с API Graph.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="8ddfc-127">Единственным исключением являются группы Yammer, которые должны создаваться из веб-интерфейса Yammer.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="8ddfc-128">**Связанные параметры**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-128">**Related settings**</span></span>

<span data-ttu-id="8ddfc-129">В различных административных интерфейсах, которые могут управлять групповыми настройками, существует несколько перекрытий, о которых следует помнить.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="8ddfc-130">**Центр администрирования Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="8ddfc-131">В Центре администрирования Microsoft 365 гостевой доступ к группам включен по умолчанию, как и возможность добавления гостей владельцами.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="8ddfc-132">В этом Центре администрирования нет дополнительных элементов управления на уровне организации, доступных для групп.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="8ddfc-133">**Центр администрирования Azure AD**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-133">**Azure AD admin center**</span></span>

<span data-ttu-id="8ddfc-134">В Центре администрирования Azure AD есть элементы управления, которые могут создавать группы или назначать владельцев на порталах Azure, а также параметры политики истечения срока действия и именования.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="8ddfc-135">Центр администрирования также предоставляет ряд мер по контролю приглашений гостей, которые выходят за рамки центра администрирования Microsoft 365, например возможность ограничить возможность приглашения гостей, не внося в группу владельцев.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="8ddfc-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-136">**SharePoint**</span></span>

<span data-ttu-id="8ddfc-137">Сайты SharePoint создаются с помощью групп безопасности "Владелец", "Участник" и "Посетитель", первые два из них совпадают с группами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="8ddfc-138">Хотя членством на сайтах SharePoint Online, как правило, управляет связанная группа Microsoft 365, это не является отношением между участниками.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="8ddfc-139">Любые изменения членства на уровне группы Microsoft 365 отражаются в SharePoint, но если членство в группе SharePoint изменилось, это не отражается в группе Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="8ddfc-140">Пользовательские интерфейсы</span><span class="sxs-lookup"><span data-stu-id="8ddfc-140">User experiences</span></span>

<span data-ttu-id="8ddfc-141">Конечные пользователи могут создавать группы из нескольких служб в Microsoft 365, а в других могут делиться только с группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="8ddfc-142">Следующие службы позволяют создавать группы конечными пользователями:</span><span class="sxs-lookup"><span data-stu-id="8ddfc-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="8ddfc-143">Outlook Planner Project for the web SharePoint Stream Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="8ddfc-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="8ddfc-144">**Ограничение создания группы**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-144">**Restriction of group creation**</span></span>

<span data-ttu-id="8ddfc-145">Распространенный подход к контролю спрайтов групп заключается в ограничении того, какие пользователи могут их создавать.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="8ddfc-146">Это можно сделать, ограничив создание групп.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="8ddfc-147">Это влияет на возможность создания групп из других служб, где это может потребоваться для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="8ddfc-148">Группы Microsoft 365 не поддерживают возможность ограничить создание групп из одних приложений или служб, разрешив их другим.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="8ddfc-149">Работа с ограничениями на создание групп зависит от приложений и служб:</span><span class="sxs-lookup"><span data-stu-id="8ddfc-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="8ddfc-150">Приложение или служба</span><span class="sxs-lookup"><span data-stu-id="8ddfc-150">App or service</span></span>|<span data-ttu-id="8ddfc-151">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="8ddfc-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="8ddfc-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="8ddfc-152">Outlook</span></span>|<span data-ttu-id="8ddfc-153">**Параметр "Новая** группа" удален из меню "Новый" на странице "Люди"</span><span class="sxs-lookup"><span data-stu-id="8ddfc-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="8ddfc-154">Планировщик</span><span class="sxs-lookup"><span data-stu-id="8ddfc-154">Planner</span></span>|<span data-ttu-id="8ddfc-155">**В новом** плане объясняется, что создание группы отключено, и предлагается добавить план в существующую группу</span><span class="sxs-lookup"><span data-stu-id="8ddfc-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="8ddfc-156">Проект в Интернете и план</span><span class="sxs-lookup"><span data-stu-id="8ddfc-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="8ddfc-157">**В меню создания** группы объясняется, что создание группы ограничено, и предлагается использовать существующую группу.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="8ddfc-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8ddfc-158">SharePoint</span></span>|<span data-ttu-id="8ddfc-159">По-прежнему можно создавать сайт группы, не подключенный к группе.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="8ddfc-160">Stream</span><span class="sxs-lookup"><span data-stu-id="8ddfc-160">Stream</span></span>|<span data-ttu-id="8ddfc-161">**Параметр** "Группа" не появляется в меню **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="8ddfc-162">Teams</span><span class="sxs-lookup"><span data-stu-id="8ddfc-162">Teams</span></span>|<span data-ttu-id="8ddfc-163">Пользователь не может создать команду с новой группой, но все равно может создать команду, которая использует существующую группу.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="8ddfc-164">**Кнопка "Создать команду"** заменена кнопкой **"Создать команду из группы".**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="8ddfc-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="8ddfc-165">Yammer</span></span>|<span data-ttu-id="8ddfc-166">**Создание параметра** группы удаляется из навигации основных групп или сообществ.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="8ddfc-167">Взаимодействие служб с группами</span><span class="sxs-lookup"><span data-stu-id="8ddfc-167">Services interactions with groups</span></span>

<span data-ttu-id="8ddfc-168">См. плакат "Группы в Microsoft 365" с информацией о различных типах групп, о том, как они создаются и управляются, а также с несколькими рекомендациями по управлению.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="8ddfc-169">[![Эскиз инфографики групп](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="8ddfc-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="8ddfc-171">В следующей таблице представлен обзор взаимодействия групп Microsoft 365 с различными службами:</span><span class="sxs-lookup"><span data-stu-id="8ddfc-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="8ddfc-172">Продукт</span><span class="sxs-lookup"><span data-stu-id="8ddfc-172">Product</span></span>|<span data-ttu-id="8ddfc-173">Возможности</span><span class="sxs-lookup"><span data-stu-id="8ddfc-173">Features</span></span>|<span data-ttu-id="8ddfc-174">Делает службу</span><span class="sxs-lookup"><span data-stu-id="8ddfc-174">Does the service</span></span><br><span data-ttu-id="8ddfc-175">существуют без группы?</span><span class="sxs-lookup"><span data-stu-id="8ddfc-175">exist without a group?</span></span>|<span data-ttu-id="8ddfc-176">Может ли служба</span><span class="sxs-lookup"><span data-stu-id="8ddfc-176">Can the service</span></span><br><span data-ttu-id="8ddfc-177">создать группу?</span><span class="sxs-lookup"><span data-stu-id="8ddfc-177">create a group?</span></span>|<span data-ttu-id="8ddfc-178">Удаляет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-178">Does deleting the</span></span><br><span data-ttu-id="8ddfc-179">экземпляр удаления группы?</span><span class="sxs-lookup"><span data-stu-id="8ddfc-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="8ddfc-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="8ddfc-180">Azure AD</span></span>|<span data-ttu-id="8ddfc-181">Членство, элементы управления "Группы", "Гости"</span><span class="sxs-lookup"><span data-stu-id="8ddfc-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="8ddfc-182">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-182">Yes</span></span>|<span data-ttu-id="8ddfc-183">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-183">Yes</span></span>|<span data-ttu-id="8ddfc-184">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-184">Yes</span></span>|
|<span data-ttu-id="8ddfc-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="8ddfc-185">Exchange</span></span>|<span data-ttu-id="8ddfc-186">Календарь, почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="8ddfc-186">Calendar, mailbox</span></span>|<span data-ttu-id="8ddfc-187">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-187">Yes</span></span>|<span data-ttu-id="8ddfc-188">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-188">Yes</span></span>|<span data-ttu-id="8ddfc-189">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-189">Yes</span></span>|
|<span data-ttu-id="8ddfc-190">Forms</span><span class="sxs-lookup"><span data-stu-id="8ddfc-190">Forms</span></span>|<span data-ttu-id="8ddfc-191">Form</span><span class="sxs-lookup"><span data-stu-id="8ddfc-191">Form</span></span>|<span data-ttu-id="8ddfc-192">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-192">Yes</span></span>|<span data-ttu-id="8ddfc-193">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-193">No</span></span>|<span data-ttu-id="8ddfc-194">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-194">No</span></span>|
|<span data-ttu-id="8ddfc-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="8ddfc-195">OneNote</span></span>|<span data-ttu-id="8ddfc-196">Notebook</span><span class="sxs-lookup"><span data-stu-id="8ddfc-196">Notebook</span></span>|<span data-ttu-id="8ddfc-197">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-197">Yes</span></span>|<span data-ttu-id="8ddfc-198">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-198">No</span></span>|<span data-ttu-id="8ddfc-199">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-199">No</span></span>|
|<span data-ttu-id="8ddfc-200">Планировщик</span><span class="sxs-lookup"><span data-stu-id="8ddfc-200">Planner</span></span>|<span data-ttu-id="8ddfc-201">Доска задач</span><span class="sxs-lookup"><span data-stu-id="8ddfc-201">Task board</span></span>|<span data-ttu-id="8ddfc-202">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-202">No</span></span>|<span data-ttu-id="8ddfc-203">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-203">Yes</span></span>|<span data-ttu-id="8ddfc-204">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-204">Yes</span></span>|
|<span data-ttu-id="8ddfc-205">Приложение Power Apps</span><span class="sxs-lookup"><span data-stu-id="8ddfc-205">Power Apps app</span></span>|<span data-ttu-id="8ddfc-206">Приложение</span><span class="sxs-lookup"><span data-stu-id="8ddfc-206">App</span></span>|<span data-ttu-id="8ddfc-207">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-207">Yes</span></span>|<span data-ttu-id="8ddfc-208">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-208">No</span></span>|<span data-ttu-id="8ddfc-209">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-209">No</span></span>|
|<span data-ttu-id="8ddfc-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="8ddfc-210">Power Automate</span></span>|<span data-ttu-id="8ddfc-211">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="8ddfc-211">Workflow</span></span>|<span data-ttu-id="8ddfc-212">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-212">Yes</span></span>|<span data-ttu-id="8ddfc-213">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-213">No</span></span>|<span data-ttu-id="8ddfc-214">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-214">No</span></span>|
|<span data-ttu-id="8ddfc-215">Power BI (классическая)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-215">Power BI (classic)</span></span>|<span data-ttu-id="8ddfc-216">Рабочая группа</span><span class="sxs-lookup"><span data-stu-id="8ddfc-216">Workspace</span></span>|<span data-ttu-id="8ddfc-217">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-217">No</span></span>|<span data-ttu-id="8ddfc-218">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-218">Yes</span></span>|<span data-ttu-id="8ddfc-219">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-219">Yes</span></span>|
|<span data-ttu-id="8ddfc-220">Power BI (новый)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-220">Power BI (new)</span></span>|<span data-ttu-id="8ddfc-221">Рабочая группа</span><span class="sxs-lookup"><span data-stu-id="8ddfc-221">Workspace</span></span>|<span data-ttu-id="8ddfc-222">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-222">Yes</span></span>|<span data-ttu-id="8ddfc-223">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-223">No</span></span>|<span data-ttu-id="8ddfc-224">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-224">Yes</span></span>|
|<span data-ttu-id="8ddfc-225">Project в Интернете</span><span class="sxs-lookup"><span data-stu-id="8ddfc-225">Project for the web</span></span>|<span data-ttu-id="8ddfc-226">План проекта</span><span class="sxs-lookup"><span data-stu-id="8ddfc-226">Project plan</span></span>|<span data-ttu-id="8ddfc-227">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-227">Yes</span></span>|<span data-ttu-id="8ddfc-228">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-228">Yes</span></span>|<span data-ttu-id="8ddfc-229">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-229">No</span></span>|
|<span data-ttu-id="8ddfc-230">Стратегия</span><span class="sxs-lookup"><span data-stu-id="8ddfc-230">Roadmap</span></span>|<span data-ttu-id="8ddfc-231">Стратегия</span><span class="sxs-lookup"><span data-stu-id="8ddfc-231">Roadmap</span></span>|<span data-ttu-id="8ddfc-232">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-232">Yes</span></span>|<span data-ttu-id="8ddfc-233">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-233">Yes</span></span>|<span data-ttu-id="8ddfc-234">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-234">No</span></span>|
|<span data-ttu-id="8ddfc-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8ddfc-235">SharePoint</span></span>|<span data-ttu-id="8ddfc-236">Site</span><span class="sxs-lookup"><span data-stu-id="8ddfc-236">Site</span></span>|<span data-ttu-id="8ddfc-237">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-237">Yes</span></span>|<span data-ttu-id="8ddfc-238">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-238">Yes</span></span>|<span data-ttu-id="8ddfc-239">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-239">Yes</span></span>|
|<span data-ttu-id="8ddfc-240">Stream</span><span class="sxs-lookup"><span data-stu-id="8ddfc-240">Stream</span></span>|<span data-ttu-id="8ddfc-241">Канал, видео</span><span class="sxs-lookup"><span data-stu-id="8ddfc-241">Channel, video</span></span>|<span data-ttu-id="8ddfc-242">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-242">Yes</span></span>|<span data-ttu-id="8ddfc-243">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-243">Yes</span></span>|<span data-ttu-id="8ddfc-244">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-244">Yes</span></span>|
|<span data-ttu-id="8ddfc-245">Teams</span><span class="sxs-lookup"><span data-stu-id="8ddfc-245">Teams</span></span>|<span data-ttu-id="8ddfc-246">Команда</span><span class="sxs-lookup"><span data-stu-id="8ddfc-246">Team</span></span>|<span data-ttu-id="8ddfc-247">Нет</span><span class="sxs-lookup"><span data-stu-id="8ddfc-247">No</span></span>|<span data-ttu-id="8ddfc-248">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-248">Yes</span></span>|<span data-ttu-id="8ddfc-249">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-249">Yes</span></span>|
|<span data-ttu-id="8ddfc-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="8ddfc-250">Yammer</span></span>|<span data-ttu-id="8ddfc-251">Group</span><span class="sxs-lookup"><span data-stu-id="8ddfc-251">Group</span></span>|<span data-ttu-id="8ddfc-252">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-252">Yes</span></span>|<span data-ttu-id="8ddfc-253">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-253">Yes</span></span>|<span data-ttu-id="8ddfc-254">Да</span><span class="sxs-lookup"><span data-stu-id="8ddfc-254">Yes</span></span>|

<span data-ttu-id="8ddfc-255">Хотя в таблице выше представлен общий обзор взаимодействия групп со службами Microsoft 365, необходимо понимать ряд нюансов и нюансов.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="8ddfc-256">В следующих разделах более подробно анализ конкретных рабочих нагрузок и их взаимодействия с группами.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="8ddfc-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="8ddfc-257">Azure AD</span></span>

<span data-ttu-id="8ddfc-258">Azure AD предоставляет возможности управления удостоверениями в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="8ddfc-259">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8ddfc-260">Участие в группе</span><span class="sxs-lookup"><span data-stu-id="8ddfc-260">Group membership</span></span>
- <span data-ttu-id="8ddfc-261">Политика именования</span><span class="sxs-lookup"><span data-stu-id="8ddfc-261">Naming policy</span></span>
- <span data-ttu-id="8ddfc-262">Политика прекращения действия</span><span class="sxs-lookup"><span data-stu-id="8ddfc-262">Expiration policy</span></span>
- <span data-ttu-id="8ddfc-263">Гости</span><span class="sxs-lookup"><span data-stu-id="8ddfc-263">Guests</span></span>
- <span data-ttu-id="8ddfc-264">Ограничение создания группы</span><span class="sxs-lookup"><span data-stu-id="8ddfc-264">Restriction of Group creation</span></span>

<span data-ttu-id="8ddfc-265">**Может ли Azure AD создать группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="8ddfc-266">Да, группы Microsoft 365 можно создавать из Azure AD на веб-портале администрирования, с помощью PowerShell или API Graph.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="8ddfc-267">**Существует ли Azure AD без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="8ddfc-268">Да, Azure AD выполняет большое количество служб, которые не имеют отношения к группам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="8ddfc-269">Каждая группа Microsoft 365 представлена в Azure AD как объект.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="8ddfc-270">**Может ли быть несколько экземпляров Azure AD для одной группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="8ddfc-271">Нет, существует только один экземпляр Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="8ddfc-272">**Можно ли связывать Azure AD с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="8ddfc-273">Да, так как Azure AD является платформой, которая предоставляет службу членства в группах.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="8ddfc-274">**Можно ли изменить связь Azure AD с группой?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="8ddfc-275">Нет, Azure AD — это платформа, на которой существуют группы.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="8ddfc-276">**Удаляет ли экземпляр группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="8ddfc-277">При удалении группы в Azure AD удаляются соответствующие службы и контент, связанные с группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="8ddfc-278">Teams</span><span class="sxs-lookup"><span data-stu-id="8ddfc-278">Teams</span></span>

<span data-ttu-id="8ddfc-279">Teams — это рабочее пространство на основе чата, предназначенное для улучшения совместной работы, предоставляя единый интерфейс для взаимодействия с различными службами Майкрософт и сторонних служб.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="8ddfc-280">По умолчанию при составлении команды почтовый ящик и календарь, связанные с группой Microsoft 365, скрыты как в глобальном списке адресов в Exchange, так и в Outlook.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="8ddfc-281">Это может быть переопределено администратором вручную, если пользователь хочет использовать Outlook и Teams в одной группе Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="8ddfc-282">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8ddfc-283">Беседы</span><span class="sxs-lookup"><span data-stu-id="8ddfc-283">Conversations</span></span>
- <span data-ttu-id="8ddfc-284">Каналы & вкладок</span><span class="sxs-lookup"><span data-stu-id="8ddfc-284">Channels & tabs</span></span>
- <span data-ttu-id="8ddfc-285">Собрания</span><span class="sxs-lookup"><span data-stu-id="8ddfc-285">Meetings</span></span>

<span data-ttu-id="8ddfc-286">**Можно ли создать группу в Teams?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="8ddfc-287">Да, при создании новой команды будет создаваться новая группа Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="8ddfc-288">Кроме того, можно создать команду для существующей группы, которая в настоящее время не имеет ее.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="8ddfc-289">**Существуют ли команды без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="8ddfc-290">Нет, команда не может существовать без группы.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="8ddfc-291">**Может ли быть несколько команд на группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="8ddfc-292">Нет, отношение между командой и группой — 1:1.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="8ddfc-293">**Можно ли связывать команду с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-294">Нет, сама команда может быть связана только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="8ddfc-295">**Может ли измениться связь команды с группой?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="8ddfc-296">Нет, команда может быть связана только с группой, с которой она была изначально связана.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="8ddfc-297">**Удаляет ли команда группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="8ddfc-298">Да, удаление команды в Microsoft Teams удалит группу, связанные с группой службы и содержимое.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="8ddfc-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="8ddfc-299">Exchange</span></span>

<span data-ttu-id="8ddfc-300">Exchange Online предоставляет функции обмена сообщениями, календаря, контактов и связанных с ними функций.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="8ddfc-301">В контексте группы связан только один ресурс, а не весь экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="8ddfc-302">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8ddfc-303">Почтовый ящик и календарь</span><span class="sxs-lookup"><span data-stu-id="8ddfc-303">Mailbox and calendar</span></span>
- <span data-ttu-id="8ddfc-304">Возможность отправлять сообщения всем участникам группы по электронной почте</span><span class="sxs-lookup"><span data-stu-id="8ddfc-304">Ability to email all Group members</span></span>
- <span data-ttu-id="8ddfc-305">Хранение бесед канала Teams для целей eDiscovery, комментарии Планировщика</span><span class="sxs-lookup"><span data-stu-id="8ddfc-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="8ddfc-306">**Может ли Exchange создать группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="8ddfc-307">Да, можно создать группу в Центре администрирования Exchange Online, а также в Outlook.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="8ddfc-308">Списки рассылки Exchange также можно преобразовать в группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="8ddfc-309">**Существует ли Exchange без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="8ddfc-310">Да, Exchange Online предоставляет ряд служб, включая общие почтовые ящики и календари, без связи с группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="8ddfc-311">**Может ли быть несколько экземпляров почтовых ящиков Или календарей Exchange для одной группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="8ddfc-312">Нет, для группы может быть только один почтовый ящик и календарь Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="8ddfc-313">**Можно ли связывать почтовые ящики и календари Exchange с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-314">Нет, почтовый ящик и календарь имеют отношение 1:1 с группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="8ddfc-315">Можно поделиться почтовым ящиком с другими пользователями или группами, но это не устанавливает связь службы.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="8ddfc-316">**Может ли измениться связь почтового ящика Или календаря Exchange с группой?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="8ddfc-317">Нет, почтовый ящик и календарь нельзя изменить на другую группу.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="8ddfc-318">Однако содержимое можно перемещать из одного почтового ящика в другой в Outlook или с помощью стороне средства.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="8ddfc-319">**Удаляет ли почтовый ящик группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="8ddfc-320">Да, при удалении почтового ящика в Exchange удаляется группа, а также связанные с группой службы и содержимое.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="8ddfc-321">Forms</span><span class="sxs-lookup"><span data-stu-id="8ddfc-321">Forms</span></span>

<span data-ttu-id="8ddfc-322">Формы предоставляют веб-опросы и тесты.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="8ddfc-323">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="8ddfc-324">Владение формами</span><span class="sxs-lookup"><span data-stu-id="8ddfc-324">Ownership of forms</span></span>

<span data-ttu-id="8ddfc-325">**Могут ли формы создать группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="8ddfc-326">Нет, формы не могут создать группу.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="8ddfc-327">**Существуют ли формы без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="8ddfc-328">Да, опросы и тесты можно создавать непосредственно в учетной записи конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="8ddfc-329">**Может ли быть несколько форм для группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="8ddfc-330">Да, с группой может быть связано несколько форм.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="8ddfc-331">**Можно ли связывать формы с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-332">Нет, форму можно связывать только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="8ddfc-333">**Может ли измениться связь формы с группой?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="8ddfc-334">Нет, когда форма связана с группой (либо создается непосредственно внутри, либо владельцем, переданным от физического лица), ее нельзя перенести в другую группу.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="8ddfc-335">**Удаляет ли форма группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="8ddfc-336">Нет, удалить группу из интерфейса Forms невозможно, только отдельные формы.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="8ddfc-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="8ddfc-337">OneNote</span></span>

<span data-ttu-id="8ddfc-338">OneNote — это приложение цифровой записной книжки.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="8ddfc-339">Записная книжка OneNote, созданная с помощью группы, — это файл на связанном сайте SharePoint, а не в службе, подключенной к группе.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="8ddfc-340">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="8ddfc-341">Общая записная книжка (хранится в библиотеке SharePoint, связанной с группой)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="8ddfc-342">**Может ли OneNote создать группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="8ddfc-343">Нет, приложение OneNote не может создать группу.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="8ddfc-344">**Существуют ли записные книжки OneNote без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="8ddfc-345">Да, записные книжки можно создавать непосредственно в OneDrive или в других общих расположениях.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="8ddfc-346">**Может ли быть несколько записных книги OneNote для одной группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="8ddfc-347">Да, записная книжка создается по умолчанию, и можно добавлять другие записные книжки, однако любая ссылка на OneNote из связанных с группой служб всегда будет переходить к записной книжке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="8ddfc-348">**Можно ли связывать записную книжку OneNote с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-349">Нет, записная книжка хранится в связанной с группой библиотеке сайтов SharePoint и связывается с различными интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="8ddfc-350">Однако он может быть общим для других групп таким же образом, как он может быть общим для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="8ddfc-351">**Может ли связь записной книжки с группой измениться?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="8ddfc-352">Нет, сама записная книжка связана с группой и может быть напрямую связана с другими службами, подключенными к группе, однако содержимое можно перемещать из одной записной книжки в другую в приложении OneNote.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="8ddfc-353">**Удаляет ли записная книжка группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="8ddfc-354">Нет, но если записная книжка OneNote удалена, в некоторых службах, связанных с группой, могут быть нарушены ссылки.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="8ddfc-355">Планировщик</span><span class="sxs-lookup"><span data-stu-id="8ddfc-355">Planner</span></span>

<span data-ttu-id="8ddfc-356">Планировщик — это облегченная служба управления задачами группы.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="8ddfc-357">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="8ddfc-358">Доска для управления групповыми задачами</span><span class="sxs-lookup"><span data-stu-id="8ddfc-358">Board for managing group tasks</span></span>

<span data-ttu-id="8ddfc-359">**Может ли Планировщик создать группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="8ddfc-360">Да, при создании плана будет создаваться новая группа.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="8ddfc-361">**Существует ли доска Планировщика без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="8ddfc-362">Нет, план должен быть связан с группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="8ddfc-363">**Может ли быть несколько планов на группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="8ddfc-364">Да, для группы может быть несколько планов.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="8ddfc-365">**Можно ли связывать план с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-366">Нет, для определения доступа план зависит только от членства в группе.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="8ddfc-367">**Может ли связь плана с группой измениться?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="8ddfc-368">Нет, однако при копировании плана создается новая группа.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="8ddfc-369">Группа, созданная любым другим приложением, не будет автоматически отключаться в Планировщике для пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="8ddfc-370">Чтобы получить доступ к доске изначально, им потребуется открыть его из другого группового интерфейса, например Outlook.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="8ddfc-371">**Удаляет ли план группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="8ddfc-372">Да, при удалении плана будут удалены службы и контент, связанные с группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="8ddfc-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="8ddfc-373">Power Apps</span></span>

<span data-ttu-id="8ddfc-374">Power Apps предоставляет холст для разработки приложений без кода.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="8ddfc-375">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8ddfc-376">Приложения можно совместно использовать для запуска и изменения в группе</span><span class="sxs-lookup"><span data-stu-id="8ddfc-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="8ddfc-377">**Могут ли Power Apps создать группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="8ddfc-378">Нет, Power Apps не может создать группу Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="8ddfc-379">**Существуют ли приложения Power Apps без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="8ddfc-380">Да, приложения можно создавать в Power Apps и находиться в учетной записи создателей до тех пор, пока не будет опубликован или опубликован общий доступ.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="8ddfc-381">**Может ли быть несколько приложений на группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="8ddfc-382">Да, группа может использовать несколько приложений.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="8ddfc-383">**Можно ли связывать приложения с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-384">Да, приложение может совместно работать с несколькими группами.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="8ddfc-385">**Может ли связь приложения с группой измениться?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="8ddfc-386">Да, так как связь между Power Apps и группой Microsoft 365 заключается только в совместном использовании — приложение по-прежнему находится у создателя.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ddfc-387">[Группы должны быть включены для обеспечения безопасности, прежде чем к ним можно будет получить доступ к приложениям.](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="8ddfc-388">**Удаляет ли приложение группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="8ddfc-389">Нет, приложения не подключены к группе, кроме общего с ними.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="8ddfc-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="8ddfc-390">Power Automate</span></span>

<span data-ttu-id="8ddfc-391">Power Automate (прежнее название — Microsoft Flow) предоставляет рабочий процесс и службы автоматизации.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="8ddfc-392">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="8ddfc-393">Для запуска и изменения рабочего процесса можно совместно использовать группу.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="8ddfc-394">**Может ли Power Automate создать группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="8ddfc-395">Нет, Power Automate не может создать группу Microsoft 365 в контексте ее связи.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="8ddfc-396">Однако можно создать поток, который выполняет различные операции, такие как создание группы безопасности Azure AD или обновление членства в группе Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="8ddfc-397">**Существуют ли потоки без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="8ddfc-398">Да, потоки можно создавать в Power Automate и находиться в учетной записи создателей до тех пор, пока они не будут опубликованы или опубликованы.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="8ddfc-399">**Может ли быть несколько потоков на группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="8ddfc-400">Да, группа может использовать несколько потоков.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="8ddfc-401">**Можно ли связывать поток с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-402">Да, поток может быть общим для нескольких групп.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="8ddfc-403">**Может ли измениться связь потока с группой?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="8ddfc-404">Да, так как связь между Power Automate и группой Microsoft 365 заключается только в совместном использовании — поток по-прежнему находится с создателем.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="8ddfc-405">**Удаляет ли поток группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="8ddfc-406">Нет, как и в Power Apps, потоки не подключены к группе, кроме общего с ними.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="8ddfc-407">Power BI (классическая)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-407">Power BI (classic)</span></span>

<span data-ttu-id="8ddfc-408">Power BI предоставляет интерактивные панели мониторинга и отчеты на основе данных.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="8ddfc-409">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="8ddfc-410">Отчеты о данных</span><span class="sxs-lookup"><span data-stu-id="8ddfc-410">Data reporting</span></span>

<span data-ttu-id="8ddfc-411">**Может ли Power BI создать группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="8ddfc-412">Да, при создании классической рабочей области будет создаваться группа Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="8ddfc-413">**Существует ли классическая рабочая область Power BI без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="8ddfc-414">Нет, [классическая рабочая область в Power BI должна быть связана с группой.](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="8ddfc-415">**Может ли быть несколько рабочей области Power BI для группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="8ddfc-416">Нет, отношение между классической рабочей областью и группой — 1:1.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="8ddfc-417">**Можно ли связывать рабочее пространство с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-418">Технически нет, хотя классическая рабочая область создается вместе с группой, доступ к содержимому за пределами группы может быть общим для пользователей и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="8ddfc-419">**Может ли меняться связь рабочей области с группой?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="8ddfc-420">Нет, с группой связана сама классическая рабочая область, однако содержимое можно перемещать из одной рабочей области в другую в интерфейсе Power BI или экспортировать содержимое локально.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="8ddfc-421">**Удаляет ли рабочая область группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="8ddfc-422">Да, при удалении рабочей области в Power BI удаляются службы и контент, связанные с группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="8ddfc-423">Power BI (новый)</span><span class="sxs-lookup"><span data-stu-id="8ddfc-423">Power BI (new)</span></span>

<span data-ttu-id="8ddfc-424">Power BI предоставляет интерактивные панели мониторинга и отчеты на основе данных.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="8ddfc-425">При создании новой рабочей области в Power BI группа Microsoft 365 не создается, а создание группы другими средствами создает новую (не классическую) область в Power BI.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="8ddfc-426">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="8ddfc-427">Отчеты о данных</span><span class="sxs-lookup"><span data-stu-id="8ddfc-427">Data reporting</span></span>

<span data-ttu-id="8ddfc-428">**Может ли Power BI создать группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="8ddfc-429">Нет, создать группу Microsoft 365 из нового интерфейса Power BI невозможно.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="8ddfc-430">**Существует ли новая рабочая область Power BI без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="8ddfc-431">Да, в Power BI можно создавать отчеты и рабочей области, не связанные с группами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="8ddfc-432">**Может ли быть несколько рабочей области для группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="8ddfc-433">Да, [несколькими рабочей областью, созданными с](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)помощью Power BI, можно совместно использовать одну группу.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="8ddfc-434">**Можно ли связывать рабочее пространство с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-435">Нет, рабочая область, созданная Power BI, может быть связана только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="8ddfc-436">**Может ли меняться связь рабочей области с группой?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="8ddfc-437">Да и нет.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-437">Yes and no.</span></span> <span data-ttu-id="8ddfc-438">Рабочая область, созданная Power BI, может быть связана только с одной группой одновременно, но может изменить связь в любое время.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="8ddfc-439">Рабочая область, созданная в Power BI группой, навсегда связана с этой группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="8ddfc-440">**Удаляет ли рабочая область группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="8ddfc-441">Да, при удалении рабочей области в Power BI удаляются службы и контент, связанные с группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="8ddfc-442">Project в Интернете</span><span class="sxs-lookup"><span data-stu-id="8ddfc-442">Project for the web</span></span>

<span data-ttu-id="8ddfc-443">Project для Интернета позволяет создавать планы проектов, диаграммы Гант и схемы.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="8ddfc-444">Основные функции, предоставляемые группам.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-444">Key features provided to groups.</span></span>

- <span data-ttu-id="8ddfc-445">Планы проектов</span><span class="sxs-lookup"><span data-stu-id="8ddfc-445">Project plans</span></span>

<span data-ttu-id="8ddfc-446">**Может ли Project для Интернета создать группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="8ddfc-447">Да, можно создать группу Microsoft 365 непосредственно из Project в Интернете.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="8ddfc-448">**Существуют ли проекты без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="8ddfc-449">Да, проекты могут существовать без связи с группой Microsoft 365, однако для назначения задач требуется связь с группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="8ddfc-450">**Может ли быть несколько проектов на группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="8ddfc-451">Да, можно подключить несколько проектов в одной группе.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="8ddfc-452">**Можно ли связывать проект с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-453">Нет, проект может быть связан только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="8ddfc-454">**Может ли связь проекта с группой измениться?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="8ddfc-455">Нет, после того как связь с группой установлена, она не может измениться.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="8ddfc-456">**Удаляет ли проект группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="8ddfc-457">Нет, удаление проекта в Project в Интернете не удалит группу.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="8ddfc-458">Стратегия</span><span class="sxs-lookup"><span data-stu-id="8ddfc-458">Roadmap</span></span>

<span data-ttu-id="8ddfc-459">План позволяет создавать планы проектов с project для Интернета и Project Online.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="8ddfc-460">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8ddfc-461">Планы проектов</span><span class="sxs-lookup"><span data-stu-id="8ddfc-461">Project roadmaps</span></span>

<span data-ttu-id="8ddfc-462">**Можно ли создать группу в roadmap?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="8ddfc-463">Да, можно создать группу Microsoft 365 непосредственно из плана.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="8ddfc-464">**Существует ли план действий без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="8ddfc-465">Да, планы могут существовать без связи с группой Microsoft 365, однако для совместного использования этой карты требуется связь с группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="8ddfc-466">**Может ли быть несколько стратегических карт на группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="8ddfc-467">Да, можно подключить несколько карт к одной группе.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="8ddfc-468">**Можно ли связывать план с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-469">Нет, план может быть связан только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="8ddfc-470">**Может ли меняться связь карты с группой?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="8ddfc-471">Нет, после того как связь с группой установлена, она не может измениться.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="8ddfc-472">**Удаляет ли план группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="8ddfc-473">Нет, при удалении плана группа не будет удалена.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="8ddfc-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8ddfc-474">SharePoint</span></span>

<span data-ttu-id="8ddfc-475">SharePoint — это веб-платформа управления контентом, которая, помимо прочего, предоставляет службы хранения для ряда служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="8ddfc-476">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8ddfc-477">Библиотека документов</span><span class="sxs-lookup"><span data-stu-id="8ddfc-477">Document library</span></span>
- <span data-ttu-id="8ddfc-478">Библиотека для хранения записной книжки OneNote</span><span class="sxs-lookup"><span data-stu-id="8ddfc-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="8ddfc-479">Хранилище вики-файлов Teams</span><span class="sxs-lookup"><span data-stu-id="8ddfc-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="8ddfc-480">**Может ли SharePoint создать группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="8ddfc-481">Да, при создании сайта группы в SharePoint по умолчанию создается группа Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="8ddfc-482">Кроме того, можно создать группу и при желании команду для существующего сайта.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="8ddfc-483">**Существуют ли сайты SharePoint без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="8ddfc-484">Да, SharePoint предлагает ряд не связанных с группой служб и сайтов, таких как сайты связи и концентраторы.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="8ddfc-485">**Может ли быть несколько сайтов на группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="8ddfc-486">Нет, на группу может быть только один сайт.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="8ddfc-487">Частные каналы в Teams используют дополнительные сайты, которые не подключены к группе.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="8ddfc-488">**Можно ли связывать сайты с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-489">Технически нет, но во время создания сайта с группой контент можно совместно использовать с другими группами.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="8ddfc-490">**Может ли связь сайта с группой измениться?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="8ddfc-491">Нет, сам сайт связан с группой, однако контент можно перемещать с одного сайта на другой в интерфейсе SharePoint, экспортировать контент локально или с помощью сторонного средства.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="8ddfc-492">**Удаляет ли сайт группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="8ddfc-493">Да, при удалении сайта в SharePoint удаляются службы и контент, связанные с группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="8ddfc-494">Stream</span><span class="sxs-lookup"><span data-stu-id="8ddfc-494">Stream</span></span>

<span data-ttu-id="8ddfc-495">Microsoft Stream — это платформа для размещения видео и общего доступа.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="8ddfc-496">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8ddfc-497">Хранилище видео</span><span class="sxs-lookup"><span data-stu-id="8ddfc-497">Video storage</span></span>
- <span data-ttu-id="8ddfc-498">Запись собрания Teams</span><span class="sxs-lookup"><span data-stu-id="8ddfc-498">Teams meeting recording</span></span>
- <span data-ttu-id="8ddfc-499">Видеоканалы</span><span class="sxs-lookup"><span data-stu-id="8ddfc-499">Video channels</span></span>

<span data-ttu-id="8ddfc-500">**Может ли Stream создать группу?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="8ddfc-501">Да, можно создать группу Microsoft 365 непосредственно из Stream.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="8ddfc-502">**Существует ли Stream без группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="8ddfc-503">Да, видеоканалы и видео могут существовать в Stream без связи с группой.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="8ddfc-504">**Может ли быть несколько видео и каналов для группы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="8ddfc-505">Да, в каждой группе может быть несколько видео и каналов.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="8ddfc-506">**Можно ли связывать видео или канал с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="8ddfc-507">Да, хотя видео или канал создается с группой, его можно совместно использовать с другими группами.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="8ddfc-508">**Может ли ее связь с группой измениться?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="8ddfc-509">Да и нет; видео в Stream принадлежат исходному загрузителю или записи собраний, поэтому их можно связывать с любой группой, однако каналы видео могут быть связаны только с группой, в котором они изначально были созданы.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="8ddfc-510">**Удаляет ли группа видео или каналы?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="8ddfc-511">Нет, при удалении видео или каналов группа не удаляется.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="8ddfc-512">Однако при удалении самой группы в Stream удаляются связанные с группой службы и контент, за исключением фактических видео.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="8ddfc-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="8ddfc-513">Yammer</span></span>

<span data-ttu-id="8ddfc-514">Yammer — это корпоративная социальная платформа, призванная способствовать вовлечению сообщества в организации и между ними.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="8ddfc-515">При создании сообщества (прежнее название — "группа") в Yammer создается почтовый ящик, но в настоящее время это не используется.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="8ddfc-516">Группу Microsoft 365, связанную с Yammer, нельзя использовать с командой в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="8ddfc-517">**Основные функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8ddfc-518">Область беседы</span><span class="sxs-lookup"><span data-stu-id="8ddfc-518">Conversation area</span></span>

<span data-ttu-id="8ddfc-519">**Может ли Yammer создать группу Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="8ddfc-520">Да, при создании новой группы в Yammer будет создаваться новая группа Microsoft 365, если платформы подключены и пользователь может создать группу.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="8ddfc-521">Группу Yammer со связанной группой Microsoft 365 нельзя создать в интерфейсе или службе, кроме самой Yammer.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="8ddfc-522">**Существует ли группа Yammer без группы Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="8ddfc-523">Да, можно создать группу Yammer без группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="8ddfc-524">Если платформа Yammer не подключена к группам Microsoft 365 или пользователи не могут создать группу Microsoft 365, группы Yammer создаются без связи с группами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="8ddfc-525">**Может ли быть несколько групп Yammer для группы Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="8ddfc-526">Нет, отношение между группой Yammer и группой Microsoft 365 составляет 1:1.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="8ddfc-527">**Можно ли связывать группу Yammer с несколькими группами Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="8ddfc-528">Нет, группу Yammer можно связывать только с одной группой Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="8ddfc-529">Публикации могут быть общими или перенесены в другие группы Yammer.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="8ddfc-530">**Может ли связь группы Yammer с группой Microsoft 365 измениться?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="8ddfc-531">Нет, группу Yammer можно связывать только с группой Microsoft 365, с которой она была изначально связана.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="8ddfc-532">**Удаляет ли группа Yammer группу Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="8ddfc-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="8ddfc-533">Да, при удалении группы в Yammer будут удалены связанные службы и контент, связанные с группой Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8ddfc-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8ddfc-534">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="8ddfc-534">Related topics</span></span>

[<span data-ttu-id="8ddfc-535">Пошаговая пошаговая работа по планированию управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="8ddfc-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="8ddfc-536">Создание плана управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="8ddfc-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

