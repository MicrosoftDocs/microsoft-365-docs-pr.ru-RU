---
title: Основные принципы защиты от атак типа "отказ в обслуживании" Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Сведения о том, как корпорация Майкрософт использует основные принципы абсорптион, обнаружения и смягчения защиты от атак типа "отказ в обслуживании" (DoS).
ms.openlocfilehash: b04ec717f7c97e44c6ed4011156666e8c27f06c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693159"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="d77ce-103">Основные принципы защиты от атак типа "отказ в обслуживании"</span><span class="sxs-lookup"><span data-stu-id="d77ce-103">Core principles of defense against denial-of-service attacks</span></span>

<span data-ttu-id="d77ce-104">Три основных принципа защиты от сетевых атак DoS: Абсорптион, обнаружение и устранение.</span><span class="sxs-lookup"><span data-stu-id="d77ce-104">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation.</span></span> <span data-ttu-id="d77ce-105">Абсорптион происходит перед обнаружением, а обнаружение происходит перед устранением.</span><span class="sxs-lookup"><span data-stu-id="d77ce-105">Absorption happens before detection, and detection happens before mitigation.</span></span> <span data-ttu-id="d77ce-106">Абсорптион — это лучшая защита от атак DoS.</span><span class="sxs-lookup"><span data-stu-id="d77ce-106">Absorption is the best defense against a DoS attack.</span></span> <span data-ttu-id="d77ce-107">Если атака не удается обнаружить, она не может быть снижена.</span><span class="sxs-lookup"><span data-stu-id="d77ce-107">If the attack can't be detected, it can't be mitigated.</span></span> <span data-ttu-id="d77ce-108">Но если не удается придерживаться самой минимальной атаки DoS, службы не будут работать достаточно долго для обнаружения атаки.</span><span class="sxs-lookup"><span data-stu-id="d77ce-108">But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="d77ce-109">В большинстве организаций невозможно приобрести чрезмерную мощность DoS-атак, так как это требует значительных капиталовложений в технологии и технические навыки.</span><span class="sxs-lookup"><span data-stu-id="d77ce-109">It is not economically feasible for most organizations to purchase excess capacity to absorb DoS attacks, as this requires a considerable investment in technology and technical skills.</span></span> <span data-ttu-id="d77ce-110">Это выделит одно из преимуществ для обеспечения безопасности при использовании облачных служб Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d77ce-110">This highlights one of the security benefits of using Microsoft cloud services.</span></span> <span data-ttu-id="d77ce-111">Подобный масштаб служб Майкрософт обеспечивает надежную защиту сети для облачных клиентов с учетом выгодных затрат.</span><span class="sxs-lookup"><span data-stu-id="d77ce-111">The sheer scale of Microsoft services provides strong network protection to cloud customers in a cost-effective manner.</span></span> <span data-ttu-id="d77ce-112">Но даже при большом масштабе должно быть баланс между абсорптион, обнаружением и снижением.</span><span class="sxs-lookup"><span data-stu-id="d77ce-112">But even at a large scale, there must be a balance between absorption, detection, and mitigation.</span></span> <span data-ttu-id="d77ce-113">Чтобы найти это сальдо, оцените возможности взлома Microsoft для оценки того, сколько необходимо для Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d77ce-113">To find that balance, Microsoft studies attack growth rates to estimate how much Microsoft needs to absorb.</span></span>

<span data-ttu-id="d77ce-114">Обнаружение — это игра Cat-and-Mouse.</span><span class="sxs-lookup"><span data-stu-id="d77ce-114">Detection is a cat-and-mouse game.</span></span> <span data-ttu-id="d77ce-115">Необходимо постоянно искать новые способы атаки на людей и попытаться неменять системы.</span><span class="sxs-lookup"><span data-stu-id="d77ce-115">You must constantly look for new ways people are attack and try to defeat your systems.</span></span> <span data-ttu-id="d77ce-116">Обнаружение-> смягчение проблем > обнаружения > и т. д. — это бессрочное постоянное состояние, которое будет выполняться неограниченно.</span><span class="sxs-lookup"><span data-stu-id="d77ce-116">Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that continues indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="d77ce-117">Защита от атак DoS</span><span class="sxs-lookup"><span data-stu-id="d77ce-117">Defending Against DoS Attacks</span></span>

<span data-ttu-id="d77ce-118">Чтобы успешно защититься от атак DoS, необходимо раннее обнаружение.</span><span class="sxs-lookup"><span data-stu-id="d77ce-118">To successfully defend against a DoS attack, early detection is essential.</span></span> <span data-ttu-id="d77ce-119">Обнаруживая атаку до того, как система перегружена, защитник может выполнить план ответа.</span><span class="sxs-lookup"><span data-stu-id="d77ce-119">By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="d77ce-120">Приведенная ниже формула позволяет оценить время, влияющее на воздействие атак DoS:</span><span class="sxs-lookup"><span data-stu-id="d77ce-120">The following formula helps approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="d77ce-121">**Максимальная мощность (в байтах/с)/скорость роста (байт/сек) = время на воздействие (в секундах)**</span><span class="sxs-lookup"><span data-stu-id="d77ce-121">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in sec)**</span></span>

<span data-ttu-id="d77ce-122">Если срок действия истекает после возникновения неблагоприятного влияния, то, скорее всего, атака на DoS будет успешной.</span><span class="sxs-lookup"><span data-stu-id="d77ce-122">If the time-to-detection occurs after time-to-impact, it is likely the DoS attack will be successful.</span></span> <span data-ttu-id="d77ce-123">Если время ожидания исправляется до начала действия, службы атаковать должны быть в сети и доступны при использовании стратегий устранения.</span><span class="sxs-lookup"><span data-stu-id="d77ce-123">If the time-to-detection occurs before time-to-impact, the attacked services should remain online and accessible if mitigation strategies are used.</span></span> <span data-ttu-id="d77ce-124">Таким образом, для защиты от атак DoS можно выполнить только два действия.</span><span class="sxs-lookup"><span data-stu-id="d77ce-124">Thus, there are only two things that can be done to defend against DoS attacks:</span></span>

- <span data-ttu-id="d77ce-125">Увеличьте емкость, чтобы увеличить максимальный объем максимальной мощности (что, в свою очередь, больше времени на обнаружение атак); также</span><span class="sxs-lookup"><span data-stu-id="d77ce-125">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="d77ce-126">Сократите время для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d77ce-126">Decrease the time to detect.</span></span>

<span data-ttu-id="d77ce-127">Повышение емкости имеет прямой финансовый эффект.</span><span class="sxs-lookup"><span data-stu-id="d77ce-127">Increasing capacity has a direct fiscal impact.</span></span> <span data-ttu-id="d77ce-128">Корпорация Майкрософт рекомендует, чтобы клиенты разработали по крайней мере базовую емкость абсорптион, чтобы они могли выдерживать некоторый уровень атак DoS.</span><span class="sxs-lookup"><span data-stu-id="d77ce-128">Microsoft recommends that customers develop at least basic absorption capacity to ensure that they can survive some level of DoS attack.</span></span> <span data-ttu-id="d77ce-129">Фактическая мощность абсорптион зависит от клиента, так как у каждого клиента есть собственные пороговые значения для экспозиции, риска и финансовых аутлай.</span><span class="sxs-lookup"><span data-stu-id="d77ce-129">The actual absorption capacity varies from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay.</span></span> <span data-ttu-id="d77ce-130">По экономическойм причинам инвестиции в исследование и время, позволяющие сократить время обнаружения, обычно представляют собой наиболее экономичную защиту.</span><span class="sxs-lookup"><span data-stu-id="d77ce-130">For economic reasons, investments in research and time for ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
