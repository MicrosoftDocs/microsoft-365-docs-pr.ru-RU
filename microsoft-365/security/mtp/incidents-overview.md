---
title: Обзор инцидентов в службе Защиты от угроз (Майкрософт)
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
- m365-initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b0cfa6ed4af6ef9c5686cb25d5b2f0522d818860
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412902"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="eff83-104">Обзор инцидентов в службе Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="eff83-104">Incidents overview in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="eff83-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="eff83-105">**Applies to:**</span></span>
- <span data-ttu-id="eff83-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="eff83-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="eff83-107">Инциденты основываются на соответствующих предупреждениях.</span><span class="sxs-lookup"><span data-stu-id="eff83-107">Incidents are based on related alerts.</span></span> <span data-ttu-id="eff83-108">Оповещения создаются в том случае, если в вашей сети встречается вредоносное событие или действие.</span><span class="sxs-lookup"><span data-stu-id="eff83-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="eff83-109">Отдельные оповещения предоставляют важную информацию о том, что происходит при атаках.</span><span class="sxs-lookup"><span data-stu-id="eff83-109">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="eff83-110">Тем не менее, как правило, атаки используют различные векторы и методы для выполнения нарушений.</span><span class="sxs-lookup"><span data-stu-id="eff83-110">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="eff83-111">ПиеЦинг индивидуальные подотчетные лица могут быть проблематичными и занимать много времени.</span><span class="sxs-lookup"><span data-stu-id="eff83-111">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="eff83-112">В этом кратком видеоролике приводится обзор происшествий в защите от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="eff83-112">This short video gives an overview of incidents in Microsoft Threat Protection.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="eff83-113">Инцидент — это набор коррелированных оповещений, которые составляют историю атак.</span><span class="sxs-lookup"><span data-stu-id="eff83-113">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="eff83-114">Вредоносные и подозрительные события, обнаруженные в различных объектах устройств, пользователей и почтовых ящиков в сети, автоматически объединяются службой защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="eff83-114">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft Threat Protection.</span></span> <span data-ttu-id="eff83-115">Группировка связанных оповещений в инцидент дает средствам защиты более полное представление о атаках.</span><span class="sxs-lookup"><span data-stu-id="eff83-115">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="eff83-116">Например, защитники безопасности могут видеть, где начался атака, какие тактики использовались и насколько атака пропало в сети.</span><span class="sxs-lookup"><span data-stu-id="eff83-116">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="eff83-117">Кроме того, они могут просматривать область атаки, например количество устройств, пользователей и почтовых ящиков, влияние на их воздействие и другие сведения об затронутых объектах.</span><span class="sxs-lookup"><span data-stu-id="eff83-117">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="eff83-118">Если этот параметр включен, защита от угроз Майкрософт может автоматически исследовать и разрешать отдельные оповещения с помощью автоматизации и искусственного интеллекта.</span><span class="sxs-lookup"><span data-stu-id="eff83-118">If enabled, Microsoft Threat Protection can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="eff83-119">Кроме того, защитники безопасности могут выполнять дополнительные действия по исправлению для устранения атак прямо из представления происшествий.</span><span class="sxs-lookup"><span data-stu-id="eff83-119">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="eff83-120">Инциденты за последние 30 дней показаны в очереди инцидентов.</span><span class="sxs-lookup"><span data-stu-id="eff83-120">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="eff83-121">Отсюда, защитники безопасности могут видеть, какие инциденты должны определять приоритет на основе уровня риска и других факторов.</span><span class="sxs-lookup"><span data-stu-id="eff83-121">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="eff83-122">Защитники безопасности также могут переименовывать инциденты, назначать их отдельным аналитикам, классифицировать и добавлять теги в инциденты для более эффективного и настраиваемого управления инцидентами.</span><span class="sxs-lookup"><span data-stu-id="eff83-122">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="eff83-123">См. также</span><span class="sxs-lookup"><span data-stu-id="eff83-123">See also</span></span>
- [<span data-ttu-id="eff83-124">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="eff83-124">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="eff83-125">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="eff83-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="eff83-126">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="eff83-126">Manage incidents</span></span>](manage-incidents.md)
