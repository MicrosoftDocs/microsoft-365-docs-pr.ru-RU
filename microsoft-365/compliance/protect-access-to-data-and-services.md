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
description: Узнайте, как защитить доступ пользователей и устройств к Microsoft 365 и службам и защитить от потери данных.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051701"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="6fb3a-103">Защита доступа пользователей и устройств</span><span class="sxs-lookup"><span data-stu-id="6fb3a-103">Protect user and device access</span></span>

<span data-ttu-id="6fb3a-104">Защита доступа к Microsoft 365 и службам имеет решающее значение для защиты от кибератак и защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="6fb3a-105">Такие же защиты можно применить и к другим приложениям SaaS в вашей среде и даже к локальному приложению, опубликованным с Azure Active Directory Application Proxy.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="6fb3a-106">Шаг 1. Обзор рекомендаций</span><span class="sxs-lookup"><span data-stu-id="6fb3a-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="6fb3a-107">Рекомендуемые возможности для защиты удостоверений и устройств, имеющих доступ к Office 365 и отличных от SaaS-служб и локальных приложений, которые опубликованы с помощью прокси приложения Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="6fb3a-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Другие языки](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="6fb3a-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="6fb3a-109">Шаг 2. Защита учетных записей администратора и доступа</span><span class="sxs-lookup"><span data-stu-id="6fb3a-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="6fb3a-110">Административные учетные записи, которые вы используете для администрирования Microsoft 365 среды, включают повышенные привилегии.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="6fb3a-111">Это ценные цели для хакеров и кибератак.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="6fb3a-112">Начните с использования учетных записей администратора только для администрирования.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="6fb3a-113">Администраторы должны иметь отдельную учетную запись пользователя для регулярного, неуправленного использования и использовать свою административную учетную запись только при необходимости для выполнения задачи, связанной с их функцией работы.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="6fb3a-114">Защита учетных записей администратора с помощью многофакторной проверки подлинности и условного доступа.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="6fb3a-115">Дополнительные сведения см. в [дополнительных сведениях о защите учетных записей администратора.](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)</span><span class="sxs-lookup"><span data-stu-id="6fb3a-115">For more information, see [Protecting administrator accounts](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="6fb3a-116">Далее настройте управление привилегированным доступом в Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="6fb3a-117">С помощью Privileged Access Management можно детально управлять доступом к привилегированным задачам администрирования в Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="6fb3a-118">Это поможет защитить организацию от нарушений, которые могут использовать существующие привилегированные учетные записи администратора с постоянный доступ к конфиденциальным данным или доступ к критически важным настройкам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="6fb3a-119">Обзор управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="6fb3a-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="6fb3a-120">Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="6fb3a-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="6fb3a-121">Другой верхней рекомендацией является использование рабочих станций, специально настроенных для административной работы.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="6fb3a-122">Это специальные устройства, которые используются только для административных задач.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="6fb3a-123">См. [в этой ленте "Защита привилегированного доступа".](/windows-server/identity/securing-privileged-access/securing-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="6fb3a-123">See [Securing privileged access](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="6fb3a-124">Наконец, можно смягчить последствия непреднамеренного отсутствия административного доступа, создав в клиенте две или более учетных записей аварийного доступа.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="6fb3a-125">См. в руб. Управление [учетными записями аварийного доступа в Azure AD.](/azure/active-directory/users-groups-roles/directory-emergency-access)</span><span class="sxs-lookup"><span data-stu-id="6fb3a-125">See [Manage emergency access accounts in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="6fb3a-126">Шаг 3. Настройка рекомендуемых политик доступа к удостоверениям и устройствам</span><span class="sxs-lookup"><span data-stu-id="6fb3a-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="6fb3a-127">Многофакторная проверка подлинности (MFA) и политики условного доступа — это мощные средства для смягчения последствий взлома учетных записей и несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="6fb3a-128">Рекомендуется реализовать набор политик, которые были протестированы вместе.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="6fb3a-129">Дополнительные сведения, включая этапы развертывания, см. в настройках [удостоверений и доступа к устройствам.](../security/defender-365-security/microsoft-365-policies-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="6fb3a-129">For more information, including deployment steps, see [Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="6fb3a-130">Эти политики реализуют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="6fb3a-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="6fb3a-131">Проверка подлинности Mult-factor</span><span class="sxs-lookup"><span data-stu-id="6fb3a-131">Mult-factor authentication</span></span>
- <span data-ttu-id="6fb3a-132">Условный доступ</span><span class="sxs-lookup"><span data-stu-id="6fb3a-132">Conditional access</span></span>
- <span data-ttu-id="6fb3a-133">Защита приложений intune (защита приложений и данных для устройств)</span><span class="sxs-lookup"><span data-stu-id="6fb3a-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="6fb3a-134">Соответствие устройств Intune требованиям</span><span class="sxs-lookup"><span data-stu-id="6fb3a-134">Intune device compliance</span></span>
- <span data-ttu-id="6fb3a-135">Защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="6fb3a-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="6fb3a-136">Реализация соответствия требованиям устройства Intune требует регистрации устройств.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="6fb3a-137">Управление устройствами позволяет убедиться, что они являются здоровыми и совместимыми, прежде чем разрешить им доступ к ресурсам в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="6fb3a-138">См. [запись устройств для управления в Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="6fb3a-138">See [Enroll devices for management in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="6fb3a-139">Шаг 4. Настройка SharePoint политик доступа к устройствам</span><span class="sxs-lookup"><span data-stu-id="6fb3a-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="6fb3a-140">Корпорация Майкрософт рекомендует защищать контент на SharePoint с конфиденциальным и строго регулируемым контентом с помощью элементов управления доступом к устройствам.</span><span class="sxs-lookup"><span data-stu-id="6fb3a-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="6fb3a-141">Дополнительные сведения см. в рекомендациях политики по обеспечению безопасности [SharePoint сайтов и файлов.](../security/defender-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6fb3a-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>



