---
title: Базовая инфраструктура Microsoft 365 корпоративный для некорпоративных организаций
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Предлагаем упрощенную пошаговую инструкцию для базовой инфраструктуры Microsoft 365 корпоративный для некорпоративных организаций.
ms.openlocfilehash: 8e2c254bf352baa14ff62dad500e5cdfa0af4563
ms.sourcegitcommit: 639607bbf02bdedd3fa5cd7b0984b422fe6c874e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "35624637"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-for-non-enterprises"></a><span data-ttu-id="3e7c7-103">Базовая инфраструктура Microsoft 365 корпоративный для некорпоративных организаций</span><span class="sxs-lookup"><span data-stu-id="3e7c7-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="3e7c7-104">Некорпоративные организации также могут развернуть Microsoft 365 корпоративный, чтобы воспользоваться преимуществами интегрированной и безопасной инфраструктуры, удобной для совместной работы и развития творческого потенциала.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-104">Non-enterprise organizations can also deploy Microsoft 365 Enterprise and realize the business value of an integrated and secure infrastructure that enables teamwork and unlocks creativity.</span></span> <span data-ttu-id="3e7c7-105">Характерные особенности некорпоративных организаций:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-105">A non-enterprise typically has:</span></span>

- <span data-ttu-id="3e7c7-106">Локальная инфраструктура — небольшая (серверы электронной почты, файловые серверы и домен доменных служб Active Directory) или вовсе отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-106">A small amount of on-premises IT infrastructure, such as email and file servers and an Active Directory Domain Services (AD DS) domain, or none at all.</span></span>
- <span data-ttu-id="3e7c7-107">Небольшая численность ИТ-отдела, причем большинство ИТ-сотрудников занимаются задачами широкого профиля, а не специализируются на определенных задачах, таких как сети или электронная почта.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-107">A small IT staff, most of whom are IT generalists, rather than specialists in a specific technology or workload such as networking or email.</span></span>

<span data-ttu-id="3e7c7-108">Для небольших некорпоративных организаций корпорация Майкрософт предлагает [Microsoft 365 бизнес](https://www.microsoft.com/microsoft-365/business).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-108">For your smaller, non-enterprise organization, Microsoft offers [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="3e7c7-109">Тем не менее, есть причины, в силу которых вам моет потребоваться Microsoft 365 корпоративный, например:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-109">However, there are reasons why you might need Microsoft 365 Enterprise, such as:</span></span>

- <span data-ttu-id="3e7c7-110">Вашей организации требуется или в будущем потребуется более 300 лицензий Microsoft 365, тогда как в Microsoft 365 бизнес это максимальное количество.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-110">Your organization needs more or will need more than 300 Microsoft 365 licenses, which is the maximum for Microsoft 365 Business.</span></span>
- <span data-ttu-id="3e7c7-111">Вашей организации требуются расширенные возможности эффективной работы, голосовой связи и аналитики, недоступные в Microsoft 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-111">Your organization needs the advanced productivity, voice, security, and analytics that are not available with Microsoft 365 Business.</span></span>

<span data-ttu-id="3e7c7-112">В этой статье приведена упрощенная пошаговая инструкция по развертыванию базовой инфраструктуры Microsoft 365 корпоративный для вашей некорпоративной организации.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-112">This article steps you through a simplified deployment of the foundation infrastructure of Microsoft 365 Enterprise suitable for your non-enterprise.</span></span>

## <a name="first-set-up-your-subscription"></a><span data-ttu-id="3e7c7-113">Во-первых, необходимо настроить подписку.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-113">First, set up your subscription</span></span>

<span data-ttu-id="3e7c7-114">Нужно настроить домены системы доменных имен (DNS) для своей подписки.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-114">You must set up the Domain Name System (DNS) domains for your subscription.</span></span> <span data-ttu-id="3e7c7-115">Если у вас уже есть подписка на Office 365, то это должно быть уже сделано.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-115">If you already have an Office 365 subscription, this should have been done.</span></span> <span data-ttu-id="3e7c7-116">Если нет, то выполните инструкции, перечисленные в статье [Добавление домена в Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-116">If not, follow the instructions in [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span></span>

<span data-ttu-id="3e7c7-117">Затем нужно настроить дополнительные параметры безопасности для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-117">Next, you need to configure additional security for Microsoft 365.</span></span> <span data-ttu-id="3e7c7-118">Выполните инструкции, перечисленные в статье [Настройка усиленной защиты](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-118">Follow the instructions in [Configure increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

## <a name="phase-1-networking"></a><span data-ttu-id="3e7c7-119">Этап 1. Сеть</span><span class="sxs-lookup"><span data-stu-id="3e7c7-119">Phase 1: Networking</span></span>

<span data-ttu-id="3e7c7-120">В некорпоративных организациях обычно используется локальное подключение к Интернету, при этом не используются прокси-серверы, брандмауэры и устройства проверки пакетов.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-120">Non-enterprise organizations typically have local Internet connections in each office and do not use proxy servers, firewalls, or packet inspection devices.</span></span> <span data-ttu-id="3e7c7-121">У поставщика услуг Интернета (ISP), обслуживающего каждый офис, имеется локальный для этого региона DNS-сервер, поэтому трафик направляется на сетевое расположение Microsoft 365, ближайшее к офисам и работающим в этих офисах локальным пользователям.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-121">The Internet service provider (ISP) serving each office has a regionally local DNS server so that traffic is directed to the Microsoft 365 network location that is closest to your offices and their on-premises users.</span></span>

<span data-ttu-id="3e7c7-122">Таким образом, необходимо убедиться у поставщика услуг Интернета, что подключение в каждом офисе:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-122">Therefore, you only need to verify with your ISP that the connection at each of your office locations:</span></span>

- <span data-ttu-id="3e7c7-123">Использует локальный DNS-сервер для этого региона.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-123">Uses a regionally local DNS server.</span></span>
- <span data-ttu-id="3e7c7-124">Пригодно для существующих и будущих потребностей при увеличении объема используемых облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-124">Is adequate for current and future needs as your users begin using more Microsoft 365 cloud services.</span></span>

<span data-ttu-id="3e7c7-125">Если вы используете прокси-серверы, брандмауэры или средства проверки пакетов, дополнительные сведения см. в  статье [Сетевая инфраструктура для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="3e7c7-125">If you do use proxy servers, firewalls, or packet inspection devices, see [Networking infrastructure for Microsoft 365 Enterprise](networking-infrastructure.md) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="3e7c7-126">Конфигурация на этом этапе</span><span class="sxs-lookup"><span data-stu-id="3e7c7-126">Your configuration so far</span></span>

<span data-ttu-id="3e7c7-127">Вот наглядное сводное представление, на котором выделен элемент 1-го этапа.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-127">Here is a visual summary with the Phase 1 element highlighted.</span></span> <span data-ttu-id="3e7c7-128">**У вашей организации** может быть несколько офисов, в каждом из которых используется локальное подключение к Интернету, при этом поставщик услуг Интернета использует локальный DNS-сервер для этого региона.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-128">**Your organization** can be multiple offices, each of which has a local Internet connection with an ISP that uses a regionally local DNS server.</span></span> <span data-ttu-id="3e7c7-129">Используя подключение к Интернету, пользователи в каждом офисе подключаются к ближайшему расположению сети Microsoft 365 и к ресурсам вашей подписки Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-129">Through the ISP, users in each office can reach the nearest Microsoft 365 network location and the resources of your Microsoft 365 subscription.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a><span data-ttu-id="3e7c7-130">Этап 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="3e7c7-130">Phase 2: Identity</span></span>

<span data-ttu-id="3e7c7-131">Каждый сотрудник вашей организации должен иметь возможность войти в систему. Для этого требуется учетная запись пользователя в клиенте Azure Active Directory (Azure AD) вашей подписки Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-131">Each of the employees of your organization must be able to sign in, which requires a user account in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="3e7c7-132">Для размещения учетных записей используются группы. Другие группы используются для общения и для получения доступа к разрешенным ресурсам, например, к сайтам SharePoint Online или к команде.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-132">Groups are then used to contain user accounts and other groups to communicate or gain access to permissioned resources, such as a SharePoint Online site or a team.</span></span> 

### <a name="administrator-accounts"></a><span data-ttu-id="3e7c7-133">Учетные записи администратора</span><span class="sxs-lookup"><span data-stu-id="3e7c7-133">Administrator accounts</span></span>

<span data-ttu-id="3e7c7-134">Для защиты учетных записей глобальных администраторов необходимо включить требование очень стойких паролей и многофакторной проверки подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-134">Protect your global administrator user accounts by requiring very strong passwords and multi-factor authentication (MFA).</span></span> <span data-ttu-id="3e7c7-135">Дополнительные сведения см. в статье [Защита учетных записей глобальных администраторов](identity-designate-protect-admin-accounts.md#protect-global-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-135">See [Protect your Office 365 global administrator accounts](identity-designate-protect-admin-accounts.md#protect-global-administrator-accounts) for more information about configuration.</span></span>

<span data-ttu-id="3e7c7-136">Если в вашей организации требуется высокий уровень безопасности и вы используете Microsoft 365 корпоративный E5, используйте службу Privileged Identity Management в Azure AD, чтобы включить предоставление своевременного доступа администраторам.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-136">If your organization requires high security and you have Microsoft 365 Enterprise E5, use Azure AD Privileged Identity Management to enable just-in-time administrator access.</span></span> <span data-ttu-id="3e7c7-137">Дополнительные сведения см. в статье [Настройка глобальных администраторов по требованию](identity-designate-protect-admin-accounts.md#set-up-on-demand-global-administrators).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-137">See [Set up on-demand global administrators](identity-designate-protect-admin-accounts.md#set-up-on-demand-global-administrators) for more information.</span></span>

### <a name="recommendations-for-groups"></a><span data-ttu-id="3e7c7-138">Рекомендации для групп</span><span class="sxs-lookup"><span data-stu-id="3e7c7-138">Recommendations for groups</span></span>

<span data-ttu-id="3e7c7-139">Если у вас есть локальный домен AD DS, используйте эти группы в Microsoft 365 корпоративный в качестве групп в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-139">If you have an on-premises AD DS domain, continue to use those groups in Microsoft 365 Enterprise as groups in Azure AD.</span></span>

<span data-ttu-id="3e7c7-140">Если у вас нет локального домена AD DS, создайте группы безопасности в Azure AD со следующими уровнями безопасности.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-140">If you don’t have an on-premises AD DS domain, create security groups in Azure AD using these levels of security.</span></span>

| <span data-ttu-id="3e7c7-141">Уровень безопасности</span><span class="sxs-lookup"><span data-stu-id="3e7c7-141">Security level</span></span> | <span data-ttu-id="3e7c7-142">Описание</span><span class="sxs-lookup"><span data-stu-id="3e7c7-142">Description</span></span> | <span data-ttu-id="3e7c7-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="3e7c7-143">Examples</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="3e7c7-144">Базовый</span><span class="sxs-lookup"><span data-stu-id="3e7c7-144">Baseline</span></span> | <span data-ttu-id="3e7c7-145">Это минимальный стандарт по умолчанию, используемый для защиты данных и удостоверений устройств, обращающихся к данным.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-145">This is a minimum and default  standard for protecting data and the identities and devices that access your data.</span></span> <BR><BR> <span data-ttu-id="3e7c7-146">Этот уровень используется для большей части данных организации, находящихся под управлением большей части пользователей.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-146">This is typically most of your organization’s data managed by most of your users.</span></span> | <span data-ttu-id="3e7c7-147">Группы для рядовых сотрудников, включая направления продаж, маркетинга, поддержки, администрирования и производства.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-147">Groups for first line workers, such as sales, marketing, support, administration, and manufacturing.</span></span> |
| <span data-ttu-id="3e7c7-148">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="3e7c7-148">Sensitive</span></span> | <span data-ttu-id="3e7c7-149">На этом уровне обеспечивается дополнительная безопасность для данных, которым требуется более надежная защита по сравнению с базовым уровнем.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-149">This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="3e7c7-150">В состав этих групп входят пользователи, которые используют и создают конфиденциальные данные, относящиеся к отделам и проектам, не предназначенным для всеобщего доступа.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-150">These groups contain users that use and create sensitive data that is specific to departments and projects that are not meant to be available to everyone.</span></span> | <span data-ttu-id="3e7c7-151">Группы продуктов и маркетинга, занимающиеся разработкой будущих продуктов</span><span class="sxs-lookup"><span data-stu-id="3e7c7-151">Product or marketing teams that are developing future products</span></span> |
| <span data-ttu-id="3e7c7-152">Строго контролируемый</span><span class="sxs-lookup"><span data-stu-id="3e7c7-152">Highly regulated</span></span> | <span data-ttu-id="3e7c7-153">Это высший уровень защиты, обычно он требуется для относительно небольшого объема строго засекреченных данных, относящихся к интеллектуальной собственности или к коммерческим тайнам. Также этот уровень необходим для данным, для которых обязательно выполнение требований безопасности.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-153">Highly regulated: This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span> |  <span data-ttu-id="3e7c7-154">Исследовательские, юридические и финансовые группы, а также группы, в которых хранятся или используются данные по клиентам или партнерам.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-154">Research, legal, and financial teams, or teams storing or using customer or partner data.</span></span> |
||||

### <a name="hybrid-identity"></a><span data-ttu-id="3e7c7-155">Гибридная идентификация</span><span class="sxs-lookup"><span data-stu-id="3e7c7-155">Hybrid identity</span></span>

<span data-ttu-id="3e7c7-156">Если у вас есть локальный домен AD DS, необходимо синхронизировать набор учетных записей пользователей, групп и контактов вашего домена с клиентом Azure AD вашей подписки Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-156">If you have an on-premises AD DS domain, you need to synchronize the set of user accounts, groups, and contacts of your domain with the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="3e7c7-157">Для ваших некорпоративных пользователей настройте Azure AD Connect на сервере с синхронизацией хэша паролей (PHS).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-157">For your non-enterprise, you configure Azure AD Connect on a server with password hash synchronization (PHS).</span></span> <span data-ttu-id="3e7c7-158">Дополнительные сведения см. в статье [Синхронизация удостоверений](identity-azure-ad-connect.md).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-158">See [Synchronize identities](identity-azure-ad-connect.md) for more information.</span></span>

### <a name="more-secure-user-access-with-conditional-access-policies"></a><span data-ttu-id="3e7c7-159">Более безопасный доступ пользователей с помощью политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="3e7c7-159">More secure user access with conditional access policies</span></span>

<span data-ttu-id="3e7c7-160">Azure AD проверяет условия входа пользователей и может задействовать политики условного доступа, чтобы предоставить или запретить доступа, а также требовать выполнения дальнейших действий для завершения входа.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-160">Azure AD evaluates the conditions of user sign-ins and can use conditional access policies to grant or deny access and impose further actions that must be taken to complete the sign-in.</span></span> <span data-ttu-id="3e7c7-161">Например, если служба Azure AD определит, что вход происходит в условиях среднего или высокого риска, она может потребовать, чтобы пользователь прошел многофакторную проверку подлинности для завершения входа.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-161">For example, if Azure AD determines that the sign-in is happening under medium or high-risk conditions, it can require the user to perform MFA to complete the sign-in.</span></span>

<span data-ttu-id="3e7c7-162">Политики условного доступа применяются к учетным записям пользователей и к группам.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-162">You apply conditional access policies to user accounts or groups.</span></span> <span data-ttu-id="3e7c7-163">Чтобы упростить назначение политик условного доступа, создайте в организации следующие группы безопасности AD:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-163">To facilitate an easier assignment of conditional access policies, create these Azure AD security groups in your organization:</span></span>

- <span data-ttu-id="3e7c7-164">BASELINE</span><span class="sxs-lookup"><span data-stu-id="3e7c7-164">Baseline</span></span>

  <span data-ttu-id="3e7c7-165">Содержит группы и учетные записи пользователей с доступом к базовым данным.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-165">Contains the groups or user accounts for users with access to baseline data.</span></span>

- <span data-ttu-id="3e7c7-166">SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="3e7c7-166">Sensitive</span></span>

  <span data-ttu-id="3e7c7-167">Содержит группы и учетные записи пользователей с доступом к конфиденциальным данным.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-167">Contains the groups or user accounts for users with access to sensitive data.</span></span>

- <span data-ttu-id="3e7c7-168">HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-168">HIGHLY-REGULATED</span></span>

  <span data-ttu-id="3e7c7-169">Содержит группы или учетные записи пользователей с доступом к строго контролируемым данным.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-169">Contains the groups or user accounts for users with access to highly regulated data.</span></span>

- <span data-ttu-id="3e7c7-170">COND-ACCESS-EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="3e7c7-170">COND-ACCESS-EXCLUDE</span></span>

  <span data-ttu-id="3e7c7-171">Пустая группа, которую можно использовать, чтобы временно исключать пользователей из политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-171">An empty group that you can use to temporarily exclude a user from conditional access policies.</span></span>

<span data-ttu-id="3e7c7-172">Ниже приведен список политик условного доступа Azure AD, которые следует включить или создать.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-172">Here is the list of Azure AD conditional access policies to enable or create.</span></span>

| <span data-ttu-id="3e7c7-173">Политика условного доступа Azure AD</span><span class="sxs-lookup"><span data-stu-id="3e7c7-173">Azure AD conditional access policy</span></span> | <span data-ttu-id="3e7c7-174">Группы, к которым применяется эта политика</span><span class="sxs-lookup"><span data-stu-id="3e7c7-174">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="3e7c7-175">Базовая политика: требовать многофакторную проверку подлинности для администраторов</span><span class="sxs-lookup"><span data-stu-id="3e7c7-175">Baseline policy: Require MFA for admins</span></span> | <span data-ttu-id="3e7c7-176">Эта политика применяется к ролям администраторов, поэтому нет необходимости создавать группы.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-176">This policy applies to admin roles, so no groups need to be specified.</span></span> <span data-ttu-id="3e7c7-177">Эту политику просто нужно включить.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-177">This policy just needs to be enabled.</span></span> <span data-ttu-id="3e7c7-178">Все остальные политики необходимо создать и включить.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-178">All subsequent policies need to be created and enabled.</span></span> |
| <span data-ttu-id="3e7c7-179">Блокировать клиенты, не поддерживающие современную проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="3e7c7-179">Block clients that don't support modern authentication</span></span> | <span data-ttu-id="3e7c7-180">В параметрах политики выберите "Все пользователи".</span><span class="sxs-lookup"><span data-stu-id="3e7c7-180">Select “All users” in the policy settings.</span></span> |
| <span data-ttu-id="3e7c7-181">Требовать многофакторную проверку подлинности при среднем или высоком риске входа (требуется Microsoft 365 корпоративный E5)</span><span class="sxs-lookup"><span data-stu-id="3e7c7-181">Require MFA when sign-in risk is medium or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="3e7c7-182">BASELINE</span><span class="sxs-lookup"><span data-stu-id="3e7c7-182">Baseline</span></span> |
| <span data-ttu-id="3e7c7-183">Требовать многофакторную проверку подлинности при низком, среднем или высоком риске входа (требуется Microsoft 365 корпоративный E5)</span><span class="sxs-lookup"><span data-stu-id="3e7c7-183">Require MFA when sign-in risk is low, medium, or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="3e7c7-184">SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="3e7c7-184">Sensitive</span></span> |
| <span data-ttu-id="3e7c7-185">Всегда требовать многофакторную проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="3e7c7-185">Always require MFA</span></span> | <span data-ttu-id="3e7c7-186">HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-186">HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="3e7c7-187">Требовать использования одобренных приложений на устройствах с iOS и Android</span><span class="sxs-lookup"><span data-stu-id="3e7c7-187">Require approved apps on iOS and Android devices</span></span> | <span data-ttu-id="3e7c7-188">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-188">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="3e7c7-189">Требовать использования соответствующих политике компьютеров</span><span class="sxs-lookup"><span data-stu-id="3e7c7-189">Require compliant PCs</span></span> | <span data-ttu-id="3e7c7-190">BASELINE</span><span class="sxs-lookup"><span data-stu-id="3e7c7-190">Baseline</span></span> |
| <span data-ttu-id="3e7c7-191">Требовать использования соответствующих политике компьютеров, устройств с iOS и Android</span><span class="sxs-lookup"><span data-stu-id="3e7c7-191">Require compliant PCs and iOS and Android devices</span></span> | <span data-ttu-id="3e7c7-192">SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-192">SENSITIVE, HIGHLY-REGULATED</span></span> |
|||

<span data-ttu-id="3e7c7-193">Здесь нужно создать и включить политику риска пользователей в службе защиты идентификации Azure AD (требуется Microsoft 365 корпоративный E5)</span><span class="sxs-lookup"><span data-stu-id="3e7c7-193">Here is the Azure AD Identity Protection (requires Microsoft 365 Enterprise E5) user risk policy to create and enable.</span></span>

| <span data-ttu-id="3e7c7-194">Политика риска пользователя в службе защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="3e7c7-194">Azure AD Identity Protection user risk policy</span></span> | <span data-ttu-id="3e7c7-195">Группы, к которым применяется эта политика</span><span class="sxs-lookup"><span data-stu-id="3e7c7-195">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="3e7c7-196">Пользователи с высоким уровнем риска должны сменить пароль</span><span class="sxs-lookup"><span data-stu-id="3e7c7-196">High risk users must change passwords</span></span> | <span data-ttu-id="3e7c7-197">В параметрах политики выберите "Все пользователи".</span><span class="sxs-lookup"><span data-stu-id="3e7c7-197">Select “All users” in the policy settings.</span></span> |
|||

<span data-ttu-id="3e7c7-198">Инструкции см. в статье [Основные политики идентификации и доступа для устройств](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-198">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="groups-for-easier-management"></a><span data-ttu-id="3e7c7-199">Упрощение управления с помощью групп</span><span class="sxs-lookup"><span data-stu-id="3e7c7-199">Groups for easier management</span></span>

<span data-ttu-id="3e7c7-200">Ниже описаны некоторые функции, позволяющие упростить управление группами и лицензированием.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-200">Here are some features that can make group and licensing management easier for you.</span></span>

| <span data-ttu-id="3e7c7-201">Функция</span><span class="sxs-lookup"><span data-stu-id="3e7c7-201">Feature</span></span> | <span data-ttu-id="3e7c7-202">Использование</span><span class="sxs-lookup"><span data-stu-id="3e7c7-202">Use</span></span> |
|:------|:-----|
| <span data-ttu-id="3e7c7-203">Самостоятельное управление группами</span><span class="sxs-lookup"><span data-stu-id="3e7c7-203">Self-service group management</span></span> | <span data-ttu-id="3e7c7-204">Разрешите управление группами Azure AD владельцам групп, а не ИТ-специалистам.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-204">Allow management of Azure AD groups by group owners instead of IT staff.</span></span> <span data-ttu-id="3e7c7-205">Дополнительные сведения см. в статье [Самостоятельное управление группами](identity-self-service-group-management.md#allow-users-to-create-and-manage-their-own-groups).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-205">See [Self-service group management](identity-self-service-group-management.md#allow-users-to-create-and-manage-their-own-groups) for more information.</span></span> |
| <span data-ttu-id="3e7c7-206">Динамическое членство в группах</span><span class="sxs-lookup"><span data-stu-id="3e7c7-206">Dynamic group membership</span></span> | <span data-ttu-id="3e7c7-207">Настройте автоматическое добавление или удаление учетных записей пользователей из групп Azure AD на основании атрибутов учетных записей пользователей, таких как отдел или страна.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-207">Configure automatic addition or removal of user accounts from Azure AD groups based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="3e7c7-208">Дополнительные сведения см. в статье [Динамическое членство в группах](identity-self-service-group-management.md#set-up-dynamic-group-membership).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-208">See [Dynamic group membership](identity-self-service-group-management.md#set-up-dynamic-group-membership) for more information.</span></span> |
| <span data-ttu-id="3e7c7-209">Групповое лицензирование</span><span class="sxs-lookup"><span data-stu-id="3e7c7-209">Group-based licensing</span></span> | <span data-ttu-id="3e7c7-210">Используйте членство в группах, чтобы автоматически назначать лицензии учетным записям пользователей или отменять назначение.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-210">Use group membership to automatically assign or unassign licenses to user accounts.</span></span> <span data-ttu-id="3e7c7-211">Дополнительные сведения см. в статье [Групповое лицензирование](identity-self-service-group-management.md#set-up-automatic-licensing).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-211">See [Group-based licensing](identity-self-service-group-management.md#set-up-automatic-licensing) for more information.</span></span> |
|  |  |

<span data-ttu-id="3e7c7-212">При использовании группового лицензирования создайте группу с названием LICENSED. В этой группе будут содержаться имена учетных записей пользователей, которым назначается лицензия Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-212">If you are using group-based licensing, create a group named LICENSED to contain user account names that are assigned a Microsoft 365 Enterprise license.</span></span>

### <a name="monitor-user-access"></a><span data-ttu-id="3e7c7-213">Мониторинг доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="3e7c7-213">Monitor user access</span></span>

<span data-ttu-id="3e7c7-214">Если вы используете Microsoft 365 корпоративный E5, можно использовать защиту идентификации Azure AD для мониторинга и анализа попыток входа пользователей на предмет компрометации учетных данных.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-214">If you have Microsoft 365 Enterprise E5, you can use Azure AD Identity Protection to monitor and analyze user sign-ins for credential compromise.</span></span> <span data-ttu-id="3e7c7-215">Дополнительные сведения см. в статье [Защита от компрометации учетных данных](identity-multi-factor-authentication.md#protect-against-credential-compromise).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-215">See [Protect against credential compromise](identity-multi-factor-authentication.md#protect-against-credential-compromise) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="3e7c7-216">Конфигурация на этом этапе</span><span class="sxs-lookup"><span data-stu-id="3e7c7-216">Your configuration so far</span></span>

<span data-ttu-id="3e7c7-217">Вот наглядное представление этапа "Идентификация" для гибридной идентификации, на котором выделены новые элементы.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-217">Here is a visual summary of the Identity phase for hybrid identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
<span data-ttu-id="3e7c7-218">Новые и выделенные элементы этапа "Гибридная идентификация" включают:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-218">The new and highlighted hybrid identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | <span data-ttu-id="3e7c7-219">Локальный домен AD DS с учетными записями пользователей и группами.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-219">An on-premises AD DS domain with user accounts and groups.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | <span data-ttu-id="3e7c7-220">Сервер под управлением Windows, на котором запущено решение Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-220">A Windows-based server running Azure AD Connect.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | <span data-ttu-id="3e7c7-221">Синхронизированный набор учетных записей и групп AD DS в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-221">The synchronized set of AD DS accounts and groups in Azure AD.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="3e7c7-222">Параметры Azure AD для проверки подлинности, защиты глобальных учетных записей и более удобного управления группами и лицензиями.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-222">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="3e7c7-223">Политики условного доступа Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-223">Azure AD conditional access policies.</span></span> |
|||

<span data-ttu-id="3e7c7-224">Вот наглядное представление этапа "Идентификация" для только облачной идентификации, на котором выделены новые элементы.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-224">Here is a visual summary of the Identity phase for cloud-only identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config-cloud-only.png)
 
<span data-ttu-id="3e7c7-225">Новые и выделенные элементы этапа "Только облачная идентификация" включают:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-225">The new and highlighted cloud-only identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="3e7c7-226">Параметры Azure AD для проверки подлинности, защиты глобальных учетных записей и более удобного управления группами и лицензиями.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-226">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="3e7c7-227">Политики условного доступа Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-227">Azure AD conditional access policies.</span></span> |
|||



## <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="3e7c7-228">Этап 3. Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="3e7c7-228">Phase 3: Windows 10 Enterprise</span></span>

<span data-ttu-id="3e7c7-229">Чтобы убедиться, что устройства с Windows 10 Корпоративная интегрированы в инфраструктуру удостоверений и безопасности Microsoft 365, можно использовать следующие способы:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-229">To ensure that your Windows 10 Enterprise devices are integrated into the identity and security infrastructure of Microsoft 365, here are your options:</span></span>

- <span data-ttu-id="3e7c7-230">Гибридная среда (есть локальный домен AD DS)</span><span class="sxs-lookup"><span data-stu-id="3e7c7-230">Hybrid (you have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="3e7c7-231">Все существующие устройства с Windows 10 Корпоративная, уже присоединенные к вашему домену AD DS, необходимо подключить к клиенту Azure AD</span><span class="sxs-lookup"><span data-stu-id="3e7c7-231">For each existing Windows 10 Enterprise device already joined to your AD DS domain, join them to the Azure AD tenant.</span></span> <span data-ttu-id="3e7c7-232">Инструкции см. в статье [Настройка гибридных устройств, присоединенных к Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=872870).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-232">See [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870) for the instructions.</span></span>

  <span data-ttu-id="3e7c7-233">Все новые устройства с Windows 10 Корпоративная необходимо присоединить к домену AD DS, а затем присоединить к клиенту Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-233">For each new Windows 10 Enterprise device, join them to your AD DS domain, and then join them to the Azure AD tenant.</span></span>

  <span data-ttu-id="3e7c7-234">Все устройства с Windows 10 Корпоративная необходимо зарегистрировать в службе управления мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-234">For each Windows 10 Enterprise device, enroll them for mobile device management.</span></span> <span data-ttu-id="3e7c7-235">Инструкции см. в статье [Регистрация устройств с Windows 10 в Intune с помощью групповой политики](https://go.microsoft.com/fwlink/p/?linkid=872871).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-235">See [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for the instructions.</span></span>

- <span data-ttu-id="3e7c7-236">Только облачная среда (нет локального домена AD DS)</span><span class="sxs-lookup"><span data-stu-id="3e7c7-236">Cloud-only (you do not have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="3e7c7-237">Присоедините каждое устройство с Windows 10 Корпоративная к клиенту Azure AD своей подписки.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-237">Join each Windows 10 Enterprise device to the Azure AD tenant of your subscription.</span></span>

  <span data-ttu-id="3e7c7-238">Дополнительные сведения см. в статье [Присоединение рабочего устройства к сети организации](https://docs.microsoft.com/ru-RU/azure/active-directory/user-help/user-help-join-device-on-network).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-238">See [Join your work device to your organization's network](https://docs.microsoft.com/en-us/azure/active-directory/user-help/user-help-join-device-on-network) for more information.</span></span>


<span data-ttu-id="3e7c7-239">После установки и присоединения на все устройства с Windows 10 Корпоративная будут автоматически устанавливать устанавливаться обновления из облачной службы Центра обновления Windows для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-239">Once installed and joined, each Windows 10 Enterprise device automatically installs updates from the Windows Update for Business cloud service.</span></span> <span data-ttu-id="3e7c7-240">В некорпоративных организациях обычно не нужно настраивать инфраструктуру для распространения и установки обновлений Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-240">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute and install Windows 10 updates.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="3e7c7-241">Конфигурация на этом этапе</span><span class="sxs-lookup"><span data-stu-id="3e7c7-241">Your configuration so far</span></span>

<span data-ttu-id="3e7c7-242">Вот наглядное представление этапа развертывания Windows 10 Корпоративная, на котором выделены новые элементы.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-242">Here is a visual summary of the Windows 10 Enterprise phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
<span data-ttu-id="3e7c7-243">Новые и выделенные элементы этапа "Windows 10 Корпоративная" включают:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-243">The new and highlighted Windows 10 Enterprise elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | <span data-ttu-id="3e7c7-244">ОС Windows 10 Корпоративная установлена на устройствах с Windows, например, на локальном ноутбуке.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-244">Windows 10 Enterprise installed on Windows devices, with an on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | <span data-ttu-id="3e7c7-245">Центр обслуживания корпоративного лицензирования предоставляет образы для новой установки Windows 10 Корпоративная; служба Центра обновления Windows для бизнеса предоставляет последние обновления.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-245">The Volume Licensing Service Center, which provides images for new installations of Windows 10 Enterprise, and the Windows Update for Business service, which provides the latest updates.</span></span> |
|||

## <a name="phase-4-office-365-proplus"></a><span data-ttu-id="3e7c7-246">Этап 4. Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="3e7c7-246">Phase 4: Office 365 ProPlus</span></span>

<span data-ttu-id="3e7c7-247">В состав Microsoft 365 корпоративный входит Office 365 профессиональный плюс — версия Microsoft Office, доступная по подписке.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-247">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Microsoft Office.</span></span> <span data-ttu-id="3e7c7-248">Office 365 профессиональный плюс, как и Office 2016 или Office 2019, устанавливается непосредственно на клиентских устройствах.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-248">Like Office 2016 or Office 2019, Office 365 ProPlus is installed directly on your client devices.</span></span> <span data-ttu-id="3e7c7-249">При этом Office 365 профессиональный плюс получает обновления, регулярно включающие новые функции.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-249">However, Office 365 ProPlus receives updates that include new features on a regular basis.</span></span> <span data-ttu-id="3e7c7-250">Дополнительные сведения см. в статье [Office 365 профессиональный плюс на предприятии](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-250">See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

<span data-ttu-id="3e7c7-251">В некорпоративной организации необходимо вручную установить Office 365 профессиональный плюс на устройствах.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-251">For your non-enterprise organization, you manually install Office 365 ProPlus on devices.</span></span> <span data-ttu-id="3e7c7-252">Это можно сделать при подготовке новых устройств к использованию, также это могут сделать пользователи в процессе перехода на новую инфраструктуру.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-252">This can be done as part of preparing a new device for use, or by the user as part of their onboarding process.</span></span>

<span data-ttu-id="3e7c7-253">Как бы то ни было, администратор или пользователь входят на портал Office 365 в https://portal.office.com.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-253">In either case, the administrator or the user signs in to the Office 365 portal at https://portal.office.com.</span></span> <span data-ttu-id="3e7c7-254">На **главной вкладке Microsoft Office** щелкните **Установить Office** и пройдите все шаги процесса установки.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-254">On the **Microsoft Office Home** tab, click **Install Office** and step through the installation process.</span></span>

<span data-ttu-id="3e7c7-255">Обновления компонентов Office 365 профессиональный плюс ежемесячно устанавливаются на все компьютеры, на которых установлен этот пакет.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-255">Feature updates to Office 365 ProPlus are downloaded monthly by each computer on which it is installed.</span></span> <span data-ttu-id="3e7c7-256">В некорпоративных организациях обычно не нужно настраивать инфраструктуру для распространения и установки обновлений Office 365 профессиональный плюс.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-256">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute Office 365 ProPlus updates.</span></span> 

### <a name="your-configuration-so-far"></a><span data-ttu-id="3e7c7-257">Конфигурация на этом этапе</span><span class="sxs-lookup"><span data-stu-id="3e7c7-257">Your configuration so far</span></span>

<span data-ttu-id="3e7c7-258">Вот наглядное представление этапа развертывания Office 365 профессиональный плюс, на котором выделены новые элементы.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-258">Here is a visual summary of the Office 365 ProPlus phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
<span data-ttu-id="3e7c7-259">Новые и выделенные элементы этапа "Office 365 профессиональный плюс" включают:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-259">The new and highlighted Office 365 ProPlus elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | <span data-ttu-id="3e7c7-260">Пакет Office 365 профессиональный плюс установлен на устройствах, например, на локальном ноутбуке.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-260">Office 365 ProPlus installed on devices, with an on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | <span data-ttu-id="3e7c7-261">Устройства обращаются в сеть доставки содержимого Office (CDN) для Office 365 профессиональный плюс, чтобы получать обновления для Office 365 профессиональный плюс.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-261">The Office Content Delivery Network (CDN) for Office 365 ProPlus, which devices access for Office 365 ProPlus updates.</span></span> |
|||

## <a name="phase-5-mobile-device-management"></a><span data-ttu-id="3e7c7-262">Этап 5. Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="3e7c7-262">Phase 5: Mobile device management</span></span>

<span data-ttu-id="3e7c7-263">Microsoft 365 корпоративный включает Microsoft Intune для управления мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-263">Microsoft 365 Enterprise includes Microsoft Intune for mobile device management.</span></span> <span data-ttu-id="3e7c7-264">С помощью Intune можно управлять устройствами с Windows, iOS, Android и macOS, чтобы защитить ресурсы организации, включая данные.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-264">With Intune, you can manage Windows, iOS, Android, and macOS devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="3e7c7-265">В Intune используются учетные записи пользователей, групп и компьютеров в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-265">Intune uses the user, group, and computer accounts of Azure AD.</span></span>

<span data-ttu-id="3e7c7-266">В Intune поддерживается два способа управления мобильными устройствами:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-266">Intune provides two types of mobile device management:</span></span>

- <span data-ttu-id="3e7c7-267">Управление мобильными устройствами (MDM) при регистрации устройств в Intune.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-267">Mobile device management (MDM) is when devices get enrolled in Intune.</span></span> <span data-ttu-id="3e7c7-268">После регистрации эти устройства становятся управляемыми, они могут получать политики, правила и параметры, используемые в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-268">Once enrolled, they are managed devices and can receive the policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="3e7c7-269">Как правило, такие устройства принадлежат вашей организации и выдаются сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-269">These types of devices are typically owned by your organization and issued to your employees.</span></span>

- <span data-ttu-id="3e7c7-270">Пользователи со своими собственными личными устройствами могут не желать регистрировать эти устройства или разрешать управление своими устройствами системе Intune с вашими политиками и параметрами.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-270">Users with their own personal devices may not want to enroll their devices or be managed by Intune with your policies and settings.</span></span> <span data-ttu-id="3e7c7-271">Тем не менее, вам все равно нужно защитить ресурсы и данные организации.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-271">However, you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="3e7c7-272">В этом случае вы можете защитить свои приложения с помощью управления мобильными приложениями (MAM).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-272">For this scenario, you can protect your apps with mobile application management (MAM).</span></span>  

<span data-ttu-id="3e7c7-273">Политики Intune могут обеспечить соответствие устройств требованиям и защиту приложений.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-273">Intune policies can enforce device compliance and app protection.</span></span> <span data-ttu-id="3e7c7-274">Вот список политик Intune, которые необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-274">Here is the list of Intune policies to create.</span></span>

| <span data-ttu-id="3e7c7-275">Политики Intune</span><span class="sxs-lookup"><span data-stu-id="3e7c7-275">Intune policies</span></span> | <span data-ttu-id="3e7c7-276">Группы, к которым применяется эта политика</span><span class="sxs-lookup"><span data-stu-id="3e7c7-276">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="3e7c7-277">Политика соответствия устройства требованиям для Windows</span><span class="sxs-lookup"><span data-stu-id="3e7c7-277">Device compliance policy for Windows</span></span> | <span data-ttu-id="3e7c7-278">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-278">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="3e7c7-279">Политика соответствия устройства требованиям для iOS</span><span class="sxs-lookup"><span data-stu-id="3e7c7-279">Device compliance policy for iOS</span></span> | <span data-ttu-id="3e7c7-280">SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-280">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="3e7c7-281">Политика соответствия устройства требованиям для macOS</span><span class="sxs-lookup"><span data-stu-id="3e7c7-281">Device compliance for macOS</span></span> | <span data-ttu-id="3e7c7-282">SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-282">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="3e7c7-283">Политика соответствия устройства требованиям для Android и Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="3e7c7-283">Device compliance policy for Android and Android Enterprise</span></span> | <span data-ttu-id="3e7c7-284">SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-284">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="3e7c7-285">Политика защиты приложений для iOS</span><span class="sxs-lookup"><span data-stu-id="3e7c7-285">App protection policy for iOS</span></span> | <span data-ttu-id="3e7c7-286">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-286">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="3e7c7-287">Политика защиты приложений для macOS</span><span class="sxs-lookup"><span data-stu-id="3e7c7-287">App protection policy for macOS</span></span> | <span data-ttu-id="3e7c7-288">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-288">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="3e7c7-289">Политика защиты приложений для Android и Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="3e7c7-289">App protection policy for Android and Android Enterprise</span></span> | <span data-ttu-id="3e7c7-290">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-290">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
|||
    
<span data-ttu-id="3e7c7-291">Инструкции см. в статье [Основные политики идентификации и доступа для устройств](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-291">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="3e7c7-292">Конфигурация на этом этапе</span><span class="sxs-lookup"><span data-stu-id="3e7c7-292">Your configuration so far</span></span>

<span data-ttu-id="3e7c7-293">Вот наглядное представление этапа "Управление мобильными устройствами", на котором выделены новые элементы.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-293">Here is a visual summary of the Mobile Device Management phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
<span data-ttu-id="3e7c7-294">Новые и выделенные элементы этапа "Управление мобильными устройствами" включают:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-294">The new and highlighted mobile device management elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | <span data-ttu-id="3e7c7-295">Устройства, зарегистрированные в Intune: в качестве примера показан локальный ноутбук под управлением Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-295">Devices that are enrolled in Intune, showing an on-premises laptop running Windows 10 Enterprise as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | <span data-ttu-id="3e7c7-296">Политики Intune для обеспечения соответствия устройств и защиты приложений.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-296">Intune policies for device compliance and app protection.</span></span> |
|||

## <a name="phase-6-information-protection"></a><span data-ttu-id="3e7c7-297">Этап 6. Защита данных</span><span class="sxs-lookup"><span data-stu-id="3e7c7-297">Phase 6: Information protection</span></span>

<span data-ttu-id="3e7c7-298">В Microsoft 365 корпоративный предусмотрен целый ряд функций защиты информации, с помощью которых можно по-разному классифицировать данные, применяя к ним различные уровни управления, безопасности и защиты.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-298">Microsoft 365 Enterprise has a host of information protection features that allow you to treat classifications of data differently by applying different levels of governance, security, and protection.</span></span> 

<span data-ttu-id="3e7c7-299">Например, для обычной переписки большинства сотрудников и для документов, над которыми работают эти сотрудники, требуется некоторый базовый уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-299">For example, normal correspondence between most employees and the documents on which they work need a certain baseline level of protection.</span></span> <span data-ttu-id="3e7c7-300">Для финансовых записей, данных о клиентах и интеллектуальной собственности требуется более высокий уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-300">Financial records, customer data, and your intellectual property need a higher level of protection.</span></span>

<span data-ttu-id="3e7c7-301">Первый шаг в стратегии защиты информации состоит в определении уровней защиты.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-301">The first step to an information protection strategy is to determine the levels of protection.</span></span> <span data-ttu-id="3e7c7-302">Во многих организациях используются следующие уровни, которые уже применяются для политик условного доступа:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-302">Many organizations use these levels, which are already being used for conditional access policies:</span></span>

- <span data-ttu-id="3e7c7-303">Базовый</span><span class="sxs-lookup"><span data-stu-id="3e7c7-303">Baseline</span></span>

  <span data-ttu-id="3e7c7-304">Примеры данных: обычная деловая переписка (электронная почта) и файлы администраторов, специалистов по продажам и сотрудников службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-304">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span>

- <span data-ttu-id="3e7c7-305">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="3e7c7-305">Sensitive</span></span>

  <span data-ttu-id="3e7c7-306">Примеры данных: финансовые и юридические сведения, данные об исследованиях и разработке новых продуктов или услуг.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-306">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span>

- <span data-ttu-id="3e7c7-307">Строго контролируемый</span><span class="sxs-lookup"><span data-stu-id="3e7c7-307">Highly regulated</span></span>

  <span data-ttu-id="3e7c7-308">Примеры данных: личные сведения ваших клиентов и партнеров, финансовая информация или интеллектуальная собственность вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-308">Examples include customer and partner personally identifiable information and your organization’s financial information or intellectual property.</span></span>

<span data-ttu-id="3e7c7-309">На основе этих уровней безопасности необходимо определить и применить:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-309">Based on these levels of data security, the next step is to identify and implement:</span></span>

- <span data-ttu-id="3e7c7-310">Пользовательские типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="3e7c7-310">Custom sensitive information types</span></span>

  <span data-ttu-id="3e7c7-311">В Microsoft 365 предусмотрен широкий набор типов конфиденциальной информации, например, номера медицинского страхования или номера кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-311">Microsoft 365 supplies a wide selection of sensitive information types, such as health service and credit card numbers.</span></span> <span data-ttu-id="3e7c7-312">Если в предоставленном списке нет нужного вам типа информации, можно создать собственный тип.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-312">If you do not find one that you need in the supplied list, you can create your own.</span></span>

- <span data-ttu-id="3e7c7-313">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="3e7c7-313">Retention labels</span></span>

  <span data-ttu-id="3e7c7-314">Необходимо определить, как долго следует хранить документы определенных типов или с определенным содержимым в соответствии с правилами организации и региональными нормативными требованиями.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-314">To comply with organization policies and regional regulations, you might have to specify how long specific types of documents or documents with specific contents should be retained.</span></span> <span data-ttu-id="3e7c7-315">Это задачу можно решить для электронной почты и документов с помощью меток хранения.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-315">You can implement this for email and documents using retention labels.</span></span>

- <span data-ttu-id="3e7c7-316">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="3e7c7-316">Sensitivity labels</span></span>

  <span data-ttu-id="3e7c7-317">Можно помечать сообщения электронной почты и документы, используя именованные метки конфиденциальности, чтобы можно было применять дополнительные уровни безопасности.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-317">You can label email or documents with a named sensitivity label so that additional levels of security can be applied.</span></span> <span data-ttu-id="3e7c7-318">Это могут быть водяные знаки, шифрование и разрешения, указывающие, кому разрешен доступ к электронной почте или документу, и какие действия разрешены.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-318">Examples are watermarks, encryption, and permissions, which specify who is allowed to access the email or document and what they are allowed to do.</span></span>

<span data-ttu-id="3e7c7-319">Дополнительные сведения см. в статье [Типы классификации Microsoft 365](infoprotect-configure-classification.md#microsoft-365-classification-types).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-319">See [Microsoft 365 classification types](infoprotect-configure-classification.md#microsoft-365-classification-types) for more information.</span></span>

<span data-ttu-id="3e7c7-320">Если вы используете метки конфиденциальности с разрешениями, то можно создать дополнительные группы безопасности Azure AD, чтобы определить, каким пользователям доступны те или иные действия с электронной почтой и документами.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-320">If you use sensitivity labels with permissions, you might have to create additional Azure AD security groups to define who is allowed to do what with email and documents.</span></span> 

<span data-ttu-id="3e7c7-321">Например, нужно создать метку конфиденциальности RESEARCH, чтобы защитить электронную почту и документы исследовательской группы.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-321">For example, you need to create a RESEARCH sensitivity label to protect the email and documents of your research team.</span></span> <span data-ttu-id="3e7c7-322">Вы определяете, что:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-322">You determine that:</span></span>

- <span data-ttu-id="3e7c7-323">Исследователи должны иметь возможность изменения документов, помеченных меткой конфиденциальности RESEARCH.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-323">Researchers must have the ability to change documents marked with the RESEARCH sensitivity label.</span></span>
- <span data-ttu-id="3e7c7-324">Сотрудники, не связанные с исследовательской деятельностью, должны иметь только возможность просмотра документов, помеченных меткой конфиденциальности RESEARCH.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-324">Non-research employees only need to have the ability to view documents marked with the RESEARCH sensitivity label.</span></span> 

<span data-ttu-id="3e7c7-325">Это означает, что нужно создать и настроить еще две группы:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-325">This means you need to create and manage two additional groups:</span></span>

- <span data-ttu-id="3e7c7-326">RESEARCH-ALL</span><span class="sxs-lookup"><span data-stu-id="3e7c7-326">RESEARCH-ALL</span></span>
- <span data-ttu-id="3e7c7-327">RESEARCH-VIEW</span><span class="sxs-lookup"><span data-stu-id="3e7c7-327">RESEARCH-VIEW</span></span>

<span data-ttu-id="3e7c7-328">Эти группы и их разрешения входит в состав конфигурации метки конфиденциальности RESEARCH.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-328">These groups and their permissions become part of the RESEARCH sensitivity label's configuration.</span></span>

<span data-ttu-id="3e7c7-329">Если метки конфиденциальности настроены с групповыми разрешениями, необходимо управлять членством в этих группах.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-329">For sensitivity labels configured with group-based permissions, you must manage the membership of these groups.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="3e7c7-330">Конфигурация на этом этапе</span><span class="sxs-lookup"><span data-stu-id="3e7c7-330">Your configuration so far</span></span>

<span data-ttu-id="3e7c7-331">Вот наглядное представление этапа "Защита информации", на котором выделены новые элементы.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-331">Here is a visual summary of the Information Protection phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
<span data-ttu-id="3e7c7-332">Новые и выделенные элементы этапа "Защита информации" включают:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-332">The new and highlighted information protection elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | <span data-ttu-id="3e7c7-333">Метки конфиденциальности для трех уровней безопасности, применяемых пользователями к документам.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-333">Sensitivity labels for the three levels of security that users can apply to documents.</span></span> |
|||

<span data-ttu-id="3e7c7-334">Пользовательские типы данных и метки хранения не показаны.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-334">Custom information types and retention labels are not shown.</span></span>

## <a name="onboarding"></a><span data-ttu-id="3e7c7-335">Адаптация</span><span class="sxs-lookup"><span data-stu-id="3e7c7-335">Onboarding</span></span>

<span data-ttu-id="3e7c7-336">Благодаря инфраструктуре Microsoft 365 корпоративный вы можете легко осуществить адаптацию новых сотрудников.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-336">With your Microsoft 365 Enterprise infrastructure in place, you can easily onboard your employees.</span></span>

### <a name="a-new-windows-10-enterprise-device"></a><span data-ttu-id="3e7c7-337">Новое устройство с Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="3e7c7-337">A new Windows 10 Enterprise device</span></span>

<span data-ttu-id="3e7c7-338">Перед выдачей сотруднику нового устройства с Windows 10 Корпоративная:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-338">Before giving an employee a new Windows 10 Enterprise device:</span></span>

- <span data-ttu-id="3e7c7-339">Если используется гибридная идентификация</span><span class="sxs-lookup"><span data-stu-id="3e7c7-339">For hybrid identity</span></span>

  <span data-ttu-id="3e7c7-340">Подключите устройство к домену AD DS, присоедините устройство к клиенту Azure AD, затем зарегистрируйте устройство в Intune.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-340">Join the device to your AD DS domain, join the device to your Azure AD tenant, and then enroll the device in Intune.</span></span>

- <span data-ttu-id="3e7c7-341">Если используется только облачная идентификация</span><span class="sxs-lookup"><span data-stu-id="3e7c7-341">For cloud-only identity</span></span>

  <span data-ttu-id="3e7c7-342">Присоедините устройство к клиенту Azure AD вашей подписки Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-342">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>

### <a name="existing-employee-with-an-ad-ds-user-account"></a><span data-ttu-id="3e7c7-343">Существующий сотрудник с учетной записью пользователя AD DS</span><span class="sxs-lookup"><span data-stu-id="3e7c7-343">Existing employee with an AD DS user account</span></span>

<span data-ttu-id="3e7c7-344">При первоначальном переходе вашей организации, если используется гибридная идентификация, добавьте учетную запись пользователя AD DS в следующие группы Azure AD:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-344">As part of the initial onboarding for your organization when using hybrid identity, add the AD DS user account to these Azure AD groups:</span></span>

- <span data-ttu-id="3e7c7-345">LICENSED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-345">Licensed</span></span>
- <span data-ttu-id="3e7c7-346">Соответствующие группы безопасности AD DS или Azure AD, являющиеся участниками групп BASELINE, SENSITIVE и HIGHLY-REGULATED в Azure AD</span><span class="sxs-lookup"><span data-stu-id="3e7c7-346">The appropriate AD DS or Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="3e7c7-347">Группы меток конфиденциальности (по мере необходимости)</span><span class="sxs-lookup"><span data-stu-id="3e7c7-347">Sensitivity label groups (as needed)</span></span>

<span data-ttu-id="3e7c7-348">Существующий сотрудник уже должен быть уже добавлен в соответствующие группы AD DS на уровне рабочих групп, отделов и регионов.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-348">The existing employee should already be added to the appropriate workgroup, departmental, and regional AD DS groups.</span></span>

<span data-ttu-id="3e7c7-349">В центре администрирования Microsoft 365 можно добавить учетную запись пользователя для нескольких групп Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-349">You can add a user account to multiple Azure AD groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3e7c7-350">В окне свойств учетной записи пользователя щелкните **Управление группами > Добавление членства в группах**.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-350">From the properties of the user account, click **Manage groups > Add memberships**.</span></span>

<span data-ttu-id="3e7c7-351">Если вы хотите использовать оболочку PowerShell, см данную [загружаемую книгу Excel](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true), которая создает команды PowerShell на основе указанной учетной записи пользователя и выбранных имен групп.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-351">If you want to use PowerShell, see this [downloadable Excel workbook](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true), which generates the PowerShell commands based on a specified user account and selected group names.</span></span>

### <a name="new-employee-with-a-cloud-only-user-account"></a><span data-ttu-id="3e7c7-352">Новый сотрудник с полностью облачной учетной записью</span><span class="sxs-lookup"><span data-stu-id="3e7c7-352">New employee with a cloud-only user account</span></span>

<span data-ttu-id="3e7c7-353">При первоначальном переходе вашей организации, если используется только облачная идентификация, добавьте учетную запись нового пользователя в следующие группы:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-353">As part of the initial onboarding for your organization when using cloud-only identity, add the new user account to these groups:</span></span>

- <span data-ttu-id="3e7c7-354">LICENSED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-354">Licensed</span></span>
- <span data-ttu-id="3e7c7-355">Соответствующие группы безопасности Azure AD, являющиеся участниками групп BASELINE, SENSITIVE и HIGHLY-REGULATED в Azure AD</span><span class="sxs-lookup"><span data-stu-id="3e7c7-355">The appropriate Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="3e7c7-356">Группы на уровне рабочих групп, отделов и регионов</span><span class="sxs-lookup"><span data-stu-id="3e7c7-356">Workgroup, departmental, and regional groups</span></span>
- <span data-ttu-id="3e7c7-357">Группы меток конфиденциальности (по мере необходимости)</span><span class="sxs-lookup"><span data-stu-id="3e7c7-357">Sensitivity label groups (as needed)</span></span>

### <a name="initial-sign-in-to-microsoft-365"></a><span data-ttu-id="3e7c7-358">Начальный вход в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3e7c7-358">Initial sign-in to Microsoft 365</span></span>

<span data-ttu-id="3e7c7-359">Когда сотрудники впервые входят в Microsoft 365, попросите их:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-359">For the first time employees sign in to Microsoft 365, instruct them to:</span></span>

1. <span data-ttu-id="3e7c7-360">Войти на свои устройства с помощью учетных данных своих учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-360">Sign into their devices with their user account credentials.</span></span>
2. <span data-ttu-id="3e7c7-361">В веб-браузере войти на портал Office 365 по адресу https://portal.office.com.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-361">Using a browser, sign in to the Office 365 portal at https://portal.office.com.</span></span>
3. <span data-ttu-id="3e7c7-362">На **главной вкладке Office 365** щелкнуть **Установить Office**, чтобы установить Office 365 профессиональный плюс на свои устройства.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-362">From the **Office 365 Home** tab, click **Install Office** to install Office 365 ProPlus on their device.</span></span>

## <a name="end-results"></a><span data-ttu-id="3e7c7-363">Итоговые результаты</span><span class="sxs-lookup"><span data-stu-id="3e7c7-363">End results</span></span>

<span data-ttu-id="3e7c7-364">Ниже приведены результаты настройки базовой инфраструктуры Microsoft 365 корпоративный для некорпоративной организации.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-364">Here are the results of configuring the Microsoft 365 Enterprise foundation infrastructure for your non-enterprise organization.</span></span>

### <a name="infrastructure-results"></a><span data-ttu-id="3e7c7-365">Результаты для инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="3e7c7-365">Infrastructure results</span></span>

<span data-ttu-id="3e7c7-366">После построения и настройки инфраструктуры Microsoft 365 корпоративный у вас должно быть следующее:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-366">After the build-out and configuration of your Microsoft 365 Enterprise infrastructure, you should have:</span></span>

- <span data-ttu-id="3e7c7-367">Локальное подключение к Интернету в каждом офисе с достаточной пропускной способностью. Такое подключение предоставляется поставщиком услуг Интернета, использующим локальный DNS-сервер для этого региона.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-367">A local Internet connection for each of your offices with sufficient bandwidth supplied by an ISP that uses a regionally local DNS server.</span></span>
- <span data-ttu-id="3e7c7-368">При использовании гибридной идентификации служба Azure AD Connect должна работать на сервере, который синхронизирует ваш локальный домен AD DS с вашим клиентом Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-368">For hybrid identity, Azure AD Connect running on a server that synchronizes your on-premises AD DS domain with your Azure AD tenant.</span></span>
- <span data-ttu-id="3e7c7-369">Следующие группы:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-369">These groups:</span></span>
  - <span data-ttu-id="3e7c7-370">LICENSED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-370">Licensed</span></span>
  - <span data-ttu-id="3e7c7-371">COND-ACCESS-EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="3e7c7-371">COND-ACCESS-EXCLUDE</span></span>
  - <span data-ttu-id="3e7c7-372">Соответствующие группы безопасности AD DS или Azure AD, также являющиеся участниками групп BASELINE, SENSITIVE и HIGHLY-REGULATED в Azure AD</span><span class="sxs-lookup"><span data-stu-id="3e7c7-372">The appropriate AD DS or Azure AD security groups that are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span> 
  - <span data-ttu-id="3e7c7-373">Группы на уровне рабочих групп, отделов и регионов</span><span class="sxs-lookup"><span data-stu-id="3e7c7-373">Workgroup, departmental, and regional groups</span></span>
  - <span data-ttu-id="3e7c7-374">Группы меток конфиденциальности (по мере необходимости)</span><span class="sxs-lookup"><span data-stu-id="3e7c7-374">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="3e7c7-375">Политики условного доступа для входа в Azure AD, использующие группы BASELINE, SENSITIVE, HIGHLY-REGULATED и COND-ACCESS-EXCLUDE в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-375">Azure AD sign-in conditional access policies that use the BASELINE, SENSITIVE, and HIGHLY-REGULATED, and COND-ACCESS-EXCLUDE Azure AD groups.</span></span>
- <span data-ttu-id="3e7c7-376">Политики соответствия устройств и приложений требованиям в Intune.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-376">Intune application and device compliance policies.</span></span>
- <span data-ttu-id="3e7c7-377">Пользовательские типы конфиденциальной информации (по мере необходимости).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-377">Custom sensitive information types (as needed).</span></span>
- <span data-ttu-id="3e7c7-378">Метки хранения (по мере необходимости).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-378">Retention labels (as needed).</span></span>
- <span data-ttu-id="3e7c7-379">Метки конфиденциальности (по мере необходимости).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-379">Sensitivity labels (as needed).</span></span>

<span data-ttu-id="3e7c7-380">Вот наглядное сводное представление инфраструктуры, если в организации используется гибридная идентификация, включающая ваш домен AD DS, сервер Azure AD Connect и синхронизированных пользователей и группы AD DS.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-380">Here is a visual summary of the infrastructure if your organization uses hybrid identity, which includes your AD DS domain, an Azure AD Connect server, and synchronized AD DS users and groups.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
<span data-ttu-id="3e7c7-381">Вот наглядное представление инфраструктуры в случае, если организация использует только облачную идентификацию.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-381">Here is a visual summary of the infrastructure if your organization uses cloud-only identity.</span></span>
 
![](./media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a><span data-ttu-id="3e7c7-382">Результаты для сотрудников</span><span class="sxs-lookup"><span data-stu-id="3e7c7-382">Employee results</span></span>

<span data-ttu-id="3e7c7-383">После перехода на новую инфраструктуру у каждого сотрудника должно быть следующее:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-383">After their onboarding, each employee should have:</span></span>

- <span data-ttu-id="3e7c7-384">Высокоскоростной локальный сетевой канал, соединяющий используемое устройство с облачными службами Microsoft 365 в этом регионе.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-384">A performant, on-premises network path from their device to the Microsoft 365 cloud services in their region.</span></span>
- <span data-ttu-id="3e7c7-385">Учетная запись, являющаяся участником следующих групп:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-385">A user account with these group memberships:</span></span>
   - <span data-ttu-id="3e7c7-386">LICENSED</span><span class="sxs-lookup"><span data-stu-id="3e7c7-386">Licensed</span></span>
   - <span data-ttu-id="3e7c7-387">Соответствующие группы безопасности AD DS или Azure AD, также являющиеся участниками групп BASELINE, SENSITIVE и HIGHLY-REGULATED в Azure AD для политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="3e7c7-387">The appropriate AD DS or Azure AD security groups, which are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups for conditional access policies</span></span> 
   - <span data-ttu-id="3e7c7-388">Соответствующие группы на уровне рабочих групп, отделов и регионов</span><span class="sxs-lookup"><span data-stu-id="3e7c7-388">The appropriate workgroup, departmental, and regional groups</span></span>
   - <span data-ttu-id="3e7c7-389">Группы меток конфиденциальности (по мере необходимости)</span><span class="sxs-lookup"><span data-stu-id="3e7c7-389">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="3e7c7-390">Новое устройство с Windows 10 Корпоративная, при этом:</span><span class="sxs-lookup"><span data-stu-id="3e7c7-390">A Windows 10 Enterprise device that:</span></span>
   - <span data-ttu-id="3e7c7-391">Это устройство присоединено к клиенту Azure AD (только облачное решение) или одновременно к клиенту Azure AD и к вашему домену AD DS (гибридное решение).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-391">Is joined to the Azure AD tenant (cloud-only) or to both the Azure AD tenant and your AD DS domain (hybrid).</span></span>
   - <span data-ttu-id="3e7c7-392">Это устройство автоматически обновляется, получая последние улучшения продукта и улучшения безопасности Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-392">Automatically updates itself with the latest Windows 10 Enterprise product improvements and security enhancements.</span></span>
   - <span data-ttu-id="3e7c7-393">На это устройство установлен пакет Office 365 профессиональный плюс, который автоматически обновляется, получая последние улучшения продукта и улучшения безопасности Office.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-393">Has Office 365 ProPlus installed, which automatically updates itself with the latest Office product improvements and security enhancements.</span></span>
   - <span data-ttu-id="3e7c7-394">Это устройство зарегистрировано в Intune и подчиняется политикам соответствия устройств и политикам защиты приложений в Intune.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-394">Is enrolled in Intune and subject to Intune device compliance policies and app protection policies.</span></span>

## <a name="next-step"></a><span data-ttu-id="3e7c7-395">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="3e7c7-395">Next step</span></span>

<span data-ttu-id="3e7c7-396">Развертывание [нагрузок и сценариев](deploy-workloads.md) с использованием возможностей и конфигурации базовой инфраструктуры Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-396">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
