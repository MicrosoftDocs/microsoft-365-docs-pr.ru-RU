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
description: Узнайте о инфраструктуре сети Contoso и о том, как компания использует технологию SD – WAN для оптимальной производительности сети для Microsoft 365 для корпоративных облачных служб.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754018"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="b3041-103">Сеть корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="b3041-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="b3041-p101">Чтобы принять облачную инфраструктуру, компания Contoso изработала фундаментальный сдвиг сетевого трафика к облачным службам. Вместо внутренней модели "звезда", которая нацелена на сетевое подключение и трафик для следующего уровня иерархии Office, они сопоставили расположения пользователей с локальными выходами в Интернет и локальными подключениями к ближайшему сетевому расположению Microsoft 365 в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b3041-p101">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels. Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="b3041-106">Сетевая инфраструктура</span><span class="sxs-lookup"><span data-stu-id="b3041-106">Networking infrastructure</span></span>

<span data-ttu-id="b3041-107">Это элементы сети, связывающие офисы Contoso по всему миру:</span><span class="sxs-lookup"><span data-stu-id="b3041-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="b3041-108">Сеть WAN с многопротокольной коммутацией по меткам (MPLS)</span><span class="sxs-lookup"><span data-stu-id="b3041-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="b3041-p102">Глобальная сеть MPLS соединяет штаб-квартира с региональными офисами и региональными офисами для спутниковых офисов в конфигурации с периферийными и центральными офисами. Сеть позволяет пользователям получать доступ к локальным серверам, которые составляют бизнес-приложения в штаб-квартирах Париж. Кроме того, он направляет любой общий Интернет трафик в Office Париж, где устройства безопасности сети пропускают запросы. В каждом офисе маршрутизаторы доставлять трафик на проводные узлы или точки беспроводного доступа в подсетях, использующих пространство частных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="b3041-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration. The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters. It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="b3041-113">Локальный прямой доступ к Интернету для трафика Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3041-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="b3041-p103">В каждом офисе есть устройство глобальной сети WAN (SD-WAN), имеющее одну или несколько локальных сетевых каналов ISP, подключенных к Интернету через прокси-сервер. Обычно это реализуется в виде связи WAN с локальным поставщиком услуг Интернета, который также предоставляет общедоступные IP-адреса и локальный DNS-сервер.</span><span class="sxs-lookup"><span data-stu-id="b3041-p103">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="b3041-116">Интернет-представительство</span><span class="sxs-lookup"><span data-stu-id="b3041-116">Internet presence</span></span>

  <span data-ttu-id="b3041-p104">Contoso владеет \. общедоступным доменом имен com для contoso. Общедоступный веб-сайт contoso для заказа продуктов — это набор серверов в центре обработки данных, подключенном к Интернету, в кампусе Париж. Contoso использует диапазон общедоступных IP-адресов (или 24) в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b3041-p104">Contoso owns the contoso\.com public domain name. The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="b3041-120">На рисунке 1 показана сетевая инфраструктура Contoso и ее подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="b3041-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Сеть Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="b3041-122">**Рисунок 1: сеть Contoso**</span><span class="sxs-lookup"><span data-stu-id="b3041-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="b3041-123">Использование технологии SD-WAN для оптимального подключения к ресурсам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b3041-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="b3041-124">В компании Contoso следуют указанным ниже [принципам сетевого подключения для Microsoft 365](microsoft-365-network-connectivity-principles.md):</span><span class="sxs-lookup"><span data-stu-id="b3041-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="b3041-125">Определение и дифференциация сетевого трафика Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3041-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="b3041-126">Локальная организация исходящего трафика для сетевых подключений.</span><span class="sxs-lookup"><span data-stu-id="b3041-126">Egress network connections locally</span></span>
- <span data-ttu-id="b3041-127">Недопущение "узких" мест в сети.</span><span class="sxs-lookup"><span data-stu-id="b3041-127">Avoid network hairpins</span></span>
- <span data-ttu-id="b3041-128">Обход дублируемых устройств обеспечения безопасности сети.</span><span class="sxs-lookup"><span data-stu-id="b3041-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="b3041-129">Существует три категории сетевого трафика для Microsoft 365: *оптимизировать*, разрешить и *использовать* *по умолчанию*.</span><span class="sxs-lookup"><span data-stu-id="b3041-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="b3041-130">Оптимизировать и разрешать трафик является надежным сетевым трафиком, зашифрованным и защищенным в конечных точках и предназначенным для сети Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3041-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="b3041-131">В компании Contoso решили следующее:</span><span class="sxs-lookup"><span data-stu-id="b3041-131">Contoso decided to:</span></span>

- <span data-ttu-id="b3041-132">Используйте прямой выход из Интернета для оптимизации и разрешения трафика категорий, а также для перенаправления трафика категории по умолчанию в Центральное подключение к Интернету на основе Париж.</span><span class="sxs-lookup"><span data-stu-id="b3041-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="b3041-133">Развертывайте устройства с SD для глобальной сети на каждом офисе, чтобы выполнить эти принципы и обеспечить оптимальную производительность сети для служб Microsoft 365 Cloud.</span><span class="sxs-lookup"><span data-stu-id="b3041-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="b3041-134">Устройство SD-WAN оснащено портом для подключения к локальной сети офиса и несколькими портами для подключения к глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="b3041-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="b3041-135">Один порт WAN подключается к своей сети MPLS.</span><span class="sxs-lookup"><span data-stu-id="b3041-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="b3041-136">Другой подключается к локальной цепи ISP.</span><span class="sxs-lookup"><span data-stu-id="b3041-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="b3041-137">Устройство SD-WAN выполняет маршрутизацию оптимизированного и разрешенного сетевого трафика в канал поставщика услуг Интернета.</span><span class="sxs-lookup"><span data-stu-id="b3041-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="b3041-138">Инфраструктура бизнес-приложений contoso</span><span class="sxs-lookup"><span data-stu-id="b3041-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="b3041-139">Компания Contoso разработана как бизнес-приложение и инфраструктура интрасети сервера для следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="b3041-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="b3041-140">В подчиненных офисах используются локальные кэширующие серверы для хранения часто используемых документов и внутренних веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="b3041-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="b3041-p107">В региональных центрах используются региональные серверы приложений, предназначенные для региональных и подчиненных офисов. Эти серверы синхронизируются с серверами в центральном офисе в Париже.</span><span class="sxs-lookup"><span data-stu-id="b3041-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="b3041-143">Центры обработки данных для Париж содержат централизованные серверы приложений, которые обслуживают всю организацию.</span><span class="sxs-lookup"><span data-stu-id="b3041-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="b3041-144">На рисунке 2 показана процентная доля мощности сетевого трафика, используемая при доступе к серверам в интрасети contoso.</span><span class="sxs-lookup"><span data-stu-id="b3041-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![Инфраструктура Contoso для внутренних приложений](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="b3041-146">**Рисунок 2: инфраструктура Contoso для внутренних приложений**</span><span class="sxs-lookup"><span data-stu-id="b3041-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="b3041-147">Для спутниковых или региональных офисных отделений 60 процентов ресурсов, необходимых сотрудникам, могут обслуживать спутниковые и региональные серверы центрального офиса.</span><span class="sxs-lookup"><span data-stu-id="b3041-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="b3041-148">Дополнительные 40 процентов запросов ресурсов должны поступать по каналу WAN в кампусе Париж.</span><span class="sxs-lookup"><span data-stu-id="b3041-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="b3041-149">Анализ сети и подготовка к работе с Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="b3041-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="b3041-150">Успешное внедрение Microsoft 365 для корпоративных служб пользователями Contoso зависит от высокой доступности и работоспособного подключения к Интернету или напрямую к облачным службам Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b3041-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="b3041-151">В компании Contoso выполнены следующие действия по планированию и внедрению оптимизированного подключения к Microsoft 365 для корпоративных облачных служб.</span><span class="sxs-lookup"><span data-stu-id="b3041-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="b3041-152">Создание схемы глобальной сети организации для упрощения планирования</span><span class="sxs-lookup"><span data-stu-id="b3041-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="b3041-153">Для запуска планирования сети компания Contoso создала схему, в которой показаны расположения Office, существующие сетевые подключения, существующие сетевые устройства периметра и классы службы, управляемые в сети.</span><span class="sxs-lookup"><span data-stu-id="b3041-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="b3041-154">Эта схема использовалась для каждого последующего этапа планирования и реализации сетевого подключения.</span><span class="sxs-lookup"><span data-stu-id="b3041-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="b3041-155">Создание плана для Microsoft 365 для подключения к корпоративной сети в корпоративной сети</span><span class="sxs-lookup"><span data-stu-id="b3041-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="b3041-156">В компании Contoso использовались [принципы сетевых подключений microsoft 365](microsoft-365-network-connectivity-principles.md) и примеры сетевых архитектур, чтобы идентифицировать SD/WAN в качестве предпочтительной топологии для подключения к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3041-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="b3041-157">Проанализируйте использование подключения к Интернету и пропускную способность MPLS – WAN на каждом офисе и увеличьте пропускную способность по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="b3041-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="b3041-158">Все сведения о текущем использовании Office были проанализированы, а цепи были увеличены, так что предсказуемый трафик на основе Microsoft 365 на облачной основе будет работать в среднем на 20 процентов неиспользуемых мощностей.</span><span class="sxs-lookup"><span data-stu-id="b3041-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="b3041-159">Оптимизация производительности служб Microsoft Network Services</span><span class="sxs-lookup"><span data-stu-id="b3041-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="b3041-160">Для оптимальной производительности компания Contoso определила набор конечных точек Office 365, Intune и Azure, а также настроенные брандмауэры, устройства безопасности и другие системы в пути к Интернету.</span><span class="sxs-lookup"><span data-stu-id="b3041-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="b3041-161">Конечные точки для Office 365 оптимизация и разрешение трафика категорий были настроены на устройствах SD с глобальной сетью для маршрутизации через цепь ISP.</span><span class="sxs-lookup"><span data-stu-id="b3041-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="b3041-162">Настройка внутренних DNS-имен</span><span class="sxs-lookup"><span data-stu-id="b3041-162">Configure internal DNS</span></span>

   <span data-ttu-id="b3041-163">Для обеспечения трафика в Microsoft 365 необходима работоспособная DNS, которую можно найти в локальной сети.</span><span class="sxs-lookup"><span data-stu-id="b3041-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="b3041-164">Проверка подключения к конечной точке сети и порту</span><span class="sxs-lookup"><span data-stu-id="b3041-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="b3041-165">Компания Contoso запустила средства тестирования сетевых подключений Майкрософт для проверки возможности подключения для Microsoft 365 для корпоративных облачных служб.</span><span class="sxs-lookup"><span data-stu-id="b3041-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="b3041-166">Оптимизация компьютеров сотрудников для подключения к сети</span><span class="sxs-lookup"><span data-stu-id="b3041-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="b3041-167">Отдельные компьютеры были проверены, чтобы убедиться, что установлены последние обновления операционной системы, и что мониторинг безопасности конечной точки был активен на всех клиентах.</span><span class="sxs-lookup"><span data-stu-id="b3041-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="b3041-168">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="b3041-168">Next step</span></span>

<span data-ttu-id="b3041-169">Узнайте, как Contoso применяет [локальные доменные службы Active Directory в облаке](contoso-identity.md) для сотрудников и Федерацию проверки подлинности для клиентов и бизнес-партнеров.</span><span class="sxs-lookup"><span data-stu-id="b3041-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3041-170">Дополнительные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="b3041-170">See also</span></span>

[<span data-ttu-id="b3041-171">Сетевая схема для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3041-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="b3041-172">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="b3041-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b3041-173">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="b3041-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
