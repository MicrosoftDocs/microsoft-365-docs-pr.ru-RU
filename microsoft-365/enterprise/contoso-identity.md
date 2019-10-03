---
title: Удостоверение для корпорации Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Сведения о том, как Contoso использует службу "удостоверение как услуга" (IDaaS) и предоставляет облачную проверку подлинности для сотрудников, а также федеративную проверку подлинности для партнеров и клиентов.
ms.openlocfilehash: 5c78e8cc9235eb2ca5de091c05d1883ed6cca1b4
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369610"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="e07e5-103">Удостоверение для корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="e07e5-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="e07e5-104">**Сводка.** Сведения о том, как Contoso использует службу "удостоверение как услуга" (IDaaS) и предоставляет облачную проверку подлинности для сотрудников, а также федеративную проверку подлинности для партнеров и клиентов.</span><span class="sxs-lookup"><span data-stu-id="e07e5-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="e07e5-105">Корпорация Майкрософт предоставляет удостоверение как услугу (IDaaS) в своих облачных предложениях с Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e07e5-105">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="e07e5-106">Для перехода на Microsoft 365 Enterprise в решении IDaaS Contoso нужно было использовать локального поставщика удостоверений и по-прежнему включать федеративную проверку подлинности с помощью существующих надежных сторонних поставщиков удостоверений.</span><span class="sxs-lookup"><span data-stu-id="e07e5-106">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="e07e5-107">Лес доменных служб Active Directory Contoso</span><span class="sxs-lookup"><span data-stu-id="e07e5-107">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="e07e5-108">Contoso использует один лес доменных служб Active Directory (AD DS) для contoso.com с семью поддоменами, по одному для каждого региона мира.</span><span class="sxs-lookup"><span data-stu-id="e07e5-108">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="e07e5-109">Главный офис, региональные и вспомогательные офисы содержат контроллеры доменов для локальной проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="e07e5-109">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="e07e5-110">На рисунке 1 показан лес Contoso с региональными доменами для разных частей света, в которых находятся региональные офисы.</span><span class="sxs-lookup"><span data-stu-id="e07e5-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Лес Contoso и домены по всему миру](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="e07e5-112">**Рис. 1. Лес Contoso и домены по всему миру**</span><span class="sxs-lookup"><span data-stu-id="e07e5-112">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="e07e5-113">Contoso необходимо было использовать учетные записи и группы в лесу contoso.com для проверки подлинности и авторизации своих рабочих нагрузок и служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e07e5-113">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="e07e5-114">Инфраструктура федеративной аутентификации Contoso</span><span class="sxs-lookup"><span data-stu-id="e07e5-114">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="e07e5-115">Корпорация Contoso разрешает:</span><span class="sxs-lookup"><span data-stu-id="e07e5-115">Contoso allows:</span></span>

- <span data-ttu-id="e07e5-116">клиентам использовать свои учетные записи Майкрософт, Facebook или Google Mail для входа на общедоступный веб-сайт;</span><span class="sxs-lookup"><span data-stu-id="e07e5-116">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="e07e5-117">поставщикам и партнерам использовать свои учетные записи LinkedIn, Salesforce или Google Mail для входа в партнерскую экстрасеть.</span><span class="sxs-lookup"><span data-stu-id="e07e5-117">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="e07e5-p103">На рисунке 2 показана сеть периметра Contoso, которая содержит общедоступный веб-сайт, партнерскую экстрасеть и набор серверов служб федерации Active Directory (AD FS). Сеть периметра подключена к Интернету, в котором находятся клиенты, партнеры и Интернет-службы.</span><span class="sxs-lookup"><span data-stu-id="e07e5-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Поддержка федеративной аутентификации клиентов и партнеров в компании Contoso](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="e07e5-121">**Рис. 2. Поддержка федеративной аутентификации клиентов и партнеров в корпорации Contoso**</span><span class="sxs-lookup"><span data-stu-id="e07e5-121">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="e07e5-122">Серверы AD FS в DMZ выполняют проверку подлинности учетных данных клиентов с использованием поставщиков удостоверений для доступа к общедоступному веб-сайту и учетных данных партнеров в партнерской экстрасети.</span><span class="sxs-lookup"><span data-stu-id="e07e5-122">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="e07e5-123">В компании Contoso решили сохранить эту инфраструктуру и выделить ее для проверки подлинности клиентов и партнеров.</span><span class="sxs-lookup"><span data-stu-id="e07e5-123">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD B2B and B2C solutions.</span></span> <span data-ttu-id="e07e5-124">Архитекторы удостоверений Contoso изучают преобразование этой инфраструктуры для решений Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) и [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="e07e5-124">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="e07e5-125">Гибридное удостоверение с синхронизацией хэша пароля для облачной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="e07e5-125">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="e07e5-126">Contoso необходимо было использовать собственный локальный лес AD DS при проверке подлинности для доступа к облачным ресурсам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e07e5-126">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="e07e5-127">Было решено использовать синхронизацию хэша пароля (PHS).</span><span class="sxs-lookup"><span data-stu-id="e07e5-127">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="e07e5-128">PHS синхронизирует локальный лес AD DS с клиентом Azure AD подписки на Microsoft 365 Enterprise. При этом копируются учетные записи пользователей и групп, а также хэшированные версии паролей от учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="e07e5-128">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="e07e5-129">Для постоянной синхронизации каталога Contoso развернула средство Azure AD Connect на сервере в собственном ЦОД в Париже.</span><span class="sxs-lookup"><span data-stu-id="e07e5-129">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> <span data-ttu-id="e07e5-130">На рис. 3 показан сервер, на котором Azure AD Connect опрашивает лес AD DS Contoso для выявления изменений и затем синхронизирует эти изменения с клиентом Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e07e5-130">Figure 3 shows the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Инфраструктура синхронизации каталога PHS Contoso](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="e07e5-132">**Рисунок 3. Инфраструктура синхронизации каталога PHS Contoso**</span><span class="sxs-lookup"><span data-stu-id="e07e5-132">**Figure 3: Contoso's PHS directory synchronization infrastructure**</span></span>


## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="e07e5-133">Политики условного доступа для доступа к удостоверению и устройству</span><span class="sxs-lookup"><span data-stu-id="e07e5-133">Conditional access policies for identity and device access</span></span>

<span data-ttu-id="e07e5-134">В Contoso создали набор [политик условного доступа](identity-access-policies.md) Azure AD и Intune для трех уровней защиты:</span><span class="sxs-lookup"><span data-stu-id="e07e5-134">Contoso created a set of Azure AD and Intune [conditional access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="e07e5-135">**Базовая** защита применяется ко всем учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="e07e5-135">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="e07e5-136">Защита **конфиденциальных данных** применяется к старшим руководителям и руководству высшего звена</span><span class="sxs-lookup"><span data-stu-id="e07e5-136">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="e07e5-137">Защита **строго регулируемых данных** применяется к определенным пользователям из финансового, юридического и исследовательского отделов, имеющим доступ к строго регулируемым данным</span><span class="sxs-lookup"><span data-stu-id="e07e5-137">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="e07e5-138">На рис. 4 показан получившийся в итоге набор политик условного доступа к удостоверениям и устройствам.</span><span class="sxs-lookup"><span data-stu-id="e07e5-138">Figure 4 shows their resulting set of identity and device conditional access policies.</span></span>

![Политики условного доступа к удостоверениям и устройствам в Contoso](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="e07e5-140">**Рисунок 4. Политики условного доступа к удостоверениям и устройствам в Contoso**</span><span class="sxs-lookup"><span data-stu-id="e07e5-140">**Figure 4: Contoso’s identity and device conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="e07e5-141">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="e07e5-141">Next step</span></span>

<span data-ttu-id="e07e5-142">[Узнайте,](contoso-win10.md) как в корпорации Contoso используют инфраструктуру System Center Configuration Manager для развертывания Windows 10 Корпоративная в организации и поддержания ее в актуальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="e07e5-142">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="e07e5-143">См. также</span><span class="sxs-lookup"><span data-stu-id="e07e5-143">See also</span></span>

[<span data-ttu-id="e07e5-144">Удостоверение для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="e07e5-144">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="e07e5-145">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="e07e5-145">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e07e5-146">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="e07e5-146">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
