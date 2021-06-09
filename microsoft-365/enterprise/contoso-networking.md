---
title: Сеть корпорации Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Поймите инфраструктуру сети Contoso и то, как компания использует свою технологию SD-WAN для оптимальной производительности сетей для Microsoft 365 корпоративных облачных служб.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754018"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="30612-103">Сеть корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="30612-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="30612-104">Чтобы принять облачную инфраструктуру, Contoso разработала фундаментальный сдвиг в способе перемещения сетевого трафика в облачные службы.</span><span class="sxs-lookup"><span data-stu-id="30612-104">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels.</span></span> <span data-ttu-id="30612-105">Вместо внутренней модели, которая фокусирует сетевое подключение и трафик на следующем уровне иерархии офисов, они сопоясают расположения пользователей с локальным интернет-отступом и локальными подключениями к ближайшему расположению Microsoft 365 сети в Интернете.</span><span class="sxs-lookup"><span data-stu-id="30612-105">Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="30612-106">Инфраструктура сети</span><span class="sxs-lookup"><span data-stu-id="30612-106">Networking infrastructure</span></span>

<span data-ttu-id="30612-107">Это сетевые элементы, связывающие офисы Contoso по всему миру:</span><span class="sxs-lookup"><span data-stu-id="30612-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="30612-108">Сеть WAN с многопротокольной коммутацией по меткам (MPLS)</span><span class="sxs-lookup"><span data-stu-id="30612-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="30612-109">Сеть WAN MPLS соединяет штаб-квартиру в Париже с региональными офисами и региональными офисами со спутниковыми офисами в конфигурации с помощью центра связи.</span><span class="sxs-lookup"><span data-stu-id="30612-109">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration.</span></span> <span data-ttu-id="30612-110">Сеть позволяет пользователям получать доступ к локальному серверу, который является частью бизнес-приложений в парижской штаб-квартире.</span><span class="sxs-lookup"><span data-stu-id="30612-110">The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters.</span></span> <span data-ttu-id="30612-111">Он также передает любой общий интернет-трафик в парижский офис, где устройства сетевой безопасности чистили запросы.</span><span class="sxs-lookup"><span data-stu-id="30612-111">It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests.</span></span> <span data-ttu-id="30612-112">В каждом офисе маршрутизаторы доставляют трафик проводным хостам или точкам беспроводного доступа в подсетях, которые используют личное пространство IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="30612-112">Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="30612-113">Локальный прямой доступ к интернету для Microsoft 365 трафика</span><span class="sxs-lookup"><span data-stu-id="30612-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="30612-114">Каждый офис имеет программное устройство WAN (SD-WAN), которое имеет один или несколько локальных сетевых цепей интернет-провайдера с собственным подключением к Интернету через прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="30612-114">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server.</span></span> <span data-ttu-id="30612-115">Это обычно реализуется в качестве ссылки WAN на локальный isP, который также предоставляет общедоступные IP-адреса и локальный DNS-сервер.</span><span class="sxs-lookup"><span data-stu-id="30612-115">This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="30612-116">Интернет-представительство</span><span class="sxs-lookup"><span data-stu-id="30612-116">Internet presence</span></span>

  <span data-ttu-id="30612-117">Contoso владеет доменным именем contoso \. com.</span><span class="sxs-lookup"><span data-stu-id="30612-117">Contoso owns the contoso\.com public domain name.</span></span> <span data-ttu-id="30612-118">Общедоступный веб-сайт Contoso для заказа продуктов — это набор серверов в центр обработки данных, подключенный к Интернету в кампусе Парижа.</span><span class="sxs-lookup"><span data-stu-id="30612-118">The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus.</span></span> <span data-ttu-id="30612-119">Contoso использует диапазон общедоступных IP-адресов /24 в Интернете.</span><span class="sxs-lookup"><span data-stu-id="30612-119">Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="30612-120">На рисунке 1 показана инфраструктура сети Contoso и ее подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="30612-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Сеть Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="30612-122">**Рис. 1. Сеть Contoso**</span><span class="sxs-lookup"><span data-stu-id="30612-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="30612-123">Использование технологии SD-WAN для оптимального подключения к ресурсам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="30612-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="30612-124">В компании Contoso следуют указанным ниже [принципам сетевого подключения для Microsoft 365](microsoft-365-network-connectivity-principles.md):</span><span class="sxs-lookup"><span data-stu-id="30612-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="30612-125">Определение и дифференциация сетевого трафика Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30612-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="30612-126">Локальная организация исходящего трафика для сетевых подключений.</span><span class="sxs-lookup"><span data-stu-id="30612-126">Egress network connections locally</span></span>
- <span data-ttu-id="30612-127">Недопущение "узких" мест в сети.</span><span class="sxs-lookup"><span data-stu-id="30612-127">Avoid network hairpins</span></span>
- <span data-ttu-id="30612-128">Обход дублируемых устройств обеспечения безопасности сети.</span><span class="sxs-lookup"><span data-stu-id="30612-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="30612-129">Существует три категории сетевого трафика для Microsoft 365: *Оптимизируйте,* *разрешить* и *по умолчанию*.</span><span class="sxs-lookup"><span data-stu-id="30612-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="30612-130">Оптимизация и разрешение трафика — это надежный сетевой трафик, зашифрованный и защищенный в конечных точках и предназначенный для Microsoft 365 сети.</span><span class="sxs-lookup"><span data-stu-id="30612-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="30612-131">В компании Contoso решили следующее:</span><span class="sxs-lookup"><span data-stu-id="30612-131">Contoso decided to:</span></span>

- <span data-ttu-id="30612-132">Используйте прямой интернет-регресс для оптимизации и допуска трафика категорий и для перенаправки всего трафика категории по умолчанию в центральное подключение к Интернету в Париже.</span><span class="sxs-lookup"><span data-stu-id="30612-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="30612-133">Развертывание устройств SD-WAN в каждом офисе в качестве простого способа выполнения этих принципов и достижения оптимальной производительности сети для Microsoft 365 облачных служб.</span><span class="sxs-lookup"><span data-stu-id="30612-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="30612-134">Устройство SD-WAN оснащено портом для подключения к локальной сети офиса и несколькими портами для подключения к глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="30612-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="30612-135">Один порт WAN подключается к сети MPLS.</span><span class="sxs-lookup"><span data-stu-id="30612-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="30612-136">Другой подключается к локальной схеме isP.</span><span class="sxs-lookup"><span data-stu-id="30612-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="30612-137">Устройство SD-WAN выполняет маршрутизацию оптимизированного и разрешенного сетевого трафика в канал поставщика услуг Интернета.</span><span class="sxs-lookup"><span data-stu-id="30612-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="30612-138">Инфраструктура бизнес-приложений Contoso</span><span class="sxs-lookup"><span data-stu-id="30612-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="30612-139">Contoso архитектором своей бизнес-приложения и инфраструктуры серверной интрасети для следующих проектов:</span><span class="sxs-lookup"><span data-stu-id="30612-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="30612-140">В подчиненных офисах используются локальные кэширующие серверы для хранения часто используемых документов и внутренних веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="30612-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="30612-p107">В региональных центрах используются региональные серверы приложений, предназначенные для региональных и подчиненных офисов. Эти серверы синхронизируются с серверами в центральном офисе в Париже.</span><span class="sxs-lookup"><span data-stu-id="30612-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="30612-143">Центр обработки данных кампуса в Париже содержит централизованные серверы приложений, обслуживающих всю организацию.</span><span class="sxs-lookup"><span data-stu-id="30612-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="30612-144">На рисунке 2 показан процент пропускной способности сетевого трафика, используемого при доступе к серверам внутрисети Contoso.</span><span class="sxs-lookup"><span data-stu-id="30612-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![Инфраструктура Contoso для внутренних приложений](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="30612-146">**Рис. 2. Инфраструктура Contoso для внутренних приложений**</span><span class="sxs-lookup"><span data-stu-id="30612-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="30612-147">Для офисов спутникового или регионального концентратора 60 процентов ресурсов, необходимых сотрудникам, могут быть обслуживаются серверами региональных и спутниковых офисных серверов.</span><span class="sxs-lookup"><span data-stu-id="30612-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="30612-148">Дополнительные 40 процентов запросов на ресурсы должны переходить по ссылке WAN в кампус в Париже.</span><span class="sxs-lookup"><span data-stu-id="30612-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="30612-149">Анализ сети и подготовка к Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="30612-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="30612-150">Успешное Microsoft 365 корпоративных служб пользователями Contoso зависит от высокодоступного и результативного подключения к Интернету или непосредственно к облачным службам Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="30612-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="30612-151">Contoso принял эти меры для планирования и реализации оптимизированных подключений для Microsoft 365 корпоративных облачных служб:</span><span class="sxs-lookup"><span data-stu-id="30612-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="30612-152">Создание сетевой схемы WAN для планирования</span><span class="sxs-lookup"><span data-stu-id="30612-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="30612-153">Чтобы приступить к планированию сети, Contoso создала схему с указанием расположения офисов, существующего подключения к сети, существующих устройств периметра сети и классов служб, управляемых в сети.</span><span class="sxs-lookup"><span data-stu-id="30612-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="30612-154">Они использовали эту схему для каждого последующего шага при планировании и реализации подключения к сети.</span><span class="sxs-lookup"><span data-stu-id="30612-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="30612-155">Создание плана для Microsoft 365 для подключения к корпоративной сети</span><span class="sxs-lookup"><span data-stu-id="30612-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="30612-156">Для определения SD-WAN в качестве предпочтительной топологии [для](microsoft-365-network-connectivity-principles.md) Microsoft 365 contoso использовал принципы сетевого подключения Microsoft 365 и образцы эталонных сетевых архитектур.</span><span class="sxs-lookup"><span data-stu-id="30612-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="30612-157">Анализ использования подключения к Интернету и пропускной способности MPLS-WAN в каждом офисе и увеличение пропускной способности при необходимости</span><span class="sxs-lookup"><span data-stu-id="30612-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="30612-158">Было проанализировано текущее использование каждого офиса, а цепи были увеличены таким образом, чтобы Microsoft 365 облачного трафика функционировал в среднем на 20 процентов неиспользоваемой емкости.</span><span class="sxs-lookup"><span data-stu-id="30612-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="30612-159">Оптимизация производительности сетевых служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="30612-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="30612-160">Contoso определил набор конечных точек Office 365, Intune и Azure, а также настроил брандмауэры, устройства безопасности и другие системы на пути к интернету для оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="30612-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="30612-161">Конечные точки для Office 365 и разрешить трафик категории были настроены на устройства SD-WAN для маршрутивки по схеме ISP.</span><span class="sxs-lookup"><span data-stu-id="30612-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="30612-162">Настройка внутренней DNS</span><span class="sxs-lookup"><span data-stu-id="30612-162">Configure internal DNS</span></span>

   <span data-ttu-id="30612-163">Для обеспечения трафика в Microsoft 365 необходима работоспособная DNS, которую можно найти в локальной сети.</span><span class="sxs-lookup"><span data-stu-id="30612-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="30612-164">Проверка конечной точки сети и подключения к порту</span><span class="sxs-lookup"><span data-stu-id="30612-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="30612-165">Contoso запустила средства тестирования подключения к сети Майкрософт для проверки подключения Microsoft 365 для корпоративных облачных служб.</span><span class="sxs-lookup"><span data-stu-id="30612-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="30612-166">Оптимизация компьютеров сотрудников для подключения к сети</span><span class="sxs-lookup"><span data-stu-id="30612-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="30612-167">Были проверены отдельные компьютеры, чтобы обеспечить установку последних обновлений операционной системы и активное наблюдение за безопасностью конечных точек для всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="30612-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="30612-168">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="30612-168">Next step</span></span>

<span data-ttu-id="30612-169">Узнайте, как Contoso использует собственные службы [домена Active Directory](contoso-identity.md) в облаке для сотрудников и федературу проверки подлинности для клиентов и бизнес-партнеров.</span><span class="sxs-lookup"><span data-stu-id="30612-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="30612-170">См. также</span><span class="sxs-lookup"><span data-stu-id="30612-170">See also</span></span>

[<span data-ttu-id="30612-171">Дорожная карта сети для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30612-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="30612-172">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="30612-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="30612-173">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="30612-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
