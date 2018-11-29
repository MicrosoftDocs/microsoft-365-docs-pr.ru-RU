---
title: Шаг 2. Настройка локальных подключений к Интернету для всех офисов
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как настроить разрешение DNS для повышения производительности.
ms.openlocfilehash: 9ccd5c477b4aeda8e7dcf482cc09c8a357f19f40
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870456"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="b3c3c-103">Шаг 2. Настройка локальных подключений к Интернету для всех офисов</span><span class="sxs-lookup"><span data-stu-id="b3c3c-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="b3c3c-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="b3c3c-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="b3c3c-p101">На шаге 2 вы настраиваете локальные подключения к Интернету с использованием локальных DNS-серверов для всех офисов. Это необходимо для того, чтобы снизить задержку подключения и обеспечить подключение локальных клиентских компьютеров к ближайшей точке входа в облачные службы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3c3c-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="b3c3c-p102">В традиционных сетях крупных организаций интернет-трафик движется через сетевую магистраль к центральному подключению к Интернету. Это не способствует оптимизации производительности для глобально распределенной инфраструктуры SaaS, которая включает продукты Office 365 и Enterprise Mobility + Security (EMS) в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3c3c-p102">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection. This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Enterprise Mobility + Security (EMS) products in Microsoft 365.</span></span>

<span data-ttu-id="b3c3c-p103">Глобальная сеть Майкрософт включает серверы переднего плана для облачных служб Microsoft 365 по всему миру. Для обеспечения максимальной производительности локальные клиенты должны обращаться к ближайшему серверу переднего плана, а не отправлять трафик через сетевую магистраль на сервер переднего плана, расположенный ближе всего к центральному подключению к Интернету.</span><span class="sxs-lookup"><span data-stu-id="b3c3c-p103">The Microsoft Global Network includes front end servers to the set of cloud services for Microsoft 365 all over the world. For the best performance, on-premises clients should access a front-end server that is geographically closest to them, rather than sending the traffic over a network backbone and to the front-end server that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="b3c3c-p104">Чтобы направлять клиентский запрос на ближайший сервер переднего плана, DNS-серверы Майкрософт используют DNS-запросы, соответствующие исходному запросу клиента на подключение. Поэтому для минимальной задержки в сети:</span><span class="sxs-lookup"><span data-stu-id="b3c3c-p104">To direct a client request to the geographically nearest front-end server, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request. Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="b3c3c-113">Все офисы вашей организации должны иметь локальные подключения к Интернету для сетевого трафика категории [Оптимизировать](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="b3c3c-113">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="b3c3c-114">Каждое локальное подключение к Интернету должно использовать региональный DNS-сервер для исходящего интернет-трафика из этого места.</span><span class="sxs-lookup"><span data-stu-id="b3c3c-114">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="b3c3c-115">Дополнительную информацию см. в разделе [Локальная организация исходящего трафика для сетевых подключений](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span><span class="sxs-lookup"><span data-stu-id="b3c3c-115">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="b3c3c-116">Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step2), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="b3c3c-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="b3c3c-117">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="b3c3c-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="b3c3c-118">Удаление разворотов пакетов</span><span class="sxs-lookup"><span data-stu-id="b3c3c-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
