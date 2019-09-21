---
title: Изолированные сайты групп SharePoint Online
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
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Сводка. Сведения о том, как использовать изолированные сайты групп SharePoint Online.
ms.openlocfilehash: 07f4d84493cdc7c0e153186164824fe8aa1e36bc
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090015"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="21adc-103">Изолированные сайты групп SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="21adc-103">Isolated SharePoint Online team sites</span></span>

 <span data-ttu-id="21adc-104">**Сводка.** Сведения о том, как использовать изолированные сайты групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="21adc-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="21adc-p101">Сайты групп SharePoint Online позволяют быстро создать пространство для совместной работы над заметками, статьями и документами. Кроме того, вы получаете доступ к календарю и другим ресурсам Microsoft Office 365. В основе сайтов групп SharePoint Online лежит группа Office 365 и упрощенная модель администрирования, позволяющая организовать совместную работу как отдельных членов группы, так и всех сотрудников организации. Сайт группы SharePoint Online, используемый по умолчанию, позволяет членам группы Office 365 приглашать других пользователей и настраивать разрешения.</span><span class="sxs-lookup"><span data-stu-id="21adc-p101">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on an Office 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Office 365 group to invite other users and control permissions settings.</span></span>
  
<span data-ttu-id="21adc-p102">Но в некоторых случаях необходимо создать такой сайт группы SharePoint Online для совместной работы, над разрешениями для которого ведется более строгий контроль. Он возможен благодаря настройке членства в группе и уровней разрешений в SharePoint Online, которыми управляют только администраторы SharePoint. Такой сайт называется изолированным. Доступ к нему получает ограниченный круг пользователей, которые могут совместно работать над документами, просматривать содержимое сайта или выполнять роль администраторов. Изолированный сайт предназначен для:</span><span class="sxs-lookup"><span data-stu-id="21adc-p102">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators. We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site. You might need an isolated site for the following:</span></span>
  
- <span data-ttu-id="21adc-111">размещения секретного проекта внутри организации;</span><span class="sxs-lookup"><span data-stu-id="21adc-111">A secret project within your organization.</span></span>
    
- <span data-ttu-id="21adc-112">хранения конфиденциальной информации или ценной интеллектуальной собственности организации;</span><span class="sxs-lookup"><span data-stu-id="21adc-112">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>
    
- <span data-ttu-id="21adc-113">размещения ресурсов, связанных с судебными исками, в которых организация может выступать как в роли истца, так и ответчика;</span><span class="sxs-lookup"><span data-stu-id="21adc-113">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>
    
- <span data-ttu-id="21adc-114">совместного использования подписки Office 365 несколькими связанными между собой организациями, которые являются отдельными бизнес-сущностями.</span><span class="sxs-lookup"><span data-stu-id="21adc-114">To share an Office 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>
    
<span data-ttu-id="21adc-115">Требования к изолированным сайтам:</span><span class="sxs-lookup"><span data-stu-id="21adc-115">Here are the requirements of an isolated site:</span></span>
  
- <span data-ttu-id="21adc-116">Управлять сайтом могут только администраторы SharePoint Online, которые предоставляют членство в группе для доступа к сайту и настраивают пользовательские разрешения.</span><span class="sxs-lookup"><span data-stu-id="21adc-116">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>
    
- <span data-ttu-id="21adc-117">Участники сайта не могут приглашать других членов на сайт группы.</span><span class="sxs-lookup"><span data-stu-id="21adc-117">Members of the site cannot invite other members to the team site.</span></span>
    
- <span data-ttu-id="21adc-p103">Пользователи, не являющиеся участниками изолированного сайта, не могут запрашивать доступ к сайту. При попытке доступа к любому URL-адресу, связанному с этим сайтом, отображается веб-страница "Отказано в доступе".</span><span class="sxs-lookup"><span data-stu-id="21adc-p103">Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>
    
<span data-ttu-id="21adc-p104">Обязательное централизованное управление доступом и назначение пользовательских разрешений администраторами SharePoint Online приводит к тому, что сайт остается изолированным все время. Например, существующие члены группы не могут ни намеренно, ни случайно пригласить других пользователей, имеющих подписку Office 365, но не являющихся участниками сайта, или настроить для них пользовательские разрешения.</span><span class="sxs-lookup"><span data-stu-id="21adc-p104">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Office 365 subscription who should not be members of the site.</span></span>
  
<span data-ttu-id="21adc-122">Доступны также другие функции изолированного сайта, например:</span><span class="sxs-lookup"><span data-stu-id="21adc-122">An isolated site can be used with other features, such as:</span></span>
  
- <span data-ttu-id="21adc-123">управление правами на доступ к данным, благодаря чему ресурсы на сайте остаются зашифрованными даже при скачивании в локальное расположение и последующем добавлении на другой сайт, доступ к которому есть у всех сотрудников организации;</span><span class="sxs-lookup"><span data-stu-id="21adc-123">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>
    
- <span data-ttu-id="21adc-124">защита от потери данных, предотвращающая отправку ресурсов сайта, например файлов, в электронных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="21adc-124">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="21adc-125">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="21adc-125">Next steps</span></span>

<span data-ttu-id="21adc-126">Пошаговые инструкции из статьи [Изолированный сайт группы SharePoint Online в среде разработки и тестирования Office 365](isolated-sharepoint-online-team-site-dev-test-environment.md) помогут разобраться с пробной подпиской на изолированный сайт группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="21adc-126">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>
  
<span data-ttu-id="21adc-127">Когда вы будете готовы выполнить развертывание изолированного сайта группы SharePoint Online в рабочей среде, просмотрите подробные инструкции из статьи [Разработка изолированного сайта группы SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="21adc-127">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="21adc-128">См. также</span><span class="sxs-lookup"><span data-stu-id="21adc-128">See Also</span></span>

[<span data-ttu-id="21adc-129">Разработка изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="21adc-129">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="21adc-130">Управление изолированным сайтом группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="21adc-130">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="21adc-131">Развертывание изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="21adc-131">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)


