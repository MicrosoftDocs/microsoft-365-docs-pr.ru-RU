---
title: Изолированные сайты групп SharePoint Online
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Узнайте об изолированных сайтах групп SharePoint Online, в том числе об использовании, требованиях и функциях, которые они поддерживают.
ms.openlocfilehash: 55bdf2999610310babb60b6938afb97732e5a7a0
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845095"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="896d5-103">Изолированные сайты групп SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="896d5-103">Isolated SharePoint Online team sites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="896d5-104">**Сводка.** Сведения о том, как использовать изолированные сайты групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="896d5-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="896d5-p101">Сайты групп SharePoint Online позволяют быстро создать пространство для совместной работы пользователей над заметками, статьями и документами. Кроме того, вы получаете доступ к календарю и другим ресурсам Microsoft Office 365. В основе сайтов групп SharePoint Online лежит группа Microsoft 365 и упрощенная модель администрирования, позволяющая организовать совместную работу как отдельных участников группы, так и всех сотрудников организации. Сайт группы SharePoint Online, используемый по умолчанию, позволяет участникам группы Microsoft 365 приглашать других пользователей и настраивать разрешения.</span><span class="sxs-lookup"><span data-stu-id="896d5-p101">SharePoint Online team sites are an easy way to quickly create a space for collaboration. Users can work together on notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>

<span data-ttu-id="896d5-109">Однако иногда требуется управлять доступом к сайту с помощью участия в группах, а уровнем разрешений SharePoint Online — с помощью администраторов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="896d5-109">However, you'll sometimes need site access to be controlled by group memberships, and SharePoint Online permission levels managed by SharePoint administrators.</span></span> <span data-ttu-id="896d5-110">Такой сайт называется изолированным. Доступ к нему получает ограниченный круг пользователей, которые могут совместно работать над документами, просматривать содержимое сайта или выполнять роль администраторов.</span><span class="sxs-lookup"><span data-stu-id="896d5-110">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="896d5-111">Изолированный сайт предназначен для:</span><span class="sxs-lookup"><span data-stu-id="896d5-111">You might need an isolated site for the following:</span></span>

- <span data-ttu-id="896d5-112">размещения секретного проекта внутри организации;</span><span class="sxs-lookup"><span data-stu-id="896d5-112">A secret project within your organization.</span></span>

- <span data-ttu-id="896d5-113">хранения конфиденциальной информации или ценной интеллектуальной собственности организации;</span><span class="sxs-lookup"><span data-stu-id="896d5-113">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>

- <span data-ttu-id="896d5-114">размещения ресурсов, связанных с судебными исками, в которых организация может выступать как в роли истца, так и ответчика;</span><span class="sxs-lookup"><span data-stu-id="896d5-114">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>

- <span data-ttu-id="896d5-115">совместного использования подписки Microsoft 365 несколькими связанными между собой организациями, которые являются отдельными бизнес-структурами.</span><span class="sxs-lookup"><span data-stu-id="896d5-115">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>

<span data-ttu-id="896d5-116">Требования к изолированным сайтам:</span><span class="sxs-lookup"><span data-stu-id="896d5-116">Here are the requirements of an isolated site:</span></span>

- <span data-ttu-id="896d5-117">Управлять сайтом могут только администраторы SharePoint Online, которые предоставляют членство в группе для доступа к сайту и настраивают пользовательские разрешения.</span><span class="sxs-lookup"><span data-stu-id="896d5-117">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>

- <span data-ttu-id="896d5-118">Участники сайта не могут приглашать других членов на сайт группы.</span><span class="sxs-lookup"><span data-stu-id="896d5-118">Members of the site cannot invite other members to the team site.</span></span>

- <span data-ttu-id="896d5-p103">Пользователи, не являющиеся участниками изолированного сайта, не могут запрашивать доступ к сайту. При попытке доступа к любому URL-адресу, связанному с этим сайтом, отображается веб-страница "Отказано в доступе".</span><span class="sxs-lookup"><span data-stu-id="896d5-p103">Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>

<span data-ttu-id="896d5-p104">Обязательное централизованное управление доступом и назначение пользовательских разрешений администраторами SharePoint Online приводит к тому, что сайт остается изолированным все время. Например, существующие участники группы не могут ни намеренно, ни случайно пригласить других пользователей, имеющих подписку Microsoft 365, но не являющихся участниками сайта, или настроить для них пользовательские разрешения.</span><span class="sxs-lookup"><span data-stu-id="896d5-p104">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>

<span data-ttu-id="896d5-123">Доступны также другие функции изолированного сайта, например:</span><span class="sxs-lookup"><span data-stu-id="896d5-123">An isolated site can be used with other features, such as:</span></span>

- <span data-ttu-id="896d5-124">управление правами на доступ к данным, благодаря чему ресурсы на сайте остаются зашифрованными даже при скачивании в локальное расположение и последующем добавлении на другой сайт, доступ к которому есть у всех сотрудников организации;</span><span class="sxs-lookup"><span data-stu-id="896d5-124">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>

- <span data-ttu-id="896d5-125">защита от потери данных, предотвращающая отправку ресурсов сайта, например файлов, в электронных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="896d5-125">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>

## <a name="next-steps"></a><span data-ttu-id="896d5-126">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="896d5-126">Next steps</span></span>

<span data-ttu-id="896d5-127">Пошаговые инструкции из статьи [Изолированный сайт группы SharePoint Online в среде разработки и тестирования Office 365](isolated-sharepoint-online-team-site-dev-test-environment.md) помогут разобраться с пробной подпиской на изолированный сайт группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="896d5-127">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>

<span data-ttu-id="896d5-128">Когда вы будете готовы выполнить развертывание изолированного сайта группы SharePoint Online в рабочей среде, просмотрите подробные инструкции из статьи [Разработка изолированного сайта группы SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="896d5-128">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="896d5-129">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="896d5-129">Related topics</span></span>

[<span data-ttu-id="896d5-130">Разработка изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="896d5-130">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="896d5-131">Управление изолированным сайтом группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="896d5-131">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="896d5-132">Развертывание изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="896d5-132">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
