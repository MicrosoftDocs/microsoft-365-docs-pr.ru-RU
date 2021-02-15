---
title: Удостоверение для корпорации Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Сведения о том, как Contoso использует службу "удостоверение как услуга" (IDaaS) и предоставляет облачную проверку подлинности для сотрудников, а также федеративную проверку подлинности для партнеров и клиентов.
ms.openlocfilehash: dea0f53ef1c3fdc2ea32256303c6120c614c904d
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754645"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="538ae-103">Удостоверение для корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="538ae-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="538ae-104">Корпорация Майкрософт предоставляет удостоверение как службу (IDaaS) в своих облачных предложениях через Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="538ae-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="538ae-105">Для принятия Microsoft 365 для предприятий решение Contoso IDaaS должно было использовать локального поставщика удостоверений и включить федераированную проверку подлинности с существующими доверенными сторонними поставщиками удостоверений.</span><span class="sxs-lookup"><span data-stu-id="538ae-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="538ae-106">Лес доменных служб Active Directory Contoso</span><span class="sxs-lookup"><span data-stu-id="538ae-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="538ae-107">Contoso использует один лес доменных служб Active Directory (AD DS) для contoso com с семью поддоменами, по одному для каждого региона \. мира.</span><span class="sxs-lookup"><span data-stu-id="538ae-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="538ae-108">Главный офис, региональные и вспомогательные офисы содержат контроллеры доменов для локальной проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="538ae-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="538ae-109">Вот лес Contoso с региональными доменами для различных регионов мира, которые содержат региональные концентраторы.</span><span class="sxs-lookup"><span data-stu-id="538ae-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Лес Contoso и домены по всему миру](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="538ae-111">Корпорация Contoso решила использовать учетные записи и группы в лесу contoso com для проверки подлинности и авторизации рабочих нагрузок и служб \. Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="538ae-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="538ae-112">Инфраструктура федераированной проверки подлинности Contoso</span><span class="sxs-lookup"><span data-stu-id="538ae-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="538ae-113">Корпорация Contoso разрешает:</span><span class="sxs-lookup"><span data-stu-id="538ae-113">Contoso allows:</span></span>

- <span data-ttu-id="538ae-114">Клиенты используют свои учетные записи Майкрософт, Facebook или Google Mail для входов на общедоступный веб-сайт компании.</span><span class="sxs-lookup"><span data-stu-id="538ae-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="538ae-115">Поставщики и партнеры используют свои учетные записи LinkedIn, Salesforce или Google Mail для входов в партнерской экстрасети компании.</span><span class="sxs-lookup"><span data-stu-id="538ae-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="538ae-p103">Вот DMZ Contoso, содержащая общедоступный веб-сайт, партнерская экстрасеть и набор серверов служб федерации Active Directory (AD FS). Сеть DMZ подключена к Интернету, в который входят клиенты, партнеры и интернет-службы.</span><span class="sxs-lookup"><span data-stu-id="538ae-p103">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Поддержка федераированной проверки подлинности для клиентов и партнеров в contoso](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="538ae-119">Серверы AD FS в DMZ упрощают проверку подлинности учетных данных клиента их поставщиками удостоверений для доступа к общедоступным веб-сайтам и партнерским учетным данным для доступа к партнерской экстрасети.</span><span class="sxs-lookup"><span data-stu-id="538ae-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="538ae-p104">В компании Contoso решили сохранить эту инфраструктуру и сделать ее выделенной для проверки подлинности клиентов и партнеров. Архитекторы удостоверений Contoso изучают преобразование этой инфраструктуры в решения Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) и [B2C.](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)</span><span class="sxs-lookup"><span data-stu-id="538ae-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication. Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="538ae-122">Гибридное удостоверение с синхронизацией хэша пароля для облачной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="538ae-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="538ae-123">Корпорация Contoso хочет использовать свой локальной лес AD DS для проверки подлинности в облачных ресурсах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="538ae-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="538ae-124">Было принято решение использовать синхронизацию хеш-паролей (PHS).</span><span class="sxs-lookup"><span data-stu-id="538ae-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="538ae-125">PHS синхронизирует локальное лес AD DS с клиентом Azure AD подписки Microsoft 365 для предприятий, копируя учетные записи пользователей и групп, а также hashed версию паролей учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="538ae-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="538ae-126">Для синхронизации службы каталогов компания Contoso развернула средство Azure AD Connect на сервере в своем париже.</span><span class="sxs-lookup"><span data-stu-id="538ae-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="538ae-127">Вот сервер с Azure AD Connect, который оповещает лес AD DS Contoso об изменениях и затем синхронизирует эти изменения с клиентом Azure AD.</span><span class="sxs-lookup"><span data-stu-id="538ae-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Инфраструктура синхронизации каталогов PHS Contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="538ae-129">Политики условного доступа для доступа к удостоверению и устройству</span><span class="sxs-lookup"><span data-stu-id="538ae-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="538ae-130">В Contoso создан набор [политик условного доступа](identity-access-policies.md) Azure AD и Intune для трех уровней защиты:</span><span class="sxs-lookup"><span data-stu-id="538ae-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="538ae-131">*Базовые* меры защиты применяются для всех учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="538ae-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="538ae-132">*Защита* конфиденциальных данных применяется к старшим руководителям и руководителям.</span><span class="sxs-lookup"><span data-stu-id="538ae-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="538ae-133">*Строго регулируемая* защита применяется к определенным пользователям финансового, юридического и исследовательского отделов, которые имеют доступ к строго регулируемым данным.</span><span class="sxs-lookup"><span data-stu-id="538ae-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="538ae-134">Ниже приводится итоговая настройка политик условного доступа к удостоверениям и устройствам Contoso.</span><span class="sxs-lookup"><span data-stu-id="538ae-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Политики условного доступа к удостоверениям и устройствам в Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="538ae-136">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="538ae-136">Next step</span></span>

<span data-ttu-id="538ae-137">Узнайте, как Contoso использует инфраструктуру Microsoft Endpoint Configuration Manager для развертывания и поддержания [windows 10 Корпоративная](contoso-win10.md) в организации.</span><span class="sxs-lookup"><span data-stu-id="538ae-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="538ae-138">См. также</span><span class="sxs-lookup"><span data-stu-id="538ae-138">See also</span></span>

[<span data-ttu-id="538ae-139">Стратегия удостоверений для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="538ae-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="538ae-140">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="538ae-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="538ae-141">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="538ae-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
