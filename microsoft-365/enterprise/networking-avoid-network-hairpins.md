---
title: Шаг 3. Удаление разворотов пакетов
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Удалите развороты пакетов для повышения производительности.
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583429"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="6598c-103">Шаг 3. Удаление разворотов пакетов</span><span class="sxs-lookup"><span data-stu-id="6598c-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="6598c-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="6598c-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Этап 1. Сеть](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="6598c-106">[Разворот пакетов](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) происходит, когда трафик вместо пункта назначения сначала направляется в локальный стек безопасности, брокер доступа в облако или облачный веб-шлюз.</span><span class="sxs-lookup"><span data-stu-id="6598c-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="6598c-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="6598c-107">Here is an example.</span></span>

![Пример разворота пакетов](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="6598c-109">Разворот пакетов также может объясняться плохой маршрутизацией в Интернете из-за поставщиков сетевых услуг.</span><span class="sxs-lookup"><span data-stu-id="6598c-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="6598c-110">Разворот увеличивает задержку и может перенаправлять трафик далеко от пункта назначения.</span><span class="sxs-lookup"><span data-stu-id="6598c-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="6598c-p102">Чтобы оптимизировать производительность для трафика в облачные службы Microsoft 365, проверьте, есть ли у поставщика локального подключения к Интернету прямой обмен трафиком с глобальной сетью Майкрософт в непосредственной близости от этого места. Эти подключения не имеют разворотов.</span><span class="sxs-lookup"><span data-stu-id="6598c-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="6598c-p103">Если вы используете облачные службы безопасности сети для трафика Microsoft 365, оцените разворот пакетов и его влияние на производительность. Изучите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="6598c-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="6598c-115">количество и адреса служб, через которые перенаправляется трафик, относительно своих филиалов и точек обмена трафиком глобальной сети Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="6598c-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="6598c-116">качество сетевого обмена трафиком между поставщиком услуг и вашим поставщиком услуг Интернета и Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="6598c-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="6598c-117">влияние обратной передачи в инфраструктуре поставщика услуг на производительность.</span><span class="sxs-lookup"><span data-stu-id="6598c-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="6598c-118">По возможности настройте пограничные маршрутизаторы так, чтобы они передавали доверенный трафик Microsoft 365 напрямую, не перенаправляя его через стороннее облако или облачную службу безопасности сети, которая обрабатывает ваш интернет-трафик.</span><span class="sxs-lookup"><span data-stu-id="6598c-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![Пример обхода разворота пакетов](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="6598c-120">Чтобы протестировать, насколько близко вы находитесь к точке входа в глобальную сеть Майкрософт, а также к точке подключения сети организации к поставщику услуг Интернета, воспользуйтесь [средством подключения сети Office 365](https://connectivity.office.com/).</span><span class="sxs-lookup"><span data-stu-id="6598c-120">To test how close you are to an entry point for Microsoft’s global network and how close you are to the point where your organization network connects to your ISP, use the [Office 365 Network Onboarding tool](https://connectivity.office.com/).</span></span>

<span data-ttu-id="6598c-121">Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step3), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="6598c-121">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="6598c-122">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="6598c-122">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="6598c-124">Настройка обхода трафика</span><span class="sxs-lookup"><span data-stu-id="6598c-124">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
