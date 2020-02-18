---
title: Шаг 3. Удаление разворотов пакетов
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
description: Удалите развороты пакетов для повышения производительности.
ms.openlocfilehash: f9499fdb8e8c3f7b77e3349d6cc99f6dbf465870
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066722"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="8e23e-103">Шаг 3. Удаление разворотов пакетов</span><span class="sxs-lookup"><span data-stu-id="8e23e-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="8e23e-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="8e23e-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Этап 1. Сеть](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="8e23e-106">[Разворот пакетов](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) происходит, когда трафик вместо пункта назначения сначала направляется в локальный стек безопасности, брокер доступа в облако или облачный веб-шлюз.</span><span class="sxs-lookup"><span data-stu-id="8e23e-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="8e23e-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e23e-107">Here is an example.</span></span>

![Пример разворота пакетов](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="8e23e-109">Разворот пакетов также может объясняться плохой маршрутизацией в Интернете из-за поставщиков сетевых услуг.</span><span class="sxs-lookup"><span data-stu-id="8e23e-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="8e23e-110">Разворот увеличивает задержку и может перенаправлять трафик далеко от пункта назначения.</span><span class="sxs-lookup"><span data-stu-id="8e23e-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="8e23e-p102">Чтобы оптимизировать производительность для трафика в облачные службы Microsoft 365, проверьте, есть ли у поставщика локального подключения к Интернету прямой обмен трафиком с глобальной сетью Майкрософт в непосредственной близости от этого места. Эти подключения не имеют разворотов.</span><span class="sxs-lookup"><span data-stu-id="8e23e-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="8e23e-p103">Если вы используете облачные службы безопасности сети для трафика Microsoft 365, оцените разворот пакетов и его влияние на производительность. Изучите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8e23e-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="8e23e-115">количество и адреса служб, через которые перенаправляется трафик, относительно своих филиалов и точек обмена трафиком глобальной сети Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="8e23e-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="8e23e-116">качество сетевого обмена трафиком между поставщиком услуг и вашим поставщиком услуг Интернета и Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="8e23e-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="8e23e-117">влияние обратной передачи в инфраструктуре поставщика услуг на производительность.</span><span class="sxs-lookup"><span data-stu-id="8e23e-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="8e23e-118">По возможности настройте пограничные маршрутизаторы так, чтобы они передавали доверенный трафик Microsoft 365 напрямую, не перенаправляя его через стороннее облако или облачную службу безопасности сети, которая обрабатывает ваш интернет-трафик.</span><span class="sxs-lookup"><span data-stu-id="8e23e-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![Пример обхода разворота пакетов](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="8e23e-120">Прежде чем переходить к следующему этапу, проверьте [условия](networking-exit-criteria.md#crit-networking-step3), при выполнении которых можно считать данный этап завершенным.</span><span class="sxs-lookup"><span data-stu-id="8e23e-120">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8e23e-121">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="8e23e-121">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="8e23e-123">Настройка обхода трафика</span><span class="sxs-lookup"><span data-stu-id="8e23e-123">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
