---
title: Шаг 3. Удаление разворотов пакетов
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Удалите развороты пакетов для повышения производительности.
ms.openlocfilehash: eb233c02d1d4c0198c11d520acca1d680df78a82
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073289"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="fc2e2-103">Шаг 3. Удаление разворотов пакетов</span><span class="sxs-lookup"><span data-stu-id="fc2e2-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="fc2e2-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="fc2e2-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="fc2e2-p101">[Разворот пакетов](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) происходит, когда трафик вместо пункта назначения сначала направляется в локальный стек безопасности, брокер доступа в облако или облачный веб-шлюз. Разворот пакетов также может объясняться плохой маршрутизацией в Интернете из-за поставщиков сетевых услуг. Разворот увеличивает задержку и может перенаправлять трафик далеко от пункта назначения.</span><span class="sxs-lookup"><span data-stu-id="fc2e2-p101">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway. A network hairpin could also be caused by poor routing on the Internet due to network service providers. A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="fc2e2-p102">Чтобы оптимизировать производительность для трафика в облачные службы Microsoft 365, проверьте, есть ли у поставщика локального подключения к Интернету прямой обмен трафиком с глобальной сетью Майкрософт в непосредственной близости от этого места. Эти подключения не имеют разворотов.</span><span class="sxs-lookup"><span data-stu-id="fc2e2-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="fc2e2-p103">Если вы используете облачные службы безопасности сети для трафика Microsoft 365, оцените разворот пакетов и его влияние на производительность. Изучите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fc2e2-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="fc2e2-112">количество и адреса служб, через которые перенаправляется трафик, относительно своих филиалов и точек обмена трафиком глобальной сети Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="fc2e2-112">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="fc2e2-113">качество сетевого обмена трафиком между поставщиком услуг и вашим поставщиком услуг Интернета и Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="fc2e2-113">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="fc2e2-114">влияние обратной передачи в инфраструктуре поставщика услуг на производительность.</span><span class="sxs-lookup"><span data-stu-id="fc2e2-114">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="fc2e2-115">По возможности настройте пограничные маршрутизаторы так, чтобы они передавали доверенный трафик Microsoft 365 напрямую, не перенаправляя его через стороннее облако или облачную службу безопасности сети, которая обрабатывает ваш интернет-трафик.</span><span class="sxs-lookup"><span data-stu-id="fc2e2-115">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

<span data-ttu-id="fc2e2-116">Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step3), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="fc2e2-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="fc2e2-117">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="fc2e2-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="fc2e2-118">Настройка обхода трафика</span><span class="sxs-lookup"><span data-stu-id="fc2e2-118">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
