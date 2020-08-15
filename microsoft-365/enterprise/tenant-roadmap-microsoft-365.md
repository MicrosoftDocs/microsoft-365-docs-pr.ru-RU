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
ms.collection: M365-subscription-management
ms.custom: it-pro
description: План настройки клиентов для Microsoft 365.
ms.openlocfilehash: db7054d1f6afc7e4835507dc6415e0b240918c1f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693511"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="3cb56-103">План обслуживания клиентов для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cb56-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="3cb56-104">Ваш клиент Microsoft 365 — это набор служб, назначенных Организации.</span><span class="sxs-lookup"><span data-stu-id="3cb56-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="3cb56-105">Этот клиент обычно связан с одним или несколькими доменными именами DNS и выступает в качестве центрального контейнера для различных подписок и лицензий, которые назначаются учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="3cb56-105">This tenant is typically associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> 

<span data-ttu-id="3cb56-106">При создании клиента Microsoft 365 вы назначаете его определенному географическому расположению.</span><span class="sxs-lookup"><span data-stu-id="3cb56-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="3cb56-107">Вы также можете использовать клиент с несколькими географическими расположениями и переместить клиент из одного места в другое.</span><span class="sxs-lookup"><span data-stu-id="3cb56-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="3cb56-108">Хорошо Запланированная и выполненная Конфигурация клиента важна для готовности к выпуску базовых служб сети и удостоверения.</span><span class="sxs-lookup"><span data-stu-id="3cb56-108">A well-planned and executed tenant configuration is critical to getting it ready for the foundational services of networking and identity.</span></span>

## <a name="plan"></a><span data-ttu-id="3cb56-109">План</span><span class="sxs-lookup"><span data-stu-id="3cb56-109">Plan</span></span>

<span data-ttu-id="3cb56-110">На этапе планирования реализации клиента:</span><span class="sxs-lookup"><span data-stu-id="3cb56-110">In the planning phase of your tenant implementation:</span></span>

- [<span data-ttu-id="3cb56-111">Общие сведения о подписках, лицензиях и клиентах Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3cb56-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="3cb56-112">Сведения об использовании сторонних SSL-сертификатов</span><span class="sxs-lookup"><span data-stu-id="3cb56-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="3cb56-113">Доступ к руководствам по настройке в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cb56-113">Access setup guides in the Microsoft 365 admin center</span></span>](setup-guides-for-microsoft-365.md)
- [<span data-ttu-id="3cb56-114">Общие сведения о способах интеграции клиента Microsoft 365 со службами Azure AD</span><span class="sxs-lookup"><span data-stu-id="3cb56-114">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="3cb56-115">Планирование поддержки клиентских приложений</span><span class="sxs-lookup"><span data-stu-id="3cb56-115">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="3cb56-116">Определение способа использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="3cb56-116">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="3cb56-117">Планирование обновлений для Office 2007 и Office 2010</span><span class="sxs-lookup"><span data-stu-id="3cb56-117">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="3cb56-118">Общие сведения об изоляции клиентов</span><span class="sxs-lookup"><span data-stu-id="3cb56-118">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="3cb56-119">Получение сведений о службе Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="3cb56-119">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="3cb56-120">Развертывание</span><span class="sxs-lookup"><span data-stu-id="3cb56-120">Deploy</span></span>

<span data-ttu-id="3cb56-121">На этапе развертывания реализации клиента [Добавьте домены DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) для Организации.</span><span class="sxs-lookup"><span data-stu-id="3cb56-121">In the deployment phase of your tenant implementation, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="3cb56-122">Клиенты с несколькими географическими расположениями</span><span class="sxs-lookup"><span data-stu-id="3cb56-122">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="3cb56-123">С помощью Microsoft 365 Multi-Geo организация может расширить присутствие Microsoft 365 до нескольких географических регионов или стран в существующем клиенте.</span><span class="sxs-lookup"><span data-stu-id="3cb56-123">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="3cb56-124">Приступите к [работе](microsoft-365-multi-geo.md) : Общие сведения, планирование, Настройка и администрирование с помощью Microsoft 365 с поддержкой нескольких регионов.</span><span class="sxs-lookup"><span data-stu-id="3cb56-124">[Get started](microsoft-365-multi-geo.md) in understanding, planning, configuring, and then administering with Microsoft 365 Multi-Geo.</span></span>

## <a name="moving-a-tenants-geographic-locations"></a><span data-ttu-id="3cb56-125">Перемещение географических расположений клиента</span><span class="sxs-lookup"><span data-stu-id="3cb56-125">Moving a tenant's geographic locations</span></span>

<span data-ttu-id="3cb56-126">Корпорация Майкрософт продолжает открывать новые географические расположения центра обработки данных (жеос) для служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cb56-126">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="3cb56-127">Эти новые центры обработки данных жеос добавляют ресурсы емкости и вычислительные ресурсы для поддержки роста требований клиентов и использования.</span><span class="sxs-lookup"><span data-stu-id="3cb56-127">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="3cb56-128">Кроме того, новые центры обработки данных жеос предоставляют размещению данных для основных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="3cb56-128">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="3cb56-129">Начните с понимания и запросите географические данные, используя [Перемещение основных данных в новый Geo центра обработки данных Microsoft 365](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="3cb56-129">Get started in understanding and requesting a geo data move with [Moving core data to new Microsoft 365 datacenter geo](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="3cb56-130">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="3cb56-130">Next step</span></span>

<span data-ttu-id="3cb56-131">Начните планирование клиентов с помощью [подписок, лицензий, учетных записей и клиентов](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="3cb56-131">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

