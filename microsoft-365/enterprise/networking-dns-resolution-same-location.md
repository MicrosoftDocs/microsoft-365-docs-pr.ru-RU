---
title: Шаг 2. Настройка локальных подключений к Интернету для всех офисов
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как настроить разрешение DNS для повышения производительности.
ms.openlocfilehash: 8b4302c06e75c59a1b99eb60399c9df897ad17ea
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066672"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="2da82-103">Шаг 2. Настройка локальных подключений к Интернету для всех офисов</span><span class="sxs-lookup"><span data-stu-id="2da82-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="2da82-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="2da82-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Этап 1. Сеть](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="2da82-p101">На шаге 2 вы настраиваете локальные подключения к Интернету с использованием локальных DNS-серверов для всех офисов. Это необходимо для того, чтобы снизить задержку подключения и обеспечить подключение локальных клиентских компьютеров к ближайшей точке входа в облачные службы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2da82-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="2da82-108">В традиционных сетях для крупных организаций Интернет-трафик передается по сетевой магистрали на центральное подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="2da82-108">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection.</span></span> <span data-ttu-id="2da82-109">Это не способствует оптимизации производительности глобально распределенной инфраструктуры SaaS, включающей продукты Office 365 и Intune в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2da82-109">This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Intune products in Microsoft 365.</span></span>

<span data-ttu-id="2da82-110">Глобальная сеть Майкрософт включает инфраструктуру *Distributed Service Front Door* — высокодоступную и масштабируемую граничную область сети с географически распределенными расположениями.</span><span class="sxs-lookup"><span data-stu-id="2da82-110">The Microsoft Global Network includes a *Distributed Service Front Door* infrastructure, a highly available and scalable network edge with geographically distributed locations.</span></span> <span data-ttu-id="2da82-111">Она разрывает подключение конечных пользователей в серверной части и эффективно перенаправляет трафик в глобальной сети Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2da82-111">It terminates end user connections at a front door server and efficiently routes end user traffic within the Microsoft Global Network.</span></span>

![Глобальная сеть Майкрософт](../media/networking-dns-resolution-same-location/microsoft-global-network.png)

<span data-ttu-id="2da82-113">Для обеспечения максимальной производительности локальные клиенты должны иметь доступ к ближайшему расположению Front Door, а не отправлять трафик через сетевую магистраль на расположение, ближайшее к центральному подключению организации к Интернету.</span><span class="sxs-lookup"><span data-stu-id="2da82-113">For the best performance, on-premises clients should access a front door location that is geographically closest to them, rather than sending the traffic over a network backbone and to the front door that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="2da82-114">Приведем пример.</span><span class="sxs-lookup"><span data-stu-id="2da82-114">Here’s an example.</span></span>

![Пример использования глобальной сети Майкрософт](../media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

<span data-ttu-id="2da82-116">Если пользователь в парижском филиале хочет получить доступ к сайту SharePoint Online, </span><span class="sxs-lookup"><span data-stu-id="2da82-116">When a user in the Paris branch office wants to access a SharePoint Online site:</span></span>

1. <span data-ttu-id="2da82-117">то для разрешения имени, например contoso.sharepoint.com, направляется запрос DNS.</span><span class="sxs-lookup"><span data-stu-id="2da82-117">It sends a DNS query to resolve a name, such as contoso.sharepoint.com.</span></span> 
2. <span data-ttu-id="2da82-118">DNS-сервер, предоставляемый поставщиком услуг Интернета, пересылает его на DNS-сервер Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2da82-118">The DNS server provided by the ISP forwards that query to a Microsoft DNS server.</span></span>
3. <span data-ttu-id="2da82-119">DNS-серверы Майкрософт сопоставляют исходный IP-адрес перенаправленного запроса DNS с регионом, которому назначен этот адрес.</span><span class="sxs-lookup"><span data-stu-id="2da82-119">Microsoft’s DNS servers match the source IP address of the forwarded DNS query to the region of the world assigned that address.</span></span> <span data-ttu-id="2da82-120">DNS-сервер Майкрософт сообщает в ответ IP-адрес ближайшего расположения Front Door в сети Майкрософт в Европе.</span><span class="sxs-lookup"><span data-stu-id="2da82-120">The Microsoft DNS server responds with the IP address of the nearest Microsoft Network front door in Europe.</span></span>
4. <span data-ttu-id="2da82-121">DNS-сервер поставщика услуг Интернета отправляет этот IP-адрес пользователю.</span><span class="sxs-lookup"><span data-stu-id="2da82-121">The ISP DNS server sends that IP address to the user.</span></span>
5. <span data-ttu-id="2da82-122">Пользователь инициирует подключение к серверу SharePoint через Front Door в Европе.</span><span class="sxs-lookup"><span data-stu-id="2da82-122">The user initiates a connection to the SharePoint server through the Europe front door.</span></span>

<span data-ttu-id="2da82-123">Чтобы направлять клиентский запрос в ближайшее расположение Front Door, DNS-серверы Майкрософт используют запросы DNS, соответствующие исходному запросу клиента на подключение. </span><span class="sxs-lookup"><span data-stu-id="2da82-123">To direct a client request to the geographically nearest front door, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request.</span></span> <span data-ttu-id="2da82-124">Поэтому для минимальной задержки в сети:</span><span class="sxs-lookup"><span data-stu-id="2da82-124">Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="2da82-125">Все офисы вашей организации должны иметь локальные подключения к Интернету для сетевого трафика категории [Оптимизировать](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="2da82-125">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="2da82-126">Каждое локальное подключение к Интернету должно использовать региональный DNS-сервер для исходящего интернет-трафика из этого места.</span><span class="sxs-lookup"><span data-stu-id="2da82-126">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="2da82-127">Дополнительную информацию см. в разделе [Локальная организация исходящего трафика для сетевых подключений](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span><span class="sxs-lookup"><span data-stu-id="2da82-127">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="2da82-128">Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step2), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="2da82-128">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2da82-129">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="2da82-129">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="2da82-131">Удаление разворотов пакетов</span><span class="sxs-lookup"><span data-stu-id="2da82-131">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
