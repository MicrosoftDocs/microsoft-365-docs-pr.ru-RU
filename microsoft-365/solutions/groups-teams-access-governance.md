---
title: Управляющий доступ в группах Microsoft 365, Teams и SharePoint
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
description: Сведения об управляющем доступе в группах Microsoft 365, Teams и SharePoint.
ms.openlocfilehash: 2a3a5a126a340a8ec1036eaebd22a0a0a81cf6c3
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558226"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Управляющий доступ в группах Microsoft 365, Teams и SharePoint

Существует множество элементов управления, позволяющих управлять доступом пользователей к ресурсам в группах, в Teams и SharePoint. Изучите эти параметры и определите, как они соответствуют потребностям вашей компании, чувствительность данных и область сотрудников, с которыми ваши пользователи должны работать совместно.

В следующей таблице приведены краткие справочные сведения об элементах управления доступом, доступных в Microsoft 365. Дополнительные сведения приведены в следующих разделах.

|Категория|Описание|Справка|
|:-------|:----------|:--------|
|Участие|||
||Обнаружение частных Teams|[Управление обнаружением частных Teams в Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||Членство в динамической группе на основе правил|[Создание или обновление динамической группы в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||Контролировать, кто может предоставлять общий доступ к файлам, папкам и сайтам.|[Настройка запросов на доступ и управление ими](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|условный доступ;|||
||Многофакторная проверка подлинности|[Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||Управление доступом к устройствам на основе группы, группы или чувствительности к сайту.|[Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Ограничьте доступ к сайту для неуправляемых устройств.|[Управление доступом SharePoint с неуправляемых устройств](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||Управление доступом к сайту на основе расположения|[Управление доступом к данным SharePoint и OneDrive с учетом расположения в сети](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|Гостевой доступ|||
||Разрешает или запрещает общий доступ к SharePoint из указанных доменов.|[Ограничение общего доступа к контенту SharePoint и OneDrive по доменам](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||Разрешение или блокировка членства в группах для указанных доменов.|[Разрешение или блокировка приглашений для пользователей B2B из определенных организаций](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||Запретить анонимный общий доступ.|[Отключение ссылок типа "Любой пользователь"](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||Управление разрешениями для ссылок анонимного доступа.|[Настройка разрешений ссылок для всех ссылок](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||Контроль истечения срока действия ссылок анонимного общего доступа.|[Установка срока действия для ссылок типа "Любой пользователь"](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||Управлять типом ссылки совместного доступа, которая отображается для пользователей по умолчанию.|[Изменение типа ссылки по умолчанию для сайта](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||Ограничьте внешний общий доступ для определенных пользователей.|[Ограничьте внешний общий доступ к определенным группам безопасности](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Управление гостевым доступом к группе, группе или сайту на основе чувствительности к информации.|[Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Отключите параметры общего доступа.|[Ограничение общего доступа в Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|Управление пользователями|||
||Регулярно просматривайте членство в группе и группе.|[Что такое обзоры Access Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||Автоматизация управления доступом к группам и командам.|[Что такое управление обслуживанием Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Разрешить или запретить пользователям создавать частные каналы в Teams.|[Управление жизненным циклом частных каналов в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Участие

Членство в группах и группах контролируется владельцами. Участники могут приглашать других пользователей, но приглашения отправляются владельцам для утверждения. Общедоступные команды и группы могут быть обнаруживаемыми для всех пользователей в Организации, но вы можете управлять возможностью обнаружения и закрытых команд и групп:

- [Управление обнаружением частных Teams в Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

Можно динамически управлять членством группы или команды в соответствии с определенными критериями, такими как отдел. В этом случае участники и владельцы не могут приглашать участников в команду.

- [Создание или обновление динамической группы в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

Сайты SharePoint предоставляют возможность добавлять владельцев, участников и посетителей отдельно от группы или из состава группы. В зависимости от ваших требований может потребоваться ограничить круг лиц, которые могут приглашать людей на сайте. Кроме того, в зависимости от чувствительности сведений на определенном сайте может потребоваться запретить пользователям предоставлять общий доступ к файлам и папкам. Эти ограничения настраиваются для группы, группы или владельца сайта.

- [Настройка запросов на доступ и управление ими](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>условный доступ;

С помощью Microsoft 365 вы можете требовать многофакторную проверку подлинности как для сотрудников внутри организации, так и за ее пределами. В случаях, когда пользователям предлагается второй фактор проверки подлинности, существует множество вариантов. Настоятельно рекомендуется развернуть многофакторную проверку подлинности для вашей организации:

- [Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

Если у вас есть конфиденциальные сведения в некоторых группах и Teams, вы можете применять политики управления устройствами на основе метки конфиденциальности группы или группы. Вы можете заблокировать доступ полностью из неуправляемых устройств или только с ограниченным доступом через Интернет:

- [Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

В SharePoint можно ограничить доступ к сайтам из определенных сетевых расположений.

- [Управление доступом к данным SharePoint и OneDrive с учетом расположения в сети](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


Дополнительные ресурсы:

- [Планирование развертывания условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Общие сведения о Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [Управление доступом SharePoint с неуправляемых устройств](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Гостевой доступ

Вы можете ограничить список гостей на основе домена своего адреса электронной почты. SharePoint предлагает параметры ограничений для домена в масштабах Организации и для определенных сайтов. Группы и Teams используют списки разрешенных и запрещенных доменов в Azure AD. Обязательно настройте оба параметра, чтобы избежать нежелательного общего доступа и обеспечить единообразие взаимодействия с пользователем.

- [Ограничение общего доступа к контенту SharePoint и OneDrive по доменам](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [Разрешение или блокировка приглашений для пользователей B2B из определенных организаций](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 обеспечивает анонимный общий доступ к файлам и папкам *, используя ссылки* для общего доступа. *Все* ссылки могут быть переадресованы, а любой пользователь, у которого есть ссылка, может получить доступ к общему элементу. В зависимости от того, какова чувствительность данных, рекомендуется управлять тем, как будут использоваться *все* ссылки, в том числе полностью отключать разрешения ссылок на доступ только для чтения, а также задавать срок действия для них:

- [Отключение ссылок типа "Любой пользователь"](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [Настройка разрешений ссылок для всех ссылок](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [Установка срока действия для ссылок типа "Любой пользователь"](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

При совместном использовании файлов и папок у пользователей есть несколько типов ссылок, из которых можно выбрать один. Чтобы снизить риск случайного использования общего доступа, вы можете изменить тип ссылки по умолчанию, который будет предоставляться пользователям. Например, изменение параметров по умолчанию для *всех* ссылок, которые позволяют анонимному доступу к *пользователям в* ссылках Организации, снизить риск нежелательного внешнего общего доступа к конфиденциальным сведениям:

- [Изменение типа ссылки по умолчанию для сайта](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

Если в Организации есть конфиденциальные данные, которые необходимо предоставить гостям, но вы беспокоитесь о неприемлемом совместном доступе, вы можете ограничить внешний общий доступ к файлам и папкам членам указанных групп безопасности. Таким образом вы можете ограничить общий доступ к определенной группе людей или потребовать от пользователей пройти обучение по соответствующему внешнему общему доступу перед добавлением в группу безопасности:

- [Ограничьте внешний общий доступ к определенным группам безопасности](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Группы и Teams имеют настройки уровня Организации, которые разрешают или запрещают гостевой доступ. Вы можете [ограничить гостевой доступ к определенным командам или группам с помощью Microsoft PowerShell](per-group-guest-access.md), поэтому мы рекомендуем сделать это с помощью метки конфиденциальности. С помощью меток конфиденциальности вы можете автоматически разрешать или запрещать гостевой доступ на основе примененной Метки:

- [Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Microsoft 365 предлагает множество различных способов обмена информацией. Если у вас есть конфиденциальные сведения и вы хотите ограничить общий доступ, ознакомьтесь с разрешениями для ограничения общего доступа:

- [Ограничение общего доступа в Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

Дополнительные ресурсы:

- [Настройка безопасной совместной работы с помощью Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [Ограничьте случайное воздействие файлов при обмене с людьми за пределами вашей организации](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [Создание безопасной среды гостевого общего доступа](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [Включение внешней совместной работы B2B и управление пользователями, которые могут приглашать гостей](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Управление пользователями

По мере развития групп и команд в организации рекомендуется проанализировать членство в группе и группе на регулярной основе. Это может быть особенно полезно для групп и групп с изменяемым членством, которые содержат конфиденциальные сведения, или те, которые включают гостей. Рассмотрите настройку проверок доступа для этих команд и групп:

- [Что такое обзоры Access Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Многие организации имеют деловые отношения с другими организациями или ключевыми поставщиками, с которыми они работают. Управление пользователями и доступ к ресурсам в таких сценариях может быть непростой задачей. Рекомендуется автоматизировать некоторые задачи управления пользователями и даже перенести их в партнерскую организацию.

- [Что такое управление обслуживанием Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

Частные каналы в Teams позволяют использовать ограниченные беседы и общий доступ к файлам между подмножествами участников группы. В зависимости от конкретных потребностей бизнеса вы можете разрешить или заблокировать эту возможность.

- [Частные каналы в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Управление жизненным циклом частных каналов в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

Дополнительные ресурсы:

- [Управление удостоверениями Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>Статьи по теме

[Безопасность и соответствие в Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Управление параметрами общего доступа в SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Создание внешней сети в Yammer и управление ею](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[Настройте Teams с тремя уровнями защиты](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
