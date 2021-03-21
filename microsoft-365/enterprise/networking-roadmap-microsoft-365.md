---
title: Дорожная карта сети для Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Дорожная карта для реализации сетевой сети Microsoft 365.
ms.openlocfilehash: be1691138290a592822bfb4d59286fe795270450
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923556"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="302aa-103">Дорожная карта сети для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="302aa-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="302aa-104">Microsoft 365 для предприятия включает облачные службы совместной работы и производительности, Microsoft Intune и многие службы удостоверений и безопасности Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="302aa-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="302aa-105">Для всех этих облачных служб используются безопасные, производительные и надежные подключения с клиентских устройств через Интернет или выделенные каналы.</span><span class="sxs-lookup"><span data-stu-id="302aa-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="302aa-106">Чтобы разместить эти службы и сделать их доступными клиентам по всему миру, корпорация Майкрософт разработала сетевую инфраструктуру, в которой основное внимание уделено производительности и интеграции.</span><span class="sxs-lookup"><span data-stu-id="302aa-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="302aa-107">Важной частью подключения к Microsoft 365 является настройка сетевых и интернет-подключений для оптимизации доступа.</span><span class="sxs-lookup"><span data-stu-id="302aa-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="302aa-108">Настройка локальной сети для доступа к глобально распределенному облаку Software-as-a-Service (SaaS) отличается от традиционной сети, оптимизированной для трафика в локальном центре обработки данных и центральном подключении к Интернету.</span><span class="sxs-lookup"><span data-stu-id="302aa-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="302aa-109">С помощью этих статей можно ознакомиться с основными различиями пограничных устройств, клиентских компьютеров и локальной сети, а также изменять их для обеспечения оптимальной производительности для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="302aa-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="302aa-110">Планирование</span><span class="sxs-lookup"><span data-stu-id="302aa-110">Plan</span></span>

<span data-ttu-id="302aa-111">На этапе планирования реализации сети:</span><span class="sxs-lookup"><span data-stu-id="302aa-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="302aa-112">Понять, как работает сеть Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="302aa-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="302aa-113">Оценка текущего подключения к сети</span><span class="sxs-lookup"><span data-stu-id="302aa-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="302aa-114">Определите, правильно ли ExpressRoute для организации</span><span class="sxs-lookup"><span data-stu-id="302aa-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="302aa-115">Планирование сетевых устройств</span><span class="sxs-lookup"><span data-stu-id="302aa-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="302aa-116">Настройка сети для миграции</span><span class="sxs-lookup"><span data-stu-id="302aa-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="302aa-117">Развертывание</span><span class="sxs-lookup"><span data-stu-id="302aa-117">Deploy</span></span>

<span data-ttu-id="302aa-118">На этапе развертывания сетевой реализации:</span><span class="sxs-lookup"><span data-stu-id="302aa-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="302aa-119">Убедитесь, что корпоративная сеть оптимизирована для подключения Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="302aa-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="302aa-120">Добавление доменов DNS для организации</span><span class="sxs-lookup"><span data-stu-id="302aa-120">Add the DNS domains for your organization</span></span>](../admin/setup/add-domain.md)
- [<span data-ttu-id="302aa-121">Оптимизация подключения к конечным точкам Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="302aa-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="302aa-122">Оптимизация подключения для удаленных сотрудников</span><span class="sxs-lookup"><span data-stu-id="302aa-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="302aa-123">При необходимости [настройте ExpressRoute](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="302aa-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="302aa-124">Управление</span><span class="sxs-lookup"><span data-stu-id="302aa-124">Manage</span></span>

<span data-ttu-id="302aa-125">На этапе управления реализацией сети:</span><span class="sxs-lookup"><span data-stu-id="302aa-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="302aa-126">Убедитесь, что сетевые устройства используют последние конечные точки Office 365</span><span class="sxs-lookup"><span data-stu-id="302aa-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="302aa-127">Мониторинг и настройка производительности сети</span><span class="sxs-lookup"><span data-stu-id="302aa-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="302aa-128">Мониторинг подключений ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="302aa-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="302aa-129">Поставщики сетевого оборудования</span><span class="sxs-lookup"><span data-stu-id="302aa-129">Network equipment vendors</span></span>

<span data-ttu-id="302aa-130">Если вы поставщик сетевого оборудования, присоединяйтесь к партнерской программе [Microsoft 365 Networking.](microsoft-365-networking-partner-program.md)</span><span class="sxs-lookup"><span data-stu-id="302aa-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="302aa-131">Регистрация в программе для создания принципов сетевого подключения Microsoft 365 к продуктам и решениям.</span><span class="sxs-lookup"><span data-stu-id="302aa-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="302aa-132">Как Contoso сделала сеть для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="302aa-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="302aa-133">Посмотрите, как корпорация Contoso, вымышленная представительская многонациональная компания, [оптимизировала сетевые устройства и подключения к Интернету](contoso-networking.md) для облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="302aa-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Корпорация Contoso](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="302aa-135">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="302aa-135">Next step</span></span>

<span data-ttu-id="302aa-136">Начните планирование сетей с помощью обзора подключения к сети [Microsoft 365.](microsoft-365-networking-overview.md)</span><span class="sxs-lookup"><span data-stu-id="302aa-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>