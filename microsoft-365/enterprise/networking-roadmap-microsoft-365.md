---
title: План сети для Microsoft 365
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
description: План реализации сети Microsoft 365.
ms.openlocfilehash: 2962adf7bdca35d06672696471e0932fd1a7b09c
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787755"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="4e800-103">План сети для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e800-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="4e800-104">Microsoft 365 для предприятий включает облачные службы для совместной работы и повышения производительности, Microsoft Intune, а также множество служб удостоверений и безопасности Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="4e800-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="4e800-105">Для всех этих облачных служб используются безопасные, производительные и надежные подключения с клиентских устройств через Интернет или выделенные каналы.</span><span class="sxs-lookup"><span data-stu-id="4e800-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="4e800-106">Чтобы разместить эти службы и сделать их доступными клиентам по всему миру, корпорация Майкрософт разработала сетевую инфраструктуру, в которой основное внимание уделено производительности и интеграции.</span><span class="sxs-lookup"><span data-stu-id="4e800-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="4e800-107">Важной частью подключения Microsoft 365 является настройка сети и подключений к Интернету для оптимизированного доступа.</span><span class="sxs-lookup"><span data-stu-id="4e800-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="4e800-108">Настройка локальной сети для доступа к глобально распределенному облаку SaaS отличается от традиционной сети, оптимизированной для трафика к локальному центру обработки данных и центральному подключению к Интернету.</span><span class="sxs-lookup"><span data-stu-id="4e800-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="4e800-109">С помощью этих статей можно ознакомиться с основными различиями пограничных устройств, клиентских компьютеров и локальной сети, а также изменять их для обеспечения оптимальной производительности для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e800-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="4e800-110">План</span><span class="sxs-lookup"><span data-stu-id="4e800-110">Plan</span></span>

<span data-ttu-id="4e800-111">На этапе планирования сетевой реализации:</span><span class="sxs-lookup"><span data-stu-id="4e800-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="4e800-112">Понять, как работает сеть Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e800-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="4e800-113">Оценка текущего сетевого подключения</span><span class="sxs-lookup"><span data-stu-id="4e800-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="4e800-114">Определение того, является ли ExpressRoute правильным для вашей организации</span><span class="sxs-lookup"><span data-stu-id="4e800-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="4e800-115">Планирование сетевых устройств</span><span class="sxs-lookup"><span data-stu-id="4e800-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="4e800-116">Настройка сети для миграции</span><span class="sxs-lookup"><span data-stu-id="4e800-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="4e800-117">Развертывание</span><span class="sxs-lookup"><span data-stu-id="4e800-117">Deploy</span></span>

<span data-ttu-id="4e800-118">На этапе развертывания сетевой реализации:</span><span class="sxs-lookup"><span data-stu-id="4e800-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="4e800-119">Убедитесь, что ваша корпоративная сеть оптимизирована для подключения к Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e800-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="4e800-120">Добавление доменов DNS для организации</span><span class="sxs-lookup"><span data-stu-id="4e800-120">Add the DNS domains for your organization</span></span>](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [<span data-ttu-id="4e800-121">Оптимизация подключения к конечным точкам Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e800-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="4e800-122">Оптимизация подключения для удаленных работников</span><span class="sxs-lookup"><span data-stu-id="4e800-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="4e800-123">При необходимости [настройте ExpressRoute](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="4e800-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="4e800-124">Управление</span><span class="sxs-lookup"><span data-stu-id="4e800-124">Manage</span></span>

<span data-ttu-id="4e800-125">На этапе управления сетевой реализацией:</span><span class="sxs-lookup"><span data-stu-id="4e800-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="4e800-126">Убедитесь, что сетевые устройства используют последние конечные точки Office 365</span><span class="sxs-lookup"><span data-stu-id="4e800-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="4e800-127">Мониторинг и настройка производительности сети</span><span class="sxs-lookup"><span data-stu-id="4e800-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="4e800-128">Отслеживание подключений ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="4e800-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="4e800-129">Поставщики сетевого оборудования</span><span class="sxs-lookup"><span data-stu-id="4e800-129">Network equipment vendors</span></span>

<span data-ttu-id="4e800-130">Если вы поставщик сетевого оборудования, присоединяйтесь к партнерской программе [Microsoft 365 networking.](microsoft-365-networking-partner-program.md)</span><span class="sxs-lookup"><span data-stu-id="4e800-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="4e800-131">Зарегистрироваться в программе, чтобы встроить принципы сетевого подключения Microsoft 365 в свои продукты и решения.</span><span class="sxs-lookup"><span data-stu-id="4e800-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="4e800-132">Как Contoso в сети для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e800-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="4e800-133">Посмотрите, как корпорация Contoso, вымышленная представительская многонациональная компания, [оптимизировала сетевые устройства и подключения к Интернету](contoso-networking.md) для облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e800-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Корпорация Contoso](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="4e800-135">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="4e800-135">Next step</span></span>

<span data-ttu-id="4e800-136">Начните планирование сети с помощью обзора сетевых подключений [Microsoft 365.](microsoft-365-networking-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4e800-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>
