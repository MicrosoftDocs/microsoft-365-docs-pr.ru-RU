---
title: Общие сведения о происшествиях в защитнике Microsoft 365
description: Выясните, какие инциденты видно на других устройствах, у других пользователей и в почтовых ящиках.
keywords: инциденты, оповещения, исследование, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверение, почтовый ящик, электронная почта, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: e5ac3e9a02c333d3168c328aa6ad5532c48af99e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846692"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="ed6b6-104">Общие сведения о происшествиях в защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed6b6-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ed6b6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ed6b6-105">**Applies to:**</span></span>
- <span data-ttu-id="ed6b6-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed6b6-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="ed6b6-107">Инциденты основываются на соответствующих предупреждениях.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-107">Incidents are based on related alerts.</span></span> <span data-ttu-id="ed6b6-108">Оповещения создаются в том случае, если в вашей сети встречается вредоносное событие или действие.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="ed6b6-109">Отдельные оповещения предоставляют важную информацию о том, что происходит при атаках.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-109">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="ed6b6-110">Тем не менее, как правило, атаки используют различные векторы и методы для выполнения нарушений.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-110">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="ed6b6-111">ПиеЦинг индивидуальные подотчетные лица могут быть проблематичными и занимать много времени.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-111">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="ed6b6-112">В этом кратком видеоролике приводится обзор происшествий в защитнике Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-112">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="ed6b6-113">Инцидент — это набор коррелированных оповещений, которые составляют историю атак.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-113">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="ed6b6-114">Вредоносные и подозрительные события, обнаруженные в различных объектах устройств, пользователей и почтовых ящиков в сети, автоматически объединяются защитником Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-114">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="ed6b6-115">Группировка связанных оповещений в инцидент дает средствам защиты более полное представление о атаках.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-115">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="ed6b6-116">Например, защитники безопасности могут видеть, где начался атака, какие тактики использовались и насколько атака пропало в сети.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-116">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="ed6b6-117">Кроме того, они могут просматривать область атаки, например количество устройств, пользователей и почтовых ящиков, влияние на их воздействие и другие сведения об затронутых объектах.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-117">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="ed6b6-118">Если этот параметр включен, защитник Microsoft 365 может автоматически исследовать и разрешать отдельные оповещения с помощью автоматизации и искусственного интеллекта.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-118">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="ed6b6-119">Кроме того, защитники безопасности могут выполнять дополнительные действия по исправлению для устранения атак прямо из представления происшествий.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-119">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="ed6b6-120">Инциденты за последние 30 дней показаны в очереди инцидентов.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-120">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="ed6b6-121">Отсюда, защитники безопасности могут видеть, какие инциденты должны определять приоритет на основе уровня риска и других факторов.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-121">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="ed6b6-122">Защитники безопасности также могут переименовывать инциденты, назначать их отдельным аналитикам, классифицировать и добавлять теги в инциденты для более эффективного и настраиваемого управления инцидентами.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-122">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="ed6b6-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ed6b6-123">See also</span></span>
- [<span data-ttu-id="ed6b6-124">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="ed6b6-124">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="ed6b6-125">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="ed6b6-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="ed6b6-126">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="ed6b6-126">Manage incidents</span></span>](manage-incidents.md)
