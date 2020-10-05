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
- M365initiative-coredeploy
ms.custom: it-pro
description: План настройки клиентов для Microsoft 365.
ms.openlocfilehash: e4b2af9143070caa1ebd8fd66ef9f367f85d3bb9
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357914"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="30b18-103">План обслуживания клиентов для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30b18-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="30b18-104">Ваш клиент Microsoft 365 — это набор служб, назначенных Организации.</span><span class="sxs-lookup"><span data-stu-id="30b18-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="30b18-105">Как правило, этот клиент связан с одним или несколькими доменными именами DNS и выступает в качестве центрального контейнера для различных подписок и лицензий, которые назначаются учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="30b18-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span>

<span data-ttu-id="30b18-106">При создании клиента Microsoft 365 вы назначаете его определенному географическому расположению.</span><span class="sxs-lookup"><span data-stu-id="30b18-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="30b18-107">Вы также можете использовать клиент с несколькими географическими расположениями и переместить клиент из одного места в другое.</span><span class="sxs-lookup"><span data-stu-id="30b18-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="30b18-108">Чтобы клиент был готов для основных служб сети и удостоверения, необходимо тщательно спланировать и выполнить настройку клиента.</span><span class="sxs-lookup"><span data-stu-id="30b18-108">To get your tenant ready for the foundational services of networking and identity, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="plan"></a><span data-ttu-id="30b18-109">План</span><span class="sxs-lookup"><span data-stu-id="30b18-109">Plan</span></span>

<span data-ttu-id="30b18-110">Чтобы спланировать реализацию клиента, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="30b18-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="30b18-111">Общие сведения о подписках, лицензиях и клиентах Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="30b18-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="30b18-112">Сведения об использовании сторонних SSL-сертификатов</span><span class="sxs-lookup"><span data-stu-id="30b18-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="30b18-113">Общие сведения о способах интеграции клиента Microsoft 365 со службами Azure AD</span><span class="sxs-lookup"><span data-stu-id="30b18-113">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="30b18-114">Планирование поддержки клиентских приложений</span><span class="sxs-lookup"><span data-stu-id="30b18-114">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="30b18-115">Определение способа использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="30b18-115">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="30b18-116">Планирование обновлений для Office 2007 и Office 2010</span><span class="sxs-lookup"><span data-stu-id="30b18-116">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="30b18-117">Общие сведения об изоляции клиентов</span><span class="sxs-lookup"><span data-stu-id="30b18-117">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="30b18-118">Получение сведений о службе Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="30b18-118">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="30b18-119">Развертывание</span><span class="sxs-lookup"><span data-stu-id="30b18-119">Deploy</span></span>

<span data-ttu-id="30b18-120">Чтобы развернуть клиент, [Добавьте домены DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) для Организации и используйте [руководства по настройке в центре администрирования Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="30b18-120">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization and use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="30b18-121">Клиенты с несколькими географическими расположениями</span><span class="sxs-lookup"><span data-stu-id="30b18-121">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="30b18-122">С помощью Microsoft 365 Multi-Geo организация может расширить присутствие Microsoft 365 до нескольких географических регионов или стран в существующем клиенте.</span><span class="sxs-lookup"><span data-stu-id="30b18-122">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="30b18-123">Для получения сведений о Microsoft 365 с поддержкой нескольких регионов, в том числе о планировании, настройке и администрировании, [Начните отсюда](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="30b18-123">For information about Microsoft 365 Multi-Geo, including how to plan, configure, and administer it, [start here](microsoft-365-multi-geo.md).</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="30b18-124">Перемещение географических расположений клиента</span><span class="sxs-lookup"><span data-stu-id="30b18-124">Move a tenant's geographic locations</span></span>

<span data-ttu-id="30b18-125">Корпорация Майкрософт продолжает открывать новые географические расположения центра обработки данных (жеос) для служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="30b18-125">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="30b18-126">Эти новые центры обработки данных жеос добавляют ресурсы емкости и вычислительные ресурсы для поддержки роста требований клиентов и использования.</span><span class="sxs-lookup"><span data-stu-id="30b18-126">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="30b18-127">Кроме того, новые центры обработки данных жеос предоставляют размещению данных для основных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="30b18-127">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="30b18-128">Сведения о центре обработки данных Майкрософт 365, в том числе о том, как запрашивать перемещение географических данных, [начинаются отсюда](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="30b18-128">For information about Microsoft 365 datacenter geo, including how to request a geo data move, [start here](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="30b18-129">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="30b18-129">Next step</span></span>

<span data-ttu-id="30b18-130">Начните планирование клиентов с помощью [подписок, лицензий, учетных записей и клиентов](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="30b18-130">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

