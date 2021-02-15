---
title: Обзор инцидентов в Защитнике Microsoft 365
description: Выясните, какие инциденты видно на других устройствах, у других пользователей и в почтовых ящиках.
keywords: инциденты, оповещения, исследование, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверение, почтовый ящик, электронная почта, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
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
ms.openlocfilehash: 7fcbecddd5e8f83e9c78d6db90939fbfc2f2df07
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929286"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="63c1f-104">Обзор инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63c1f-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="63c1f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="63c1f-105">**Applies to:**</span></span>
- <span data-ttu-id="63c1f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63c1f-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="63c1f-107">Хотите испытать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="63c1f-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="63c1f-108">Вы можете [оценить его в лабораторной среде](https://aka.ms/mtp-trial-lab) или запустить [пилотный проект в производственной среде.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="63c1f-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="63c1f-109">Инциденты основаны на связанных оповещениях.</span><span class="sxs-lookup"><span data-stu-id="63c1f-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="63c1f-110">Оповещения создаются в том случае, если в вашей сети встречается вредоносное событие или действие.</span><span class="sxs-lookup"><span data-stu-id="63c1f-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="63c1f-111">Отдельные оповещения предоставляют ценные сведения о атаке.</span><span class="sxs-lookup"><span data-stu-id="63c1f-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="63c1f-112">Однако атаки обычно используют различные векторы и методы для нарушения безопасности.</span><span class="sxs-lookup"><span data-stu-id="63c1f-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="63c1f-113">Совместное размещание отдельных подсказок может быть сложной задачей и отнимает много времени.</span><span class="sxs-lookup"><span data-stu-id="63c1f-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="63c1f-114">В этом коротком видео представлен обзор инцидентов в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="63c1f-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="63c1f-115">Инцидент — это коллекция коррелирующих оповещений, которые составляют историю атаки.</span><span class="sxs-lookup"><span data-stu-id="63c1f-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="63c1f-116">Вредоносные и подозрительные события, найденные в различных устройствах, пользователях и почтовых ящиках в сети, автоматически объединяются Защитником Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="63c1f-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="63c1f-117">Группировка связанных оповещений в инцидент предоставляет защитникам безопасности полное представление об атаке.</span><span class="sxs-lookup"><span data-stu-id="63c1f-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="63c1f-118">Например, защитники безопасности могут видеть, где началась атака, какие приемы использовались и как далеко атака прошла в сеть.</span><span class="sxs-lookup"><span data-stu-id="63c1f-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="63c1f-119">Они также могут видеть область атаки, например количество устройств, пользователей и почтовых ящиков, серьезное влияние и другие сведения о затронутых сущностях.</span><span class="sxs-lookup"><span data-stu-id="63c1f-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="63c1f-120">Если этот режим включен, Microsoft 365 Defender может автоматически исследовать и разрешать отдельные оповещения с помощью автоматизации и искусственного интеллекта.</span><span class="sxs-lookup"><span data-stu-id="63c1f-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="63c1f-121">Защитники безопасности также могут выполнять дополнительные действия по исправлению, чтобы устранить атаку прямо из представления инцидентов.</span><span class="sxs-lookup"><span data-stu-id="63c1f-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="63c1f-122">Инциденты за последние 30 дней показываются в очереди инцидентов.</span><span class="sxs-lookup"><span data-stu-id="63c1f-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="63c1f-123">Здесь защитники безопасности могут видеть, какие инциденты следует расставить в приоритете на основе уровня риска и других факторов.</span><span class="sxs-lookup"><span data-stu-id="63c1f-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="63c1f-124">Защитники безопасности также могут переименовывать инциденты, назначать их отдельным аналитикам, классифицировать и добавлять теги к инцидентам для улучшения и настройки управления инцидентами.</span><span class="sxs-lookup"><span data-stu-id="63c1f-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="63c1f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="63c1f-125">See also</span></span>
- [<span data-ttu-id="63c1f-126">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="63c1f-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="63c1f-127">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="63c1f-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="63c1f-128">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="63c1f-128">Manage incidents</span></span>](manage-incidents.md)
