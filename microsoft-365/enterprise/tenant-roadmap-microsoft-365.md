---
title: План клиента для Microsoft 365
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
description: План по настройкам клиентов для Microsoft 365.
ms.openlocfilehash: d2640a036eedda0b0962a15a03dcf0211ea0209b
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948401"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="ee471-103">План клиента для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ee471-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="ee471-104">Клиент Microsoft 365 — это набор служб, которые назначены вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ee471-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="ee471-105">Как правило, этот клиент связан с одним или более вашими общедоступными доменными именами DNS и выступает в качестве центрального и изолированного контейнера для различных подписок и лицензий, которые вы назначаете учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="ee471-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="ee471-106">Дополнительные сведения см. в подписках, лицензиях, учетных записях и клиентах [облачных предложений Майкрософт.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="ee471-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="ee471-107">При создании клиента Microsoft 365 вы назначаете его определенному географическому расположению.</span><span class="sxs-lookup"><span data-stu-id="ee471-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="ee471-108">Вы также можете иметь клиент с несколькими географическими расположениями и перемещать его из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="ee471-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="ee471-109">Чтобы клиент был готов к пользователям, группам, лицензиям и облачным приложениям, важно тщательно спланировать и выполнить настройку клиента.</span><span class="sxs-lookup"><span data-stu-id="ee471-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="ee471-110">Настройка клиента Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ee471-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="ee471-111">Убедившись, что сеть оптимизирована для доступа к Microsoft 365 как для локального, так и для удаленных сотрудников, следующие важные задачи — планирование и настройка клиента Microsoft 365 для доменных имен DNS, общих служб и для инфраструктуры удостоверений, поддерживающую безопасный вход пользователей.</span><span class="sxs-lookup"><span data-stu-id="ee471-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="ee471-112">План</span><span class="sxs-lookup"><span data-stu-id="ee471-112">Plan</span></span>

<span data-ttu-id="ee471-113">Чтобы спланировать реализацию клиента, спланируйте:</span><span class="sxs-lookup"><span data-stu-id="ee471-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="ee471-114">Подписки, лицензии и клиенты Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="ee471-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="ee471-115">Использование сторонних SSL-сертификатов</span><span class="sxs-lookup"><span data-stu-id="ee471-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="ee471-116">Способы интеграции клиента Microsoft 365 со службами Azure AD</span><span class="sxs-lookup"><span data-stu-id="ee471-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="ee471-117">Планирование поддержки клиентских приложений</span><span class="sxs-lookup"><span data-stu-id="ee471-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="ee471-118">Определение использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="ee471-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="ee471-119">Планирование обновлений Office 2007 и Office 2010</span><span class="sxs-lookup"><span data-stu-id="ee471-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="ee471-120">Понимание изоляции клиента</span><span class="sxs-lookup"><span data-stu-id="ee471-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="ee471-121">Развертывание</span><span class="sxs-lookup"><span data-stu-id="ee471-121">Deploy</span></span>

<span data-ttu-id="ee471-122">Чтобы развернуть клиент:</span><span class="sxs-lookup"><span data-stu-id="ee471-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="ee471-123">Добавьте [домены DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) для организации.</span><span class="sxs-lookup"><span data-stu-id="ee471-123">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="ee471-124">Используйте руководства [по настройке в Центре администрирования Microsoft 365.](setup-guides-for-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="ee471-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="ee471-125">Создайте [инфраструктуру удостоверений](identity-roadmap-microsoft-365.md) и [забезопасные входы пользователей.](microsoft-365-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="ee471-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="ee471-126">Перемещение географических местоположений клиента</span><span class="sxs-lookup"><span data-stu-id="ee471-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="ee471-127">Корпорация Майкрософт продолжает открывать новые географические расположения центров обработки данных для служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee471-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="ee471-128">Эти новые геополии центра обработки данных добавляют мощности и вычислительные ресурсы для поддержки роста потребностей клиентов и использования.</span><span class="sxs-lookup"><span data-stu-id="ee471-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="ee471-129">Кроме того, новые геополии центра обработки данных предлагают географическое место хранения данных для основных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="ee471-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="ee471-130">Дополнительные сведения см. в теме "Перемещение основных данных в новые географические области центра обработки данных [Microsoft 365".](moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="ee471-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="ee471-131">Развертывание Microsoft 365 с несколькими географическими службами</span><span class="sxs-lookup"><span data-stu-id="ee471-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="ee471-132">С помощью Microsoft 365 Multi-Geo организация может расширить присутствие Microsoft 365 до нескольких географических регионов или стран в существующем клиенте.</span><span class="sxs-lookup"><span data-stu-id="ee471-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="ee471-133">Дополнительные сведения см. на странице [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="ee471-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="ee471-134">Управление несколькими клиентами Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ee471-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="ee471-135">Хотя один клиент идеально подходит для вашей оганизации, вы можете быть одной из многих организаций с несколькими арендаторами.</span><span class="sxs-lookup"><span data-stu-id="ee471-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="ee471-136">Причины могут включать слияния и приобретения, административную изоляцию или децентрализованную ИТ-структуру.</span><span class="sxs-lookup"><span data-stu-id="ee471-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="ee471-137">Если у вас несколько клиентов Microsoft 365, дополнительные сведения см. в указанных здесь статьях.</span><span class="sxs-lookup"><span data-stu-id="ee471-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="ee471-138">Взаимодействие между клиентами</span><span class="sxs-lookup"><span data-stu-id="ee471-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="ee471-139">Миграция почтовых ящиков между клиентами</span><span class="sxs-lookup"><span data-stu-id="ee471-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="ee471-140">Миграция между клиентами</span><span class="sxs-lookup"><span data-stu-id="ee471-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="ee471-141">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="ee471-141">Next step</span></span>

<span data-ttu-id="ee471-142">Начните планирование клиентов с [помощью подписок, лицензий, учетных записей и клиентов.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="ee471-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
