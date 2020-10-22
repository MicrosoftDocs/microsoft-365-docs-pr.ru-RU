---
title: План обслуживания клиентов для Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: План настройки клиентов для Microsoft 365.
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656011"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="c9fa2-103">План обслуживания клиентов для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9fa2-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="c9fa2-104">Ваш клиент Microsoft 365 — это набор служб, назначенных Организации.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="c9fa2-105">Как правило, этот клиент связан с одним или несколькими доменными именами DNS и выступает в качестве центрального контейнера для различных подписок и лицензий, которые назначаются учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="c9fa2-106">Для получения дополнительных сведений см [подписки, лицензии, учетные записи и клиенты для облачных услуг Майкрософт](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="c9fa2-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="c9fa2-107">При создании клиента Microsoft 365 вы назначаете его определенному географическому расположению.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="c9fa2-108">Вы также можете использовать клиент с несколькими географическими расположениями и переместить клиент из одного места в другое.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="c9fa2-109">Чтобы клиент был готов для идентификации, важно тщательно спланировать и выполнить настройку клиента.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-109">To get your tenant ready for identity, it's critical to carefully plan and execute your tenant configuration.</span></span>


## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="c9fa2-110">Настройка клиента Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9fa2-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="c9fa2-111">Убедившись, что сеть оптимизирована для доступа к Microsoft 365 для локальных и удаленных сотрудников, следующие крупные задачи планируются, а затем настраивают свой клиент Microsoft 365 для доменных имен DNS, общих служб и этой инфраструктуры удостоверений, которая поддерживает безопасный вход пользователя.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

## <a name="plan"></a><span data-ttu-id="c9fa2-112">План</span><span class="sxs-lookup"><span data-stu-id="c9fa2-112">Plan</span></span>

<span data-ttu-id="c9fa2-113">Чтобы спланировать реализацию клиента, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="c9fa2-114">Общие сведения о подписках, лицензиях и клиентах Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="c9fa2-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="c9fa2-115">Сведения об использовании сторонних SSL-сертификатов</span><span class="sxs-lookup"><span data-stu-id="c9fa2-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="c9fa2-116">Общие сведения о способах интеграции клиента Microsoft 365 со службами Azure AD</span><span class="sxs-lookup"><span data-stu-id="c9fa2-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="c9fa2-117">Планирование поддержки клиентских приложений</span><span class="sxs-lookup"><span data-stu-id="c9fa2-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="c9fa2-118">Определение способа использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="c9fa2-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="c9fa2-119">Планирование обновлений для Office 2007 и Office 2010</span><span class="sxs-lookup"><span data-stu-id="c9fa2-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="c9fa2-120">Общие сведения об изоляции клиентов</span><span class="sxs-lookup"><span data-stu-id="c9fa2-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="c9fa2-121">Получение сведений о службе Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="c9fa2-121">Get the details on Microsoft 365 service assurance</span></span>](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a><span data-ttu-id="c9fa2-122">Развертывание</span><span class="sxs-lookup"><span data-stu-id="c9fa2-122">Deploy</span></span>

<span data-ttu-id="c9fa2-123">Чтобы развернуть клиент:</span><span class="sxs-lookup"><span data-stu-id="c9fa2-123">To deploy your tenant:</span></span> 

- <span data-ttu-id="c9fa2-124">Добавьте [домены DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) для Организации.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-124">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="c9fa2-125">Используйте [руководства по настройке в центре администрирования Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="c9fa2-125">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="c9fa2-126">Создайте [инфраструктуру идентификации](identity-roadmap-microsoft-365.md) и [Обеспечьте безопасность пользовательских входов](microsoft-365-secure-sign-in.md).</span><span class="sxs-lookup"><span data-stu-id="c9fa2-126">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="c9fa2-127">Перемещение географических расположений клиента</span><span class="sxs-lookup"><span data-stu-id="c9fa2-127">Move a tenant's geographic locations</span></span>

<span data-ttu-id="c9fa2-128">Корпорация Майкрософт продолжает открывать новые географические расположения центра обработки данных (жеос) для служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-128">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="c9fa2-129">Эти новые центры обработки данных жеос добавляют ресурсы емкости и вычислительные ресурсы для поддержки роста требований клиентов и использования.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-129">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="c9fa2-130">Кроме того, новые центры обработки данных жеос предоставляют размещению данных для основных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-130">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="c9fa2-131">Дополнительные сведения см. [в статье Перемещение основных данных в новый центр обработки данных Microsoft 365 жеос](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="c9fa2-131">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="c9fa2-132">Развертывание Microsoft 365 с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="c9fa2-132">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="c9fa2-133">С помощью Microsoft 365 Multi-Geo организация может расширить присутствие Microsoft 365 до нескольких географических регионов или стран в существующем клиенте.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-133">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="c9fa2-134">Более подробную информацию можно найти в [статье Microsoft 365 с поддержкой нескольких регионов](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="c9fa2-134">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenancies"></a><span data-ttu-id="c9fa2-135">Управление несколькими клиентыми Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9fa2-135">Manage multiple Microsoft 365 tenancies</span></span> 

<span data-ttu-id="c9fa2-136">Несмотря на то, что у вас есть один клиент для вашего оганизатион, вы можете столкнуться с одной из многочисленных организаций, имеющих несколько клиенты.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-136">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenancies.</span></span> <span data-ttu-id="c9fa2-137">Причинами для нескольких клиенты могут быть слияния и приобретения, Административная изоляция или децентрализована.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-137">Reasons for multiple tenancies can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="c9fa2-138">Если у вас несколько клиенты Microsoft 365, ознакомьтесь со статьями, посвященными следующим статьям.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-138">If you have multiple Microsoft 365 tenancies, see these articles for more information about:</span></span>

- [<span data-ttu-id="c9fa2-139">Взаимодействие между клиентами</span><span class="sxs-lookup"><span data-stu-id="c9fa2-139">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="c9fa2-140">Миграция почтовых ящиков между клиентами</span><span class="sxs-lookup"><span data-stu-id="c9fa2-140">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="c9fa2-141">Миграция между клиентами</span><span class="sxs-lookup"><span data-stu-id="c9fa2-141">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a><span data-ttu-id="c9fa2-142">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="c9fa2-142">Next step</span></span>

<span data-ttu-id="c9fa2-143">Начните планирование клиентов с помощью [подписок, лицензий, учетных записей и клиентов](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="c9fa2-143">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
