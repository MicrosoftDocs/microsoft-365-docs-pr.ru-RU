---
title: Удостоверение для корпорации Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/17/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Сведения о том, как Contoso использует службу "удостоверение как услуга" (IDaaS) и предоставляет облачную проверку подлинности для сотрудников, а также федеративную проверку подлинности для партнеров и клиентов.
ms.openlocfilehash: bcd83eaafb5df86d9a660aeb74b2e97f7bdc6b7b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277602"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="9aeaa-103">Удостоверение для корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="9aeaa-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="9aeaa-104">**Сводка.** Сведения о том, как Contoso использует службу "удостоверение как услуга" (IDaaS) и предоставляет облачную проверку подлинности для сотрудников, а также федеративную проверку подлинности для партнеров и клиентов.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="9aeaa-105">Корпорация Майкрософт предоставляет удостоверение как услугу (IDaaS) в своих облачных предложениях с Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9aeaa-105">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="9aeaa-106">Для перехода на Microsoft 365 Enterprise в решении IDaaS Contoso нужно было использовать локального поставщика удостоверений и по-прежнему включать федеративную проверку подлинности с помощью существующих надежных сторонних поставщиков удостоверений.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-106">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (AD). To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="9aeaa-107">Лес доменных служб Active Directory Contoso</span><span class="sxs-lookup"><span data-stu-id="9aeaa-107">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="9aeaa-108">Contoso использует один лес доменных служб Active Directory (AD DS) для contoso.com с семью поддоменами, по одному для каждого региона мира.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-108">Contoso uses a single Windows Server Active Directory (AD) forest for contoso.com with seven domains, one for each region of the world.</span></span> <span data-ttu-id="9aeaa-109">Главный офис, региональные и вспомогательные офисы содержат контроллеры доменов для локальной проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-109">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="9aeaa-110">На рисунке 1 показан лес Contoso с региональными доменами для разных частей света, в которых находятся региональные офисы.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="9aeaa-111">**Рис. 1. Лес Contoso и домены по всему миру**</span><span class="sxs-lookup"><span data-stu-id="9aeaa-111">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="9aeaa-112">Contoso необходимо было использовать учетные записи и группы в лесу contoso.com для проверки подлинности и авторизации своих рабочих нагрузок и служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-112">Contoso wants to use the accounts and groups in the contoso.com forest for authentication and authorization for its cloud-based apps and workloads.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="9aeaa-113">Инфраструктура федеративной аутентификации Contoso</span><span class="sxs-lookup"><span data-stu-id="9aeaa-113">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="9aeaa-114">Корпорация Contoso разрешает:</span><span class="sxs-lookup"><span data-stu-id="9aeaa-114">Contoso allows:</span></span>

- <span data-ttu-id="9aeaa-115">клиентам использовать свои учетные записи Майкрософт, Facebook или Google Mail для входа на общедоступный веб-сайт;</span><span class="sxs-lookup"><span data-stu-id="9aeaa-115">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="9aeaa-116">поставщикам и партнерам использовать свои учетные записи LinkedIn, Salesforce или Google Mail для входа в партнерскую экстрасеть.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-116">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="9aeaa-p103">На рисунке 2 показана сеть периметра Contoso, которая содержит общедоступный веб-сайт, партнерскую экстрасеть и набор серверов служб федерации Active Directory (AD FS). Сеть периметра подключена к Интернету, в котором находятся клиенты, партнеры и Интернет-службы.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="9aeaa-119">**Рис. 2. Поддержка федеративной аутентификации клиентов и партнеров в корпорации Contoso**</span><span class="sxs-lookup"><span data-stu-id="9aeaa-119">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="9aeaa-120">Серверы AD FS в сети периметра выполняют аутентификацию клиентов на общедоступном веб-сайте и партнеров в партнерской экстрасети.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-120">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="9aeaa-p104">Корпорация Contoso решила сохранить эту инфраструктуру и выделить ее для проверки подлинности клиентов и партнеров. Специалисты по удостоверениям Contoso изучают возможность преобразования этой инфраструктуры в решения Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) и [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="9aeaa-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="9aeaa-123">Гибридное удостоверение с синхронизацией хэша пароля для облачной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="9aeaa-123">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="9aeaa-124">Contoso необходимо было использовать собственный локальный лес AD DS при проверке подлинности для доступа к облачным ресурсам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-124">Contoso wanted to leverage its on-premises Windows Server AD forest for authentication to Microsoft 365 cloud resources. It decided on pass-through authentication (PTA) with password hash synchronization (PHS).</span></span> <span data-ttu-id="9aeaa-125">Было решено использовать синхронизацию хэша пароля (PHS).</span><span class="sxs-lookup"><span data-stu-id="9aeaa-125">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="9aeaa-126">PHS синхронизирует локальный лес AD DS с клиентом Azure AD подписки на Microsoft 365 Enterprise. При этом копируются учетные записи пользователей и групп, а также хэшированные версии паролей от учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-126">PHS synchronizes the on-premises Windows Server AD forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords. Contoso decided on PHS to provide an alternate method of authentication directly with the Azure AD tenant in the event that PTA is not available.</span></span> 

<span data-ttu-id="9aeaa-127">Для постоянной синхронизации каталога Contoso развернула средство Azure AD Connect на сервере в собственном ЦОД в Париже.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-127">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter. Figure 4 shows the server running Azure AD Connect polling the Contoso Windows Server AD forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span> <span data-ttu-id="9aeaa-128">На рис. 3 показан сервер, на котором Azure AD Connect опрашивает лес AD DS Contoso для выявления изменений и затем синхронизирует эти изменения с клиентом Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-128">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter. Figure 4 shows the server running Azure AD Connect polling the Contoso Windows Server AD forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="9aeaa-129">**Рисунок 3. Инфраструктура синхронизации каталога PHS Contoso**</span><span class="sxs-lookup"><span data-stu-id="9aeaa-129">**Figure 3: Contoso's directory synchronization infrastructure**</span></span>


## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="9aeaa-130">Политики условного доступа для доступа к удостоверению и устройству</span><span class="sxs-lookup"><span data-stu-id="9aeaa-130">Conditional access policies for identity and device access</span></span>

<span data-ttu-id="9aeaa-131">В Contoso создали набор [политик условного доступа](identity-access-policies.md) Azure AD и Intune для трех уровней защиты:</span><span class="sxs-lookup"><span data-stu-id="9aeaa-131">Contoso created a set of Azure AD and Intune [conditional access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="9aeaa-132">**Базовая** защита применяется ко всем учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-132">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="9aeaa-133">Защита **конфиденциальных данных** применяется к старшим руководителям и руководству высшего звена</span><span class="sxs-lookup"><span data-stu-id="9aeaa-133">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="9aeaa-134">Защита **строго регулируемых данных** применяется к определенным пользователям из финансового, юридического и исследовательского отделов, имеющим доступ к строго регулируемым данным</span><span class="sxs-lookup"><span data-stu-id="9aeaa-134">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="9aeaa-135">На рис. 4 показан получившийся в итоге набор политик условного доступа к удостоверениям и устройствам.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-135">Figure 5 shows their resulting set of conditional access policies for identity.</span></span>

![](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="9aeaa-136">**Рисунок 4. Политики условного доступа к удостоверениям и устройствам в Contoso**</span><span class="sxs-lookup"><span data-stu-id="9aeaa-136">**Figure 4: Contoso’s identity and device conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="9aeaa-137">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="9aeaa-137">Next step</span></span>

<span data-ttu-id="9aeaa-138">[Узнайте,](contoso-win10.md) как в корпорации Contoso используют инфраструктуру System Center Configuration Manager для развертывания Windows 10 Корпоративная в организации и поддержания ее в актуальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-138">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="9aeaa-139">См. также</span><span class="sxs-lookup"><span data-stu-id="9aeaa-139">See also</span></span>

[<span data-ttu-id="9aeaa-140">Удостоверение для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="9aeaa-140">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="9aeaa-141">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="9aeaa-141">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9aeaa-142">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="9aeaa-142">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
