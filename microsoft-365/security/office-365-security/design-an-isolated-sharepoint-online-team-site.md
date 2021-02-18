---
title: Разработка изолированного сайта группы SharePoint Online
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Разработка изолированных сайтов групп SharePoint Online, включая определение уровней разрешений, назначение разрешений пользователям с группами доступа и вложенными группами Azure AD.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d53f3b45e3f406dfb0b38bcc910bd34876acb08
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288339"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="a25f1-103">Разработка изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a25f1-103">Design an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a25f1-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="a25f1-104">**Applies to**</span></span>
- [<span data-ttu-id="a25f1-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="a25f1-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a25f1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a25f1-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


 <span data-ttu-id="a25f1-107">**Сводка.** Пошаговое руководство по разработке изолированных сайтов групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a25f1-107">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="a25f1-108">В этой статье описаны основные проектные решения, которые необходимо принять перед созданием изолированного сайта группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a25f1-108">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="a25f1-109">Этап 1. Определение групп SharePoint и уровней разрешений</span><span class="sxs-lookup"><span data-stu-id="a25f1-109">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="a25f1-110">Каждый сайт группы SharePoint Online по умолчанию создается со следующими группами SharePoint:</span><span class="sxs-lookup"><span data-stu-id="a25f1-110">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="a25f1-111">\<site name> Members</span><span class="sxs-lookup"><span data-stu-id="a25f1-111">\<site name> Members</span></span>

- <span data-ttu-id="a25f1-112">\<site name> Посетители</span><span class="sxs-lookup"><span data-stu-id="a25f1-112">\<site name> Visitors</span></span>

- <span data-ttu-id="a25f1-113">\<site name> Владельцы</span><span class="sxs-lookup"><span data-stu-id="a25f1-113">\<site name> Owners</span></span>

<span data-ttu-id="a25f1-114">Эти группы отделены от групп Microsoft 365 и Azure Active Directory (AD) и являются основой для назначения разрешений для ресурсов сайта.</span><span class="sxs-lookup"><span data-stu-id="a25f1-114">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="a25f1-p101">Набор разрешений, определяющий возможности члена группы SharePoint на сайте, — это уровень разрешений. По умолчанию для сайта группы SharePoint Online доступно три уровня разрешений: "Изменение", "Чтение" и "Полный доступ". В приведенной ниже таблице показаны группы SharePoint и назначенные им по умолчанию уровни разрешений.</span><span class="sxs-lookup"><span data-stu-id="a25f1-p101">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level. There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control. The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="a25f1-118">Группа SharePoint</span><span class="sxs-lookup"><span data-stu-id="a25f1-118">SharePoint group</span></span>|<span data-ttu-id="a25f1-119">Уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="a25f1-119">Permission level</span></span>|
|---|---|
|<span data-ttu-id="a25f1-120">\<site name> Members</span><span class="sxs-lookup"><span data-stu-id="a25f1-120">\<site name> Members</span></span>|<span data-ttu-id="a25f1-121">Редактирование</span><span class="sxs-lookup"><span data-stu-id="a25f1-121">Edit</span></span>|
|<span data-ttu-id="a25f1-122">\<site name> Посетители</span><span class="sxs-lookup"><span data-stu-id="a25f1-122">\<site name> Visitors</span></span>|<span data-ttu-id="a25f1-123">Чтение</span><span class="sxs-lookup"><span data-stu-id="a25f1-123">Read</span></span>|
|<span data-ttu-id="a25f1-124">\<site name> Владельцы</span><span class="sxs-lookup"><span data-stu-id="a25f1-124">\<site name> Owners</span></span>|<span data-ttu-id="a25f1-125">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="a25f1-125">Full control</span></span>|
|

 <span data-ttu-id="a25f1-p102">**Рекомендация.** Вы можете создавать дополнительные группы SharePoint и уровни разрешений. Но мы рекомендуем использовать заданные по умолчанию группы SharePoint и уровни разрешений для изолированного сайта SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a25f1-p102">**Best practice:** You can create additional SharePoint groups and permission levels. However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="a25f1-128">Ниже 10 групп и уровней разрешений SharePoint по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a25f1-128">Here are the default SharePoint groups and permission levels.</span></span>

![Группы SharePoint и уровни разрешений по умолчанию для сайта SharePoint Online.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="a25f1-130">Этап 2. Назначение разрешений пользователям с помощью групп доступа</span><span class="sxs-lookup"><span data-stu-id="a25f1-130">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="a25f1-131">Вы можете назначать разрешения пользователям, добавляя их учетную запись пользователя или группу Microsoft 365 или Azure AD, членом которой является учетная запись пользователя, в группы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a25f1-131">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="a25f1-132">После этого учетным записям пользователей прямо или косвенно через членство в группе Microsoft 365 или Azure AD будет назначен уровень разрешений, связанный с группой SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a25f1-132">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="a25f1-133">Предоставление разрешений на примере групп SharePoint по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="a25f1-133">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="a25f1-134">Членам группы **\<site name> "Участники"** SharePoint, которая может включать как учетные записи пользователей, так и группы, назначен уровень разрешений **на** редактирование</span><span class="sxs-lookup"><span data-stu-id="a25f1-134">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="a25f1-135">Членам группы **\<site name> "Посетители** SharePoint", которая может включать как учетные записи пользователей, так и группы, назначен уровень разрешений **"Чтение"**</span><span class="sxs-lookup"><span data-stu-id="a25f1-135">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="a25f1-136">Членам группы **\<site name> Владельцев** SharePoint, которая может включать как учетные записи пользователей, так и группы, назначен уровень разрешений **"Полный доступ"**</span><span class="sxs-lookup"><span data-stu-id="a25f1-136">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="a25f1-p104">**Рекомендация.** Вы можете управлять разрешениями через отдельные учетные записи пользователей, но рекомендуем использовать для этого одну группу Azure AD (т. н. группу доступа). Это позволяет управлять разрешениями через членство в группе доступа, не управляя списком учетных записей для каждой группы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a25f1-p104">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead. This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="a25f1-139">Группы Azure AD для Microsoft 365 отличаются от групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a25f1-139">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="a25f1-140">Группы Azure AD отображаются в Центре администрирования  Microsoft  365 с типом "Безопасность" и не имеют адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a25f1-140">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="a25f1-141">Группами Azure AD можно управлять с помощью указанных ниже средств.</span><span class="sxs-lookup"><span data-stu-id="a25f1-141">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="a25f1-142">доменные службы Active Directory;</span><span class="sxs-lookup"><span data-stu-id="a25f1-142">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="a25f1-143">Это группы, созданные в локальной инфраструктуре AD DS и синхронизированные с подпиской на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a25f1-143">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="a25f1-144">В Центре администрирования Microsoft 365  эти группы имеют состояние синхронизации **с Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="a25f1-144">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="a25f1-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="a25f1-145">Office 365</span></span>

    <span data-ttu-id="a25f1-146">Это группы, созданные с помощью Центра администрирования Microsoft 365, портала Azure или Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a25f1-146">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="a25f1-147">В Центре администрирования Microsoft 365 эти группы имеют статус **облака.** </span><span class="sxs-lookup"><span data-stu-id="a25f1-147">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="a25f1-148">**Практический опыт:** Если вы используете AD DS локально и синхронизируете свою подписку на Microsoft 365, выполните управление пользователями и группой с помощью AD DS.</span><span class="sxs-lookup"><span data-stu-id="a25f1-148">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="a25f1-149">Рекомендуемая структура изолированных сайтов групп SharePoint Online указана ниже.</span><span class="sxs-lookup"><span data-stu-id="a25f1-149">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="a25f1-150">Группа SharePoint</span><span class="sxs-lookup"><span data-stu-id="a25f1-150">SharePoint group</span></span>|<span data-ttu-id="a25f1-151">Группа доступа на основе Azure AD</span><span class="sxs-lookup"><span data-stu-id="a25f1-151">Azure AD-based access group</span></span>|<span data-ttu-id="a25f1-152">Уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="a25f1-152">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="a25f1-153">\<site name> Members</span><span class="sxs-lookup"><span data-stu-id="a25f1-153">\<site name> Members</span></span>|<span data-ttu-id="a25f1-154">\<site name> Members</span><span class="sxs-lookup"><span data-stu-id="a25f1-154">\<site name> Members</span></span>|<span data-ttu-id="a25f1-155">Редактирование</span><span class="sxs-lookup"><span data-stu-id="a25f1-155">Edit</span></span>|
|<span data-ttu-id="a25f1-156">\<site name> Посетители</span><span class="sxs-lookup"><span data-stu-id="a25f1-156">\<site name> Visitors</span></span>|<span data-ttu-id="a25f1-157">\<site name> Viewers</span><span class="sxs-lookup"><span data-stu-id="a25f1-157">\<site name> Viewers</span></span>|<span data-ttu-id="a25f1-158">Чтение</span><span class="sxs-lookup"><span data-stu-id="a25f1-158">Read</span></span>|
|<span data-ttu-id="a25f1-159">\<site name> Владельцы</span><span class="sxs-lookup"><span data-stu-id="a25f1-159">\<site name> Owners</span></span>|<span data-ttu-id="a25f1-160">\<site name> Администраторы</span><span class="sxs-lookup"><span data-stu-id="a25f1-160">\<site name> Admins</span></span>|<span data-ttu-id="a25f1-161">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="a25f1-161">Full control</span></span>|
|

 <span data-ttu-id="a25f1-162">**Практический опыт:** Хотя вы можете использовать группы Microsoft 365 или Azure AD в качестве членов групп SharePoint, мы рекомендуем использовать группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a25f1-162">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="a25f1-163">Группы Azure AD, управляемые через AD DS или Microsoft 365, дают вам больше гибкости для назначения разрешений с помощью вложенных групп.</span><span class="sxs-lookup"><span data-stu-id="a25f1-163">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="a25f1-164">Вот группы SharePoint по умолчанию, настроенные для использования групп доступа на основе Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a25f1-164">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![Использование групп доступа в качестве участников групп сайтов SharePoint Online по умолчанию.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="a25f1-166">При создании трех групп доступа учитывайте следующее:</span><span class="sxs-lookup"><span data-stu-id="a25f1-166">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="a25f1-167">В группе доступа "Администраторы" должно быть всего несколько членов, соответствующее небольшому количеству администраторов SharePoint Online, управляющих сайтом группы. **\<site name>**</span><span class="sxs-lookup"><span data-stu-id="a25f1-167">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="a25f1-168">Большинство участников сайта находятся в группах доступа **\<site name> "Участники"** или **\<site name> "Посетители".**</span><span class="sxs-lookup"><span data-stu-id="a25f1-168">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="a25f1-169">Так как члены группы доступа **\<site name> "Участники"** могут удалять или изменять ресурсы на сайте, внимательно продумайте его членство.</span><span class="sxs-lookup"><span data-stu-id="a25f1-169">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="a25f1-170">Если у вас есть сомнения, добавьте участника сайта в группу **\<site name> доступа "Просмотры".**</span><span class="sxs-lookup"><span data-stu-id="a25f1-170">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="a25f1-171">Вот пример групп SharePoint и групп доступа для изолированного сайта с именем ProjectX.</span><span class="sxs-lookup"><span data-stu-id="a25f1-171">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![Пример использования групп доступа для сайта SharePoint Online с именем ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="a25f1-173">Этап 3. Использование вложенных групп Azure AD</span><span class="sxs-lookup"><span data-stu-id="a25f1-173">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="a25f1-174">Если в проекте немного людей, один уровень групп доступа на основе Azure AD, добавленных в группы SharePoint сайта, подойдет для большинства сценариев.</span><span class="sxs-lookup"><span data-stu-id="a25f1-174">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="a25f1-175">Однако если у вас много людей и они уже являются членами установленных групп Azure AD, то проще назначать разрешения SharePoint с помощью вложенных групп или групп, содержащих другие группы в качестве членов.</span><span class="sxs-lookup"><span data-stu-id="a25f1-175">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="a25f1-p111">Например, вы хотите создать изолированный сайт группы SharePoint Online для совместной работы руководителей отделов продаж, маркетинга, поддержки, а также инженерно-технического и юридического отделов, и у этих отделов уже есть группы руководителей. Вместо того чтобы создавать группу для новых участников сайта и добавлять в нее все учетные записи руководителей, добавьте существующие группы руководителей каждого отдела в новую группу.</span><span class="sxs-lookup"><span data-stu-id="a25f1-p111">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership. Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="a25f1-178">Если вы делите подписку Microsoft 365 между несколькими организациями, один уровень членства в группах для изолированного сайта для организации может оказаться трудноуправляемым из-за большого количества учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="a25f1-178">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="a25f1-179">В этом случае можно использовать вложенные группы Azure AD для каждой организации, которые содержат группы в своей организации для управления разрешениями.</span><span class="sxs-lookup"><span data-stu-id="a25f1-179">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="a25f1-180">Чтобы использовать вложенные группы Azure AD:</span><span class="sxs-lookup"><span data-stu-id="a25f1-180">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="a25f1-181">Определите или создайте группы Azure AD, которые будут содержать учетные записи пользователей, и добавьте соответствующие учетные записи пользователей в качестве членов.</span><span class="sxs-lookup"><span data-stu-id="a25f1-181">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="a25f1-182">Создайте общую группу доступа на основе Azure AD, которая будет содержать другие группы Azure AD, и добавьте эти группы в качестве членов.</span><span class="sxs-lookup"><span data-stu-id="a25f1-182">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="a25f1-183"> Чтобы предоставить общей группе доступа нужный уровень доступа, укажите группу SharePoint и соответствующий уровень разрешений.</span><span class="sxs-lookup"><span data-stu-id="a25f1-183">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="a25f1-184">Вы не можете использовать вложенные группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a25f1-184">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="a25f1-185">Вот пример вложенных групп Azure AD для группы доступа членов ProjectX.</span><span class="sxs-lookup"><span data-stu-id="a25f1-185">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![Пример использования вложенных групп доступа для группы доступа участников сайта ProjectX.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="a25f1-187">Так как все учетные записи пользователей в группах "Исследования", "Инженер" и "Проект" предназначены для участников сайта, их группы Azure AD проще добавить в группу доступа "Участники ProjectX".</span><span class="sxs-lookup"><span data-stu-id="a25f1-187">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="a25f1-188">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="a25f1-188">Next step</span></span>

<span data-ttu-id="a25f1-189">Сведения о создании и настройке изолированного сайта в рабочей среде см. в статье [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="a25f1-189">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a25f1-190">См. также</span><span class="sxs-lookup"><span data-stu-id="a25f1-190">See Also</span></span>

[<span data-ttu-id="a25f1-191">Изолированные сайты групп SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a25f1-191">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="a25f1-192">Управление изолированным сайтом группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a25f1-192">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="a25f1-193">Развертывание изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a25f1-193">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
