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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказано об инфраструктуре сети компании Contoso и о том, как специалисты компании используют разработанную ими технологию SD-WAN для достижения оптимальной производительности сети для облачных служб Microsoft 365 корпоративный.
ms.openlocfilehash: 20279ac0aed1b7ad86e1fc8e1d78a412230eba52
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068352"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="b69ae-103">Сеть корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="b69ae-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="b69ae-p101">Чтобы перейти к инфраструктуре, включающей облако, специалисты по сетям компании Contoso фундаментальным образом изменили способ, которым сетевой трафик поступает в облачные службы. Вместо модели с внутренней звездообразной топологией, в которой подключения сети и трафик нацелены на следующий уровень офисной иерархии Contoso, специалисты ввели новую. Для этого они сопоставили ближайшее сетевое расположение Microsoft 365 в Интернете и расположения пользователей с локальным исходящим интернет-трафиком и локальными подключениями.</span><span class="sxs-lookup"><span data-stu-id="b69ae-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud services travels. Instead of an internal hub and spoke model that focusses network connectivity and traffic for the next level of the Contoso office hierarchy, they worked to map user locations to local Internet egress and local connections to the closest Microsoft 365 network location on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="b69ae-106">Сетевая инфраструктура компании Contoso</span><span class="sxs-lookup"><span data-stu-id="b69ae-106">Contoso's networking infrastructure</span></span>

<span data-ttu-id="b69ae-107">Ниже перечислены элементы сети компании Contoso, соединяющие офисы компании, расположенные по всему миру.</span><span class="sxs-lookup"><span data-stu-id="b69ae-107">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="b69ae-108">Сеть WAN с многопротокольной коммутацией по меткам (MPLS)</span><span class="sxs-lookup"><span data-stu-id="b69ae-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="b69ae-p102">Сеть MPLS WAN соединяет главный офис компании в Париже с региональными офисами, а также региональные офисы с подчиненными офисами с использованием конфигурации со звездообразной топологией. Это сделано для того, чтобы пользователи могли получать доступ к локальным серверам, на которых работают бизнес-приложения в парижском офисе. Кроме того, эта сеть маршрутизирует весь интернет-трафик общего назначения в офис в Париже, в котором устройства обеспечения безопасности сети "очищают" запросы. В каждом офисе маршрутизаторы передают трафик в проводные узлы или точки беспроводного доступа в подсетях, в которых используется частное пространство IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="b69ae-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="b69ae-113">Локальный непосредственный доступ в Интернет для трафика Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b69ae-113">Local direct Internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="b69ae-p103">В каждом офисе есть устройство программно-конфигурируемой сети WAN (SD-WAN) с одной или несколькими локальными сетями поставщиков услуг Интернета с собственными подключениями к Интернету через прокси-сервер. Такую конфигурацию обычно реализуют в виде канала глобальной сети к локальному поставщику услуг Интернета, который также предоставляет общедоступные IP-адреса и локальный DNS-сервер.</span><span class="sxs-lookup"><span data-stu-id="b69ae-p103">Each office has a Software-Defined WAN (SD-WAN) device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="b69ae-116">Интернет-представительство</span><span class="sxs-lookup"><span data-stu-id="b69ae-116">Internet presence</span></span>

  <span data-ttu-id="b69ae-p104">Компании Contoso принадлежит общедоступное доменное имя contoso.com. Общедоступный веб-сайт компании Contoso, предназначенный для заказа ее продукции, представляет собой ряд серверов в центре обработки данных, подключенном к Интернету, в кампусе в Париже. Компания Contoso использует диапазон общедоступных IP-адресов /24 в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b69ae-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="b69ae-120">Нас рисунке 1 показана инфраструктура сети компании Contoso и ее подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="b69ae-120">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![Сеть компании Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="b69ae-122">**Рис. 1. Сеть компании Contoso**</span><span class="sxs-lookup"><span data-stu-id="b69ae-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="b69ae-123">Использование технологии SD-WAN для оптимального подключения к ресурсам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b69ae-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="b69ae-124">В компании Contoso следуют указанным ниже [принципам подключения к сети для Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles):</span><span class="sxs-lookup"><span data-stu-id="b69ae-124">Contoso followed [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) to:</span></span>

1. <span data-ttu-id="b69ae-125">Определение и дифференциация сетевого трафика Office 365.</span><span class="sxs-lookup"><span data-stu-id="b69ae-125">Identify and differentiate Office 365 network traffic</span></span>
2. <span data-ttu-id="b69ae-126">Локальная организация исходящего трафика для сетевых подключений.</span><span class="sxs-lookup"><span data-stu-id="b69ae-126">Egress network connections locally</span></span>
3. <span data-ttu-id="b69ae-127">Недопущение "узких" мест в сети.</span><span class="sxs-lookup"><span data-stu-id="b69ae-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="b69ae-128">Обход дублируемых устройств обеспечения безопасности сети.</span><span class="sxs-lookup"><span data-stu-id="b69ae-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="b69ae-129">Существует три категории сетевого трафика для Office 365: оптимизированный, разрешенный, а также используемый по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b69ae-129">There are three categories of network traffic for Office 365: Optimize, Allow, and Default.</span></span> <span data-ttu-id="b69ae-130">Оптимизированный и разрешенный трафик представляет собой надежный сетевой трафик, зашифрованный и защищенный в конечных точках и направляемый в сеть Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b69ae-130">Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="b69ae-131">В компании Contoso решили следующее:</span><span class="sxs-lookup"><span data-stu-id="b69ae-131">Contoso decided to:</span></span>

- <span data-ttu-id="b69ae-132">Использовать непосредственный исходящий интернет-трафик для передачи оптимизированного и разрешенного трафика, а также перенаправлять весь трафик, используемый по умолчанию, к центральному подключению к Интернету в Париже.</span><span class="sxs-lookup"><span data-stu-id="b69ae-132">Use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

- <span data-ttu-id="b69ae-133">Развернуть устройства SD-WAN во всех расположениях офисов компании в качестве простого способа выполнения перечисленных выше принципов. Кроме того, этот подход позволяет достичь оптимальной производительности сети для работы с облачными службами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b69ae-133">Deploy SD-WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="b69ae-134">Устройство SD-WAN оснащено портом для подключения к локальной сети офиса и несколькими портами для подключения к глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="b69ae-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="b69ae-135">Один порт глобальной сети подключен к сети MPLS компании, а другой порт глобальной сети подключен к сети локального поставщика услуг Интернета.</span><span class="sxs-lookup"><span data-stu-id="b69ae-135">One WAN port connects to their MPLS network and another WAN port connects to a local ISP circuit.</span></span> <span data-ttu-id="b69ae-136">Устройство SD-WAN выполняет маршрутизацию оптимизированного и разрешенного сетевого трафика в канал поставщика услуг Интернета.</span><span class="sxs-lookup"><span data-stu-id="b69ae-136">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="b69ae-137">Инфраструктура бизнес-приложений компании Contoso</span><span class="sxs-lookup"><span data-stu-id="b69ae-137">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="b69ae-138">Специалисты компании Contoso разработали инфраструктуру интрасети для бизнес-приложений и серверов для указанных ниже целей.</span><span class="sxs-lookup"><span data-stu-id="b69ae-138">Contoso has architected its line of business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="b69ae-139">В подчиненных офисах используются локальные кэширующие серверы для хранения часто используемых документов и внутренних веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="b69ae-139">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="b69ae-p107">В региональных центрах используются региональные серверы приложений, предназначенные для региональных и подчиненных офисов. Эти серверы синхронизируются с серверами в центральном офисе в Париже.</span><span class="sxs-lookup"><span data-stu-id="b69ae-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="b69ae-142">В кампусе в Париже расположены центры обработки данных с централизованными серверами приложений, которые обслуживают всю организацию.</span><span class="sxs-lookup"><span data-stu-id="b69ae-142">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="b69ae-143">На рисунке 2 показан процент сетевого трафика при доступе к серверам в интрасети компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="b69ae-143">Figure 2 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![Инфраструктура корпорации Contoso для внутренних приложений](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="b69ae-145">**Рис. 2. Инфраструктура компании Contoso для внутренних приложений**</span><span class="sxs-lookup"><span data-stu-id="b69ae-145">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="b69ae-p108">60 % ресурсов, необходимых сотрудникам подчиненных или региональных центральных офисов, могут обслуживаться серверами подчиненных и региональных центральных офисов. Дополнительные 40 % запросов на ресурсы должны передаваться в кампус в Париже по каналу глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="b69ae-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a><span data-ttu-id="b69ae-148">Анализ и подготовка сети компании Contoso для использования Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="b69ae-148">Contoso's network analysis and preparation of their network for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b69ae-p109">То, насколько охотно пользователи в компании Contoso начнут использовать службы Microsoft 365 корпоративный, зависит от доступности и пропускной способности подключения к Интернету или непосредственно к облачным службам (Майкрософт). Чтобы спланировать и реализовать оптимальное подключение к облачным службам Microsoft 365 корпоративный, в компании Contoso выполнили указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b69ae-p109">Successful adoption of Microsoft 365 Enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 Enterprise cloud services:</span></span>

1. <span data-ttu-id="b69ae-151">Создание схемы глобальной сети, используемой компанией, для упрощения планирования</span><span class="sxs-lookup"><span data-stu-id="b69ae-151">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="b69ae-p110">Специалисты компании Contoso начали планирование сети компании с создания схемы, на которой показаны расположения компании, существующие сетевые подключения, имеющиеся устройства периметра сети и классы служб, управляемые в сети. Они использовали эту схему на каждом последующем этапе планирования и реализации подключений к сети.</span><span class="sxs-lookup"><span data-stu-id="b69ae-p110">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network. They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="b69ae-154">Создание плана подключений к сети для работы с Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="b69ae-154">Created a plan for Microsoft 365 Enterprise network connectivity</span></span>

   <span data-ttu-id="b69ae-155">Специалисты компании Contoso воспользовались [принципами подключения к сети для Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles), разработали эталонные сетевые архитектуры и приняли SD-WAN в качестве предпочтительной топологии для подключения к Office 365.</span><span class="sxs-lookup"><span data-stu-id="b69ae-155">Contoso used the [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) and provided reference network architectures to determine SD-WAN as their preferred topology for Office 365 connectivity.</span></span>

3. <span data-ttu-id="b69ae-156">Анализ использования подключения к Интернету и пропускной способности сети MPLS WAN в каждом офисе и расширение полосы пропускания сети (при необходимости)</span><span class="sxs-lookup"><span data-stu-id="b69ae-156">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="b69ae-157">В каждом офисе было проанализировано текущее использование сети и расширена ее полоса пропускания, чтобы при прохождении прогнозируемого объема трафика для работы с облачными службами Microsoft 365 оставался неиспользованный запас пропускной способности, равный приблизительно 20 %.</span><span class="sxs-lookup"><span data-stu-id="b69ae-157">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="b69ae-158">Оптимизация производительности сети при доступе к сетевым службам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b69ae-158">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="b69ae-159">В компании Contoso определили набор конечных точек Office 365, Intune и Azure и настроили брандмауэры, устройства для обеспечения безопасности и другие системы, включенные в маршрут в Интернете, достигнув при этом оптимальной производительности сети.</span><span class="sxs-lookup"><span data-stu-id="b69ae-159">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance.</span></span> <span data-ttu-id="b69ae-160">Конечные точки для оптимизированного и разрешенного трафика Office 365 были настроены в устройствах SD-WAN для маршрутизации через сеть поставщика услуг Интернета.</span><span class="sxs-lookup"><span data-stu-id="b69ae-160">Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="b69ae-161">Настройка внутренних DNS</span><span class="sxs-lookup"><span data-stu-id="b69ae-161">Configured internal DNS</span></span>

   <span data-ttu-id="b69ae-162">Для передачи трафика в Office 365 и обратно необходима работоспособная DNS, которую можно найти в локальной сети.</span><span class="sxs-lookup"><span data-stu-id="b69ae-162">DNS is required to be functional and to be looked up locally for Office 365 traffic.</span></span>

6. <span data-ttu-id="b69ae-163">Проверка подключений к конечным точкам сети и портам</span><span class="sxs-lookup"><span data-stu-id="b69ae-163">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="b69ae-164">С помощью средств проверки, предоставленных Майкрософт, специалисты компании Contoso проверили подключения к облачным службам Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="b69ae-164">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 Enterprise cloud services.</span></span>

7. <span data-ttu-id="b69ae-165">Оптимизация компьютеров сотрудников для подключения к сети</span><span class="sxs-lookup"><span data-stu-id="b69ae-165">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="b69ae-166">Специалисты компании проверили, установлены ли на компьютерах последние обновления операционных систем и на всех ли клиентах активны системы мониторинга безопасности в конечных точках.</span><span class="sxs-lookup"><span data-stu-id="b69ae-166">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="b69ae-167">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="b69ae-167">Next step</span></span>

<span data-ttu-id="b69ae-168">[Узнайте,](contoso-identity.md) как специалисты компании Contoso используют локальные доменные службы Active Directory (AD DS) в облаке для сотрудников и федерацию проверки подлинности для клиентов и партнеров по бизнесу.</span><span class="sxs-lookup"><span data-stu-id="b69ae-168">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises Active Directory Domain Services (AD DS) in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="b69ae-169">См. также</span><span class="sxs-lookup"><span data-stu-id="b69ae-169">See also</span></span>

[<span data-ttu-id="b69ae-170">Сеть для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="b69ae-170">Networking for Microsoft 365 Enterprise</span></span>](networking-infrastructure.md)

[<span data-ttu-id="b69ae-171">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="b69ae-171">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b69ae-172">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="b69ae-172">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
