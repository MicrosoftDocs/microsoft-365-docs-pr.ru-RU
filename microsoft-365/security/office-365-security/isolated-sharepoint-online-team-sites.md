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
ms.openlocfilehash: 0646ffc37256702844b550fd1beb841944b2d509
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819537"
---
# <a name="isolated-sharepoint-online-team-sites"></a>Изолированные сайты групп SharePoint Online

 **Сводка.** Сведения о том, как использовать изолированные сайты групп SharePoint Online.
  
SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.
  
However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators. We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site. You might need an isolated site for the following:
  
- размещения секретного проекта внутри организации;
    
- хранения конфиденциальной информации или ценной интеллектуальной собственности организации;
    
- размещения ресурсов, связанных с судебными исками, в которых организация может выступать как в роли истца, так и ответчика;
    
- совместного использования подписки Microsoft 365 несколькими связанными между собой организациями, которые являются отдельными бизнес-структурами.
    
Требования к изолированным сайтам:
  
- Управлять сайтом могут только администраторы SharePoint Online, которые предоставляют членство в группе для доступа к сайту и настраивают пользовательские разрешения.
    
- Участники сайта не могут приглашать других членов на сайт группы.
    
- Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.
    
The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.
  
Доступны также другие функции изолированного сайта, например:
  
- управление правами на доступ к данным, благодаря чему ресурсы на сайте остаются зашифрованными даже при скачивании в локальное расположение и последующем добавлении на другой сайт, доступ к которому есть у всех сотрудников организации;
    
- защита от потери данных, предотвращающая отправку ресурсов сайта, например файлов, в электронных сообщениях.
    
## <a name="next-steps"></a>Дальнейшие действия

Пошаговые инструкции из статьи [Изолированный сайт группы SharePoint Online в среде разработки и тестирования Office 365](isolated-sharepoint-online-team-site-dev-test-environment.md) помогут разобраться с пробной подпиской на изолированный сайт группы SharePoint Online.
  
Когда вы будете готовы выполнить развертывание изолированного сайта группы SharePoint Online в рабочей среде, просмотрите подробные инструкции из статьи [Разработка изолированного сайта группы SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).
  
## <a name="related-topics"></a>Связанные статьи

[Разработка изолированного сайта группы SharePoint Online](design-an-isolated-sharepoint-online-team-site.md)
  
[Управление изолированным сайтом группы SharePoint Online](manage-an-isolated-sharepoint-online-team-site.md)

[Развертывание изолированного сайта группы SharePoint Online](deploy-an-isolated-sharepoint-online-team-site.md)


