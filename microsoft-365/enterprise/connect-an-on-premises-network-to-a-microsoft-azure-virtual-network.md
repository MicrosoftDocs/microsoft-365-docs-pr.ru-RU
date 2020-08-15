---
title: Подключение локальной сети к виртуальной сети Microsoft Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 81190961-5454-4a5c-8b0e-6ae75b9fb035
description: Сводка. Узнайте, как настроить распределенную виртуальную сеть Azure для серверных рабочих нагрузок Office с VPN-подключением типа "сеть-сеть".
ms.openlocfilehash: cddb9cfcff02f91ef76f989b87e9dda049cc1b08
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696430"
---
# <a name="connect-an-on-premises-network-to-a-microsoft-azure-virtual-network"></a><span data-ttu-id="8370a-103">Подключение локальной сети к виртуальной сети Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="8370a-103">Connect an on-premises network to a Microsoft Azure virtual network</span></span>

<span data-ttu-id="8370a-p101">Виртуальная сеть Azure подключается к вашей локальной сети, расширяя ее за счет подсетей и виртуальных машин, размещенных в службах инфраструктуры Azure. Это подключение обеспечивает компьютерам локальной сети прямой доступ к виртуальным машинам Azure, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="8370a-p101">A cross-premises Azure virtual network is connected to your on-premises network, extending your network to include subnets and virtual machines hosted in Azure infrastructure services. This connection lets computers on your on-premises network to directly access virtual machines in Azure and vice versa.</span></span> 

<span data-ttu-id="8370a-p102">Например, сервер синхронизации каталогов, работающий на виртуальной машине Azure, должен запросить локальные контроллеры домена для изменения учетных записей и синхронизировать эти изменения с вашей подпиской на Microsoft 365. В этой статье показано, как настроить локальную виртуальную сеть Azure с помощью VPN-подключения типа "сеть-сеть", готового к размещению виртуальных машин Azure.</span><span class="sxs-lookup"><span data-stu-id="8370a-p102">For example, a directory synchronization server running on an Azure virtual machine needs to query your on-premises domain controllers for changes to accounts and synchronize those changes with your Microsoft 365 subscription. This article shows you how to set up a cross-premises Azure virtual network using a site-to-site virtual private network (VPN) connection that is ready to host Azure virtual machines.</span></span>

## <a name="configure-a-cross-premises-azure-virtual-network"></a><span data-ttu-id="8370a-108">Настройка виртуальной сети Azure с несколькими локальными сайтами</span><span class="sxs-lookup"><span data-stu-id="8370a-108">Configure a cross-premises Azure virtual network</span></span>

<span data-ttu-id="8370a-p103">Виртуальные машины в Azure не должны быть изолированы от локальной среды. Чтобы подключить виртуальные машины Azure к локальным сетевым ресурсам, необходимо настроить виртуальную сеть Azure. На схеме ниже показаны компоненты, необходимые для развертывания виртуальной сети Azure с виртуальной машиной в Azure.</span><span class="sxs-lookup"><span data-stu-id="8370a-p103">Your virtual machines in Azure don't have to be isolated from your on-premises environment. To connect Azure virtual machines to your on-premises network resources, you must configure a cross-premises Azure virtual network. The following diagram shows the required components to deploy a cross-premises Azure virtual network with a virtual machine in Azure.</span></span>
  
![Локальная сеть, подключенная к Microsoft Azure с помощью VPN-подключения типа "сеть-сеть"](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
 
<span data-ttu-id="8370a-p104">На схеме показано VPN-подключение типа "сеть-сеть", установленное между локальной сетью и виртуальной сетью Azure. VPN-подключение типа "сеть-сеть":</span><span class="sxs-lookup"><span data-stu-id="8370a-p104">In the diagram, there are two networks connected by a site-to-site VPN connection: the on-premises network and the Azure virtual network. The site-to-site VPN connection is:</span></span>

- <span data-ttu-id="8370a-115">установлено между двумя конечными точками, имеющими адрес в общедоступной сети Интернет.</span><span class="sxs-lookup"><span data-stu-id="8370a-115">Between two endpoints that are addressable and located on the public Internet.</span></span>
- <span data-ttu-id="8370a-116">Прерывается VPN-устройством в локальной сети и VPN-шлюзом в виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="8370a-116">Terminated by a VPN device on the on-premises network and an Azure VPN gateway on the Azure virtual network.</span></span>

<span data-ttu-id="8370a-p105">Виртуальная сеть Azure используется для размещения виртуальных машин. Исходящий сетевой трафик виртуальных машин сперва направляется в VPN-шлюз, который затем перенаправляет сетевой трафик через VPN-подключение типа "сеть-сеть" на VPN-устройство в локальной сети. Затем инфраструктура маршрутизации локальной сети перенаправляет трафик по назначению.</span><span class="sxs-lookup"><span data-stu-id="8370a-p105">The Azure virtual network hosts virtual machines. Network traffic originating from virtual machines on the Azure virtual network gets forwarded to the VPN gateway, which then forwards the traffic across the site-to-site VPN connection to the VPN device on the on-premises network. The routing infrastructure of the on-premises network then forwards the traffic to its destination.</span></span>

>[!Note]
><span data-ttu-id="8370a-p106">Вы также можете использовать [ExpressRoute](https://azure.microsoft.com/services/expressroute/) (прямое подключение между вашей организацией и сетью Майкрософт). Данные, передаваемые через ExpressRoute, не попадают в Интернет. В этой статье нет инструкций по использованию ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="8370a-p106">You can also use [ExpressRoute](https://azure.microsoft.com/services/expressroute/), which is a direct connection between your organization and Microsoft's network. Traffic over ExpressRoute does not travel over the public Internet. This article does not describe the use of ExpressRoute.</span></span>
>
  
<span data-ttu-id="8370a-123">Чтобы настроить VPN-подключение между виртуальной сетью Azure и локальной сетью, выполните указанные ниже действия:</span><span class="sxs-lookup"><span data-stu-id="8370a-123">To set up the VPN connection between your Azure virtual network and your on-premises network, follow these steps:</span></span> 
  
1. <span data-ttu-id="8370a-124">**Локальная сеть.** Определите и создайте локальный сетевой маршрут для адресного пространства виртуальной сети Azure, который указывает на локальное VPN-устройство.</span><span class="sxs-lookup"><span data-stu-id="8370a-124">**On-premises:** Define and create an on-premises network route for the address space of the Azure virtual network that points to your on-premises VPN device.</span></span>
    
2. <span data-ttu-id="8370a-125">**Microsoft Azure.**  Создайте виртуальную сеть Azure с VPN-подключением типа "сеть-сеть".</span><span class="sxs-lookup"><span data-stu-id="8370a-125">**Microsoft Azure:** Create an Azure virtual network with a site-to-site VPN connection.</span></span> 
    
3. <span data-ttu-id="8370a-126">**Локальная сеть.** Настройте аппаратное или программное локальное VPN-устройство для прерывания VPN-подключения, которое использует IPsec.</span><span class="sxs-lookup"><span data-stu-id="8370a-126">**On premises:** Configure your on-premises hardware or software VPN device to terminate the VPN connection, which uses Internet Protocol security (IPsec).</span></span>
    
<span data-ttu-id="8370a-127">После установки VPN-подключения типа "сеть-сеть" добавьте виртуальные машины Azure в подсети виртуальной сети.</span><span class="sxs-lookup"><span data-stu-id="8370a-127">After you establish the site-to-site VPN connection, you add Azure virtual machines to the subnets of the virtual network.</span></span>
  
## <a name="plan-your-azure-virtual-network"></a><span data-ttu-id="8370a-128">Планирование виртуальной сети Azure</span><span class="sxs-lookup"><span data-stu-id="8370a-128">Plan your Azure virtual network</span></span>
<a name="PlanningVirtual"></a>

### <a name="prerequisites"></a><span data-ttu-id="8370a-129">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="8370a-129">Prerequisites</span></span>
<a name="Prerequisites"></a>

- <span data-ttu-id="8370a-p107">Подписка на Azure. Сведения о подписках на Azure см. на странице [Как приобрести Azure](https://azure.microsoft.com/pricing/purchase-options/).</span><span class="sxs-lookup"><span data-stu-id="8370a-p107">An Azure subscription. For information about Azure subscriptions, go to the [How To Buy Azure page](https://azure.microsoft.com/pricing/purchase-options/).</span></span>
    
- <span data-ttu-id="8370a-132">Доступное частное пространство IPv4-адресов, которое необходимо назначить виртуальной сети и ее подсетям, с достаточным количеством адресов с учетом возможного расширения.</span><span class="sxs-lookup"><span data-stu-id="8370a-132">An available private IPv4 address space to assign to the virtual network and its subnets, with sufficient room for growth to accommodate the number of virtual machines needed now and in the future.</span></span>
    
- <span data-ttu-id="8370a-p108">Доступное VPN-устройство в локальной сети для прерывания VPN-подключения типа "сеть-сеть", которое поддерживает требования для IPsec. Дополнительные сведения см. в статье [О VPN-устройствах для подключений VPN-шлюзов типа "сеть-сеть"](https://go.microsoft.com/fwlink/p/?LinkId=393093).</span><span class="sxs-lookup"><span data-stu-id="8370a-p108">An available VPN device in your on-premises network to terminate the site-to-site VPN connection that supports the requirements for IPsec. For more information, see [About VPN devices for site-to-site virtual network connections](https://go.microsoft.com/fwlink/p/?LinkId=393093).</span></span>
    
- <span data-ttu-id="8370a-135">Изменение инфраструктуры маршрутизации для перенаправления трафика, поступающего в адресное пространство виртуальной сети Azure, на VPN-устройство, которое принимает VPN-подключение типа "сеть-сеть".</span><span class="sxs-lookup"><span data-stu-id="8370a-135">Changes to your routing infrastructure so that traffic routed to the address space of the Azure virtual network gets forwarded to the VPN device that hosts the site-to-site VPN connection.</span></span>
    
- <span data-ttu-id="8370a-136">Веб-прокси, который предоставляет доступ в Интернет компьютерам, подключенным к локальной сети и виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="8370a-136">A web proxy that gives computers that are connected to the on-premises network and the Azure virtual network access to the Internet.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="8370a-137">Допущения по архитектуре решения</span><span class="sxs-lookup"><span data-stu-id="8370a-137">Solution architecture design assumptions</span></span>

<span data-ttu-id="8370a-138">Ниже перечислены проектные решения для этой архитектуры.</span><span class="sxs-lookup"><span data-stu-id="8370a-138">The following list represents the design choices that have been made for this solution architecture.</span></span> 
  
- <span data-ttu-id="8370a-p109">Это решение использует одну виртуальную сеть Azure с VPN-подключением типа "сеть-сеть". В виртуальной сети Azure размещается одна подсеть, которая может содержать несколько виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="8370a-p109">This solution uses a single Azure virtual network with a site-to-site VPN connection. The Azure virtual network hosts a single subnet that can contain multiple virtual machines.</span></span> 
    
- <span data-ttu-id="8370a-p110">Вы можете использовать службу RRAS в Windows Server 2016 или Windows Server 2012, чтобы установить VPN-подключение типа "сеть-сеть" с защитой IPsec между локальной сетью и виртуальной сетью Azure. Вы также можете использовать другие VPN-устройства, например Cisco или Juniper Networks.</span><span class="sxs-lookup"><span data-stu-id="8370a-p110">You can use the Routing and Remote Access Service (RRAS) in Windows Server 2016 or Windows Server 2012 to establish an IPsec site-to-site VPN connection between the on-premises network and the Azure virtual network. You can also use other options, such as Cisco or Juniper Networks VPN devices.</span></span>
    
- <span data-ttu-id="8370a-p111">В локальной сети по-прежнему могут размещаться сетевые службы, такие как доменные службы Active Directory (AD DS), служба доменных имен (DNS), и прокси-серверы. В зависимости от ваших требований, некоторые из этих сетевых ресурсов может быть удобнее разместить в виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="8370a-p111">The on-premises network might still have network services like Active Directory Domain Services (AD DS), Domain Name System (DNS), and proxy servers. Depending on your requirements, it might be beneficial to place some of these network resources in the Azure virtual network.</span></span>
    
<span data-ttu-id="8370a-p112">Для существующей виртуальной сети Azure с одной или несколькими подсетями определите, осталось ли адресное пространство для дополнительной подсети и размещения необходимых виртуальных машин, учитывая ваши требования. Если адресного пространства для дополнительной подсети не осталось, создайте дополнительную виртуальную сеть с собственным VPN-подключением типа "сеть-сеть".</span><span class="sxs-lookup"><span data-stu-id="8370a-p112">For an existing Azure virtual network with one or more subnets, determine whether there is remaining address space for an additional subnet to host your needed virtual machines, based on your requirements. If you don't have remaining address space for an additional subnet, create an additional virtual network that has its own site-to-site VPN connection.</span></span>
  
### <a name="plan-the-routing-infrastructure-changes-for-the-azure-virtual-network"></a><span data-ttu-id="8370a-147">Планирование изменения инфраструктуры маршрутизации для виртуальной сети Azure</span><span class="sxs-lookup"><span data-stu-id="8370a-147">Plan the routing infrastructure changes for the Azure virtual network</span></span>

<span data-ttu-id="8370a-148">Локальную инфраструктуру маршрутизации необходимо настроить так, чтобы трафик, поступающий в пространство адресов виртуальной сети Azure, направлялся в локальное VPN-устройство с VPN-подключением типа "сеть-сеть".</span><span class="sxs-lookup"><span data-stu-id="8370a-148">You must configure your on-premises routing infrastructure to forward traffic destined for the address space of the Azure virtual network to the on-premises VPN device that is hosting the site-to-site VPN connection.</span></span>
  
<span data-ttu-id="8370a-149">Конкретный метод обновления инфраструктуры маршрутизации зависит от того, как выполняется управление сведениями о маршрутизации, например:</span><span class="sxs-lookup"><span data-stu-id="8370a-149">The exact method of updating your routing infrastructure depends on how you manage routing information, which can be:</span></span>
  
- <span data-ttu-id="8370a-150">таблица маршрутизации обновляется в соответствии с ручной настройкой;</span><span class="sxs-lookup"><span data-stu-id="8370a-150">Routing table updates based on manual configuration.</span></span>
    
- <span data-ttu-id="8370a-151">таблица маршрутизации обновляется в соответствии с протоколами маршрутизации, например RIP или OSPF.</span><span class="sxs-lookup"><span data-stu-id="8370a-151">Routing table updates based on routing protocols, such as Routing Information Protocol (RIP) or Open Shortest Path First (OSPF).</span></span>
    
<span data-ttu-id="8370a-152">Проконсультируйтесь со своим специалистом по маршрутизации, чтобы убедиться, что трафик, предназначенный для виртуальной сети Azure, перенаправляется на локальное VPN-устройство.</span><span class="sxs-lookup"><span data-stu-id="8370a-152">Consult with your routing specialist to make sure that traffic destined for the Azure virtual network is forwarded to the on-premises VPN device.</span></span>
  
### <a name="plan-for-firewall-rules-for-traffic-to-and-from-the-on-premises-vpn-device"></a><span data-ttu-id="8370a-153">Планирование правил брандмауэра для входящего и исходящего трафика на локальном VPN-устройстве</span><span class="sxs-lookup"><span data-stu-id="8370a-153">Plan for firewall rules for traffic to and from the on-premises VPN device</span></span>

<span data-ttu-id="8370a-154">Если VPN-устройство размещается в сети периметра, которая соединяется с Интернетом через брандмауэр, рекомендуем настроить на брандмауэре перечисленные ниже правила, чтобы сделать возможным VPN-подключение типа "сеть-сеть".</span><span class="sxs-lookup"><span data-stu-id="8370a-154">If your VPN device is on a perimeter network that has a firewall between the perimeter network and the Internet, you might have to configure the firewall for the following rules to allow the site-to-site VPN connection.</span></span>
  
- <span data-ttu-id="8370a-155">Трафик к VPN-устройству (входящий):</span><span class="sxs-lookup"><span data-stu-id="8370a-155">Traffic to the VPN device (incoming from the Internet):</span></span>
    
  - <span data-ttu-id="8370a-156">Конечный IP-адрес VPN-устройства и протокол IP 50</span><span class="sxs-lookup"><span data-stu-id="8370a-156">Destination IP address of the VPN device and IP protocol 50</span></span>
    
  - <span data-ttu-id="8370a-157">Конечный IP-адрес VPN-устройства и конечный порт UDP 500</span><span class="sxs-lookup"><span data-stu-id="8370a-157">Destination IP address of the VPN device and UDP destination port 500</span></span>
    
  - <span data-ttu-id="8370a-158">Конечный IP-адрес VPN-устройства и конечный порт UDP 4500</span><span class="sxs-lookup"><span data-stu-id="8370a-158">Destination IP address of the VPN device and UDP destination port 4500</span></span>
    
- <span data-ttu-id="8370a-159">Трафик с VPN-устройства (исходящий):</span><span class="sxs-lookup"><span data-stu-id="8370a-159">Traffic from the VPN device (outgoing to the Internet):</span></span>
    
  - <span data-ttu-id="8370a-160">Исходный IP-адрес VPN-устройства и протокол IP 50</span><span class="sxs-lookup"><span data-stu-id="8370a-160">Source IP address of the VPN device and IP protocol 50</span></span>
    
  - <span data-ttu-id="8370a-161">Исходный IP-адрес VPN-устройства и исходный порт UDP 500</span><span class="sxs-lookup"><span data-stu-id="8370a-161">Source IP address of the VPN device and UDP source port 500</span></span>
    
  - <span data-ttu-id="8370a-162">Исходный IP-адрес VPN-устройства и исходный порт UDP 4500</span><span class="sxs-lookup"><span data-stu-id="8370a-162">Source IP address of the VPN device and UDP source port 4500</span></span>
    
### <a name="plan-for-the-private-ip-address-space-of-the-azure-virtual-network"></a><span data-ttu-id="8370a-163">Планирование пространства частных IP-адресов виртуальной сети Azure</span><span class="sxs-lookup"><span data-stu-id="8370a-163">Plan for the private IP address space of the Azure virtual network</span></span>

<span data-ttu-id="8370a-164">Пространство частных IP-адресов виртуальной сети Azure должно иметь достаточный размер для адресов, используемых платформой Azure для размещения виртуальной сети как минимум с одной подсетью, в которой достаточно адресов для размещения виртуальных машин Azure.</span><span class="sxs-lookup"><span data-stu-id="8370a-164">The private IP address space of the Azure virtual network must be able to accommodate addresses used by Azure to host the virtual network and with at least one subnet that has enough addresses for your Azure virtual machines.</span></span>
  
<span data-ttu-id="8370a-165">Чтобы определить необходимое количество адресов для подсети, посчитайте количество виртуальных машин, необходимых на данный момент, оцените потенциал роста и определите размер подсети, пользуясь следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="8370a-165">To determine the number of addresses needed for the subnet, count the number of virtual machines that you need now, estimate for future growth, and then use the following table to determine the size of the subnet.</span></span>
  
|<span data-ttu-id="8370a-166">**Необходимое количество виртуальных машин**</span><span class="sxs-lookup"><span data-stu-id="8370a-166">**Number of virtual machines needed**</span></span>|<span data-ttu-id="8370a-167">**Необходимое количество бит узла**</span><span class="sxs-lookup"><span data-stu-id="8370a-167">**Number of host bits needed**</span></span>|<span data-ttu-id="8370a-168">**Размер подсети**</span><span class="sxs-lookup"><span data-stu-id="8370a-168">**Size of the subnet**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8370a-169">1–3</span><span class="sxs-lookup"><span data-stu-id="8370a-169">1-3</span></span>  <br/> |<span data-ttu-id="8370a-170">3</span><span class="sxs-lookup"><span data-stu-id="8370a-170">3</span></span>  <br/> |<span data-ttu-id="8370a-171">/29</span><span class="sxs-lookup"><span data-stu-id="8370a-171">/29</span></span>  <br/> |
|<span data-ttu-id="8370a-172">4–11</span><span class="sxs-lookup"><span data-stu-id="8370a-172">4-11</span></span>  <br/> |<span data-ttu-id="8370a-173">4</span><span class="sxs-lookup"><span data-stu-id="8370a-173">4</span></span>  <br/> |<span data-ttu-id="8370a-174">/28</span><span class="sxs-lookup"><span data-stu-id="8370a-174">/28</span></span>  <br/> |
|<span data-ttu-id="8370a-175">12–27</span><span class="sxs-lookup"><span data-stu-id="8370a-175">12-27</span></span>  <br/> |<span data-ttu-id="8370a-176">5</span><span class="sxs-lookup"><span data-stu-id="8370a-176">5</span></span>  <br/> |<span data-ttu-id="8370a-177">/27</span><span class="sxs-lookup"><span data-stu-id="8370a-177">/27</span></span>  <br/> |
|<span data-ttu-id="8370a-178">28–59</span><span class="sxs-lookup"><span data-stu-id="8370a-178">28-59</span></span>  <br/> |<span data-ttu-id="8370a-179">6</span><span class="sxs-lookup"><span data-stu-id="8370a-179">6</span></span>  <br/> |<span data-ttu-id="8370a-180">/26</span><span class="sxs-lookup"><span data-stu-id="8370a-180">/26</span></span>  <br/> |
|<span data-ttu-id="8370a-181">60–123</span><span class="sxs-lookup"><span data-stu-id="8370a-181">60-123</span></span>  <br/> |<span data-ttu-id="8370a-182">7</span><span class="sxs-lookup"><span data-stu-id="8370a-182">7</span></span>  <br/> |<span data-ttu-id="8370a-183">/25</span><span class="sxs-lookup"><span data-stu-id="8370a-183">/25</span></span>  <br/> |
   
### <a name="planning-worksheet-for-configuring-your-azure-virtual-network"></a><span data-ttu-id="8370a-184">Таблица планирования настройки виртуальной сети Azure</span><span class="sxs-lookup"><span data-stu-id="8370a-184">Planning worksheet for configuring your Azure virtual network</span></span>
<span data-ttu-id="8370a-185"><a name="worksheet"> </a></span><span class="sxs-lookup"><span data-stu-id="8370a-185"><a name="worksheet"> </a></span></span>

<span data-ttu-id="8370a-186">Прежде чем создавать виртуальную сеть Azure для размещения виртуальных машин, необходимо определить нужные параметры в следующих таблицах.</span><span class="sxs-lookup"><span data-stu-id="8370a-186">Before you create an Azure virtual network to host virtual machines, you must determine the settings needed in the following tables.</span></span>
  
<span data-ttu-id="8370a-187">Чтобы задать параметры виртуальной сети, заполните таблицу V.</span><span class="sxs-lookup"><span data-stu-id="8370a-187">For the settings of the virtual network, fill in Table V.</span></span>
  
 <span data-ttu-id="8370a-188">**Таблица V. Настройка распределенной виртуальной сети**</span><span class="sxs-lookup"><span data-stu-id="8370a-188">**Table V: Cross-premises virtual network configuration**</span></span>
  
|<span data-ttu-id="8370a-189">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8370a-189">**Item**</span></span>|<span data-ttu-id="8370a-190">**Элемент Configuration**</span><span class="sxs-lookup"><span data-stu-id="8370a-190">**Configuration element**</span></span>|<span data-ttu-id="8370a-191">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8370a-191">**Description**</span></span>|<span data-ttu-id="8370a-192">**Значение**</span><span class="sxs-lookup"><span data-stu-id="8370a-192">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8370a-193">1.</span><span class="sxs-lookup"><span data-stu-id="8370a-193">1.</span></span>  <br/> |<span data-ttu-id="8370a-194">Имя виртуальной сети</span><span class="sxs-lookup"><span data-stu-id="8370a-194">Virtual network name</span></span>  <br/> |<span data-ttu-id="8370a-195">Имя, назначаемое виртуальной сети Azure (например, DirSyncNet).</span><span class="sxs-lookup"><span data-stu-id="8370a-195">A name to assign to the Azure virtual network (example DirSyncNet).</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png) |
|<span data-ttu-id="8370a-197">2.</span><span class="sxs-lookup"><span data-stu-id="8370a-197">2.</span></span>  <br/> |<span data-ttu-id="8370a-198">Расположение виртуальной сети</span><span class="sxs-lookup"><span data-stu-id="8370a-198">Virtual network location</span></span>  <br/> |<span data-ttu-id="8370a-199">Центр обработки данных Azure, в котором будет расположена виртуальная сеть (например, Запад США).</span><span class="sxs-lookup"><span data-stu-id="8370a-199">The Azure datacenter that will contain the virtual network (such as West US).</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="8370a-201">3.</span><span class="sxs-lookup"><span data-stu-id="8370a-201">3.</span></span>  <br/> |<span data-ttu-id="8370a-202">IP-адрес VPN-устройства</span><span class="sxs-lookup"><span data-stu-id="8370a-202">VPN device IP address</span></span>  <br/> |<span data-ttu-id="8370a-p113">Общедоступный IPv4-адрес интерфейса VPN-устройства в Интернете. Попросите ИТ-отдел определить этот адрес.</span><span class="sxs-lookup"><span data-stu-id="8370a-p113">The public IPv4 address of your VPN device's interface on the Internet. Work with your IT department to determine this address.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="8370a-206">4.</span><span class="sxs-lookup"><span data-stu-id="8370a-206">4.</span></span>  <br/> |<span data-ttu-id="8370a-207">Адресное пространство виртуальной сети</span><span class="sxs-lookup"><span data-stu-id="8370a-207">Virtual network address space</span></span>  <br/> |<span data-ttu-id="8370a-p114">Адресное пространство (определенное в одном префиксе личного адреса) для виртуальной сети. Определите это адресное пространство при поддержке ИТ-отдела. Оно должно быть представлено в формате CIDR, также известном как формат префикса сети. Пример: 10.24.64.0/20.</span><span class="sxs-lookup"><span data-stu-id="8370a-p114">The address space (defined in a single private address prefix) for the virtual network. Work with your IT department to determine this address space. The address space should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format. An example is 10.24.64.0/20.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png) <br/> |
|<span data-ttu-id="8370a-213">5.</span><span class="sxs-lookup"><span data-stu-id="8370a-213">5.</span></span>  <br/> |<span data-ttu-id="8370a-214">Общий ключ IPsec</span><span class="sxs-lookup"><span data-stu-id="8370a-214">IPsec shared key</span></span>  <br/> |<span data-ttu-id="8370a-p115">32-значный случайный буквенно-цифровой ключ, который будет использоваться для проверки подлинности обеих сторон VPN-подключения. Определите значение этого ключа при поддержке ИТ-отдела, а затем сохраните его в надежном месте. Вы также можете ознакомиться со статьей [Создание случайной строки для предварительного ключа IPsec](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).</span><span class="sxs-lookup"><span data-stu-id="8370a-p115">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection. Work with your IT or security department to determine this key value and then store it in a secure location. Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  </span></span><br/> |![линия](../media/Common-Images/TableLine.png) <br/> |
   
<span data-ttu-id="8370a-219">Укажите подсети этого решения в таблице S.</span><span class="sxs-lookup"><span data-stu-id="8370a-219">Fill in Table S for the subnets of this solution.</span></span>
  
- <span data-ttu-id="8370a-p116">Для первой подсети определите 28-битовое адресное пространство (с длиной префикса /28) подсети шлюза Azure. Сведения о том, как определить это адресное пространство, см. в статье [Расчет адресного пространства подсетей шлюза для виртуальных сетей Azure](https://blogs.technet.microsoft.com/solutions_advisory_board/2016/12/01/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks/).</span><span class="sxs-lookup"><span data-stu-id="8370a-p116">For the first subnet, determine a 28-bit address space (with a /28 prefix length) for the Azure gateway subnet. See [Calculating the gateway subnet address space for Azure virtual networks](https://blogs.technet.microsoft.com/solutions_advisory_board/2016/12/01/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks/) for information about how to determine this address space.</span></span>
    
- <span data-ttu-id="8370a-222">Для второй подсети укажите понятное имя, одно пространство IP-адресов на основе адресного пространства виртуальной сети.</span><span class="sxs-lookup"><span data-stu-id="8370a-222">For the second subnet, specify a friendly name, a single IP address space based on the virtual network address space, and a descriptive purpose.</span></span>
    
<span data-ttu-id="8370a-p117">Определите эти адресные пространства из адресного пространства виртуальной сети при поддержке ИТ-отдела. Оба адресных пространства должны быть представлены в формате CIDR.</span><span class="sxs-lookup"><span data-stu-id="8370a-p117">Work with your IT department to determine these address spaces from the virtual network address space. Both address spaces should be in CIDR format.</span></span>
  
 <span data-ttu-id="8370a-225">**Таблица S. Подсети виртуальной сети**</span><span class="sxs-lookup"><span data-stu-id="8370a-225">**Table S: Subnets in the virtual network**</span></span>
  
|<span data-ttu-id="8370a-226">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8370a-226">**Item**</span></span>|<span data-ttu-id="8370a-227">**Имя подсети**</span><span class="sxs-lookup"><span data-stu-id="8370a-227">**Subnet name**</span></span>|<span data-ttu-id="8370a-228">**Адресное пространство подсети**</span><span class="sxs-lookup"><span data-stu-id="8370a-228">**Subnet address space**</span></span>|<span data-ttu-id="8370a-229">**Назначение**</span><span class="sxs-lookup"><span data-stu-id="8370a-229">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8370a-230">1.</span><span class="sxs-lookup"><span data-stu-id="8370a-230">1.</span></span>  <br/> |<span data-ttu-id="8370a-231">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="8370a-231">GatewaySubnet</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="8370a-233">Подсеть, используемая шлюзом Azure.</span><span class="sxs-lookup"><span data-stu-id="8370a-233">The subnet used by the Azure gateway.</span></span>  <br/> |
|<span data-ttu-id="8370a-234">2.</span><span class="sxs-lookup"><span data-stu-id="8370a-234">2.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
   
<span data-ttu-id="8370a-p118">Для локальных DNS-серверов, используемых виртуальными машинами в виртуальной сети, заполните таблицу D. Присвойте каждому DNS-серверу понятное имя и один IP-адрес. Это понятное имя необязательно должно совпадать с именем узла или именем компьютера на DNS-сервере. Обратите внимание, что представлено два пустых поля, но вы можете добавить еще. Определите этот список при поддержке ИТ-отдела.</span><span class="sxs-lookup"><span data-stu-id="8370a-p118">For the on-premises DNS servers that you want the virtual machines in the virtual network to use, fill in Table D. Give each DNS server a friendly name and a single IP address. This friendly name does not need to match the host name or computer name of the DNS server. Note that two blank entries are listed, but you can add more. Work with your IT department to determine this list.</span></span>
  
 <span data-ttu-id="8370a-242">**Таблица D. Локальные DNS-сервера**</span><span class="sxs-lookup"><span data-stu-id="8370a-242">**Table D: On-premises DNS servers**</span></span>
  
|<span data-ttu-id="8370a-243">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8370a-243">**Item**</span></span>|<span data-ttu-id="8370a-244">**Понятное имя DNS-сервера**</span><span class="sxs-lookup"><span data-stu-id="8370a-244">**DNS server friendly name**</span></span>|<span data-ttu-id="8370a-245">**IP-адрес DNS-сервера**</span><span class="sxs-lookup"><span data-stu-id="8370a-245">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8370a-246">1.</span><span class="sxs-lookup"><span data-stu-id="8370a-246">1.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="8370a-249">2.</span><span class="sxs-lookup"><span data-stu-id="8370a-249">2.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
   
<span data-ttu-id="8370a-p119">Чтобы отправлять пакеты из виртуальной сети Azure в сеть организации с помощью VPN-подключения типа "сеть-сеть", необходимо настроить виртуальную сеть с локальной сетью. Эта локальная сеть содержит список адресных пространств (в формате CIDR) для всех расположений в локальной сети организации, которые должны быть доступны виртуальным машинам в виртуальной сети. Это могут быть все расположения в локальной сети или подсети. Список адресных пространств, которые определяют локальную сеть, должен быть уникален и не должен пересекаться с адресными пространствами, используемыми для этой или других виртуальных сетей.</span><span class="sxs-lookup"><span data-stu-id="8370a-p119">To route packets from the Azure virtual network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network. This local network has a list of the address spaces (in CIDR format) for all of the locations on your organization's on-premises network that the virtual machines in the virtual network must reach. This can be all of the locations on the on-premises network or a subset. The list of address spaces that define your local network must be unique and must not overlap with the address spaces used for this virtual network or your other cross-premises virtual networks.</span></span>
  
<span data-ttu-id="8370a-p120">Укажите список адресных пространств локальной сети в таблице L. Обратите внимание, что представлено три пустых поля, но обычно требуется больше. Определите этот список при поддержке ИТ-отдела.</span><span class="sxs-lookup"><span data-stu-id="8370a-p120">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more. Work with your IT department to determine this list.</span></span>
  
 <span data-ttu-id="8370a-258">**Таблица L. Префиксы адресов для локальной сети**</span><span class="sxs-lookup"><span data-stu-id="8370a-258">**Table L: Address prefixes for the local network**</span></span>
  
|<span data-ttu-id="8370a-259">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8370a-259">**Item**</span></span>|<span data-ttu-id="8370a-260">**Адресное пространство локальной сети**</span><span class="sxs-lookup"><span data-stu-id="8370a-260">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8370a-261">1.</span><span class="sxs-lookup"><span data-stu-id="8370a-261">1.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="8370a-263">2.</span><span class="sxs-lookup"><span data-stu-id="8370a-263">2.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="8370a-265">3.</span><span class="sxs-lookup"><span data-stu-id="8370a-265">3.</span></span>  <br/> |![линия](../media/Common-Images/TableLine.png)  <br/> |
   
## <a name="deployment-roadmap"></a><span data-ttu-id="8370a-267">План развертывания</span><span class="sxs-lookup"><span data-stu-id="8370a-267">Deployment roadmap</span></span>
<span data-ttu-id="8370a-268"><a name="DeploymentRoadmap"> </a></span><span class="sxs-lookup"><span data-stu-id="8370a-268"><a name="DeploymentRoadmap"> </a></span></span>

<span data-ttu-id="8370a-269">Создание виртуальной сети и добавление виртуальных машин в Azure состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="8370a-269">Creating the cross-premises virtual network and adding virtual machines in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="8370a-270">Этап 1. Подготовка локальной сети.</span><span class="sxs-lookup"><span data-stu-id="8370a-270">Phase 1: Prepare your on-premises network.</span></span>
    
- <span data-ttu-id="8370a-271">Этап 2. Создание виртуальной сети в Azure.</span><span class="sxs-lookup"><span data-stu-id="8370a-271">Phase 2: Create the cross-premises virtual network in Azure.</span></span>
    
- <span data-ttu-id="8370a-272">Этап 3 (необязательный). Добавление виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="8370a-272">Phase 3 (Optional): Add virtual machines.</span></span>
    
### <a name="phase-1-prepare-your-on-premises-network"></a><span data-ttu-id="8370a-273">Этап 1. Подготовка локальной сети</span><span class="sxs-lookup"><span data-stu-id="8370a-273">Phase 1: Prepare your on-premises network</span></span>
<a name="Phase1"></a>

<span data-ttu-id="8370a-p121">В локальной сети необходимо настроить маршрут, который указывает на маршрутизатор на границе локальной сети и направляет на него трафик, предназначенный для адресного пространства виртуальной сети. Обратитесь к администратору сети, чтобы определить, как добавить маршрут в инфраструктуру локальной сети.</span><span class="sxs-lookup"><span data-stu-id="8370a-p121">You must configure your on-premises network with a route that points to and ultimately delivers traffic destined for the address space of the virtual network to the router on the edge of the on-premises network. Consult with your network administrator to determine how to add the route to the routing infrastructure of your on-premises network.</span></span>
  
<span data-ttu-id="8370a-276">Ниже показана полученная в итоге конфигурация.</span><span class="sxs-lookup"><span data-stu-id="8370a-276">Here is your resulting configuration.</span></span>
  
![Локальная сеть должна иметь маршрут для адресного пространства виртуальной сети, указывающий на VPN-устройство.](../media/90bab36b-cb60-4ea5-81d5-4737b696d41c.png)
  
### <a name="phase-2-create-the-cross-premises-virtual-network-in-azure"></a><span data-ttu-id="8370a-278">Этап 2. Создание распределенной виртуальной сети в Azure</span><span class="sxs-lookup"><span data-stu-id="8370a-278">Phase 2: Create the cross-premises virtual network in Azure</span></span>
<a name="Phase2"></a>

<span data-ttu-id="8370a-p122">Сначала откройте командную строку Azure PowerShell. Если вы еще не установили Azure PowerShell, см. статью [Начало работы с Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="8370a-p122">First, open an Azure PowerShell prompt. If you have not installed Azure PowerShell, see [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>

 
<span data-ttu-id="8370a-281">Затем войдите в свою учетную запись Azure с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="8370a-281">Next, login to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="8370a-282">Получите имя подписки с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="8370a-282">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort SubscriptionName | Select SubscriptionName
```

<span data-ttu-id="8370a-p123">Задайте свою подписку Azure с помощью этих команд. Замените весь текст в кавычках, в том числе символы "<" и ">", правильными именами подписок.</span><span class="sxs-lookup"><span data-stu-id="8370a-p123">Set your Azure subscription with these commands. Replace everything within the quotes, including the < and > characters, with the correct subscription name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="8370a-p124">Затем создайте группу ресурсов для виртуальной сети. Чтобы определить уникальное имя группы ресурсов, используйте следующую команду для вывода списка имеющихся групп ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8370a-p124">Next, create a new resource group for your virtual network. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="8370a-287">Создайте группу ресурсов с помощью следующих команд.</span><span class="sxs-lookup"><span data-stu-id="8370a-287">Create your new resource group with these commands.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<Table V - Item 2 - Value column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="8370a-288">Затем необходимо создать виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="8370a-288">Next, you create the Azure virtual network.</span></span>
  
```powershell
# Fill in the variables from previous values and from Tables V, S, and D
$rgName="<name of your new resource group>"
$locName="<Azure location of your new resource group>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$gwSubnetPrefix="<Table S - Item 1 - Subnet address space column>"
$SubnetName="<Table S - Item 2 - Subnet name column>"
$SubnetPrefix="<Table S - Item 2 - Subnet address space column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the Azure virtual network and a network security group that allows incoming remote desktop connections to the subnet that is hosting virtual machines
$gatewaySubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnetPrefix
$vmSubnet=New-AzVirtualNetworkSubnetConfig -Name $SubnetName -AddressPrefix $SubnetPrefix
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gatewaySubnet,$vmSubnet -DNSServer $dnsServers
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName -Location $locShortName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$nsg=Get-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $SubnetName -AddressPrefix $SubnetPrefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="8370a-289">Ниже показана полученная в итоге конфигурация.</span><span class="sxs-lookup"><span data-stu-id="8370a-289">Here is your resulting configuration.</span></span>
  
![Виртуальная сеть пока не подключена к локальной.](../media/54a37782-a6cc-4d48-b38d-73e128b44a82.png)
  
<span data-ttu-id="8370a-291">Затем используйте следующие команды, чтобы создать шлюзы для VPN-подключения типа "сеть-сеть".</span><span class="sxs-lookup"><span data-stu-id="8370a-291">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
```powershell
# Fill in the variables from previous values and from Tables V and L
$vnetName="<Table V - Item 1 - Value column>"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -SubnetId $vnet.Subnets[0].Id
# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig
# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix
# Create the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway
```

<span data-ttu-id="8370a-292">Ниже показана полученная в итоге конфигурация.</span><span class="sxs-lookup"><span data-stu-id="8370a-292">Here is your resulting configuration.</span></span>
  
![Для виртуальной сети теперь настроен шлюз.](../media/82dd66b2-a4b7-48f6-a89b-cfdd94630980.png)
  
<span data-ttu-id="8370a-p125">Затем настройте локальное VPN-устройство для подключения к VPN-шлюзу Azure. Дополнительные сведения см. в статье [О VPN-устройствах для подключений VPN-шлюзов типа "сеть-сеть"](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span><span class="sxs-lookup"><span data-stu-id="8370a-p125">Next, configure your on-premises VPN device to connect to the Azure VPN gateway. For more information, see [About VPN Devices for site-to-site Azure Virtual Network connections](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="8370a-296">Чтобы настроить VPN-устройство, вам потребуется следующее:</span><span class="sxs-lookup"><span data-stu-id="8370a-296">To configure your VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="8370a-297">Общедоступный IPv4-адрес VPN-шлюза Azure для виртуальной сети.</span><span class="sxs-lookup"><span data-stu-id="8370a-297">The public IPv4 address of the Azure VPN gateway for your virtual network.</span></span> <span data-ttu-id="8370a-298">Используйте команду **Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName** для отображения данного адреса.</span><span class="sxs-lookup"><span data-stu-id="8370a-298">Use the **Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName** command to display this address.</span></span>
    
- <span data-ttu-id="8370a-299">Общий ключ IPsec для VPN-подключения типа "сеть-сеть" (таблица V, элемент 5, столбец "Значение").</span><span class="sxs-lookup"><span data-stu-id="8370a-299">The IPsec pre-shared key for the site-to-site VPN connection (Table V- Item 5 - Value column).</span></span>
    
<span data-ttu-id="8370a-300">Ниже показана полученная в итоге конфигурация.</span><span class="sxs-lookup"><span data-stu-id="8370a-300">Here is your resulting configuration.</span></span>
  
![Теперь виртуальная сеть подключена к локальной.](../media/6379c423-4f22-4453-941b-7ff32484a0a5.png)
  
### <a name="phase-3-optional-add-virtual-machines"></a><span data-ttu-id="8370a-302">Этап 3 (необязательный). Добавление виртуальных машин</span><span class="sxs-lookup"><span data-stu-id="8370a-302">Phase 3 (Optional): Add virtual machines</span></span>

<span data-ttu-id="8370a-p127">Создайте необходимые виртуальные машины в Azure. Дополнительные сведения см. в статье [Создание виртуальной машины Windows с помощью портала Azure](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span><span class="sxs-lookup"><span data-stu-id="8370a-p127">Create the virtual machines you need in Azure. For more information, see [Create a Windows virtual machine with the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span></span>
  
<span data-ttu-id="8370a-305">Используйте указанные ниже параметры:</span><span class="sxs-lookup"><span data-stu-id="8370a-305">Use the following settings:</span></span>
  
- <span data-ttu-id="8370a-p128">На вкладке **Основные** выберите ту же подписку и группу ресурсов, что и в виртуальной сети. Они потребуются позже для входа на виртуальной машине. В разделе **Сведения об экземпляре** выберите подходящий размер виртуальной машины. Запишите имя и пароль учетной записи администратора в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="8370a-p128">On the **Basics** tab, select the same subscription and resource group as your virtual network. You will need these later to sign in to the virtual machine. In the **Instance details** section, choose the appropriate virtual machine size. Record the administrator account user name and password in a secure location.</span></span> 
    
- <span data-ttu-id="8370a-p129">На вкладке **Сеть** выберите имя виртуальной сети и подсеть для размещения виртуальных машин (не GatewaySubnet). Для всех остальных параметров оставьте значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8370a-p129">On the **Networking** tab, select the name of your virtual network and the subnet for hosting virtual machines (not the GatewaySubnet). Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="8370a-p130">Проверьте внутренний DNS, чтобы убедиться, что виртуальная машина правильно использует DNS и для виртуальной машины добавлены адресные записи (A). Чтобы предоставить виртуальным машинам Azure доступ к Интернету, их необходимо настроить на использование прокси-сервера локальной сети. Обратитесь к администратору сети за дополнительными инструкциями по настройке сервера.</span><span class="sxs-lookup"><span data-stu-id="8370a-p130">Verify that your virtual machine is using DNS correctly by checking your internal DNS to ensure that Address (A) records were added for you new virtual machine. To access the Internet, your Azure virtual machines must be configured to use your on-premises network's proxy server. Contact your network administrator for additional configuration steps to perform on the server.</span></span>
  
<span data-ttu-id="8370a-315">Ниже показана полученная в итоге конфигурация.</span><span class="sxs-lookup"><span data-stu-id="8370a-315">Here is your resulting configuration.</span></span>
  
![В виртуальной сети теперь размещены виртуальные машины, доступные из локальной сети.](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
  
## <a name="next-step"></a><span data-ttu-id="8370a-317">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="8370a-317">Next step</span></span>
  
[<span data-ttu-id="8370a-318">Развертывание синхронизации каталогов Microsoft 365 в Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="8370a-318">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>](deploy-microsoft-365-directory-synchronization-dirsync-in-microsoft-azure.md)
