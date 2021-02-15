---
title: Управление доступом в группах Microsoft 365, Teams и SharePoint
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
description: Узнайте об управлении доступом в группах Microsoft 365, Teams и SharePoint.
ms.openlocfilehash: fb1bec219ef0d27c2a908f5f385185a1a70e01e1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613470"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Управление доступом в группах Microsoft 365, Teams и SharePoint

Существует множество элементов управления, позволяющих управлять доступом пользователей к ресурсам в группах, командах и SharePoint. Просмотрите эти параметры и продумайте, как они соедиряду с вашими бизнес-потребностями, конфиденциальность ваших данных и область пользователей, с которых должны работать ваши пользователи.

В следующей таблице приводится краткий справочник по средствам управления доступом, доступным в Microsoft 365. Дополнительные сведения предоставляются в следующих разделах.

|Категория|Описание|Справка|
|:-------|:----------|:--------|
|Участие|||
||Обнаружение закрытых команд|[Управление обнаружением закрытых команд в Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||Динамическое членство в группах на основе правил|[Создание или обновление динамической группы в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||Управление тем, кто может делиться файлами, папками и сайтами.|[Настройка запросов на доступ и управление ими](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|условный доступ;|||
||Многофакторная проверка подлинности|[Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||Управление доступом устройств на основе конфиденциальности группы, группы или сайта.|[Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Ограничение доступа к сайту для неугодных устройств.|[Управление доступом к SharePoint с неугодных устройств](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||Управление доступом к сайту на основе расположения|[Управление доступом к данным SharePoint и OneDrive с учетом расположения в сети](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|Гостевой доступ|||
||Разрешить или заблокировать общий доступ к SharePoint из указанных доменов.|[Ограничение общего доступа к контенту SharePoint и OneDrive по домену](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||Разрешить или заблокировать членство в группах или группах из указанных доменов.|[Разрешение или блокировка приглашений пользователям B2B из определенных организаций](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||Запретить анонимный общий доступ.|[Отключение ссылок типа "Любой пользователь"](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||Управление разрешениями для ссылок анонимного доступа.|[Настройка разрешений ссылок для ссылок "Любой"](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||Управление истечением срока действия ссылок анонимного общего доступа.|[Установка срока действия для ссылок типа "Любой пользователь"](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||Управление типом ссылки для общего доступа, которая отображается для пользователей по умолчанию.|[Изменение типа ссылки по умолчанию для сайта](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||Ограничить внешний общий доступ определенными людьми.|[Ограничение внешнего общего доступа указанными группами безопасности](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Управление гостевим доступом к группе, команде или сайту на основе конфиденциальности информации.|[Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Отключите параметры общего доступа.|[Ограничение общего доступа в Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|Управление пользователями|||
||Регулярно проверяют членство в группах и группах.|[Что такое проверки доступа Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||Автоматизация управления доступом к группам и командам.|[Что такое управление правами Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Разрешить или заблокировать для людей создание частных каналов в Teams.|[Управление жизненным циклом частных каналов в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Участие

Членство в командах и группах контролируется владельцами. Участники могут приглашать других, но приглашения отправляются владельцам для утверждения. Хотя общедоступные команды и группы могут быть обнаружены любыми в организации, вы можете контролировать, могут ли частные команды и группы быть обнаруживаемыми:

- [Управление обнаружением закрытых команд в Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

Членством в группе или команде можно управлять динамически на основе некоторых критериев, например отдела. В этом случае участники и владельцы не могут приглашать людей в команду.

- [Создание или обновление динамической группы в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

Сайты SharePoint предоставляют возможность добавлять владельцев, участников и посетителей отдельно от членства в группах или командах. В зависимости от ваших требований может потребоваться ограничить, кто может приглашать людей на сайт. Кроме того, в зависимости от конфиденциальности сведений на заданных веб-сайте может потребоваться ограничить доступ к файлам и папок. Эти ограничения настраиваются командой, группой или владельцем сайта:

- [Настройка запросов на доступ и управление ими](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>условный доступ;

С помощью Microsoft 365 вы можете требовать многофакторную проверку подлинности как для людей внутри, так и за пределами организации. При запросе второго фактора проверки подлинности существует множество вариантов. Настоятельно рекомендуется развертывать многофакторную проверку подлинности в организации:

- [Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

Если в некоторых группах и командах есть конфиденциальную информацию, вы можете применить политики управления устройствами на основе метки конфиденциальности группы или команды. Вы можете полностью заблокировать доступ с неугодных устройств или разрешить ограниченный доступ только через Интернет:

- [Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

В SharePoint можно ограничить доступ к сайтам из указанных сетевых местоположений.

- [Управление доступом к данным SharePoint и OneDrive с учетом расположения в сети](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


Дополнительные ресурсы:

- [Планирование развертывания условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Обзор Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [Управление доступом к SharePoint с неугодных устройств](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Гостевой доступ

Вы можете ограничить гостей в зависимости от домена их адреса электронной почты. SharePoint предлагает параметры ограничения домена для всей организации и сайта. Группы и Teams используют списки допустимой и не разрешаемой службы доменов в Azure AD. Не забудьте настроить оба параметра, чтобы избежать нежелательного общего доступа и обеспечить согласованное использование пользователями:

- [Ограничение общего доступа к контенту SharePoint и OneDrive по домену](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [Разрешение или блокировка приглашений пользователям B2B из определенных организаций](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 разрешает анонимный общий доступ к файлам и папок с помощью *ссылок "Любой* доступ". *Ссылки* могут переадад кому угодно, а любой, у кого есть ссылка, может получить доступ к общему элементу. В зависимости от конфиденциальности данных рассмотрите  возможность управления использованием ссылок "Любой человек", включая их отключение полностью, ограничение разрешений ссылок только для чтения или установка для них срока действия:

- [Отключение ссылок типа "Любой пользователь"](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [Настройка разрешений ссылок для ссылок "Любой"](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [Установка срока действия для ссылок типа "Любой пользователь"](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

При совместном использовании файлов и папок пользователям необходимо выбрать несколько типов ссылок. Чтобы снизить риск случайного несоответствующего общего доступа, можно изменить тип ссылки по умолчанию, представляемый пользователям при совместном использовании. Например, изменение ссылок  по умолчанию на ссылки  "Любой" (с разрешением анонимного доступа) на ссылки "Люди в организации" может снизить риск нежелательного внешнего общего доступа к конфиденциальной информации:

- [Изменение типа ссылки по умолчанию для сайта](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

Если в вашей организации есть конфиденциальные данные, которые необходимо делиться с гостями, но вас беспокоит недопустимое совместное использование, можно ограничить внешний общий доступ к файлам и папок членам указанных групп безопасности. Таким образом, можно ограничить внешний доступ определенной группой пользователей или потребовать от пользователей обучения по соответствующему внешнему совместному доступу перед их добавлением в группу безопасности:

- [Ограничение внешнего общего доступа указанными группами безопасности](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Группы и Teams имеют параметры на уровне организации, которые позволяют разрешить или запретить гостевой доступ. Хотя вы можете ограничить гостевой доступ определенным командам или группам с помощью [Microsoft PowerShell,](per-group-guest-access.md)мы рекомендуем сделать это с помощью метки конфиденциальности. С помощью меток конфиденциальности вы можете автоматически разрешить или запретить гостевой доступ на основе метки:

- [Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Microsoft 365 предлагает множество различных методов общего доступа к информации. Если у вас есть конфиденциальную информацию и вы хотите ограничить ее общий доступ, просмотрите варианты ограничения общего доступа:

- [Ограничение общего доступа в Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

Дополнительные ресурсы:

- [Настройка безопасной совместной работы с помощью Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [Ограничьте случайное воздействие файлов при обмене с людьми за пределами вашей организации](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [Создание безопасной среды гостевого общего доступа](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [Включить внешнюю совместную работу B2B и управлять тем, кто может приглашать гостей](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Управление пользователями

По мере развития групп и команд в организации лучше регулярно пересматривать членство в командах и группах. Это может быть особенно полезно для команд и групп с меняющимся членством, тех, которые содержат конфиденциальную информацию, или для групп, включающих гостей. Рассмотрите возможность настройки проверки доступа для этих команд и групп:

- [Что такое проверки доступа Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Многие организации имеют деловые отношения с другими организациями или ключевыми поставщиками, с которыми они тесно сотрудничают. В этих сценариях управление пользователями и доступ к ресурсам может быть сложной задачей. Рассмотрите возможность автоматизации некоторых задач управления пользователями и даже их преобразования в партнерской организации.

- [Что такое управление правами Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

Частные каналы в Teams позволяют обмениваться файлами и беседами в области между подмножеством участников команды. В зависимости от конкретных бизнес-потребностей вы можете разрешить или заблокировать эту возможность.

- [Частные каналы в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Управление жизненным циклом частных каналов в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

Дополнительные ресурсы:

- [Управление удостоверением Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>Связанные статьи

[Пошаговая пошаговая работа по планированию управления совместной работой](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Создание плана управления совместной работой](collaboration-governance-first.md)

[Безопасность и соответствие в Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Управление настройками общего доступа в SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Создание внешней сети в Yammer и управление ею](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[Настройка Teams с тремя уровнями защиты](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
