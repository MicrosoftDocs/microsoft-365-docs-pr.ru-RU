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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f462e6018f03080b41e46f45629dc4bfe44b3ef9
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200021"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="1f727-104">Обзор инцидентов в службе Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1f727-104">Incidents overview in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1f727-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1f727-105">**Applies to:**</span></span>
- <span data-ttu-id="1f727-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1f727-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="1f727-107">Основой всех происшествий являются оповещения.</span><span class="sxs-lookup"><span data-stu-id="1f727-107">The basis of all incidents are alerts.</span></span> <span data-ttu-id="1f727-108">Оповещения создаются в том случае, если в вашей сети встречается вредоносное событие или действие.</span><span class="sxs-lookup"><span data-stu-id="1f727-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="1f727-109">Отдельные оповещения предоставляют ценные признаки о том, что происходит с конкретными событиями или объектами.</span><span class="sxs-lookup"><span data-stu-id="1f727-109">Individual alerts provide valuable clues in what's happening on individual events or entities.</span></span> <span data-ttu-id="1f727-110">Тем не менее, как правило, атаки используют различные векторы атаки для нарушения безопасности.</span><span class="sxs-lookup"><span data-stu-id="1f727-110">However, attacks typically employ various attack vectors to carry out a breach.</span></span> <span data-ttu-id="1f727-111">Сбор отдельных признаков в единую картину может быть непростой и трудоемкой задачей.</span><span class="sxs-lookup"><span data-stu-id="1f727-111">Piecing individual clues together can be a challenging and time-consuming task.</span></span> 

<span data-ttu-id="1f727-112">Защита от угроз (Майкрософт) соединяет точки от отдельных оповещений.</span><span class="sxs-lookup"><span data-stu-id="1f727-112">Microsoft Threat Protection connects the dots on individual alerts.</span></span> <span data-ttu-id="1f727-113">Вредоносные события в указанных ниже объектах выводятся в Центре безопасности Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="1f727-113">Malicious events on the following entities are surfaced in the Microsoft 365 security center:</span></span>
- <span data-ttu-id="1f727-114">Устройства</span><span class="sxs-lookup"><span data-stu-id="1f727-114">Devices</span></span>
- <span data-ttu-id="1f727-115">Пользователи</span><span class="sxs-lookup"><span data-stu-id="1f727-115">Users</span></span>
- <span data-ttu-id="1f727-116">Почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="1f727-116">Mailboxes</span></span>

<span data-ttu-id="1f727-117">Подозрительные события, которые демонстрируют характеристики принадлежности к массированной атаке, объединяются в инцидент.</span><span class="sxs-lookup"><span data-stu-id="1f727-117">Suspicious events that show characteristics of being part of a larger attack are aggregated into an incident.</span></span> 

<span data-ttu-id="1f727-118">У вас будет точная информация о месте начала атаки и сведения, позволяющие понять весь объем атаки.</span><span class="sxs-lookup"><span data-stu-id="1f727-118">You'll know exactly where an attack started and other details to help you see the extent of the attack.</span></span>

<span data-ttu-id="1f727-119">Эта платформа предоставляет защитников безопасности с корректными визуальными элементами и презентациями для понимания и устранения сложных межобъектных угроз.</span><span class="sxs-lookup"><span data-stu-id="1f727-119">The platform provides security defenders with the right visuals and data representations to understand and address complex cross-entity threats.</span></span> 

<span data-ttu-id="1f727-120">У вас будет представление не только о масштабах атаки, но также у вас будет доступ к службам, которые позволят предпринять тактические шаги для сдерживания инцидента.</span><span class="sxs-lookup"><span data-stu-id="1f727-120">Not only will you have visibility on the scope of an attack, but you'll also have access to services that will allow you to take tactical steps to contain an incident.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1f727-121">См. также</span><span class="sxs-lookup"><span data-stu-id="1f727-121">Related topics</span></span>
- [<span data-ttu-id="1f727-122">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="1f727-122">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="1f727-123">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="1f727-123">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="1f727-124">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="1f727-124">Manage incidents</span></span>](manage-incidents.md)
