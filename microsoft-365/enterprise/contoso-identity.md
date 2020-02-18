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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Сведения о том, как Contoso использует службу "удостоверение как услуга" (IDaaS) и предоставляет облачную проверку подлинности для сотрудников, а также федеративную проверку подлинности для партнеров и клиентов.
ms.openlocfilehash: 77c90740fd39080ccc204552bc8407aa107e354a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068472"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="17181-103">Удостоверение для корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="17181-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="17181-104">Корпорация Майкрософт предоставляет удостоверение как услугу (IDaaS) в своих облачных предложениях с Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="17181-104">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="17181-105">Для перехода на Microsoft 365 Enterprise в решении IDaaS Contoso нужно было использовать локального поставщика удостоверений и по-прежнему включать федеративную проверку подлинности с помощью существующих надежных сторонних поставщиков удостоверений.</span><span class="sxs-lookup"><span data-stu-id="17181-105">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="17181-106">Лес доменных служб Active Directory Contoso</span><span class="sxs-lookup"><span data-stu-id="17181-106">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="17181-107">Contoso использует один лес доменных служб Active Directory (AD DS) для contoso.com с семью поддоменами, по одному для каждого региона мира.</span><span class="sxs-lookup"><span data-stu-id="17181-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="17181-108">Главный офис, региональные и вспомогательные офисы содержат контроллеры доменов для локальной проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="17181-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="17181-109">Ниже показан лес Contoso с региональными доменами для разных частей света, в которых находятся региональные офисы.</span><span class="sxs-lookup"><span data-stu-id="17181-109">Here is the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Лес Contoso и домены по всему миру](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="17181-111">Contoso необходимо было использовать учетные записи и группы в лесу contoso.com для проверки подлинности и авторизации своих рабочих нагрузок и служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17181-111">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="17181-112">Инфраструктура федеративной аутентификации Contoso</span><span class="sxs-lookup"><span data-stu-id="17181-112">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="17181-113">Корпорация Contoso разрешает:</span><span class="sxs-lookup"><span data-stu-id="17181-113">Contoso allows:</span></span>

- <span data-ttu-id="17181-114">клиентам использовать свои учетные записи Майкрософт, Facebook или Google Mail для входа на общедоступный веб-сайт;</span><span class="sxs-lookup"><span data-stu-id="17181-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="17181-115">поставщикам и партнерам использовать свои учетные записи LinkedIn, Salesforce или Google Mail для входа в партнерскую экстрасеть.</span><span class="sxs-lookup"><span data-stu-id="17181-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="17181-p103">Ниже показана сеть периметра Contoso, содержащая общедоступный веб-сайт, партнерскую экстрасеть и набор серверов служб федерации Active Directory (AD FS). Сеть периметра подключена к Интернету, в котором находятся клиенты, партнеры и Интернет-службы.</span><span class="sxs-lookup"><span data-stu-id="17181-p103">Here is the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Поддержка федеративной аутентификации клиентов и партнеров в компании Contoso](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="17181-119">Серверы AD FS в DMZ выполняют проверку подлинности учетных данных клиентов с использованием поставщиков удостоверений для доступа к общедоступному веб-сайту и учетных данных партнеров в партнерской экстрасети.</span><span class="sxs-lookup"><span data-stu-id="17181-119">AD FS servers in the DMZ facilitate the authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="17181-p104">Корпорация Contoso решила сохранить эту инфраструктуру и выделить ее для проверки подлинности клиентов и партнеров. Архитекторы удостоверений Contoso изучают возможность преобразования этой инфраструктуры в решения Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) и [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="17181-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="17181-122">Гибридное удостоверение с синхронизацией хэша пароля для облачной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="17181-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="17181-123">Contoso необходимо было использовать собственный локальный лес AD DS при проверке подлинности для доступа к облачным ресурсам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17181-123">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="17181-124">Было решено использовать синхронизацию хэша пароля (PHS).</span><span class="sxs-lookup"><span data-stu-id="17181-124">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="17181-125">PHS синхронизирует локальный лес AD DS с клиентом Azure AD подписки на Microsoft 365 Enterprise. При этом копируются учетные записи пользователей и групп, а также хэшированные версии паролей от учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="17181-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="17181-126">Для постоянной синхронизации каталога Contoso развернула средство Azure AD Connect на сервере в собственном ЦОД в Париже.</span><span class="sxs-lookup"><span data-stu-id="17181-126">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> 

<span data-ttu-id="17181-127">Ниже показан сервер, на котором Azure AD Connect опрашивает лес AD DS Contoso для выявления изменений и затем синхронизирует эти изменения с клиентом Azure AD.</span><span class="sxs-lookup"><span data-stu-id="17181-127">Here is the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Инфраструктура синхронизации каталога PHS Contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="17181-129">Политики условного доступа для доступа к удостоверению и устройству</span><span class="sxs-lookup"><span data-stu-id="17181-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="17181-130">В Contoso создан набор [политик условного доступа](identity-access-policies.md) Azure AD и Intune для трех уровней защиты:</span><span class="sxs-lookup"><span data-stu-id="17181-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="17181-131">**Базовая** защита применяется ко всем учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="17181-131">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="17181-132">Защита **конфиденциальных данных** применяется к старшим руководителям и руководству высшего звена</span><span class="sxs-lookup"><span data-stu-id="17181-132">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="17181-133">Защита **строго регулируемых данных** применяется к определенным пользователям из финансового, юридического и исследовательского отделов, имеющим доступ к строго регулируемым данным</span><span class="sxs-lookup"><span data-stu-id="17181-133">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="17181-134">Ниже показан итоговый набор политик условного доступа к удостоверениям и устройствам.</span><span class="sxs-lookup"><span data-stu-id="17181-134">Here is Contoso's resulting set of identity and device Conditional Access policies.</span></span>

![Политики условного доступа к удостоверениям и устройствам в Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="17181-136">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="17181-136">Next step</span></span>

<span data-ttu-id="17181-137">[Узнайте,](contoso-win10.md) как в корпорации Contoso используют инфраструктуру Microsoft Endpoint Configuration Manager для развертывания Windows 10 Корпоративная в организации и поддержания этой операционной системы в актуальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="17181-137">[Learn](contoso-win10.md) how Contoso is leveraging its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="17181-138">См. также</span><span class="sxs-lookup"><span data-stu-id="17181-138">See also</span></span>

[<span data-ttu-id="17181-139">Удостоверение для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="17181-139">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="17181-140">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="17181-140">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="17181-141">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="17181-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
