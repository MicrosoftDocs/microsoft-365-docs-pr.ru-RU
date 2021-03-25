---
title: Оценка экспозиции в управлении угрозами и уязвимостью
description: Оценка воздействия на управление рисками и уязвимостями отражает уязвимость организации к угрозам кибербезопасности.
keywords: оценка экспозиции, оценка экспозиции mdatp, оценка экспозиции mdatp tvm, оценка экспозиции организации, оценка экспозиции организации tvm, управление угрозами и уязвимостью, Microsoft Defender для Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cc7abd678d6f2d317d02c4ed2b8028e7e270b055
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076486"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a><span data-ttu-id="aa2a5-104">Оценка экспозиции — управление угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="aa2a5-104">Exposure score - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aa2a5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="aa2a5-105">**Applies to:**</span></span>

- [<span data-ttu-id="aa2a5-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="aa2a5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="aa2a5-107">Управление угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="aa2a5-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="aa2a5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa2a5-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="aa2a5-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="aa2a5-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aa2a5-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="aa2a5-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="aa2a5-111">Оценка экспозиции отображается на [панели](tvm-dashboard-insights.md) управления угрозами и уязвимостью Центра безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="aa2a5-111">Your exposure score is visible in the [Threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="aa2a5-112">Это отражает уязвимость организации к угрозам кибербезопасности.</span><span class="sxs-lookup"><span data-stu-id="aa2a5-112">It reflects how vulnerable your organization is to cybersecurity threats.</span></span> <span data-ttu-id="aa2a5-113">Низкая оценка экспозиции означает, что ваши устройства менее уязвимы от эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="aa2a5-113">Low exposure score means your devices are less vulnerable from exploitation.</span></span>

- <span data-ttu-id="aa2a5-114">Быстрое понимание и определение высокоуровневой информации о состоянии безопасности в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="aa2a5-114">Quickly understand and identify high-level takeaways about the state of security in your organization.</span></span>
- <span data-ttu-id="aa2a5-115">Обнаружение и реагирование на области, которые требуют расследования или действий для улучшения текущего состояния.</span><span class="sxs-lookup"><span data-stu-id="aa2a5-115">Detect and respond to areas that require investigation or action to improve the current state.</span></span>
- <span data-ttu-id="aa2a5-116">Общение с коллегами и руководством о влиянии усилий по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="aa2a5-116">Communicate with peers and management about the impact of security efforts.</span></span>

<span data-ttu-id="aa2a5-117">Карта позволяет просматривать тенденцию оценки экспозиции на высоком уровне со временем.</span><span class="sxs-lookup"><span data-stu-id="aa2a5-117">The card gives you a high-level view of your exposure score trend over time.</span></span> <span data-ttu-id="aa2a5-118">Любые всплески в диаграмме дают наглядное представление о высокой угрозе кибербезопасности, которую можно исследовать далее.</span><span class="sxs-lookup"><span data-stu-id="aa2a5-118">Any spikes in the chart give you a visual indication of a high cybersecurity threat exposure that you can investigate further.</span></span>

![Карта показателей экспозиции](images/tvm_exp_score.png)

## <a name="how-it-works"></a><span data-ttu-id="aa2a5-120">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="aa2a5-120">How it works</span></span>

<span data-ttu-id="aa2a5-121">Оценка экспозиции разбита на следующие уровни:</span><span class="sxs-lookup"><span data-stu-id="aa2a5-121">The exposure score is broken down into the following levels:</span></span>

- <span data-ttu-id="aa2a5-122">0-29: низкая оценка экспозиции</span><span class="sxs-lookup"><span data-stu-id="aa2a5-122">0–29: low exposure score</span></span>
- <span data-ttu-id="aa2a5-123">30-69: средняя оценка экспозиции</span><span class="sxs-lookup"><span data-stu-id="aa2a5-123">30–69: medium exposure score</span></span>
- <span data-ttu-id="aa2a5-124">70-100: высокая оценка экспозиции</span><span class="sxs-lookup"><span data-stu-id="aa2a5-124">70–100: high exposure score</span></span>

<span data-ttu-id="aa2a5-125">Вы можете устранять проблемы, основываясь [](tvm-security-recommendation.md) на рекомендациях по безопасности с приоритетами, чтобы снизить оценку экспозиции.</span><span class="sxs-lookup"><span data-stu-id="aa2a5-125">You can remediate the issues based on prioritized [security recommendations](tvm-security-recommendation.md) to reduce the exposure score.</span></span> <span data-ttu-id="aa2a5-126">У каждого программного обеспечения есть недостатки, которые преобразуются в рекомендации и приоритизируются в зависимости от риска для организации.</span><span class="sxs-lookup"><span data-stu-id="aa2a5-126">Each software has weaknesses that are transformed into recommendations and prioritized based on risk to the organization.</span></span>

## <a name="reduce-your-threat-and-vulnerability-exposure"></a><span data-ttu-id="aa2a5-127">Уменьшение воздействия угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="aa2a5-127">Reduce your threat and vulnerability exposure</span></span>

<span data-ttu-id="aa2a5-128">Снижение воздействия угрозы и уязвимости путем устранения [рекомендаций по безопасности.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="aa2a5-128">Lower your threat and vulnerability exposure by remediating [security recommendations](tvm-security-recommendation.md).</span></span> <span data-ttu-id="aa2a5-129">Сделайте наибольшее влияние на оценку экспозиции, изменив верхние рекомендации по безопасности, которые можно просмотреть в панели управления угрозами и [уязвимостями.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="aa2a5-129">Make the most impact to your exposure score by remediating the top security recommendations, which can be viewed in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="aa2a5-130">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="aa2a5-130">Related topics</span></span>

- [<span data-ttu-id="aa2a5-131">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="aa2a5-131">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="aa2a5-132">Microsoft Secure Score для устройств</span><span class="sxs-lookup"><span data-stu-id="aa2a5-132">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="aa2a5-133">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="aa2a5-133">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="aa2a5-134">Временная шкала событий</span><span class="sxs-lookup"><span data-stu-id="aa2a5-134">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
