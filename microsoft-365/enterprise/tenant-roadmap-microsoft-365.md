---
title: Дорожная карта клиента для Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Дорожная карта для набора клиентов для Microsoft 365.
ms.openlocfilehash: 4b94540293b86bd922ce4b29f970e52eb1245a01
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464037"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="6809e-103">Дорожная карта клиента для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6809e-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="6809e-104">Ваш Microsoft 365 является набором служб, которые назначены вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6809e-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="6809e-105">Как правило, этот клиент связан с одним или более общедоступными доменными именами DNS и выступает в качестве центрального и изолированного контейнера для различных подписок и лицензий, которые вы назначаете учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="6809e-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="6809e-106">Дополнительные сведения см. [в подписях, лицензиях,](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)учетных записях и клиентах облачных предложений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6809e-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="6809e-107">При создании клиента Microsoft 365 назначить его в определенное географическое расположение.</span><span class="sxs-lookup"><span data-stu-id="6809e-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="6809e-108">Вы также можете иметь клиента с несколькими географическими расположениями и перемещать клиента из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="6809e-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="6809e-109">Чтобы клиент был готов к пользовательским, группам, лицензиям и облачным приложениям, важно тщательно планировать и выполнять конфигурацию клиента.</span><span class="sxs-lookup"><span data-stu-id="6809e-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="6809e-110">Настройка клиента Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6809e-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="6809e-111">После того, как ваша сеть оптимизирована для доступа к Microsoft 365 для локального и удаленного сотрудников, в следующих больших задачах планируется настроить Microsoft 365 клиента для доменных имен DNS, общих служб и инфраструктуры удостоверений, поддерживающую безопасный вход пользователя.</span><span class="sxs-lookup"><span data-stu-id="6809e-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="6809e-112">План</span><span class="sxs-lookup"><span data-stu-id="6809e-112">Plan</span></span>

<span data-ttu-id="6809e-113">Планирование реализации клиента:</span><span class="sxs-lookup"><span data-stu-id="6809e-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="6809e-114">Понимание клиентов подписки, лицензий и Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="6809e-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="6809e-115">Понимание использования сторонних сертификатов SSL</span><span class="sxs-lookup"><span data-stu-id="6809e-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="6809e-116">Понимание способов интеграции Microsoft 365 клиента с службами Azure AD</span><span class="sxs-lookup"><span data-stu-id="6809e-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="6809e-117">Планирование поддержки клиентских приложений</span><span class="sxs-lookup"><span data-stu-id="6809e-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="6809e-118">Определение использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="6809e-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="6809e-119">Планирование обновления Office 2007 и Office 2010 г.</span><span class="sxs-lookup"><span data-stu-id="6809e-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="6809e-120">Понимание изоляции клиента</span><span class="sxs-lookup"><span data-stu-id="6809e-120">Understand tenant isolation</span></span>](/compliance/assurance/microsoft-365-isolation-controls)

### <a name="deploy"></a><span data-ttu-id="6809e-121">Развертывание</span><span class="sxs-lookup"><span data-stu-id="6809e-121">Deploy</span></span>

<span data-ttu-id="6809e-122">Развертывание клиента:</span><span class="sxs-lookup"><span data-stu-id="6809e-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="6809e-123">Добавление [доменов DNS для](../admin/setup/add-domain.md) организации.</span><span class="sxs-lookup"><span data-stu-id="6809e-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="6809e-124">Используйте руководства [по настройке в Центр администрирования Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="6809e-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="6809e-125">Создайте [инфраструктуру удостоверений](identity-roadmap-microsoft-365.md) [и обезопасите входы пользователя.](microsoft-365-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="6809e-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="6809e-126">Перемещение географических местоположений клиента</span><span class="sxs-lookup"><span data-stu-id="6809e-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="6809e-127">Корпорация Майкрософт продолжает открывать новые географические расположения центров обработки данных (geos) для Microsoft 365 служб.</span><span class="sxs-lookup"><span data-stu-id="6809e-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="6809e-128">Эти новые геоцентры данных добавляют мощности и вычислительные ресурсы для поддержки спроса клиентов и роста использования.</span><span class="sxs-lookup"><span data-stu-id="6809e-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="6809e-129">Кроме того, новые геоцентры центра обработки данных предоставляют резидентство данных для основных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="6809e-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="6809e-130">Дополнительные сведения см. в дополнительных сведениях о перемещении основных данных [в новые Microsoft 365 геоцентра данных.](moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="6809e-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="6809e-131">Развертывание Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="6809e-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="6809e-132">С помощью Microsoft 365 Multi-Geo организация может расширить присутствие Microsoft 365 до нескольких географических регионов или стран в существующем клиенте.</span><span class="sxs-lookup"><span data-stu-id="6809e-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="6809e-133">Дополнительные сведения см. на странице [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="6809e-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="6809e-134">Управление несколькими Microsoft 365 клиентов</span><span class="sxs-lookup"><span data-stu-id="6809e-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="6809e-135">Хотя наличие одного клиента для оганизации идеально подходит, вы можете быть одной из многих организаций с несколькими арендаторами.</span><span class="sxs-lookup"><span data-stu-id="6809e-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="6809e-136">Причинами могут быть слияния и приобретения, нужна административная изоляция или децентрализованная ИТ-система.</span><span class="sxs-lookup"><span data-stu-id="6809e-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="6809e-137">Если у вас несколько Microsoft 365 клиентов, см. в этих статьях дополнительные сведения о:</span><span class="sxs-lookup"><span data-stu-id="6809e-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="6809e-138">Взаимодействие между клиентами</span><span class="sxs-lookup"><span data-stu-id="6809e-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="6809e-139">Миграция почтовых ящиков между клиентами</span><span class="sxs-lookup"><span data-stu-id="6809e-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="6809e-140">Миграция между клиентами</span><span class="sxs-lookup"><span data-stu-id="6809e-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="6809e-141">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="6809e-141">Next step</span></span>

<span data-ttu-id="6809e-142">Начните планирование клиента [с подписки, лицензий, учетных записей и клиентов.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="6809e-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>