---
title: Защита доступа пользователей и устройств
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Узнайте, как защитить доступ пользователей и устройств к данным и службам Microsoft 365 и защитить от потери данных.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64baa2c9e49a9b24841ec50db3e5592ba3d7d55d
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399028"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="9b4fd-103">Защита доступа пользователей и устройств</span><span class="sxs-lookup"><span data-stu-id="9b4fd-103">Protect user and device access</span></span>

<span data-ttu-id="9b4fd-104">Защита доступа к данным и службам Microsoft 365 крайне важна для защиты от кибератак и защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="9b4fd-105">Такие же меры защиты можно применять к другим приложениям SaaS в вашей среде и даже к локальному приложению, опубликованной с помощью прокси приложения Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="9b4fd-106">Шаг 1. Обзор рекомендаций</span><span class="sxs-lookup"><span data-stu-id="9b4fd-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="9b4fd-107">Рекомендуемые возможности для защиты удостоверений и устройств, имеющих доступ к Office 365 и отличных от SaaS-служб и локальных приложений, которые опубликованы с помощью прокси приложения Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="9b4fd-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Другие языки](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="9b4fd-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="9b4fd-109">Шаг 2. Защита учетных записей администраторов и доступа</span><span class="sxs-lookup"><span data-stu-id="9b4fd-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="9b4fd-110">Административные учетные записи, которые вы используете для администрирования среды Microsoft 365, включают повышенные привилегии.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="9b4fd-111">Это ценные цели для злоумышленников и кибератак.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="9b4fd-112">Начните с использования учетных записей администратора только для администрирования.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="9b4fd-113">Администраторы должны иметь отдельную учетную запись пользователя для обычного, не административного использования и использовать административную учетную запись, только если это необходимо для выполнения задачи, связанной с их рабочими задачами.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="9b4fd-114">Защитите учетные записи администраторов с помощью многофакторной проверки подлинности и условного доступа.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="9b4fd-115">Дополнительные сведения см. [в сведениях о защите учетных записей администраторов.](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts)</span><span class="sxs-lookup"><span data-stu-id="9b4fd-115">For more information, see [Protecting administrator accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="9b4fd-116">Затем настройте управление привилегированным доступом в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="9b4fd-117">Управление привилегированным доступом позволяет детально контролировать доступ к привилегированным задачам администратора в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="9b4fd-118">Она помогает защитить организацию от нарушений безопасности, которые могут использовать существующие привилегированные учетные записи администраторов с постоянный доступ к конфиденциальным данным или доступ к критически важным настройкам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="9b4fd-119">Обзор управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="9b4fd-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="9b4fd-120">Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="9b4fd-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="9b4fd-121">Еще одной важной рекомендацией является использование рабочих станций, специально настроенных для административной работы.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="9b4fd-122">Это выделенные устройства, которые используются только для задач администрирования.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="9b4fd-123">См. ["Защита привилегированного доступа".](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="9b4fd-123">See [Securing privileged access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="9b4fd-124">Наконец, вы можете уменьшить влияние случайного отсутствия административного доступа, создав в клиенте две или более учетных записей для экстренного доступа.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="9b4fd-125">См. ["Управление учетными записями для экстренного доступа в Azure AD".](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)</span><span class="sxs-lookup"><span data-stu-id="9b4fd-125">See [Manage emergency access accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="9b4fd-126">Шаг 3. Настройка рекомендуемых политик доступа к удостоверениям и устройствам</span><span class="sxs-lookup"><span data-stu-id="9b4fd-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="9b4fd-127">Многофакторная проверка подлинности (MFA) и политики условного доступа — это мощные средства для защиты от компрометации учетных записей и несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="9b4fd-128">Мы рекомендуем реализовать набор политик, которые были протестированы вместе.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="9b4fd-129">Дополнительные сведения, включая этапы развертывания, см. в настройках доступа к [удостоверениям и устройствам.](../security/office-365-security/microsoft-365-policies-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="9b4fd-129">For more information, including deployment steps, see [Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="9b4fd-130">Эти политики реализуют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="9b4fd-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="9b4fd-131">Многоугольная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="9b4fd-131">Mult-factor authentication</span></span>
- <span data-ttu-id="9b4fd-132">условный доступ;</span><span class="sxs-lookup"><span data-stu-id="9b4fd-132">Conditional access</span></span>
- <span data-ttu-id="9b4fd-133">Защита приложений Intune (защита приложений и данных для устройств)</span><span class="sxs-lookup"><span data-stu-id="9b4fd-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="9b4fd-134">Соответствие устройств Intune требованиям</span><span class="sxs-lookup"><span data-stu-id="9b4fd-134">Intune device compliance</span></span>
- <span data-ttu-id="9b4fd-135">Защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="9b4fd-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="9b4fd-136">Реализация соответствия устройств Intune требует регистрации устройства.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="9b4fd-137">Управление устройствами позволяет убедиться в их правильной и совместительной до того, как они будут получать доступ к ресурсам в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="9b4fd-138">См. ["Регистрация устройств для управления в Intune"](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="9b4fd-138">See [Enroll devices for management in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="9b4fd-139">Шаг 4. Настройка политик доступа к устройствам SharePoint</span><span class="sxs-lookup"><span data-stu-id="9b4fd-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="9b4fd-140">Корпорация Майкрософт рекомендует защищать контент на сайтах SharePoint с помощью конфиденциального и строго регулируемого контента с помощью элементов управления доступом устройств.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="9b4fd-141">Дополнительные сведения см. в рекомендациях политики для защиты сайтов [и файлов SharePoint.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9b4fd-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>



    

