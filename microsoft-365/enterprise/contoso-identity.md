---
title: Удостоверение для корпорации Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Сведения о том, как Contoso использует службу "удостоверение как услуга" (IDaaS) и предоставляет облачную проверку подлинности для сотрудников, а также федеративную проверку подлинности для партнеров и клиентов.
ms.openlocfilehash: 10db0a35024595c4dba9a33ad83ae75bcad3870c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637251"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="1fa5f-103">Удостоверение для корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="1fa5f-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="1fa5f-104">Майкрософт предоставляет удостоверение в качестве службы (IDaaS) в облачных решениях через Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="1fa5f-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="1fa5f-105">Чтобы использовать Microsoft 365 для предприятий, решение Contoso IDaaS должно использовать свой локальный поставщик удостоверений и включала федеративный способ проверки подлинности с имеющимися надежными сторонними поставщиками удостоверений.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="1fa5f-106">Лес доменных служб Active Directory contoso</span><span class="sxs-lookup"><span data-stu-id="1fa5f-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="1fa5f-107">Contoso использует один лес доменных служб Active Directory (AD DS) для Contoso \. com с семь поддоменов, по одному для каждого региона мира.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="1fa5f-108">Главный офис, региональные и вспомогательные офисы содержат контроллеры доменов для локальной проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="1fa5f-109">Вот Лес contoso с региональными доменами для различных частей мира, которые содержат региональные концентраторы.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Лес Contoso и домены по всему миру](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="1fa5f-111">Компания Contoso решила использовать учетные записи и группы в \. лесу com для Contoso для проверки подлинности и авторизации для своей рабочей нагрузки и служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="1fa5f-112">Инфраструктура федеративной проверки подлинности contoso</span><span class="sxs-lookup"><span data-stu-id="1fa5f-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="1fa5f-113">Корпорация Contoso разрешает:</span><span class="sxs-lookup"><span data-stu-id="1fa5f-113">Contoso allows:</span></span>

- <span data-ttu-id="1fa5f-114">Клиенты могут использовать учетные записи Microsoft, Facebook или Google Mail для входа на общедоступный веб-сайт компании.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="1fa5f-115">Поставщикам и партнерам использовать свои учетные записи LinkedIn, Salesforce или Google для входа в экстрасеть партнера компании.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="1fa5f-p103">Вот ДЕМИЛИТАРИЗОВАНная группа Contoso, содержащая общедоступный веб-сайт, экстрасеть партнера и набор серверов AD FS. DMZ подключается к Интернету, который содержит клиентов, партнеров и Интернет-служб.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-p103">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of AD FS servers. The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Поддержка федеративной проверки подлинности для клиентов и партнеров contoso](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="1fa5f-119">Серверы AD FS в DMZ упрощают проверку подлинности учетных данных клиента по их поставщикам удостоверений для доступа к общедоступному веб-сайту и учетным данным партнера для доступа к экстрасети партнера.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="1fa5f-p104">Компания Contoso решила сохранить эту инфраструктуру и выделить ее для проверки подлинности клиентов и партнеров. Архитекторы удостоверений Contoso изучает преобразование этой инфраструктуры в решения Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) и [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) .</span><span class="sxs-lookup"><span data-stu-id="1fa5f-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication. Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="1fa5f-122">Гибридное удостоверение с синхронизацией хэша пароля для облачной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="1fa5f-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="1fa5f-123">Contoso требовалось использовать локальный лес AD DS для проверки подлинности в облачных ресурсах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="1fa5f-124">Решено использовать синхронизацию хэша паролей (ФС).</span><span class="sxs-lookup"><span data-stu-id="1fa5f-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="1fa5f-125">ФС синхронизирует локальный лес доменных служб Active Directory с клиентом Azure AD своей подписки Microsoft 365 для предприятия, копируя учетные записи пользователей и групп и хешированную версию паролей учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="1fa5f-126">Для синхронизации службы каталогов компания Contoso развернула средство Azure AD Connect на сервере в центре данных Париж.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="1fa5f-127">Вот сервер, на котором работает Azure AD Connect, который опрашивает лес Contoso AD DS на наличие изменений, а затем синхронизирует эти изменения с клиентом Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Инфраструктура синхронизации каталогов Contoso ФС](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="1fa5f-129">Политики условного доступа для доступа к удостоверению и устройству</span><span class="sxs-lookup"><span data-stu-id="1fa5f-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="1fa5f-130">В Contoso создан набор [политик условного доступа](identity-access-policies.md) Azure AD и Intune для трех уровней защиты:</span><span class="sxs-lookup"><span data-stu-id="1fa5f-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="1fa5f-131">*Базовые* защиты применяются ко всем учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="1fa5f-132">*Конфиденциальная* защита относится к высшим лидерам и сотрудникам руководителей.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="1fa5f-133">*Строго регулируемые* защиты применяются к определенным пользователям в отделе финансов, юридических и исследовательских отделов, имеющих доступ к данным с высоким регулируемым доступом.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="1fa5f-134">Вот итоговый набор политик условного доступа для удостоверений и устройств contoso.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Политики условного доступа к удостоверениям и устройствам в Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="1fa5f-136">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="1fa5f-136">Next step</span></span>

<span data-ttu-id="1fa5f-137">[Узнайте](contoso-win10.md) , как в компании Contoso для развертывания и сохранения текущей операционной системы Windows 10 Корпоративная в организации используется инфраструктура Configuration Manager конечных точек Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1fa5f-137">[Learn](contoso-win10.md) how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fa5f-138">См. также</span><span class="sxs-lookup"><span data-stu-id="1fa5f-138">See also</span></span>

[<span data-ttu-id="1fa5f-139">Стратегия удостоверений для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1fa5f-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="1fa5f-140">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1fa5f-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="1fa5f-141">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="1fa5f-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
