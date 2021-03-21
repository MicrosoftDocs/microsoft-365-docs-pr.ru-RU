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
ms.openlocfilehash: bd8bbb62bc87ff59594e2fb2a3e21311c2452d9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925545"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="5cb80-103">Защита доступа пользователей и устройств</span><span class="sxs-lookup"><span data-stu-id="5cb80-103">Protect user and device access</span></span>

<span data-ttu-id="5cb80-104">Защита доступа к данным и службам Microsoft 365 имеет решающее значение для защиты от кибератак и защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="5cb80-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="5cb80-105">Такие же защиты можно применить и к другим приложениям SaaS в среде и даже к локальному приложению, опубликованным с помощью прокси-приложения Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5cb80-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="5cb80-106">Шаг 1. Обзор рекомендаций</span><span class="sxs-lookup"><span data-stu-id="5cb80-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="5cb80-107">Рекомендуемые возможности для защиты удостоверений и устройств, имеющих доступ к Office 365 и отличных от SaaS-служб и локальных приложений, которые опубликованы с помощью прокси приложения Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5cb80-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="5cb80-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Другие языки](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="5cb80-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="5cb80-109">Шаг 2. Защита учетных записей администратора и доступа</span><span class="sxs-lookup"><span data-stu-id="5cb80-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="5cb80-110">Административные учетные записи, которые используются для администрирования среды Microsoft 365, включают повышенные привилегии.</span><span class="sxs-lookup"><span data-stu-id="5cb80-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="5cb80-111">Это ценные цели для хакеров и кибератак.</span><span class="sxs-lookup"><span data-stu-id="5cb80-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="5cb80-112">Начните с использования учетных записей администратора только для администрирования.</span><span class="sxs-lookup"><span data-stu-id="5cb80-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="5cb80-113">Администраторы должны иметь отдельную учетную запись пользователя для регулярного, неуправленного использования и использовать свою административную учетную запись только при необходимости для выполнения задачи, связанной с их функцией работы.</span><span class="sxs-lookup"><span data-stu-id="5cb80-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="5cb80-114">Защита учетных записей администратора с помощью многофакторной проверки подлинности и условного доступа.</span><span class="sxs-lookup"><span data-stu-id="5cb80-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="5cb80-115">Дополнительные сведения см. в [дополнительных сведениях о защите учетных записей администратора.](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)</span><span class="sxs-lookup"><span data-stu-id="5cb80-115">For more information, see [Protecting administrator accounts](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="5cb80-116">Затем настройте управление привилегированным доступом в Office 365.</span><span class="sxs-lookup"><span data-stu-id="5cb80-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="5cb80-117">Управление привилегированным доступом позволяет контролировать доступ к привилегированным задачам администратора в Office 365.</span><span class="sxs-lookup"><span data-stu-id="5cb80-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="5cb80-118">Это поможет защитить организацию от нарушений, которые могут использовать существующие привилегированные учетные записи администратора с постоянный доступ к конфиденциальным данным или доступ к критически важным настройкам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5cb80-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="5cb80-119">Обзор управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="5cb80-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="5cb80-120">Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="5cb80-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="5cb80-121">Другой верхней рекомендацией является использование рабочих станций, специально настроенных для административной работы.</span><span class="sxs-lookup"><span data-stu-id="5cb80-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="5cb80-122">Это специальные устройства, которые используются только для административных задач.</span><span class="sxs-lookup"><span data-stu-id="5cb80-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="5cb80-123">См. [в этой ленте "Защита привилегированного доступа".](/windows-server/identity/securing-privileged-access/securing-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="5cb80-123">See [Securing privileged access](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="5cb80-124">Наконец, можно смягчить последствия непреднамеренного отсутствия административного доступа, создав в клиенте две или более учетных записей аварийного доступа.</span><span class="sxs-lookup"><span data-stu-id="5cb80-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="5cb80-125">См. в руб. Управление [учетными записями аварийного доступа в Azure AD.](/azure/active-directory/users-groups-roles/directory-emergency-access)</span><span class="sxs-lookup"><span data-stu-id="5cb80-125">See [Manage emergency access accounts in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="5cb80-126">Шаг 3. Настройка рекомендуемых политик доступа к удостоверениям и устройствам</span><span class="sxs-lookup"><span data-stu-id="5cb80-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="5cb80-127">Многофакторная проверка подлинности (MFA) и политики условного доступа — это мощные средства для смягчения последствий взлома учетных записей и несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="5cb80-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="5cb80-128">Рекомендуется реализовать набор политик, которые были протестированы вместе.</span><span class="sxs-lookup"><span data-stu-id="5cb80-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="5cb80-129">Дополнительные сведения, включая этапы развертывания, см. в настройках [удостоверений и доступа к устройствам.](../security/office-365-security/microsoft-365-policies-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="5cb80-129">For more information, including deployment steps, see [Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="5cb80-130">Эти политики реализуют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="5cb80-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="5cb80-131">Проверка подлинности Mult-factor</span><span class="sxs-lookup"><span data-stu-id="5cb80-131">Mult-factor authentication</span></span>
- <span data-ttu-id="5cb80-132">Условный доступ</span><span class="sxs-lookup"><span data-stu-id="5cb80-132">Conditional access</span></span>
- <span data-ttu-id="5cb80-133">Защита приложений intune (защита приложений и данных для устройств)</span><span class="sxs-lookup"><span data-stu-id="5cb80-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="5cb80-134">Соответствие устройств Intune требованиям</span><span class="sxs-lookup"><span data-stu-id="5cb80-134">Intune device compliance</span></span>
- <span data-ttu-id="5cb80-135">Защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="5cb80-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="5cb80-136">Реализация соответствия требованиям устройства Intune требует регистрации устройств.</span><span class="sxs-lookup"><span data-stu-id="5cb80-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="5cb80-137">Управление устройствами позволяет убедиться, что они являются здоровыми и совместимыми, прежде чем разрешить им доступ к ресурсам в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="5cb80-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="5cb80-138">См. [запись устройств для управления в Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="5cb80-138">See [Enroll devices for management in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="5cb80-139">Шаг 4. Настройка политик доступа к устройствам SharePoint</span><span class="sxs-lookup"><span data-stu-id="5cb80-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="5cb80-140">Корпорация Майкрософт рекомендует защищать контент на сайтах SharePoint с конфиденциальным и строго регулируемым контентом с помощью элементов управления доступом к устройствам.</span><span class="sxs-lookup"><span data-stu-id="5cb80-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="5cb80-141">Дополнительные сведения см. [в рекомендациях политики по обеспечению](../security/office-365-security/sharepoint-file-access-policies.md)безопасности сайтов и файлов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5cb80-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>



