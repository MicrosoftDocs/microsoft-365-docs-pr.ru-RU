---
title: Управление приложениями в Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Реализация возможностей управления приложениями (Майкрософт).
ms.openlocfilehash: 63bd6684bc041c3c82ba6b8ddcc28c2600182b26
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430700"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a>Надстройка управления приложениями в Microsoft Cloud App Security (в предварительной версии)

>*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*

Кибератаки становятся все более изощренными в использовании приложений, развернутых в локальной и облачной инфраструктуре, и создают отправную точку для повышения привилегий, горизонтального перемещения и кражи ваших данных. Чтобы осознать потенциальные риски и остановить атаки такого типа, необходимо получить четкое представление о позиции вашей организации в отношении соответствия приложений требованиям, чтобы быстро выявлять аномальное поведение приложений и соответственно реагировать, когда такое поведение представляет риски для вашей среды, данных и пользователей.

Надстройка управления приложениями в Microsoft Cloud App Security — это возможность управления безопасностью и политиками, предназначенная для приложений с поддержкой OAuth, которые имеют доступ к данным Microsoft 365 через API Microsoft Graph. Управление приложениями обеспечивает полную видимость и возможность исправления и управления тем, как эти приложения и их пользователи получают доступ к конфиденциальным данным, хранимым в Microsoft 365, используют их и предоставляют к ним общий доступ, с помощью действенной аналитики, а также автоматических оповещений и действий политик.

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

Управление приложениями предоставляет следующие всесторонние возможности.

- **Insights**: просмотр всех сторонних приложений для платформы Microsoft 365 в вашем клиенте на одной информационной панели. Вы можете видеть состояние всех приложений и действия, связанные с оповещениями, а также реагировать или отвечать на них.
- **Управление**: создание как упреждающих, так и реактивных политик для шаблонов и поведения приложений и пользователей; защита пользователей от использования не соответствующих требованиям или вредоносных приложений и ограничение доступа рискованных приложений к вашим данным.
- **Обнаружение**: оповещения и уведомления об аномалиях в действиях приложений, а также об использовании не соответствующих требованиям, вредоносных или рискованных приложений.
- **Исправление**: наряду с возможностями автоматического исправления можно своевременно использовать элементы управления исправлениями, чтобы реагировать на обнаружение аномальных действий приложений.

Управление приложениями — это платформенное решение, которое является неотъемлемой частью экосистемы приложений Microsoft 365. Управление приложениями контролирует приложения с поддержкой OAuth, зарегистрированные в Azure Active Directory (Azure AD) и получающие доступ к данным через API Microsoft Graph. Управление приложениями предоставляет средства контроля поведения приложений, которые помогают усилить безопасность и соответствие вашей ИТ-инфраструктуры требованиям.

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a>Первое знакомство с управлением приложениями

Чтобы увидеть панель мониторинга управления приложениями, перейдите в раздел [https://aka.ms/appgovernance](https://aka.ms/appgovernance). Обратите внимание на то, что для просмотра любых данных управления приложениями вашей учетной записи, с которой вы выполняете вход, должна быть назначена одна из [ролей администратора](app-governance-get-started.md#administrator-roles).

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a>Интеграция управления приложениями с Azure AD и Microsoft Cloud App Security

Управление приложениями, Azure AD и Microsoft Cloud App Security собирают и предоставляют различные наборы данных.

- Управление приложениями предоставляет подробные сведения о действиях приложения на уровне API.
- Azure AD предоставляет основные метаданные приложений и подробные сведения о входе в них.
- Microsoft Cloud App Security предоставляет сведения о рисках, связанных с приложениями.

Обеспечивая обмен информацией между управлением приложениями, Azure AD и Microsoft Cloud App Security, вы можете отображать сводную информацию на одном портале и легко привязать другой портал для получения дополнительных сведений. Ниже приводятся примеры.

- Сведения о входе в приложения на портале управления приложениями.

  На портале управления приложениями можно увидеть сводку действий входа для каждого приложения и связаться с Центром администрирования Azure Active Directory, чтобы получить подробные сведения о событиях входа.

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- Сведения об использовании API на портале Microsoft Cloud App Security.

  На портале Microsoft Cloud App Security можно увидеть уровень использования API, а также совокупную информацию о передаче данных и ссылку на портал управления приложениями для получения более подробных сведений.

Ниже приведено краткое описание интеграции.

![Интеграция управления приложениями с Azure AD и Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

Кроме того, надстройка управления приложениями отправляет свои оповещения в качестве сигналов в Microsoft Cloud App Security и Microsoft 365 Defender и получает оповещения от Microsoft Cloud App Security для более подробного анализа инцидентов безопасности, связанных с приложениями.

<!--
Integration of alerts with MCAS and M365 Defender
Azure AD IP detections in progress to surface in M365 Defender

## Integration with Azure AD

**Feedback from Anand:** We should add some details on how MAPG works with M365 Defender (previously MTP). Also, we should highlight the integration with MCAS and AAD.

Key cross-reference resources:

- [What is application management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-application-management)
- [Common application management scenarios for Azure Active Directory (especially scenarios 3-4)](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Azure Active Directory Identity Governance documentation](https://docs.microsoft.com/azure/active-directory/governance/)
- [Managing access to apps using Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management)

## Integration with Microsoft Cloud App Security

Key cross-reference resources:

- [Cloud App Security anomaly detection alerts investigation guide](https://docs.microsoft.com/cloud-app-security/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app)
- [Monitor alerts raised in Cloud App Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Control which third-party cloud OAuth apps get permissions](https://docs.microsoft.com/cloud-app-security/manage-app-permissions)

-->

## <a name="using-app-governance"></a>Использование управления приложениями

Использование управления приложениями для защиты клиента и его данных от приложений, потенциально являющихся вредоносными или демонстрирующими аномальное поведение, относится к следующим трем основным возможностям.

| Возможность | Описание |
|:-------|:-----|
| [Видимость и анализ приложений](app-governance-visibility-insights-overview.md) | Получение всеобъемлющего представления о трафике и действиях приложений Microsoft 365 в клиенте. |
| [Политики приложений для расширения возможностей управления](app-governance-app-policies-overview.md) | Создание как упреждающих, так и реактивных политик приложений, позволяющих расширить возможности управления приложениями Microsoft 365. |
| [Обнаружение и исправление](app-governance-detect-remediate-overview.md) | На основе оповещений об обнаружении, созданных платформой или политикой, можно отслеживать аномальное поведение приложений и исправлять его либо автоматически на основе параметров политики приложений, либо вручную. |
|||
