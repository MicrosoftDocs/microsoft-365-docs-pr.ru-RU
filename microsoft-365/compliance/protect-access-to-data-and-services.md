---
title: Защита доступа пользователей и устройств
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
description: Целевая страница для защиты доступа к данным и службам O365
ms.openlocfilehash: 9fc1691e7e36f994b5d0b8a6a9735fe8ccd8735a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091025"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="0ffdf-103">Защита доступа пользователей и устройств</span><span class="sxs-lookup"><span data-stu-id="0ffdf-103">Protect user and device access</span></span>

<span data-ttu-id="0ffdf-104">Защита доступа к данным и службам Office 365 важна для защиты от кибератаки и защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-104">Protecting access to your Office 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="0ffdf-105">Одни и те же защиты можно применять к другим приложениям SaaS в среде и даже к локальным приложениям, публикуемым с помощью прокси-сервера приложения Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="0ffdf-106">Шаг 1: проверка рекомендаций</span><span class="sxs-lookup"><span data-stu-id="0ffdf-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="0ffdf-107">Рекомендуемые возможности для защиты удостоверений и устройств, имеющих доступ к Office 365 и отличных от SaaS-служб и локальных приложений, которые опубликованы с помощью прокси приложения Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="0ffdf-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Другие языки](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="0ffdf-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="0ffdf-109">Шаг 2: защита учетных записей администраторов и доступа</span><span class="sxs-lookup"><span data-stu-id="0ffdf-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="0ffdf-110">Административные учетные записи, используемые для управления средой Office 365, включают повышенные привилегии.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-110">The administrative accounts you use to administer your Office 365 environment include elevated privileges.</span></span> <span data-ttu-id="0ffdf-111">Это ценные цели для хакеров и цибераттаккерс.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="0ffdf-112">Начните с использования учетных записей администраторов только для администрирования.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="0ffdf-113">Администраторы должны иметь отдельную учетную запись пользователя для обычного, не административного использования и использовать учетную запись администратора только при необходимости выполнения задачи, связанной с должностной функцией.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="0ffdf-114">Защитите учетные записи администратора с помощью многофакторной проверки подлинности и условного доступа.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="0ffdf-115">Дополнительные сведения можно найти в статье [Защита учетных записей администраторов](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="0ffdf-115">For more information, see [Protecting administrator accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="0ffdf-116">Затем настройте управление привилегированным доступом в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="0ffdf-117">Управление привилегированным доступом позволяет осуществлять детализированный контроль над задачами привилегированного администрирования в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="0ffdf-118">Это помогает защитить организацию от нарушений, которые могут использовать существующие привилегированные учетные записи администраторов с ограниченным доступом к конфиденциальным данным или к критическим параметрам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="0ffdf-119">Общие сведения об управлении привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="0ffdf-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="0ffdf-120">Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="0ffdf-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="0ffdf-121">Еще одной рекомендацией является использование рабочих станций, специально настроенных для административной работы.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="0ffdf-122">Это выделенные устройства, которые используются только для задач администрирования.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="0ffdf-123">Обратитесь [к разделу защита привилегированного доступа](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span><span class="sxs-lookup"><span data-stu-id="0ffdf-123">See [Securing privileged access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="0ffdf-124">Наконец, вы можете уменьшить влияние непреднамеренного отсутствия административного доступа, создав две или более учетных записей для аварийного доступа в клиенте.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="0ffdf-125">Обратитесь к разделу [Управление учетными записями аварийного доступа в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="0ffdf-125">See [Manage emergency access accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="0ffdf-126">Шаг 3: Настройка рекомендуемых политик доступа к удостоверениям и устройствам</span><span class="sxs-lookup"><span data-stu-id="0ffdf-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="0ffdf-127">Многофакторная проверка подлинности (MFA) и политики условного доступа являются мощными средствами для устранения скомпрометированных учетных записей и несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="0ffdf-128">Мы рекомендуем реализовать набор политик, которые были проверены вместе.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="0ffdf-129">Дополнительные сведения, в том числе этапы развертывания, приведены в разделе [Конфигурация доступа к удостоверениям и устройствам](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).</span><span class="sxs-lookup"><span data-stu-id="0ffdf-129">For more information, including deployment steps, see [Identity and device access configurations](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).</span></span>

 <span data-ttu-id="0ffdf-130">Эти политики реализуют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="0ffdf-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="0ffdf-131">Мулт Factoring Authentication (проверка подлинности)</span><span class="sxs-lookup"><span data-stu-id="0ffdf-131">Mult-factor authentication</span></span>
- <span data-ttu-id="0ffdf-132">условный доступ;</span><span class="sxs-lookup"><span data-stu-id="0ffdf-132">Conditional access</span></span>
- <span data-ttu-id="0ffdf-133">Защита приложений в Intune (защита приложений и данных для устройств)</span><span class="sxs-lookup"><span data-stu-id="0ffdf-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="0ffdf-134">Соответствие устройства Intune</span><span class="sxs-lookup"><span data-stu-id="0ffdf-134">Intune device compliance</span></span>
- <span data-ttu-id="0ffdf-135">Защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="0ffdf-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="0ffdf-136">Для реализации соответствия требованиям к устройствам Intune необходимо зарегистрировать устройство.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="0ffdf-137">Управление устройствами позволяет убедиться, что они являются работоспособными и совместимыми, прежде чем разрешить им доступ к ресурсам в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="0ffdf-138">[В разделе Регистрация устройств для управления в Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="0ffdf-138">See [Enroll devices for management in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="0ffdf-139">Шаг 4: Настройка политик доступа к устройствам SharePoint</span><span class="sxs-lookup"><span data-stu-id="0ffdf-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="0ffdf-140">Корпорация Майкрософт рекомендует защищать контент на сайтах SharePoint с помощью конфиденциального и строго регулируемого контента с помощью управления доступом к устройствам.</span><span class="sxs-lookup"><span data-stu-id="0ffdf-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="0ffdf-141">Для получения дополнительных сведений см. [рекомендации по политике по обеспечению безопасности сайтов и файлов SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="0ffdf-141">For more information, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>



    

