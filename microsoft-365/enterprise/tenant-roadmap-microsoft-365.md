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
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909458"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="85fc7-103">Дорожная карта клиента для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="85fc7-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="85fc7-104">Клиент Microsoft 365 — это набор служб, которые назначены вашей организации.</span><span class="sxs-lookup"><span data-stu-id="85fc7-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="85fc7-105">Как правило, этот клиент связан с одним или более общедоступными доменными именами DNS и выступает в качестве центрального и изолированного контейнера для различных подписок и лицензий, которые вы назначаете учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="85fc7-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="85fc7-106">Дополнительные сведения см. [в подписях, лицензиях,](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)учетных записях и клиентах облачных предложений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="85fc7-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="85fc7-107">При создании клиента Microsoft 365 вы назначите ему определенное географическое расположение.</span><span class="sxs-lookup"><span data-stu-id="85fc7-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="85fc7-108">Вы также можете иметь клиента с несколькими географическими расположениями и перемещать клиента из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="85fc7-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="85fc7-109">Чтобы клиент был готов к пользовательским, группам, лицензиям и облачным приложениям, важно тщательно планировать и выполнять конфигурацию клиента.</span><span class="sxs-lookup"><span data-stu-id="85fc7-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="85fc7-110">Настройка клиента Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="85fc7-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="85fc7-111">После того, как ваша сеть оптимизирована для доступа к Microsoft 365 как для локального, так и для удаленных сотрудников, в следующих больших задачах планируется настроить клиента Microsoft 365 для доменных имен DNS, общих служб и инфраструктуры удостоверений, поддерживающую безопасный вход пользователя.</span><span class="sxs-lookup"><span data-stu-id="85fc7-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="85fc7-112">Планирование</span><span class="sxs-lookup"><span data-stu-id="85fc7-112">Plan</span></span>

<span data-ttu-id="85fc7-113">Планирование реализации клиента:</span><span class="sxs-lookup"><span data-stu-id="85fc7-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="85fc7-114">Понимание клиентов подписки, лицензий и Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="85fc7-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="85fc7-115">Понимание использования сторонних сертификатов SSL</span><span class="sxs-lookup"><span data-stu-id="85fc7-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="85fc7-116">Понимание способов интеграции клиента Microsoft 365 с службами Azure AD</span><span class="sxs-lookup"><span data-stu-id="85fc7-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="85fc7-117">Планирование поддержки клиентских приложений</span><span class="sxs-lookup"><span data-stu-id="85fc7-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="85fc7-118">Определение использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="85fc7-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="85fc7-119">Планирование обновлений Office 2007 и Office 2010</span><span class="sxs-lookup"><span data-stu-id="85fc7-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="85fc7-120">Понимание изоляции клиента</span><span class="sxs-lookup"><span data-stu-id="85fc7-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="85fc7-121">Развертывание</span><span class="sxs-lookup"><span data-stu-id="85fc7-121">Deploy</span></span>

<span data-ttu-id="85fc7-122">Развертывание клиента:</span><span class="sxs-lookup"><span data-stu-id="85fc7-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="85fc7-123">Добавление [доменов DNS для](../admin/setup/add-domain.md) организации.</span><span class="sxs-lookup"><span data-stu-id="85fc7-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="85fc7-124">Используйте руководства [по настройке в центре администрирования Microsoft 365.](setup-guides-for-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="85fc7-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="85fc7-125">Создайте [инфраструктуру удостоверений](identity-roadmap-microsoft-365.md) [и обезопасите входы пользователя.](microsoft-365-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="85fc7-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="85fc7-126">Перемещение географических местоположений клиента</span><span class="sxs-lookup"><span data-stu-id="85fc7-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="85fc7-127">Корпорация Майкрософт продолжает открывать новые географические расположения центров обработки данных (geos) для служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="85fc7-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="85fc7-128">Эти новые геоцентры данных добавляют мощности и вычислительные ресурсы для поддержки спроса клиентов и роста использования.</span><span class="sxs-lookup"><span data-stu-id="85fc7-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="85fc7-129">Кроме того, новые геоцентры центра обработки данных предоставляют резидентство данных для основных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="85fc7-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="85fc7-130">Дополнительные сведения см. в дополнительных сведениях о перемещении основных данных в новые геоцентры центра обработки данных Microsoft [365.](moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="85fc7-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="85fc7-131">Развертывание Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="85fc7-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="85fc7-132">С помощью Microsoft 365 Multi-Geo организация может расширить присутствие Microsoft 365 до нескольких географических регионов или стран в существующем клиенте.</span><span class="sxs-lookup"><span data-stu-id="85fc7-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="85fc7-133">Дополнительные сведения см. на странице [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="85fc7-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="85fc7-134">Управление несколькими клиентами Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="85fc7-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="85fc7-135">Хотя наличие одного клиента для оганизации идеально подходит, вы можете быть одной из многих организаций с несколькими арендаторами.</span><span class="sxs-lookup"><span data-stu-id="85fc7-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="85fc7-136">Причинами могут быть слияния и приобретения, нужна административная изоляция или децентрализованная ИТ-система.</span><span class="sxs-lookup"><span data-stu-id="85fc7-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="85fc7-137">Если у вас несколько клиентов Microsoft 365, см. в этих статьях дополнительные сведения о:</span><span class="sxs-lookup"><span data-stu-id="85fc7-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="85fc7-138">Взаимодействие между клиентами</span><span class="sxs-lookup"><span data-stu-id="85fc7-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="85fc7-139">Миграция почтовых ящиков между клиентами</span><span class="sxs-lookup"><span data-stu-id="85fc7-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="85fc7-140">Миграция между клиентами</span><span class="sxs-lookup"><span data-stu-id="85fc7-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="85fc7-141">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="85fc7-141">Next step</span></span>

<span data-ttu-id="85fc7-142">Начните планирование клиента [с подписки, лицензий, учетных записей и клиентов.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="85fc7-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>