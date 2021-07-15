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
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a><span data-ttu-id="bbd88-103">Надстройка управления приложениями в Microsoft Cloud App Security (в предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="bbd88-103">App governance add-on to Microsoft Cloud App Security (in preview)</span></span>

><span data-ttu-id="bbd88-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="bbd88-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="bbd88-105">Кибератаки становятся все более изощренными в использовании приложений, развернутых в локальной и облачной инфраструктуре, и создают отправную точку для повышения привилегий, горизонтального перемещения и кражи ваших данных.</span><span class="sxs-lookup"><span data-stu-id="bbd88-105">Cyberattacks have become increasingly sophisticated in the ways they exploit the apps you have deployed in your on-premises and cloud infrastructures, establishing a starting point for privilege escalation, lateral movement, and exfiltration of your data.</span></span> <span data-ttu-id="bbd88-106">Чтобы осознать потенциальные риски и остановить атаки такого типа, необходимо получить четкое представление о позиции вашей организации в отношении соответствия приложений требованиям, чтобы быстро выявлять аномальное поведение приложений и соответственно реагировать, когда такое поведение представляет риски для вашей среды, данных и пользователей.</span><span class="sxs-lookup"><span data-stu-id="bbd88-106">To understand the potential risks and stop these types of attacks, you need to gain clear visibility into your organization’s app compliance posture to quickly identify when an app exhibits anomalous behaviors and to respond when these behaviors present risks to your environment, data, and users.</span></span>

<span data-ttu-id="bbd88-107">Надстройка управления приложениями в Microsoft Cloud App Security — это возможность управления безопасностью и политиками, предназначенная для приложений с поддержкой OAuth, которые имеют доступ к данным Microsoft 365 через API Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="bbd88-107">The app governance add-on feature to Microsoft Cloud App Security is a security and policy management capability designed for OAuth-enabled apps that access Microsoft 365 data through Microsoft Graph APIs.</span></span> <span data-ttu-id="bbd88-108">Управление приложениями обеспечивает полную видимость и возможность исправления и управления тем, как эти приложения и их пользователи получают доступ к конфиденциальным данным, хранимым в Microsoft 365, используют их и предоставляют к ним общий доступ, с помощью действенной аналитики, а также автоматических оповещений и действий политик.</span><span class="sxs-lookup"><span data-stu-id="bbd88-108">App governance delivers full visibility, remediation, and governance into how these apps and their users access, use, and share your sensitive data stored in Microsoft 365 through actionable insights and automated policy alerts and actions.</span></span>

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

<span data-ttu-id="bbd88-109">Управление приложениями предоставляет следующие всесторонние возможности.</span><span class="sxs-lookup"><span data-stu-id="bbd88-109">App governance provides you with comprehensive:</span></span>

- <span data-ttu-id="bbd88-110">**Insights**: просмотр всех сторонних приложений для платформы Microsoft 365 в вашем клиенте на одной информационной панели.</span><span class="sxs-lookup"><span data-stu-id="bbd88-110">**Insights**: See a view of all the third-party apps for the Microsoft 365 platform in your tenant on a single dashboard.</span></span> <span data-ttu-id="bbd88-111">Вы можете видеть состояние всех приложений и действия, связанные с оповещениями, а также реагировать или отвечать на них.</span><span class="sxs-lookup"><span data-stu-id="bbd88-111">You can see all the apps’ status and alert activities and react or respond to them.</span></span>
- <span data-ttu-id="bbd88-112">**Управление**: создание как упреждающих, так и реактивных политик для шаблонов и поведения приложений и пользователей; защита пользователей от использования не соответствующих требованиям или вредоносных приложений и ограничение доступа рискованных приложений к вашим данным.</span><span class="sxs-lookup"><span data-stu-id="bbd88-112">**Governance**: Create proactive or reactive policies for app and user patterns and behaviors and protect your users from using non-compliant or malicious apps and limiting the access of risky apps to your data.</span></span>
- <span data-ttu-id="bbd88-113">**Обнаружение**: оповещения и уведомления об аномалиях в действиях приложений, а также об использовании не соответствующих требованиям, вредоносных или рискованных приложений.</span><span class="sxs-lookup"><span data-stu-id="bbd88-113">**Detection**: Be alerted and notified when there are anomalies in app activity and when non-compliant, malicious, or risky apps are used.</span></span>
- <span data-ttu-id="bbd88-114">**Исправление**: наряду с возможностями автоматического исправления можно своевременно использовать элементы управления исправлениями, чтобы реагировать на обнаружение аномальных действий приложений.</span><span class="sxs-lookup"><span data-stu-id="bbd88-114">**Remediation**: Along with automatic remediation capabilities, use remediation controls in a timely manner to respond to anomalous app activity detections.</span></span>

<span data-ttu-id="bbd88-115">Управление приложениями — это платформенное решение, которое является неотъемлемой частью экосистемы приложений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bbd88-115">App governance is a platform-based solution that is an integral part of the Microsoft 365 app ecosystem.</span></span> <span data-ttu-id="bbd88-116">Управление приложениями контролирует приложения с поддержкой OAuth, зарегистрированные в Azure Active Directory (Azure AD) и получающие доступ к данным через API Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="bbd88-116">App governance oversees and governs OAuth-enabled apps that are registered with Azure Active Directory (Azure AD) and access data through the Microsoft Graph API.</span></span> <span data-ttu-id="bbd88-117">Управление приложениями предоставляет средства контроля поведения приложений, которые помогают усилить безопасность и соответствие вашей ИТ-инфраструктуры требованиям.</span><span class="sxs-lookup"><span data-stu-id="bbd88-117">App governance provides you with application behavior controls to help strengthen the security and compliance posture of your IT infrastructure.</span></span>

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a><span data-ttu-id="bbd88-118">Первое знакомство с управлением приложениями</span><span class="sxs-lookup"><span data-stu-id="bbd88-118">A first glimpse at app governance</span></span>

<span data-ttu-id="bbd88-119">Чтобы увидеть панель мониторинга управления приложениями, перейдите в раздел [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="bbd88-119">To see the app governance dashboard, go to [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span></span> <span data-ttu-id="bbd88-120">Обратите внимание на то, что для просмотра любых данных управления приложениями вашей учетной записи, с которой вы выполняете вход, должна быть назначена одна из [ролей администратора](app-governance-get-started.md#administrator-roles).</span><span class="sxs-lookup"><span data-stu-id="bbd88-120">Note that your sign-in account must have one of the [administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a><span data-ttu-id="bbd88-121">Интеграция управления приложениями с Azure AD и Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bbd88-121">App governance integration with Azure AD and Microsoft Cloud App Security</span></span>

<span data-ttu-id="bbd88-122">Управление приложениями, Azure AD и Microsoft Cloud App Security собирают и предоставляют различные наборы данных.</span><span class="sxs-lookup"><span data-stu-id="bbd88-122">App governance, Azure AD, and Microsoft Cloud App Security collect and provide different data sets:</span></span>

- <span data-ttu-id="bbd88-123">Управление приложениями предоставляет подробные сведения о действиях приложения на уровне API.</span><span class="sxs-lookup"><span data-stu-id="bbd88-123">App governance provides detailed information about an app’s activity at the API level.</span></span>
- <span data-ttu-id="bbd88-124">Azure AD предоставляет основные метаданные приложений и подробные сведения о входе в них.</span><span class="sxs-lookup"><span data-stu-id="bbd88-124">Azure AD provides foundational app metadata and detailed information on sign-ins to apps.</span></span>
- <span data-ttu-id="bbd88-125">Microsoft Cloud App Security предоставляет сведения о рисках, связанных с приложениями.</span><span class="sxs-lookup"><span data-stu-id="bbd88-125">Microsoft Cloud App Security provides app risk information.</span></span>

<span data-ttu-id="bbd88-p106">Обеспечивая обмен информацией между управлением приложениями, Azure AD и Microsoft Cloud App Security, вы можете отображать сводную информацию на одном портале и легко привязать другой портал для получения дополнительных сведений. Ниже приводятся примеры.</span><span class="sxs-lookup"><span data-stu-id="bbd88-p106">By sharing information across app governance, Azure AD, and Microsoft Cloud App Security, you can display aggregate information in one portal and easily link to another portal for more information. Here are some examples:</span></span>

- <span data-ttu-id="bbd88-128">Сведения о входе в приложения на портале управления приложениями.</span><span class="sxs-lookup"><span data-stu-id="bbd88-128">App sign-in information in app governance:</span></span>

  <span data-ttu-id="bbd88-129">На портале управления приложениями можно увидеть сводку действий входа для каждого приложения и связаться с Центром администрирования Azure Active Directory, чтобы получить подробные сведения о событиях входа.</span><span class="sxs-lookup"><span data-stu-id="bbd88-129">From the app governance portal, you can see the aggregated sign-in activity for each app and link back to the Azure Active Directory admin center for the details of sign-in events.</span></span>

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- <span data-ttu-id="bbd88-130">Сведения об использовании API на портале Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="bbd88-130">API usage information in the Microsoft Cloud App Security portal:</span></span>

  <span data-ttu-id="bbd88-131">На портале Microsoft Cloud App Security можно увидеть уровень использования API, а также совокупную информацию о передаче данных и ссылку на портал управления приложениями для получения более подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="bbd88-131">From the Microsoft Cloud App Security portal, you can see API usage level and aggregate data transfer and link to the app governance portal for the details.</span></span>

<span data-ttu-id="bbd88-132">Ниже приведено краткое описание интеграции.</span><span class="sxs-lookup"><span data-stu-id="bbd88-132">Here's a summary of the integration.</span></span>

![Интеграция управления приложениями с Azure AD и Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

<span data-ttu-id="bbd88-134">Кроме того, надстройка управления приложениями отправляет свои оповещения в качестве сигналов в Microsoft Cloud App Security и Microsoft 365 Defender и получает оповещения от Microsoft Cloud App Security для более подробного анализа инцидентов безопасности, связанных с приложениями.</span><span class="sxs-lookup"><span data-stu-id="bbd88-134">Additionally, app governance sends its alerts as signals to Microsoft Cloud App Security and Microsoft 365 Defender, and app governance receives alerts from Microsoft Cloud App Security, to enable more detailed analysis of app-based security incidents.</span></span>

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

## <a name="using-app-governance"></a><span data-ttu-id="bbd88-135">Использование управления приложениями</span><span class="sxs-lookup"><span data-stu-id="bbd88-135">Using app governance</span></span>

<span data-ttu-id="bbd88-136">Использование управления приложениями для защиты клиента и его данных от приложений, потенциально являющихся вредоносными или демонстрирующими аномальное поведение, относится к следующим трем основным возможностям.</span><span class="sxs-lookup"><span data-stu-id="bbd88-136">Using app governance to protect your tenant and its data from potentially malicious or ill-behaved apps falls into these three core capabilities:</span></span>

| <span data-ttu-id="bbd88-137">Возможность</span><span class="sxs-lookup"><span data-stu-id="bbd88-137">Capability</span></span> | <span data-ttu-id="bbd88-138">Описание</span><span class="sxs-lookup"><span data-stu-id="bbd88-138">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="bbd88-139">Видимость и анализ приложений</span><span class="sxs-lookup"><span data-stu-id="bbd88-139">App visibility and insights</span></span>](app-governance-visibility-insights-overview.md) | <span data-ttu-id="bbd88-140">Получение всеобъемлющего представления о трафике и действиях приложений Microsoft 365 в клиенте.</span><span class="sxs-lookup"><span data-stu-id="bbd88-140">Get a 360° view on traffic and activity of the Microsoft 365 applications in your tenant.</span></span> |
| [<span data-ttu-id="bbd88-141">Политики приложений для расширения возможностей управления</span><span class="sxs-lookup"><span data-stu-id="bbd88-141">App policies for reinforced governance</span></span>](app-governance-app-policies-overview.md) | <span data-ttu-id="bbd88-142">Создание как упреждающих, так и реактивных политик приложений, позволяющих расширить возможности управления приложениями Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bbd88-142">Create proactive or reactive app policies, which will allow you to enforce governance for your Microsoft 3635 apps.</span></span> |
| [<span data-ttu-id="bbd88-143">Обнаружение и исправление</span><span class="sxs-lookup"><span data-stu-id="bbd88-143">Detection and remediation</span></span>](app-governance-detect-remediate-overview.md) | <span data-ttu-id="bbd88-144">На основе оповещений об обнаружении, созданных платформой или политикой, можно отслеживать аномальное поведение приложений и исправлять его либо автоматически на основе параметров политики приложений, либо вручную.</span><span class="sxs-lookup"><span data-stu-id="bbd88-144">Based on platform detection alerts or policy-generated detection alerts, monitor your apps for anomalous app behavior and remediate them, either automatically based on app policy settings or manually.</span></span> |
|||
