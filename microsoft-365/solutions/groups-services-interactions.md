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
ms.openlocfilehash: 331c30c86481b1729251c685de2d663fb14f390b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921028"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="31105-103">Взаимодействие служб групп</span><span class="sxs-lookup"><span data-stu-id="31105-103">Groups services interactions</span></span>

<span data-ttu-id="31105-104">Microsoft 365 Groups предоставляет общую структуру для ряда служб и рабочих нагрузок в платформе Microsoft 365 для обеспечения подключения для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="31105-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="31105-105">По своей сути существует группа Microsoft 365, которая предоставляет:</span><span class="sxs-lookup"><span data-stu-id="31105-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="31105-106">Способ управления членством (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="31105-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="31105-107">Место для обмена сообщениями и бесед (почтовый ящик Exchange, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="31105-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="31105-108">Место хранения файлов (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="31105-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="31105-109">Календарь планирования (Exchange)</span><span class="sxs-lookup"><span data-stu-id="31105-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="31105-110">Записная книжка для записи записей (OneNote)</span><span class="sxs-lookup"><span data-stu-id="31105-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="31105-111">На этапе создания группы также предусмотрен ряд других ресурсов, однако они не видны до первого доступа из службы:</span><span class="sxs-lookup"><span data-stu-id="31105-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="31105-112">Совет по управлению групповыми задачами (Планировщик)</span><span class="sxs-lookup"><span data-stu-id="31105-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="31105-113">Рабочее пространство для отчетов (Power BI)</span><span class="sxs-lookup"><span data-stu-id="31105-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="31105-114">Область общих видео (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="31105-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="31105-115">Область общих форм (Forms)</span><span class="sxs-lookup"><span data-stu-id="31105-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="31105-116">В Microsoft 365 другие службы могут взаимодействовать с группами Microsoft 365 для предоставления дополнительных функций и возможностей участникам группы.</span><span class="sxs-lookup"><span data-stu-id="31105-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="31105-117">Примеры этого:</span><span class="sxs-lookup"><span data-stu-id="31105-117">Examples of this include:</span></span>

- <span data-ttu-id="31105-118">Power Apps для приложений</span><span class="sxs-lookup"><span data-stu-id="31105-118">Power Apps for apps</span></span>
- <span data-ttu-id="31105-119">Power Automate для рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="31105-119">Power Automate for workflows</span></span>
- <span data-ttu-id="31105-120">Project on the web and Roadmap for waterfall-based project management</span><span class="sxs-lookup"><span data-stu-id="31105-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="31105-121">Группы для разговоров на основе каналов</span><span class="sxs-lookup"><span data-stu-id="31105-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="31105-122">Yammer для интересующие сообщества</span><span class="sxs-lookup"><span data-stu-id="31105-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="31105-123">Взаимодействие пользователей с группами</span><span class="sxs-lookup"><span data-stu-id="31105-123">User interactions with groups</span></span>

<span data-ttu-id="31105-124">Группы Microsoft 365 можно создавать и управлять из различных интерфейсов, как администраторов, так и конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="31105-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="31105-125">Администрирование</span><span class="sxs-lookup"><span data-stu-id="31105-125">Administrative experiences</span></span>

<span data-ttu-id="31105-126">Администраторы могут создавать и управлять группами Microsoft 365 из нескольких центров администрирования рабочей нагрузки, интерфейсов командной строки, поддерживаюющих сценарии, а также настраиваемые приложения, взаимодействующие с API graph.</span><span class="sxs-lookup"><span data-stu-id="31105-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="31105-127">Единственным исключением являются группы Yammer, которые должны создаваться из веб-интерфейса Yammer.</span><span class="sxs-lookup"><span data-stu-id="31105-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="31105-128">**Связанные параметры**</span><span class="sxs-lookup"><span data-stu-id="31105-128">**Related settings**</span></span>

<span data-ttu-id="31105-129">В различных административных интерфейсах, которые могут управлять групповыми настройками, существует несколько перекрытий, о которых следует знать.</span><span class="sxs-lookup"><span data-stu-id="31105-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="31105-130">**Центр администрирования Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="31105-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="31105-131">В центре администрирования Microsoft 365 гостевой доступ к Группам включен по умолчанию, как и возможность разрешить владельцам добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="31105-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="31105-132">Дополнительные элементы управления на уровне организации для групп из этого центра администрирования недоступны.</span><span class="sxs-lookup"><span data-stu-id="31105-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="31105-133">**Центр администрирования Azure AD**</span><span class="sxs-lookup"><span data-stu-id="31105-133">**Azure AD admin center**</span></span>

<span data-ttu-id="31105-134">Центр администрирования Azure AD позволяет определить, могут ли пользователи создавать группы или назначать владельцев на порталах Azure, а также параметры политики истечения срока действия и именования.</span><span class="sxs-lookup"><span data-stu-id="31105-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="31105-135">Центр администрирования также предоставляет ряд мер по контролю приглашений гостей, которые выходят за пределы центра администрирования Microsoft 365, например возможность ограничения возможности приглашения гостей, не владея их владельцами.</span><span class="sxs-lookup"><span data-stu-id="31105-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="31105-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="31105-136">**SharePoint**</span></span>

<span data-ttu-id="31105-137">Сайты SharePoint создаются с группами безопасности Owner, Member и Visitor, а первые два совпадают со своими коллегами microsoft 365 Group.</span><span class="sxs-lookup"><span data-stu-id="31105-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="31105-138">Хотя членство для сайтов SharePoint Online, как правило, управляется связанной группой Microsoft 365, она не является бидиректорной связью.</span><span class="sxs-lookup"><span data-stu-id="31105-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="31105-139">Любые изменения в членстве на уровне группы Microsoft 365 отражены в SharePoint, однако если членство изменено в группе SharePoint, это не отражается в группе Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="31105-140">Пользовательские впечатления</span><span class="sxs-lookup"><span data-stu-id="31105-140">User experiences</span></span>

<span data-ttu-id="31105-141">Конечные пользователи могут создавать группы из нескольких служб в Microsoft 365, а в других они могут делиться только с группой.</span><span class="sxs-lookup"><span data-stu-id="31105-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="31105-142">Следующие службы позволяют создавать группы конечными пользователями:</span><span class="sxs-lookup"><span data-stu-id="31105-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="31105-143">Проект планирования Outlook для веб-sharePoint Stream Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="31105-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="31105-144">**Ограничение создания группы**</span><span class="sxs-lookup"><span data-stu-id="31105-144">**Restriction of group creation**</span></span>

<span data-ttu-id="31105-145">Распространенный подход к борьбе с разрастаемой командой заключается в ограничении возможностей их создания пользователями.</span><span class="sxs-lookup"><span data-stu-id="31105-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="31105-146">Это можно сделать, ограничив создание групп.</span><span class="sxs-lookup"><span data-stu-id="31105-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="31105-147">Это влияет на возможность создания групп из других служб, где это может потребоваться конечному пользователю.</span><span class="sxs-lookup"><span data-stu-id="31105-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="31105-148">Microsoft 365 Groups не поддерживает возможность ограничения создания групп из одних приложений или служб, разрешая их другим.</span><span class="sxs-lookup"><span data-stu-id="31105-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="31105-149">Опыт ограничения создания групп варьируется между приложениями и службами:</span><span class="sxs-lookup"><span data-stu-id="31105-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="31105-150">Приложение или служба</span><span class="sxs-lookup"><span data-stu-id="31105-150">App or service</span></span>|<span data-ttu-id="31105-151">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="31105-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="31105-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="31105-152">Outlook</span></span>|<span data-ttu-id="31105-153">**Новый параметр группы** удаляется из нового меню на странице people</span><span class="sxs-lookup"><span data-stu-id="31105-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="31105-154">Планировщик</span><span class="sxs-lookup"><span data-stu-id="31105-154">Planner</span></span>|<span data-ttu-id="31105-155">**Новый план** объясняет, что создание группы отключено, и предлагает добавить план в существующую группу</span><span class="sxs-lookup"><span data-stu-id="31105-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="31105-156">Project for the web and Roadmap</span><span class="sxs-lookup"><span data-stu-id="31105-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="31105-157">**Создание группового** меню объясняет, что создание группы ограничено, и предлагает использовать существующую группу.</span><span class="sxs-lookup"><span data-stu-id="31105-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="31105-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="31105-158">SharePoint</span></span>|<span data-ttu-id="31105-159">По-прежнему можно создать сайт группы, не подключенный к группе.</span><span class="sxs-lookup"><span data-stu-id="31105-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="31105-160">Stream</span><span class="sxs-lookup"><span data-stu-id="31105-160">Stream</span></span>|<span data-ttu-id="31105-161">**Параметр Group** не появляется в меню **Create**.</span><span class="sxs-lookup"><span data-stu-id="31105-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="31105-162">Teams</span><span class="sxs-lookup"><span data-stu-id="31105-162">Teams</span></span>|<span data-ttu-id="31105-163">Пользователь не может создать команду с новой группой, но может создать группу, которая использует существующую группу.</span><span class="sxs-lookup"><span data-stu-id="31105-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="31105-164">**Создание кнопки команды** заменяется **командой Create team из группы.**</span><span class="sxs-lookup"><span data-stu-id="31105-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="31105-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="31105-165">Yammer</span></span>|<span data-ttu-id="31105-166">**Создание группового** параметра удаляется из основной навигации групп и сообществ.</span><span class="sxs-lookup"><span data-stu-id="31105-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="31105-167">Взаимодействие служб с группами</span><span class="sxs-lookup"><span data-stu-id="31105-167">Services interactions with groups</span></span>

<span data-ttu-id="31105-168">См. плакат Группы в Microsoft 365 для получения сведений о различных типах групп, их создания и управления, а также нескольких рекомендаций по управлению.</span><span class="sxs-lookup"><span data-stu-id="31105-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="31105-169">[![Эскиз инфографики групп](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="31105-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="31105-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="31105-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="31105-171">В следующей таблице представлен обзор взаимодействия Microsoft 365 Groups с различными службами:</span><span class="sxs-lookup"><span data-stu-id="31105-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="31105-172">Продукт</span><span class="sxs-lookup"><span data-stu-id="31105-172">Product</span></span>|<span data-ttu-id="31105-173">Возможности</span><span class="sxs-lookup"><span data-stu-id="31105-173">Features</span></span>|<span data-ttu-id="31105-174">Делает службу</span><span class="sxs-lookup"><span data-stu-id="31105-174">Does the service</span></span><br><span data-ttu-id="31105-175">существуют без группы?</span><span class="sxs-lookup"><span data-stu-id="31105-175">exist without a group?</span></span>|<span data-ttu-id="31105-176">Может ли служба</span><span class="sxs-lookup"><span data-stu-id="31105-176">Can the service</span></span><br><span data-ttu-id="31105-177">создать группу?</span><span class="sxs-lookup"><span data-stu-id="31105-177">create a group?</span></span>|<span data-ttu-id="31105-178">Удаление</span><span class="sxs-lookup"><span data-stu-id="31105-178">Does deleting the</span></span><br><span data-ttu-id="31105-179">экземпляр удалить группу?</span><span class="sxs-lookup"><span data-stu-id="31105-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="31105-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="31105-180">Azure AD</span></span>|<span data-ttu-id="31105-181">Членство, элементы управления группой, гости</span><span class="sxs-lookup"><span data-stu-id="31105-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="31105-182">Да</span><span class="sxs-lookup"><span data-stu-id="31105-182">Yes</span></span>|<span data-ttu-id="31105-183">Да</span><span class="sxs-lookup"><span data-stu-id="31105-183">Yes</span></span>|<span data-ttu-id="31105-184">Да</span><span class="sxs-lookup"><span data-stu-id="31105-184">Yes</span></span>|
|<span data-ttu-id="31105-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="31105-185">Exchange</span></span>|<span data-ttu-id="31105-186">Календарь, почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="31105-186">Calendar, mailbox</span></span>|<span data-ttu-id="31105-187">Да</span><span class="sxs-lookup"><span data-stu-id="31105-187">Yes</span></span>|<span data-ttu-id="31105-188">Да</span><span class="sxs-lookup"><span data-stu-id="31105-188">Yes</span></span>|<span data-ttu-id="31105-189">Да</span><span class="sxs-lookup"><span data-stu-id="31105-189">Yes</span></span>|
|<span data-ttu-id="31105-190">Forms</span><span class="sxs-lookup"><span data-stu-id="31105-190">Forms</span></span>|<span data-ttu-id="31105-191">Form</span><span class="sxs-lookup"><span data-stu-id="31105-191">Form</span></span>|<span data-ttu-id="31105-192">Да</span><span class="sxs-lookup"><span data-stu-id="31105-192">Yes</span></span>|<span data-ttu-id="31105-193">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-193">No</span></span>|<span data-ttu-id="31105-194">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-194">No</span></span>|
|<span data-ttu-id="31105-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="31105-195">OneNote</span></span>|<span data-ttu-id="31105-196">Notebook</span><span class="sxs-lookup"><span data-stu-id="31105-196">Notebook</span></span>|<span data-ttu-id="31105-197">Да</span><span class="sxs-lookup"><span data-stu-id="31105-197">Yes</span></span>|<span data-ttu-id="31105-198">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-198">No</span></span>|<span data-ttu-id="31105-199">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-199">No</span></span>|
|<span data-ttu-id="31105-200">Планировщик</span><span class="sxs-lookup"><span data-stu-id="31105-200">Planner</span></span>|<span data-ttu-id="31105-201">Доска задач</span><span class="sxs-lookup"><span data-stu-id="31105-201">Task board</span></span>|<span data-ttu-id="31105-202">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-202">No</span></span>|<span data-ttu-id="31105-203">Да</span><span class="sxs-lookup"><span data-stu-id="31105-203">Yes</span></span>|<span data-ttu-id="31105-204">Да</span><span class="sxs-lookup"><span data-stu-id="31105-204">Yes</span></span>|
|<span data-ttu-id="31105-205">Приложение Power Apps</span><span class="sxs-lookup"><span data-stu-id="31105-205">Power Apps app</span></span>|<span data-ttu-id="31105-206">Приложение</span><span class="sxs-lookup"><span data-stu-id="31105-206">App</span></span>|<span data-ttu-id="31105-207">Да</span><span class="sxs-lookup"><span data-stu-id="31105-207">Yes</span></span>|<span data-ttu-id="31105-208">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-208">No</span></span>|<span data-ttu-id="31105-209">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-209">No</span></span>|
|<span data-ttu-id="31105-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="31105-210">Power Automate</span></span>|<span data-ttu-id="31105-211">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="31105-211">Workflow</span></span>|<span data-ttu-id="31105-212">Да</span><span class="sxs-lookup"><span data-stu-id="31105-212">Yes</span></span>|<span data-ttu-id="31105-213">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-213">No</span></span>|<span data-ttu-id="31105-214">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-214">No</span></span>|
|<span data-ttu-id="31105-215">Power BI (классический)</span><span class="sxs-lookup"><span data-stu-id="31105-215">Power BI (classic)</span></span>|<span data-ttu-id="31105-216">Рабочая группа</span><span class="sxs-lookup"><span data-stu-id="31105-216">Workspace</span></span>|<span data-ttu-id="31105-217">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-217">No</span></span>|<span data-ttu-id="31105-218">Да</span><span class="sxs-lookup"><span data-stu-id="31105-218">Yes</span></span>|<span data-ttu-id="31105-219">Да</span><span class="sxs-lookup"><span data-stu-id="31105-219">Yes</span></span>|
|<span data-ttu-id="31105-220">Power BI (new)</span><span class="sxs-lookup"><span data-stu-id="31105-220">Power BI (new)</span></span>|<span data-ttu-id="31105-221">Рабочая группа</span><span class="sxs-lookup"><span data-stu-id="31105-221">Workspace</span></span>|<span data-ttu-id="31105-222">Да</span><span class="sxs-lookup"><span data-stu-id="31105-222">Yes</span></span>|<span data-ttu-id="31105-223">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-223">No</span></span>|<span data-ttu-id="31105-224">Да</span><span class="sxs-lookup"><span data-stu-id="31105-224">Yes</span></span>|
|<span data-ttu-id="31105-225">Project в Интернете</span><span class="sxs-lookup"><span data-stu-id="31105-225">Project for the web</span></span>|<span data-ttu-id="31105-226">План проекта</span><span class="sxs-lookup"><span data-stu-id="31105-226">Project plan</span></span>|<span data-ttu-id="31105-227">Да</span><span class="sxs-lookup"><span data-stu-id="31105-227">Yes</span></span>|<span data-ttu-id="31105-228">Да</span><span class="sxs-lookup"><span data-stu-id="31105-228">Yes</span></span>|<span data-ttu-id="31105-229">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-229">No</span></span>|
|<span data-ttu-id="31105-230">Стратегия</span><span class="sxs-lookup"><span data-stu-id="31105-230">Roadmap</span></span>|<span data-ttu-id="31105-231">Стратегия</span><span class="sxs-lookup"><span data-stu-id="31105-231">Roadmap</span></span>|<span data-ttu-id="31105-232">Да</span><span class="sxs-lookup"><span data-stu-id="31105-232">Yes</span></span>|<span data-ttu-id="31105-233">Да</span><span class="sxs-lookup"><span data-stu-id="31105-233">Yes</span></span>|<span data-ttu-id="31105-234">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-234">No</span></span>|
|<span data-ttu-id="31105-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="31105-235">SharePoint</span></span>|<span data-ttu-id="31105-236">Site</span><span class="sxs-lookup"><span data-stu-id="31105-236">Site</span></span>|<span data-ttu-id="31105-237">Да</span><span class="sxs-lookup"><span data-stu-id="31105-237">Yes</span></span>|<span data-ttu-id="31105-238">Да</span><span class="sxs-lookup"><span data-stu-id="31105-238">Yes</span></span>|<span data-ttu-id="31105-239">Да</span><span class="sxs-lookup"><span data-stu-id="31105-239">Yes</span></span>|
|<span data-ttu-id="31105-240">Stream</span><span class="sxs-lookup"><span data-stu-id="31105-240">Stream</span></span>|<span data-ttu-id="31105-241">Канал, видео</span><span class="sxs-lookup"><span data-stu-id="31105-241">Channel, video</span></span>|<span data-ttu-id="31105-242">Да</span><span class="sxs-lookup"><span data-stu-id="31105-242">Yes</span></span>|<span data-ttu-id="31105-243">Да</span><span class="sxs-lookup"><span data-stu-id="31105-243">Yes</span></span>|<span data-ttu-id="31105-244">Да</span><span class="sxs-lookup"><span data-stu-id="31105-244">Yes</span></span>|
|<span data-ttu-id="31105-245">Teams</span><span class="sxs-lookup"><span data-stu-id="31105-245">Teams</span></span>|<span data-ttu-id="31105-246">Команда</span><span class="sxs-lookup"><span data-stu-id="31105-246">Team</span></span>|<span data-ttu-id="31105-247">Нет</span><span class="sxs-lookup"><span data-stu-id="31105-247">No</span></span>|<span data-ttu-id="31105-248">Да</span><span class="sxs-lookup"><span data-stu-id="31105-248">Yes</span></span>|<span data-ttu-id="31105-249">Да</span><span class="sxs-lookup"><span data-stu-id="31105-249">Yes</span></span>|
|<span data-ttu-id="31105-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="31105-250">Yammer</span></span>|<span data-ttu-id="31105-251">Group</span><span class="sxs-lookup"><span data-stu-id="31105-251">Group</span></span>|<span data-ttu-id="31105-252">Да</span><span class="sxs-lookup"><span data-stu-id="31105-252">Yes</span></span>|<span data-ttu-id="31105-253">Да</span><span class="sxs-lookup"><span data-stu-id="31105-253">Yes</span></span>|<span data-ttu-id="31105-254">Да</span><span class="sxs-lookup"><span data-stu-id="31105-254">Yes</span></span>|

<span data-ttu-id="31105-255">Хотя в таблице выше представлен краткий обзор групповых взаимодействий с службами Microsoft 365, необходимо понимать ряд нюансов и тонкости.</span><span class="sxs-lookup"><span data-stu-id="31105-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="31105-256">В следующих разделах подробно изуметь конкретные рабочие нагрузки и их взаимодействие с группами.</span><span class="sxs-lookup"><span data-stu-id="31105-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="31105-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="31105-257">Azure AD</span></span>

<span data-ttu-id="31105-258">Azure AD предоставляет возможности управления удостоверениями в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="31105-259">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="31105-260">Участие в группе</span><span class="sxs-lookup"><span data-stu-id="31105-260">Group membership</span></span>
- <span data-ttu-id="31105-261">Политика именования</span><span class="sxs-lookup"><span data-stu-id="31105-261">Naming policy</span></span>
- <span data-ttu-id="31105-262">Политика прекращения действия</span><span class="sxs-lookup"><span data-stu-id="31105-262">Expiration policy</span></span>
- <span data-ttu-id="31105-263">Гости</span><span class="sxs-lookup"><span data-stu-id="31105-263">Guests</span></span>
- <span data-ttu-id="31105-264">Ограничение создания группы</span><span class="sxs-lookup"><span data-stu-id="31105-264">Restriction of Group creation</span></span>

<span data-ttu-id="31105-265">**Может ли Azure AD создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="31105-266">Да, группы Microsoft 365 можно создавать из Azure AD либо через веб-портал администрирования, либо через PowerShell, либо API Graph.</span><span class="sxs-lookup"><span data-stu-id="31105-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="31105-267">**Существует ли Azure AD без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="31105-268">Да, Azure AD выполняет большое количество служб, которые не имеют отношения к Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="31105-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="31105-269">Каждая группа Microsoft 365 представлена как объект в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="31105-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="31105-270">**Может ли быть несколько экземпляров Azure AD для группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="31105-271">Нет, существует только один экземпляр Azure AD.</span><span class="sxs-lookup"><span data-stu-id="31105-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="31105-272">**Можно ли связывать Azure AD с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="31105-273">Да, так как Azure AD — это платформа, которая предоставляет службу членства в группе.</span><span class="sxs-lookup"><span data-stu-id="31105-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="31105-274">**Может ли связь Azure AD с групповой переменой?**</span><span class="sxs-lookup"><span data-stu-id="31105-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="31105-275">Нет, Azure AD — это платформа, на которой существуют группы.</span><span class="sxs-lookup"><span data-stu-id="31105-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="31105-276">**Удаление экземпляра удаляет группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="31105-277">Удаление группы в Azure AD удаляет соответствующие службы и контент, связанные с группой.</span><span class="sxs-lookup"><span data-stu-id="31105-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="31105-278">Teams</span><span class="sxs-lookup"><span data-stu-id="31105-278">Teams</span></span>

<span data-ttu-id="31105-279">Teams — это рабочее пространство в центре чата, направленное на повышение эффективности совместной работы путем предоставления сингулярного интерфейса для взаимодействия с различными службами Майкрософт и сторонними пользователями.</span><span class="sxs-lookup"><span data-stu-id="31105-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="31105-280">По умолчанию при создания группы почтовый ящик и календарь, связанный с группой Microsoft 365, скрыты как из глобального списка адресов в Exchange, так и из Outlook.</span><span class="sxs-lookup"><span data-stu-id="31105-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="31105-281">Это может быть переопределено администратором вручную, если пользователь хочет использовать Outlook и Teams в одной группе Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="31105-282">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="31105-283">Беседы</span><span class="sxs-lookup"><span data-stu-id="31105-283">Conversations</span></span>
- <span data-ttu-id="31105-284">Вкладки & каналов</span><span class="sxs-lookup"><span data-stu-id="31105-284">Channels & tabs</span></span>
- <span data-ttu-id="31105-285">Собрания</span><span class="sxs-lookup"><span data-stu-id="31105-285">Meetings</span></span>

<span data-ttu-id="31105-286">**Может ли Teams создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="31105-287">Да, создание новой группы создаст новую группу Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="31105-288">Также можно создать группу для существующей группы, которая в настоящее время не имеет ее.</span><span class="sxs-lookup"><span data-stu-id="31105-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="31105-289">**Существуют ли группы без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="31105-290">Нет, группа не может существовать без группы.</span><span class="sxs-lookup"><span data-stu-id="31105-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="31105-291">**Может ли быть несколько групп в группе?**</span><span class="sxs-lookup"><span data-stu-id="31105-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="31105-292">Нет, отношения между командой и группой 1:1.</span><span class="sxs-lookup"><span data-stu-id="31105-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="31105-293">**Можно ли связывать команду с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-294">Нет, сама команда может быть связана только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="31105-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="31105-295">**Может ли измениться связь группы с группой?**</span><span class="sxs-lookup"><span data-stu-id="31105-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="31105-296">Нет, группу можно связывать только с группой, с которой она изначально была связана.</span><span class="sxs-lookup"><span data-stu-id="31105-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="31105-297">**Удаление группы удаляет группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="31105-298">Да, удаление группы в Microsoft Teams удаляет группу, связанные с группами службы и контент.</span><span class="sxs-lookup"><span data-stu-id="31105-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="31105-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="31105-299">Exchange</span></span>

<span data-ttu-id="31105-300">Exchange Online предоставляет функции обмена сообщениями, календаря, контактов и связанных с ними функций.</span><span class="sxs-lookup"><span data-stu-id="31105-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="31105-301">В контексте группы связан только один ресурс, в отличие от целого экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="31105-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="31105-302">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="31105-303">Почтовый ящик и календарь</span><span class="sxs-lookup"><span data-stu-id="31105-303">Mailbox and calendar</span></span>
- <span data-ttu-id="31105-304">Возможность отправки по электронной почте всем участникам группы</span><span class="sxs-lookup"><span data-stu-id="31105-304">Ability to email all Group members</span></span>
- <span data-ttu-id="31105-305">Хранение разговоров каналов Teams для целей eDiscovery, комментарии планировщика</span><span class="sxs-lookup"><span data-stu-id="31105-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="31105-306">**Может ли Exchange создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="31105-307">Да, можно создать группу из центра администрирования Exchange Online, а также из Outlook.</span><span class="sxs-lookup"><span data-stu-id="31105-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="31105-308">Списки рассылки Exchange также можно преобразовать в группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="31105-309">**Существует ли Exchange без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="31105-310">Да, Exchange Online предоставляет ряд служб, включая общие почтовые ящики и календари, без какой-либо групповой связи.</span><span class="sxs-lookup"><span data-stu-id="31105-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="31105-311">**Может ли быть несколько экземпляров почтовых ящиков Exchange или календарей для группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="31105-312">Нет, для группы может быть только один почтовый ящик и календарь Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="31105-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="31105-313">**Можно ли связывать почтовые ящики и календари Exchange с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-314">Нет, почтовый ящик и календарь имеют отношение 1:1 к группе.</span><span class="sxs-lookup"><span data-stu-id="31105-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="31105-315">Можно делиться почтовым ящиком с другими пользователями или группами, однако это не создает никакой формы ассоциации служб.</span><span class="sxs-lookup"><span data-stu-id="31105-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="31105-316">**Может ли измениться связь почтового ящика Exchange или календаря с группой?**</span><span class="sxs-lookup"><span data-stu-id="31105-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="31105-317">Нет, почтовый ящик и календарь нельзя изменить на другую группу.</span><span class="sxs-lookup"><span data-stu-id="31105-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="31105-318">Однако содержимое может быть перемещено из одного почтового ящика в другой в Outlook или с помощью сторонного средства.</span><span class="sxs-lookup"><span data-stu-id="31105-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="31105-319">**Удаление почтового ящика удаляет группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="31105-320">Да, удаление почтового ящика в Exchange удаляет группу, а также связанные с группой службы и контент.</span><span class="sxs-lookup"><span data-stu-id="31105-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="31105-321">Forms</span><span class="sxs-lookup"><span data-stu-id="31105-321">Forms</span></span>

<span data-ttu-id="31105-322">Forms предоставляет веб-опросы и викторины.</span><span class="sxs-lookup"><span data-stu-id="31105-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="31105-323">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="31105-324">Владение формами</span><span class="sxs-lookup"><span data-stu-id="31105-324">Ownership of forms</span></span>

<span data-ttu-id="31105-325">**Может ли Forms создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="31105-326">Нет, Forms не может создать группу.</span><span class="sxs-lookup"><span data-stu-id="31105-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="31105-327">**Существуют ли формы без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="31105-328">Да, опросы и викторины можно создавать непосредственно в учетной записи конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="31105-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="31105-329">**Может ли быть несколько форм в группе?**</span><span class="sxs-lookup"><span data-stu-id="31105-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="31105-330">Да, может быть несколько форм, связанных с группой.</span><span class="sxs-lookup"><span data-stu-id="31105-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="31105-331">**Можно ли связывать формы с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-332">Нет, форму можно связывать только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="31105-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="31105-333">**Может ли связь формы с групповой переменой?**</span><span class="sxs-lookup"><span data-stu-id="31105-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="31105-334">Нет, если форма связана с группой (либо создается непосредственно внутри, либо передается от физического лица), ее нельзя переносить в другую группу.</span><span class="sxs-lookup"><span data-stu-id="31105-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="31105-335">**Удаление формы удаляет группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="31105-336">Нет, удалить группу из интерфейса Forms невозможно, только отдельные формы.</span><span class="sxs-lookup"><span data-stu-id="31105-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="31105-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="31105-337">OneNote</span></span>

<span data-ttu-id="31105-338">OneNote — это цифровое приложение для записной книжки.</span><span class="sxs-lookup"><span data-stu-id="31105-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="31105-339">Блокнот OneNote, созданный с группой, — это файл на связанном сайте SharePoint, а не на связанной с группой службе.</span><span class="sxs-lookup"><span data-stu-id="31105-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="31105-340">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="31105-341">Общий блокнот (хранится в связанной с группой библиотеке SharePoint)</span><span class="sxs-lookup"><span data-stu-id="31105-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="31105-342">**Может ли OneNote создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="31105-343">Нет, приложение OneNote не может создать группу.</span><span class="sxs-lookup"><span data-stu-id="31105-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="31105-344">**Существуют ли записные книжки OneNote без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="31105-345">Да, записные книжки можно создавать непосредственно в OneDrive или в других общих расположениях.</span><span class="sxs-lookup"><span data-stu-id="31105-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="31105-346">**Может ли быть несколько тетрадей OneNote в группе?**</span><span class="sxs-lookup"><span data-stu-id="31105-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="31105-347">Да, записная книжка создается по умолчанию и можно добавлять другие, однако любая ссылка на OneNote из связанных с группой служб всегда будет идти в записную книжку по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="31105-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="31105-348">**Можно ли связывать записную книжку OneNote с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-349">Нет, записная книжка хранится в связанной с группой библиотеке сайтов SharePoint и связана с различными интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="31105-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="31105-350">Однако его можно совместно использовать с другими группами таким же образом, как и с отдельными лицами.</span><span class="sxs-lookup"><span data-stu-id="31105-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="31105-351">**Может ли связь ноутбука с группой измениться?**</span><span class="sxs-lookup"><span data-stu-id="31105-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="31105-352">Нет, сама записная книжка связана с группой и может напрямую получать доступ к другим службам, связанным с группой, однако содержимое может быть перемещено из одной записной книжки в другую в приложении OneNote.</span><span class="sxs-lookup"><span data-stu-id="31105-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="31105-353">**Удаление записной книжки удаляет группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="31105-354">Нет, однако при удалении записной книжки OneNote в некоторых службах, связанных с группой, могут быть нарушены ссылки.</span><span class="sxs-lookup"><span data-stu-id="31105-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="31105-355">Планировщик</span><span class="sxs-lookup"><span data-stu-id="31105-355">Planner</span></span>

<span data-ttu-id="31105-356">Planner — это облегченная служба управления групповыми задачами.</span><span class="sxs-lookup"><span data-stu-id="31105-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="31105-357">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="31105-358">Совет по управлению групповыми задачами</span><span class="sxs-lookup"><span data-stu-id="31105-358">Board for managing group tasks</span></span>

<span data-ttu-id="31105-359">**Может ли планировщик создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="31105-360">Да, создание плана создаст новую группу.</span><span class="sxs-lookup"><span data-stu-id="31105-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="31105-361">**Существует ли доска планировщика без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="31105-362">Нет, план должен быть связан с группой.</span><span class="sxs-lookup"><span data-stu-id="31105-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="31105-363">**Может ли быть несколько планов для группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="31105-364">Да, в группе может быть несколько планов.</span><span class="sxs-lookup"><span data-stu-id="31105-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="31105-365">**Можно ли связывать план с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-366">Нет, для определения доступа для плана зависит только членство в группе.</span><span class="sxs-lookup"><span data-stu-id="31105-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="31105-367">**Может ли связь плана с групповой переменой?**</span><span class="sxs-lookup"><span data-stu-id="31105-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="31105-368">Нет, однако копирование плана создает новую группу.</span><span class="sxs-lookup"><span data-stu-id="31105-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="31105-369">Группа, созданная любым другим приложением, не будет автоматически показываться в Planner для пользователя.</span><span class="sxs-lookup"><span data-stu-id="31105-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="31105-370">Чтобы получить доступ к доске, сначала необходимо открыть ее из другого группового интерфейса, например Outlook.</span><span class="sxs-lookup"><span data-stu-id="31105-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="31105-371">**Удаление плана удаляет группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="31105-372">Да, удаление плана позволит удалить службы и контент, связанные с группой.</span><span class="sxs-lookup"><span data-stu-id="31105-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="31105-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="31105-373">Power Apps</span></span>

<span data-ttu-id="31105-374">Power Apps предоставляет холст для разработки приложений без кода.</span><span class="sxs-lookup"><span data-stu-id="31105-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="31105-375">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="31105-376">Приложения можно совместно использовать с группой, которая будет запускаться и изменяться</span><span class="sxs-lookup"><span data-stu-id="31105-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="31105-377">**Может ли Power Apps создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="31105-378">Нет, Power Apps не может создать группу Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="31105-379">**Существуют ли приложения power без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="31105-380">Да, приложения можно создавать в Power Apps и находиться в учетной записи создателей до публикации или общего опубликования.</span><span class="sxs-lookup"><span data-stu-id="31105-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="31105-381">**Может ли быть несколько приложений в группе?**</span><span class="sxs-lookup"><span data-stu-id="31105-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="31105-382">Да, в группе может быть несколько приложений.</span><span class="sxs-lookup"><span data-stu-id="31105-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="31105-383">**Можно ли связывать приложения с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-384">Да, приложение можно совместно использовать с несколькими группами.</span><span class="sxs-lookup"><span data-stu-id="31105-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="31105-385">**Может ли связь приложения с группой измениться?**</span><span class="sxs-lookup"><span data-stu-id="31105-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="31105-386">Да, поскольку связь между Power Apps и группой Microsoft 365 делится только — приложение по-прежнему находится с создателем.</span><span class="sxs-lookup"><span data-stu-id="31105-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31105-387">[Группы должны быть включены для обеспечения безопасности, прежде чем приложения могут быть общими с ними.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="31105-387">[Groups must be security enabled before apps can be shared with them](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="31105-388">**Удаляет ли приложение группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="31105-389">Нет, приложения не подключены к группе, кроме общего с ними.</span><span class="sxs-lookup"><span data-stu-id="31105-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="31105-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="31105-390">Power Automate</span></span>

<span data-ttu-id="31105-391">Power Automate (ранее известный как Microsoft Flow) предоставляет рабочий процесс и службы автоматизации.</span><span class="sxs-lookup"><span data-stu-id="31105-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="31105-392">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="31105-393">Рабочий процесс можно совместно использовать для запуска и изменения группы.</span><span class="sxs-lookup"><span data-stu-id="31105-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="31105-394">**Может ли Power Automate создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="31105-395">Нет, Power Automate не может создать группу Microsoft 365 в контексте связи с ней.</span><span class="sxs-lookup"><span data-stu-id="31105-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="31105-396">Однако можно создать поток, который выполняет различные операции, такие как создание группы безопасности Azure AD или обновление членства группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="31105-397">**Существуют ли потоки без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="31105-398">Да, потоки можно создавать в Power Automate и находиться в учетной записи создателей до общего или опубликованного.</span><span class="sxs-lookup"><span data-stu-id="31105-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="31105-399">**Может ли быть несколько потоков на одну группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="31105-400">Да, может быть несколько потоков, общих с группой.</span><span class="sxs-lookup"><span data-stu-id="31105-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="31105-401">**Можно ли связывать поток с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-402">Да, поток можно совместно использовать с несколькими группами.</span><span class="sxs-lookup"><span data-stu-id="31105-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="31105-403">**Может ли связь потока с группой измениться?**</span><span class="sxs-lookup"><span data-stu-id="31105-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="31105-404">Да, так как связь между Power Automate и группой Microsoft 365 делится только — поток по-прежнему находится с создателем.</span><span class="sxs-lookup"><span data-stu-id="31105-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="31105-405">**Удаление потока удаляет группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="31105-406">Нет, как и Power Apps, потоки не подключены к группе, кроме общего с ними.</span><span class="sxs-lookup"><span data-stu-id="31105-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="31105-407">Power BI (классический)</span><span class="sxs-lookup"><span data-stu-id="31105-407">Power BI (classic)</span></span>

<span data-ttu-id="31105-408">Power BI предоставляет интерактивные панели мониторинга и отчеты на основе данных.</span><span class="sxs-lookup"><span data-stu-id="31105-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="31105-409">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="31105-410">Отчеты о данных</span><span class="sxs-lookup"><span data-stu-id="31105-410">Data reporting</span></span>

<span data-ttu-id="31105-411">**Может ли Power BI создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="31105-412">Да, создание классического рабочего пространства создаст группу Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="31105-413">**Существует ли классическое рабочее пространство Power BI без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="31105-414">Нет, [классическое рабочее пространство в Power BI должно быть связано с группой](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="31105-414">No, [a classic workspace in Power BI must be associated with a group](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="31105-415">**Может ли быть несколько бизнес-пространств Power BI в группе?**</span><span class="sxs-lookup"><span data-stu-id="31105-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="31105-416">Нет, связь между классическим рабочее пространство и группой 1:1.</span><span class="sxs-lookup"><span data-stu-id="31105-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="31105-417">**Можно ли связывать рабочее пространство с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-418">Технически нет, хотя классическое рабочее пространство создается вместе с группой, содержимое можно совместно использовать за пределами группы с пользователями и группами безопасности.</span><span class="sxs-lookup"><span data-stu-id="31105-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="31105-419">**Может ли измениться связь рабочей области с групповой группой?**</span><span class="sxs-lookup"><span data-stu-id="31105-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="31105-420">Нет, классическое рабочее пространство связано с Группой, однако содержимое можно перемещать из одного рабочего пространства в другое в интерфейсе Power BI или экспортировать содержимое локально.</span><span class="sxs-lookup"><span data-stu-id="31105-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="31105-421">**Удаление рабочей области удаляет группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="31105-422">Да, удаление рабочего пространства в Power BI будет удалять групповые и связанные с группой службы и контент.</span><span class="sxs-lookup"><span data-stu-id="31105-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="31105-423">Power BI (new)</span><span class="sxs-lookup"><span data-stu-id="31105-423">Power BI (new)</span></span>

<span data-ttu-id="31105-424">Power BI предоставляет интерактивные панели мониторинга и отчеты на основе данных.</span><span class="sxs-lookup"><span data-stu-id="31105-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="31105-425">При создании нового рабочего пространства в Power BI не создается Группа Microsoft 365, создавая группу любыми другими средствами, создает новое (не классическое) рабочее пространство в Power BI.</span><span class="sxs-lookup"><span data-stu-id="31105-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="31105-426">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="31105-427">Отчеты о данных</span><span class="sxs-lookup"><span data-stu-id="31105-427">Data reporting</span></span>

<span data-ttu-id="31105-428">**Может ли Power BI создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="31105-429">Нет, невозможно создать группу Microsoft 365 из нового интерфейса Power BI.</span><span class="sxs-lookup"><span data-stu-id="31105-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="31105-430">**Существует ли новое рабочее пространство Power BI без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="31105-431">Да, в Power BI можно создавать отчеты и рабочей области, которые не связаны с группами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="31105-432">**Может ли быть несколько пространств работы в группе?**</span><span class="sxs-lookup"><span data-stu-id="31105-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="31105-433">Да, [несколько пространств работы, созданных Power BI, можно совместно использовать с одной группой.](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)</span><span class="sxs-lookup"><span data-stu-id="31105-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="31105-434">**Можно ли связывать рабочее пространство с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-435">Нет, рабочее пространство, созданное Power BI, может быть связано только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="31105-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="31105-436">**Может ли связь рабочей области с групповой переменой?**</span><span class="sxs-lookup"><span data-stu-id="31105-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="31105-437">Да и нет.</span><span class="sxs-lookup"><span data-stu-id="31105-437">Yes and no.</span></span> <span data-ttu-id="31105-438">Рабочее пространство, созданное Power BI, может быть связано только с одной группой одновременно, но может изменить связь в любое время.</span><span class="sxs-lookup"><span data-stu-id="31105-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="31105-439">Рабочее пространство, созданное в Power BI группой, постоянно связано с этой группой.</span><span class="sxs-lookup"><span data-stu-id="31105-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="31105-440">**Удаление рабочей области удаляет группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="31105-441">Да, удаление рабочего пространства в Power BI удаляет службы и контент, связанные с группой.</span><span class="sxs-lookup"><span data-stu-id="31105-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="31105-442">Project в Интернете</span><span class="sxs-lookup"><span data-stu-id="31105-442">Project for the web</span></span>

<span data-ttu-id="31105-443">Project for the web предлагает возможность создания планов проектов, диаграмм Gantt и дорожных карт.</span><span class="sxs-lookup"><span data-stu-id="31105-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="31105-444">Ключевые функции, предоставляемые группам.</span><span class="sxs-lookup"><span data-stu-id="31105-444">Key features provided to groups.</span></span>

- <span data-ttu-id="31105-445">Планы проекта</span><span class="sxs-lookup"><span data-stu-id="31105-445">Project plans</span></span>

<span data-ttu-id="31105-446">**Может ли Project для веб-сайта создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="31105-447">Да, можно создать новую группу Microsoft 365 непосредственно из Project для Интернета.</span><span class="sxs-lookup"><span data-stu-id="31105-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="31105-448">**Существуют ли проекты без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="31105-449">Да, проекты могут существовать без связи с группой Microsoft 365, однако для назначения задач требуется объединение групп.</span><span class="sxs-lookup"><span data-stu-id="31105-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="31105-450">**Может ли быть несколько проектов в группе?**</span><span class="sxs-lookup"><span data-stu-id="31105-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="31105-451">Да, можно подключить несколько проектов в одной группе.</span><span class="sxs-lookup"><span data-stu-id="31105-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="31105-452">**Можно ли связывать проект с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-453">Нет, проект можно связывать только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="31105-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="31105-454">**Может ли связь проекта с группой измениться?**</span><span class="sxs-lookup"><span data-stu-id="31105-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="31105-455">Нет, после того как связь с группой установлена, она не может измениться.</span><span class="sxs-lookup"><span data-stu-id="31105-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="31105-456">**Удаляет ли проект группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="31105-457">Нет, удаление проекта в Project для веб-сайта не будет удалять группу.</span><span class="sxs-lookup"><span data-stu-id="31105-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="31105-458">Стратегия</span><span class="sxs-lookup"><span data-stu-id="31105-458">Roadmap</span></span>

<span data-ttu-id="31105-459">Дорожная карта предоставляет возможность создания дорожных карт проектов с помощью Project для веб-сайта и Project Online.</span><span class="sxs-lookup"><span data-stu-id="31105-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="31105-460">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="31105-461">Дорожные карты проекта</span><span class="sxs-lookup"><span data-stu-id="31105-461">Project roadmaps</span></span>

<span data-ttu-id="31105-462">**Может ли roadmap создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="31105-463">Да, можно создать новую группу Microsoft 365 непосредственно из дорожной карты.</span><span class="sxs-lookup"><span data-stu-id="31105-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="31105-464">**Существует ли дорожная карта без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="31105-465">Да, дорожные карты могут существовать без связи с группой Microsoft 365, однако для общего доступа к дорожной карте требуется объединение групп.</span><span class="sxs-lookup"><span data-stu-id="31105-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="31105-466">**Может ли быть несколько дорожных карт для группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="31105-467">Да, можно подключить несколько дорожных карт к одной группе.</span><span class="sxs-lookup"><span data-stu-id="31105-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="31105-468">**Можно ли связывать дорожную карту с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-469">Нет, дорожная карта может быть связана только с одной группой.</span><span class="sxs-lookup"><span data-stu-id="31105-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="31105-470">**Может ли дорожная карта изменить связь с групповой группой?**</span><span class="sxs-lookup"><span data-stu-id="31105-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="31105-471">Нет, после того как связь с группой установлена, она не может измениться.</span><span class="sxs-lookup"><span data-stu-id="31105-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="31105-472">**Удаляет ли дорожная карта удаление группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="31105-473">Нет, удаление дорожной карты не удаляет группу.</span><span class="sxs-lookup"><span data-stu-id="31105-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="31105-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="31105-474">SharePoint</span></span>

<span data-ttu-id="31105-475">SharePoint — это веб-платформа управления контентом, которая предоставляет, помимо прочего, службы хранения для ряда служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="31105-476">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="31105-477">Библиотека документов</span><span class="sxs-lookup"><span data-stu-id="31105-477">Document library</span></span>
- <span data-ttu-id="31105-478">Библиотека для хранения записной книжки OneNote</span><span class="sxs-lookup"><span data-stu-id="31105-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="31105-479">Хранение файлов вики teams</span><span class="sxs-lookup"><span data-stu-id="31105-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="31105-480">**Может ли SharePoint создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="31105-481">Да, создание сайта группы в SharePoint создаст группу Microsoft 365 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="31105-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="31105-482">Также можно создать группу и, необязательно, группу для существующего сайта.</span><span class="sxs-lookup"><span data-stu-id="31105-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="31105-483">**Существуют ли сайты SharePoint без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="31105-484">Да, SharePoint предлагает ряд не связанных с группой служб и сайтов, таких как сайты связи и концентраторы.</span><span class="sxs-lookup"><span data-stu-id="31105-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="31105-485">**Может ли быть несколько сайтов в группе?**</span><span class="sxs-lookup"><span data-stu-id="31105-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="31105-486">Нет, в группе может быть только один сайт.</span><span class="sxs-lookup"><span data-stu-id="31105-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="31105-487">Частные каналы в Teams используют дополнительные сайты, не подключенные к группе.</span><span class="sxs-lookup"><span data-stu-id="31105-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="31105-488">**Можно ли связывать сайты с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-489">Технически нет, но в то время как сайт создается с группой, контент можно совместно использовать с другими группами.</span><span class="sxs-lookup"><span data-stu-id="31105-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="31105-490">**Может ли связь сайта с группой измениться?**</span><span class="sxs-lookup"><span data-stu-id="31105-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="31105-491">Нет, сам сайт связан с группой, однако содержимое можно перемещать с одного сайта на другой в интерфейсе SharePoint, экспортировать контент локально или с помощью сторонних средств.</span><span class="sxs-lookup"><span data-stu-id="31105-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="31105-492">**Удаление сайта удаляет группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="31105-493">Да, удаление сайта в SharePoint удаляет групповые и связанные с группой службы и контент.</span><span class="sxs-lookup"><span data-stu-id="31105-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="31105-494">Stream</span><span class="sxs-lookup"><span data-stu-id="31105-494">Stream</span></span>

<span data-ttu-id="31105-495">Microsoft Stream — это платформа видеохостинга и обмена данными.</span><span class="sxs-lookup"><span data-stu-id="31105-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="31105-496">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="31105-497">Хранение видео</span><span class="sxs-lookup"><span data-stu-id="31105-497">Video storage</span></span>
- <span data-ttu-id="31105-498">Запись собрания команд</span><span class="sxs-lookup"><span data-stu-id="31105-498">Teams meeting recording</span></span>
- <span data-ttu-id="31105-499">Видеоканалы</span><span class="sxs-lookup"><span data-stu-id="31105-499">Video channels</span></span>

<span data-ttu-id="31105-500">**Может ли Stream создать группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="31105-501">Да, можно создать новую группу Microsoft 365 непосредственно из Stream.</span><span class="sxs-lookup"><span data-stu-id="31105-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="31105-502">**Существует ли Stream без группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="31105-503">Да, видеоканалы и видео могут существовать в Stream без связи с группой.</span><span class="sxs-lookup"><span data-stu-id="31105-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="31105-504">**Может ли быть несколько видео и каналов для группы?**</span><span class="sxs-lookup"><span data-stu-id="31105-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="31105-505">Да, в каждой группе может быть несколько видео и каналов.</span><span class="sxs-lookup"><span data-stu-id="31105-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="31105-506">**Можно ли связывать видео или канал с несколькими группами?**</span><span class="sxs-lookup"><span data-stu-id="31105-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="31105-507">Да, в то время как видео или канал создается с группой, его можно совместно использовать с другими группами.</span><span class="sxs-lookup"><span data-stu-id="31105-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="31105-508">**Может ли его связь с группой измениться?**</span><span class="sxs-lookup"><span data-stu-id="31105-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="31105-509">Да и нет; Видео в Stream принадлежат исходному загрузителю или регистратору собраний и поэтому могут быть связаны с любой группой, однако видеоканалы могут быть связаны только с группой, в какой они изначально были созданы.</span><span class="sxs-lookup"><span data-stu-id="31105-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="31105-510">**Удаление видео или каналов удаляет группу?**</span><span class="sxs-lookup"><span data-stu-id="31105-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="31105-511">Нет, удаление видео или каналов не удаляет группу.</span><span class="sxs-lookup"><span data-stu-id="31105-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="31105-512">Однако удаление самой группы в Stream удаляет связанные с группой службы и контент, за исключением фактических видео.</span><span class="sxs-lookup"><span data-stu-id="31105-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="31105-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="31105-513">Yammer</span></span>

<span data-ttu-id="31105-514">Yammer — это корпоративная социальная платформа, призванная содействовать вовлечению сообщества в организации и между ними.</span><span class="sxs-lookup"><span data-stu-id="31105-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="31105-515">Создание сообщества (ранее известного как "группа") в Yammer создает почтовый ящик, но в настоящее время это не используется.</span><span class="sxs-lookup"><span data-stu-id="31105-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="31105-516">Группа Microsoft 365, связанная с Yammer, не может использоваться с командой в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31105-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="31105-517">**Ключевые функции, предоставляемые группам**</span><span class="sxs-lookup"><span data-stu-id="31105-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="31105-518">Область беседы</span><span class="sxs-lookup"><span data-stu-id="31105-518">Conversation area</span></span>

<span data-ttu-id="31105-519">**Может ли Yammer создать группу Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="31105-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="31105-520">Да, создание новой группы в Yammer создаст новую группу Microsoft 365, если платформы подключены и пользователь может создать группу.</span><span class="sxs-lookup"><span data-stu-id="31105-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="31105-521">Группа Yammer с связанной группой Microsoft 365 не может быть создана ни в интерфейсе, ни в службе, кроме самого Yammer.</span><span class="sxs-lookup"><span data-stu-id="31105-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="31105-522">**Существует ли группа Yammer без группы Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="31105-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="31105-523">Да, можно создать группу Yammer без группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="31105-524">Если платформа Yammer не подключена к группам Microsoft 365 или у пользователей нет возможности создать группу Microsoft 365, группы Yammer создаются без объединения групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="31105-525">**Может ли быть несколько групп Yammer в группе Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="31105-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="31105-526">Нет, связь между группой Yammer и группой Microsoft 365 составляет 1:1.</span><span class="sxs-lookup"><span data-stu-id="31105-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="31105-527">**Можно ли связывать группу Yammer с несколькими группами Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="31105-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="31105-528">Нет, группу Yammer можно связывать только с одной группой Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31105-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="31105-529">Это возможно для сообщений, которые будут совместно с другими группами Yammer или перенесены в них.</span><span class="sxs-lookup"><span data-stu-id="31105-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="31105-530">**Может ли связь группы Yammer с группой Microsoft 365 измениться?**</span><span class="sxs-lookup"><span data-stu-id="31105-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="31105-531">Нет, группу Yammer можно связывать только с группой Microsoft 365, с которой она изначально была связана.</span><span class="sxs-lookup"><span data-stu-id="31105-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="31105-532">**Удаляет ли группа Yammer группу Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="31105-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="31105-533">Да, удаление группы в Yammer будет удалять связанные службы и контент Группы Майкрософт и связанные с ними службы.</span><span class="sxs-lookup"><span data-stu-id="31105-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="31105-534">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="31105-534">Related topics</span></span>

[<span data-ttu-id="31105-535">Пошаговая пошаговая работа по планированию управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="31105-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="31105-536">Создание плана управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="31105-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)