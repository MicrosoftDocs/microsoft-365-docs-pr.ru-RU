---
title: Сеть корпорации Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Узнайте о инфраструктуре сети Contoso и о том, как она использует технологию SD – WAN для оптимальной производительности сети до Microsoft 365 для корпоративных облачных служб.
ms.openlocfilehash: bc2ae68917258b94ed46ef0c1257f56e0736105c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685822"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="423cc-103">Сеть корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="423cc-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="423cc-p101">Чтобы перейти к инфраструктуре, включающей облако, специалисты по сетям компании Contoso фундаментальным образом изменили способ, которым сетевой трафик поступает в облачные службы. Вместо модели с внутренней звездообразной топологией, в которой подключения сети и трафик нацелены на следующий уровень офисной иерархии Contoso, специалисты ввели новую. Для этого они сопоставили ближайшее сетевое расположение Microsoft 365 в Интернете и расположения пользователей с локальным исходящим интернет-трафиком и локальными подключениями.</span><span class="sxs-lookup"><span data-stu-id="423cc-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud services travels. Instead of an internal hub and spoke model that focusses network connectivity and traffic for the next level of the Contoso office hierarchy, they worked to map user locations to local Internet egress and local connections to the closest Microsoft 365 network location on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="423cc-106">Сетевая инфраструктура компании Contoso</span><span class="sxs-lookup"><span data-stu-id="423cc-106">Contoso's networking infrastructure</span></span>

<span data-ttu-id="423cc-107">Ниже перечислены элементы сети компании Contoso, соединяющие офисы компании, расположенные по всему миру.</span><span class="sxs-lookup"><span data-stu-id="423cc-107">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="423cc-108">Сеть WAN с многопротокольной коммутацией по меткам (MPLS)</span><span class="sxs-lookup"><span data-stu-id="423cc-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="423cc-p102">Сеть MPLS WAN соединяет главный офис компании в Париже с региональными офисами, а также региональные офисы с подчиненными офисами с использованием конфигурации со звездообразной топологией. Это сделано для того, чтобы пользователи могли получать доступ к локальным серверам, на которых работают бизнес-приложения в парижском офисе. Кроме того, эта сеть маршрутизирует весь интернет-трафик общего назначения в офис в Париже, в котором устройства обеспечения безопасности сети "очищают" запросы. В каждом офисе маршрутизаторы передают трафик в проводные узлы или точки беспроводного доступа в подсетях, в которых используется частное пространство IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="423cc-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="423cc-113">Локальный непосредственный доступ в Интернет для трафика Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="423cc-113">Local direct Internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="423cc-p103">В каждом офисе есть устройство программно-конфигурируемой сети WAN (SD-WAN) с одной или несколькими локальными сетями поставщиков услуг Интернета с собственными подключениями к Интернету через прокси-сервер. Такую конфигурацию обычно реализуют в виде канала глобальной сети к локальному поставщику услуг Интернета, который также предоставляет общедоступные IP-адреса и локальный DNS-сервер.</span><span class="sxs-lookup"><span data-stu-id="423cc-p103">Each office has a Software-Defined WAN (SD-WAN) device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="423cc-116">Интернет-представительство</span><span class="sxs-lookup"><span data-stu-id="423cc-116">Internet presence</span></span>

  <span data-ttu-id="423cc-p104">Компании Contoso принадлежит общедоступное доменное имя contoso.com. Общедоступный веб-сайт компании Contoso, предназначенный для заказа ее продукции, представляет собой ряд серверов в центре обработки данных, подключенном к Интернету, в кампусе в Париже. Компания Contoso использует диапазон общедоступных IP-адресов /24 в Интернете.</span><span class="sxs-lookup"><span data-stu-id="423cc-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="423cc-120">Нас рисунке 1 показана инфраструктура сети компании Contoso и ее подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="423cc-120">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![Сеть компании Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="423cc-122">**Рис. 1. Сеть компании Contoso**</span><span class="sxs-lookup"><span data-stu-id="423cc-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="423cc-123">Использование технологии SD-WAN для оптимального подключения к ресурсам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="423cc-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="423cc-124">В компании Contoso следуют указанным ниже [принципам сетевого подключения для Microsoft 365](microsoft-365-network-connectivity-principles.md):</span><span class="sxs-lookup"><span data-stu-id="423cc-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

1. <span data-ttu-id="423cc-125">Определение и дифференциация сетевого трафика Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="423cc-125">Identify and differentiate Microsoft 365 network traffic</span></span>
2. <span data-ttu-id="423cc-126">Локальная организация исходящего трафика для сетевых подключений.</span><span class="sxs-lookup"><span data-stu-id="423cc-126">Egress network connections locally</span></span>
3. <span data-ttu-id="423cc-127">Недопущение "узких" мест в сети.</span><span class="sxs-lookup"><span data-stu-id="423cc-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="423cc-128">Обход дублируемых устройств обеспечения безопасности сети.</span><span class="sxs-lookup"><span data-stu-id="423cc-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="423cc-129">Существуют три категории сетевого трафика для Microsoft 365: оптимизированный, разрешенный, а также используемый по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="423cc-129">There are three categories of network traffic for Microsoft 365: Optimize, Allow, and Default.</span></span> <span data-ttu-id="423cc-130">Оптимизированный и разрешенный трафик представляет собой надежный сетевой трафик, зашифрованный и защищенный в конечных точках и направляемый в сеть Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="423cc-130">Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="423cc-131">В компании Contoso решили следующее:</span><span class="sxs-lookup"><span data-stu-id="423cc-131">Contoso decided to:</span></span>

- <span data-ttu-id="423cc-132">Использовать непосредственный исходящий интернет-трафик для передачи оптимизированного и разрешенного трафика, а также перенаправлять весь трафик, используемый по умолчанию, к центральному подключению к Интернету в Париже.</span><span class="sxs-lookup"><span data-stu-id="423cc-132">Use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

- <span data-ttu-id="423cc-133">Развернуть устройства SD-WAN во всех расположениях офисов компании в качестве простого способа выполнения перечисленных выше принципов. Кроме того, этот подход позволяет достичь оптимальной производительности сети для работы с облачными службами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="423cc-133">Deploy SD-WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="423cc-134">Устройство SD-WAN оснащено портом для подключения к локальной сети офиса и несколькими портами для подключения к глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="423cc-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="423cc-135">Один порт глобальной сети подключен к сети MPLS компании, а другой порт глобальной сети подключен к сети локального поставщика услуг Интернета.</span><span class="sxs-lookup"><span data-stu-id="423cc-135">One WAN port connects to their MPLS network and another WAN port connects to a local ISP circuit.</span></span> <span data-ttu-id="423cc-136">Устройство SD-WAN выполняет маршрутизацию оптимизированного и разрешенного сетевого трафика в канал поставщика услуг Интернета.</span><span class="sxs-lookup"><span data-stu-id="423cc-136">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="423cc-137">Инфраструктура бизнес-приложений компании Contoso</span><span class="sxs-lookup"><span data-stu-id="423cc-137">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="423cc-138">Специалисты компании Contoso разработали инфраструктуру интрасети для бизнес-приложений и серверов для указанных ниже целей.</span><span class="sxs-lookup"><span data-stu-id="423cc-138">Contoso has architected its line of business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="423cc-139">В подчиненных офисах используются локальные кэширующие серверы для хранения часто используемых документов и внутренних веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="423cc-139">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="423cc-p107">В региональных центрах используются региональные серверы приложений, предназначенные для региональных и подчиненных офисов. Эти серверы синхронизируются с серверами в центральном офисе в Париже.</span><span class="sxs-lookup"><span data-stu-id="423cc-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="423cc-142">В кампусе в Париже расположены центры обработки данных с централизованными серверами приложений, которые обслуживают всю организацию.</span><span class="sxs-lookup"><span data-stu-id="423cc-142">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="423cc-143">На рисунке 2 показан процент сетевого трафика при доступе к серверам в интрасети компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="423cc-143">Figure 2 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![Инфраструктура корпорации Contoso для внутренних приложений](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="423cc-145">**Рис. 2. Инфраструктура компании Contoso для внутренних приложений**</span><span class="sxs-lookup"><span data-stu-id="423cc-145">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="423cc-p108">60 % ресурсов, необходимых сотрудникам подчиненных или региональных центральных офисов, могут обслуживаться серверами подчиненных и региональных центральных офисов. Дополнительные 40 % запросов на ресурсы должны передаваться в кампус в Париже по каналу глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="423cc-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-for-enterprise"></a><span data-ttu-id="423cc-148">Анализ сети Contoso и подготовка своей сети к Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="423cc-148">Contoso's network analysis and preparation of their network for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="423cc-p109">Успешное внедрение Microsoft 365 для корпоративных служб пользователями Contoso зависит от высокой доступности и работоспособного подключения к Интернету или непосредственно к облачным службам Майкрософт. В компании Contoso выполнены следующие действия по планированию и внедрению оптимизированного подключения к Microsoft 365 для корпоративных облачных служб.</span><span class="sxs-lookup"><span data-stu-id="423cc-p109">Successful adoption of Microsoft 365 for enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="423cc-151">Создание схемы глобальной сети, используемой компанией, для упрощения планирования</span><span class="sxs-lookup"><span data-stu-id="423cc-151">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="423cc-p110">Специалисты компании Contoso начали планирование сети компании с создания схемы, на которой показаны расположения компании, существующие сетевые подключения, имеющиеся устройства периметра сети и классы служб, управляемые в сети. Они использовали эту схему на каждом последующем этапе планирования и реализации подключений к сети.</span><span class="sxs-lookup"><span data-stu-id="423cc-p110">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network. They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="423cc-154">Создан план для Microsoft 365 для подключения к корпоративной сети в корпоративной сети</span><span class="sxs-lookup"><span data-stu-id="423cc-154">Created a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="423cc-155">Специалисты компании Contoso воспользовались [принципами сетевого подключения для Microsoft 365](microsoft-365-network-connectivity-principles.md), разработали эталонные сетевые архитектуры и приняли SD-WAN в качестве предпочтительной топологии для подключения к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="423cc-155">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and provided reference network architectures to determine SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="423cc-156">Анализ использования подключения к Интернету и пропускной способности сети MPLS WAN в каждом офисе и расширение полосы пропускания сети (при необходимости)</span><span class="sxs-lookup"><span data-stu-id="423cc-156">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="423cc-157">В каждом офисе было проанализировано текущее использование сети и расширена ее полоса пропускания, чтобы при прохождении прогнозируемого объема трафика для работы с облачными службами Microsoft 365 оставался неиспользованный запас пропускной способности, равный приблизительно 20 %.</span><span class="sxs-lookup"><span data-stu-id="423cc-157">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="423cc-158">Оптимизация производительности сети при доступе к сетевым службам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="423cc-158">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="423cc-159">В компании Contoso определили набор конечных точек Office 365, Intune и Azure и настроили брандмауэры, устройства для обеспечения безопасности и другие системы, включенные в маршрут в Интернете, достигнув при этом оптимальной производительности сети.</span><span class="sxs-lookup"><span data-stu-id="423cc-159">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance.</span></span> <span data-ttu-id="423cc-160">Конечные точки для оптимизированного и разрешенного трафика Office 365 были настроены в устройствах SD-WAN для маршрутизации через сеть поставщика услуг Интернета.</span><span class="sxs-lookup"><span data-stu-id="423cc-160">Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="423cc-161">Настройка внутренних DNS</span><span class="sxs-lookup"><span data-stu-id="423cc-161">Configured internal DNS</span></span>

   <span data-ttu-id="423cc-162">Для обеспечения трафика в Microsoft 365 необходима работоспособная DNS, которую можно найти в локальной сети.</span><span class="sxs-lookup"><span data-stu-id="423cc-162">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="423cc-163">Проверка подключений к конечным точкам сети и портам</span><span class="sxs-lookup"><span data-stu-id="423cc-163">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="423cc-164">В компании Contoso были выполнены средства тестирования сетевых подключений, предоставляемые корпорацией Майкрософт для проверки возможности подключения для Microsoft 365 для корпоративных облачных служб.</span><span class="sxs-lookup"><span data-stu-id="423cc-164">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="423cc-165">Оптимизация компьютеров сотрудников для подключения к сети</span><span class="sxs-lookup"><span data-stu-id="423cc-165">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="423cc-166">Специалисты компании проверили, установлены ли на компьютерах последние обновления операционных систем и на всех ли клиентах активны системы мониторинга безопасности в конечных точках.</span><span class="sxs-lookup"><span data-stu-id="423cc-166">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="423cc-167">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="423cc-167">Next step</span></span>

<span data-ttu-id="423cc-168">[Узнайте,](contoso-identity.md) как специалисты компании Contoso используют локальные доменные службы Active Directory (AD DS) в облаке для сотрудников и федерацию проверки подлинности для клиентов и партнеров по бизнесу.</span><span class="sxs-lookup"><span data-stu-id="423cc-168">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises Active Directory Domain Services (AD DS) in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="423cc-169">См. также</span><span class="sxs-lookup"><span data-stu-id="423cc-169">See also</span></span>

[<span data-ttu-id="423cc-170">Сетевая схема для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="423cc-170">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="423cc-171">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="423cc-171">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="423cc-172">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="423cc-172">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
