---
title: Обзор инцидентов в Microsoft 365 Defender
description: Выясните, какие инциденты видно на других устройствах, у других пользователей и в почтовых ящиках.
keywords: инциденты, оповещения, исследование, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверение, почтовый ящик, электронная почта, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6dd13c5f83d05be3c77e5f84608fb6aa5172d9a4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500927"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="7df1b-104">Обзор инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7df1b-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7df1b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7df1b-105">**Applies to:**</span></span>
- <span data-ttu-id="7df1b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7df1b-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="7df1b-107">Хотите попробовать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="7df1b-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="7df1b-108">Вы можете [оценить его в лабораторной среде](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) или [запустить пилотный проект в производственной среде](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="7df1b-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>


<span data-ttu-id="7df1b-109">Инциденты основаны на связанных оповещениях.</span><span class="sxs-lookup"><span data-stu-id="7df1b-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="7df1b-110">Оповещения создаются в том случае, если в вашей сети встречается вредоносное событие или действие.</span><span class="sxs-lookup"><span data-stu-id="7df1b-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="7df1b-111">Отдельные оповещений предоставляют ценные подсказки о атаке на время.</span><span class="sxs-lookup"><span data-stu-id="7df1b-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="7df1b-112">Однако при атаках обычно используются различные векторы и методы для выполнения нарушения.</span><span class="sxs-lookup"><span data-stu-id="7df1b-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="7df1b-113">Совмещать отдельные подсказки вместе может быть сложной задачей и трудоемкой задачей.</span><span class="sxs-lookup"><span data-stu-id="7df1b-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="7df1b-114">В этом коротком видео приводится обзор инцидентов в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7df1b-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="7df1b-115">Инцидент — это набор коррелирующих оповещений, которые составляют историю атаки.</span><span class="sxs-lookup"><span data-stu-id="7df1b-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="7df1b-116">Вредоносные и подозрительные события, которые находятся в различных устройствах, пользователях и почтовых ящиках в сети, автоматически агрегируются Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7df1b-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="7df1b-117">Группировка связанных оповещений в инцидент дает защитникам безопасности полное представление об атаке.</span><span class="sxs-lookup"><span data-stu-id="7df1b-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="7df1b-118">Например, защитники безопасности могут видеть, с чего началась атака, какую тактику использовали и как далеко атака зашло в сеть.</span><span class="sxs-lookup"><span data-stu-id="7df1b-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="7df1b-119">Они также могут видеть область атаки, например, сколько устройств, пользователей и почтовых ящиков было затронуто, как сильное воздействие было, и другие сведения о затронутых сущностях.</span><span class="sxs-lookup"><span data-stu-id="7df1b-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="7df1b-120">Если включено, Microsoft 365 Defender может автоматически исследовать и устранять отдельные оповещения с помощью автоматизации и искусственного интеллекта.</span><span class="sxs-lookup"><span data-stu-id="7df1b-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="7df1b-121">Защитники безопасности также могут выполнять дополнительные действия по исправлению, чтобы устранить атаку прямо из представления об инцидентах.</span><span class="sxs-lookup"><span data-stu-id="7df1b-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="7df1b-122">В очереди инцидента показаны инциденты за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="7df1b-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="7df1b-123">Отсюда защитники безопасности могут увидеть, какие инциденты должны быть приоритизированы в зависимости от уровня риска и других факторов.</span><span class="sxs-lookup"><span data-stu-id="7df1b-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="7df1b-124">Защитники безопасности также могут переименовывать инциденты, назначать их отдельным аналитикам, классифицировать и добавлять теги в инциденты для улучшения и более настраиваемого управления инцидентами.</span><span class="sxs-lookup"><span data-stu-id="7df1b-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="7df1b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7df1b-125">See also</span></span>
- [<span data-ttu-id="7df1b-126">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="7df1b-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="7df1b-127">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="7df1b-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="7df1b-128">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="7df1b-128">Manage incidents</span></span>](manage-incidents.md)