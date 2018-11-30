---
title: Сеть корпорации Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказано об инфраструктуре сети компании Contoso и о том, как специалисты компании используют разработанную ими технологию SD-WAN для достижения оптимальной производительности сети при подключении к облачным службам Microsoft 365 корпоративный.
ms.openlocfilehash: 0ef9c37755927444276c83a2c5952b5cb96f22ed
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870433"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="cfce3-103">Сеть корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="cfce3-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="cfce3-104">**Сводка:** в этой статье рассказано об инфраструктуре сети компании Contoso и о том, как специалисты компании используют разработанную ими технологию SD-WAN для достижения оптимальной производительности сети при подключении к облачным службам Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="cfce3-104">**Summary:** Understand the Contoso networking infrastructure and how it uses its SD WAN technology for optimal performance network connectivity to Microsoft 365 Enterprise cloud based services.</span></span>

<span data-ttu-id="cfce3-p101">Чтобы перейти к инфраструктуре, включающей облако, специалисты по сетям компании Contoso фундаментальным образом изменили способ, которым сетевой трафик поступает в облачные службы. Вместо модели со звездообразной топологией, в которой центр сети расположен в главном офисе, специалисты ввели новую. Для этого они сопоставили расположения Майкрософт в Интернете и расположения пользователей с локальным исходящим интернет-трафиком и локальными подключениями.</span><span class="sxs-lookup"><span data-stu-id="cfce3-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud-based services travels. Instead of a hub and spoke model that focusses network connectivity on the head office, they worked to map user locations to local Internet egress and local connections to Microsoft network locations on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="cfce3-107">Сетевая инфраструктура компании Contoso</span><span class="sxs-lookup"><span data-stu-id="cfce3-107">Contoso's networking infrastructure</span></span>

<span data-ttu-id="cfce3-108">Ниже перечислены элементы сети компании Contoso, соединяющие офисы компании, расположенные по всему миру.</span><span class="sxs-lookup"><span data-stu-id="cfce3-108">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="cfce3-109">Сеть MPLS WAN</span><span class="sxs-lookup"><span data-stu-id="cfce3-109">MPLS WAN network</span></span>

  <span data-ttu-id="cfce3-p102">Сеть MPLS WAN соединяет главный офис компании в Париже с региональными офисами, а также региональные офисы с подчиненными офисами с использованием конфигурации со звездообразной топологией. Это сделано для того, чтобы пользователи могли получать доступ к локальным серверам, на которых работают бизнес-приложения в парижском офисе. Кроме того, эта сеть маршрутизирует весь интернет-трафик общего назначения в офис в Париже, в котором устройства обеспечения безопасности сети "очищают" запросы. В каждом офисе маршрутизаторы передают трафик в узлы или точки беспроводного доступа в подсетях, в которых используется частное пространство IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="cfce3-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="cfce3-114">Локальный непосредственный доступ в Интернет для трафика Office 365</span><span class="sxs-lookup"><span data-stu-id="cfce3-114">Local direct Internet access for Office 365 traffic</span></span>

  <span data-ttu-id="cfce3-p103">В каждом офисе есть устройство SD-WAN с одной или несколькими локальными сетями поставщиков услуг Интернета с собственными подключениями к Интернету через прокси-сервер. Такую конфигурацию обычно реализуют в виде канала глобальной сети к локальному поставщику услуг Интернета, который также предоставляет общедоступные IP-адреса и IP-адреса локального DNS-сервера для прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="cfce3-p103">Each office has an SD WAN device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and local DNS server IP addresses for the proxy server.</span></span>

- <span data-ttu-id="cfce3-117">Интернет-представительство</span><span class="sxs-lookup"><span data-stu-id="cfce3-117">Internet presence</span></span>

  <span data-ttu-id="cfce3-p104">Компании Contoso принадлежит общедоступное доменное имя contoso.com. Общедоступный веб-сайт компании Contoso, предназначенный для заказа ее продукции, представляет собой ряд серверов в центре обработки данных, подключенном к Интернету, в кампусе в Париже. Компания Contoso использует диапазон общедоступных IP-адресов /24 в Интернете.</span><span class="sxs-lookup"><span data-stu-id="cfce3-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="cfce3-121">Нас рисунке 1 показана инфраструктура сети компании Contoso и ее подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="cfce3-121">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![](./media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="cfce3-122">**Рис. 1. Сеть компании Contoso**</span><span class="sxs-lookup"><span data-stu-id="cfce3-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="cfce3-123">Использование технологии SD-WAN для оптимального подключения к ресурсам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cfce3-123">Use of SD WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="cfce3-124">В компании Contoso следуют указанным ниже [принципам подключения к сети для Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles).</span><span class="sxs-lookup"><span data-stu-id="cfce3-124">Contoso followed [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles):</span></span>

1. <span data-ttu-id="cfce3-125">Определение и дифференциация сетевого трафика Office 365.</span><span class="sxs-lookup"><span data-stu-id="cfce3-125">Identify and differentiate Office 365 network traffic</span></span>
2. <span data-ttu-id="cfce3-126">Локальная организация исходящего трафика для сетевых подключений.</span><span class="sxs-lookup"><span data-stu-id="cfce3-126">Egress network connections locally</span></span>
3. <span data-ttu-id="cfce3-127">Недопущение "узких" мест в сети.</span><span class="sxs-lookup"><span data-stu-id="cfce3-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="cfce3-128">Обход дублируемых устройств обеспечения безопасности сети.</span><span class="sxs-lookup"><span data-stu-id="cfce3-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="cfce3-p105">Существует три категории сетевого трафика для Office 365: оптимизированный, разрешенный, а также используемый по умолчанию. Оптимизированный и разрешенный трафик представляет собой надежный сетевой трафик, зашифрованный и защищенный в конечных точках и направляемый в центры обработки данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cfce3-p105">There are three categories of network traffic for Office 365: Optimize, Allow, and Default. Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for Microsoft datacenters.</span></span>

<span data-ttu-id="cfce3-131">Для передачи оптимизированного и разрешенного трафика в компании Contoso решили использовать непосредственный исходящий интернет-трафик, а также перенаправлять весь трафик, используемый по умолчанию, к центральному подключению к Интернету в Париже.</span><span class="sxs-lookup"><span data-stu-id="cfce3-131">Contoso decided to use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

<span data-ttu-id="cfce3-132">Специалисты компании решили развернуть устройства SD-WAN во всех расположениях офисов компании, решив, что это простой способ выполнения перечисленных выше принципов. Кроме того, этот подход позволяет достичь оптимальной производительности сети для работы с облачными службами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cfce3-132">They decided to deploy SD WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="cfce3-p106">Каждое устройство SD-WAN оснащено портом для подключения к локальной сети офиса и несколькими портами для подключения к глобальной сети. Один порт глобальной сети подключен к сети MPLS компании, а остальные порты глобальной сети подключены к сетям локальных поставщиков услуг Интернета. Устройство SD-WAN выполняет маршрутизацию оптимизированного и разрешенного сетевого трафика в каналы поставщиков услуг Интернета.</span><span class="sxs-lookup"><span data-stu-id="cfce3-p106">The SD WAN devices have a LAN port for the local office network and multiple WAN ports. One WAN port connects to their MPLS network and other WAN ports connect to local ISP circuits. The SD WAN device routes Optimize and Allow category network traffic to the ISP links.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="cfce3-136">Инфраструктура бизнес-приложений компании Contoso</span><span class="sxs-lookup"><span data-stu-id="cfce3-136">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="cfce3-137">Специалисты компании Contoso создали архитектуру бизнес-приложений и серверов для указанных ниже целей.</span><span class="sxs-lookup"><span data-stu-id="cfce3-137">Contoso has architected its line of business application and server infrastructure for the following:</span></span>

- <span data-ttu-id="cfce3-138">В подчиненных офисах используются локальные кэширующие серверы для хранения часто используемых документов и внутренних веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="cfce3-138">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="cfce3-p107">В региональных центрах используются региональные серверы приложений, предназначенные для региональных и подчиненных офисов. Эти серверы синхронизируются с серверами в центральном офисе в Париже.</span><span class="sxs-lookup"><span data-stu-id="cfce3-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="cfce3-141">В кампусе в Париже расположены центры обработки данных с централизованными серверами приложений, которые обслуживают всю организацию.</span><span class="sxs-lookup"><span data-stu-id="cfce3-141">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="cfce3-142">На рисунке 2 показан процент сетевого трафика при доступе к серверам в интрасети компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="cfce3-142">Figure 1 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![](./media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="cfce3-143">**Рис. 2. Инфраструктура компании Contoso для внутренних приложений**</span><span class="sxs-lookup"><span data-stu-id="cfce3-143">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="cfce3-p108">60 % ресурсов, необходимых сотрудникам подчиненных или региональных центральных офисов, могут обслуживаться серверами подчиненных и региональных центральных офисов. Дополнительные 40 % запросов на ресурсы должны передаваться в кампус в Париже по каналу глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="cfce3-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a><span data-ttu-id="cfce3-146">Анализ и подготовка сети компании Contoso для использования Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="cfce3-146">Contoso's network analysis and preparation of their network for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="cfce3-p109">То, насколько охотно пользователи в компании Contoso начнут использовать службы Microsoft 365 корпоративный, зависит от доступности и пропускной способности подключения к Интернету или непосредственно к облачным службам (Майкрософт). Чтобы спланировать и реализовать оптимальное подключение к облачным службам Microsoft 365 корпоративный, в компании Contoso выполнили указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="cfce3-p109">Successful adoption of Microsoft 365 Enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 Enterprise cloud services:</span></span>

1. <span data-ttu-id="cfce3-149">Создание схемы глобальной сети, используемой компанией, для упрощения планирования</span><span class="sxs-lookup"><span data-stu-id="cfce3-149">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="cfce3-p110">Специалисты компании Contoso начали планирование сети компании с создания схемы, на которой показаны расположения компании, существующие сетевые подключения, имеющиеся устройства периметра сети и классы служб, управляемые в сети. Они использовали эту схему на каждом последующем этапе планирования и реализации подключений к сети.</span><span class="sxs-lookup"><span data-stu-id="cfce3-p110">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network. They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="cfce3-152">Создание плана подключений к сети для работы с Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="cfce3-152">Created a plan for Microsoft 365 Enterprise network connectivity</span></span>

   <span data-ttu-id="cfce3-153">Специалисты компании Contoso воспользовались [принципами подключения к сети для Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles), разработали эталонные сетевые архитектуры и приняли SD-WAN в качестве предпочтительной топологии для подключения к Office 365.</span><span class="sxs-lookup"><span data-stu-id="cfce3-153">Contoso used the [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) and provided reference network architectures to determine SD WAN as their preferred topology for Office 365 connectivity.</span></span>

3. <span data-ttu-id="cfce3-154">Анализ использования подключения к Интернету и пропускной способности сети MPLS WAN в каждом офисе и расширение полосы пропускания сети (при необходимости)</span><span class="sxs-lookup"><span data-stu-id="cfce3-154">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="cfce3-155">В каждом офисе было проанализировано текущее использование сети и расширена ее полоса пропускания, чтобы при прохождении прогнозируемого объема трафика для работы с облачными службами Microsoft 365 оставался неиспользованный запас пропускной способности, равный приблизительно 20 %.</span><span class="sxs-lookup"><span data-stu-id="cfce3-155">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="cfce3-156">Оптимизация производительности сети при доступе к сетевым службам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cfce3-156">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="cfce3-p111">В компании Contoso определили набор конечных точек Office 365, Intune и Azure и настроили брандмауэры, устройства для обеспечения безопасности и другие системы, включенные в маршрут в Интернете, достигнув при этом оптимальной производительности сети. Конечные точки для оптимизированного и разрешенного трафика Office 365 были настроены в устройствах SD-WAN, обеспечивающих непосредственный доступ к Интернету.</span><span class="sxs-lookup"><span data-stu-id="cfce3-p111">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance. Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD WAN devices that provided direct Internet access.</span></span>

5. <span data-ttu-id="cfce3-159">Настройка внутренних DNS</span><span class="sxs-lookup"><span data-stu-id="cfce3-159">Configured internal DNS</span></span>

   <span data-ttu-id="cfce3-160">Для передачи трафика в Office 365 и обратно необходима работоспособная DNS, которую можно найти в локальной сети.</span><span class="sxs-lookup"><span data-stu-id="cfce3-160">DNS is required to be functional and to be looked up locally for Office 365 traffic.</span></span>

6. <span data-ttu-id="cfce3-161">Проверка подключений к конечным точкам сети и портам</span><span class="sxs-lookup"><span data-stu-id="cfce3-161">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="cfce3-162">С помощью средств проверки, предоставленных Майкрософт, специалисты компании Contoso проверили подключения к облачным службам Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="cfce3-162">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 Enterprise cloud services.</span></span>

7. <span data-ttu-id="cfce3-163">Оптимизация компьютеров сотрудников для подключения к сети</span><span class="sxs-lookup"><span data-stu-id="cfce3-163">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="cfce3-164">Специалисты компании проверили, установлены ли на компьютерах последние обновления операционных систем и на всех ли клиентах активны системы мониторинга безопасности в конечных точках.</span><span class="sxs-lookup"><span data-stu-id="cfce3-164">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="cfce3-165">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="cfce3-165">Next step</span></span>

<span data-ttu-id="cfce3-166">[Узнайте,](contoso-identity.md) как специалисты компании Contoso используют локальный поставщик удостоверений в облаке для сотрудников и федерацию проверки подлинности для клиентов и партнеров по бизнесу.</span><span class="sxs-lookup"><span data-stu-id="cfce3-166">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises identity provider in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfce3-167">См. также</span><span class="sxs-lookup"><span data-stu-id="cfce3-167">See also</span></span>

[<span data-ttu-id="cfce3-168">Сеть для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="cfce3-168">Networking for Microsoft 365 Enterprise</span></span>](networking-infrastructure.md)

[<span data-ttu-id="cfce3-169">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="cfce3-169">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="cfce3-170">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="cfce3-170">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
