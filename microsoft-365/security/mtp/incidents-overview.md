---
title: Исследование инцидентов в Microsoft Threat Protection
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
ms.openlocfilehash: 29eeb5f0699321441543057040b434c4dad61925
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235118"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="8c87a-104">Обзор инцидентов в службе Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="8c87a-104">Incidents overview in Microsoft Threat Protection</span></span>

<span data-ttu-id="8c87a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8c87a-105">**Applies to:**</span></span>
- <span data-ttu-id="8c87a-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="8c87a-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="8c87a-107">Основой всех происшествий являются оповещения.</span><span class="sxs-lookup"><span data-stu-id="8c87a-107">The basis of all incidents are alerts.</span></span> <span data-ttu-id="8c87a-108">Оповещения создаются в том случае, если в вашей сети встречается вредоносное событие или действие.</span><span class="sxs-lookup"><span data-stu-id="8c87a-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="8c87a-109">Отдельные оповещения предоставляют ценные признаки о том, что происходит с конкретными событиями или объектами.</span><span class="sxs-lookup"><span data-stu-id="8c87a-109">Individual alerts provide valuable clues in what's happening on individual events or entities.</span></span> <span data-ttu-id="8c87a-110">Тем не менее, как правило, атаки используют различные векторы атаки для нарушения безопасности.</span><span class="sxs-lookup"><span data-stu-id="8c87a-110">However, attacks typically employ various attack vectors to carry out a breach.</span></span> <span data-ttu-id="8c87a-111">Сбор отдельных признаков в единую картину может быть непростой и трудоемкой задачей.</span><span class="sxs-lookup"><span data-stu-id="8c87a-111">Piecing individual clues together can be a challenging and time-consuming task.</span></span> 

<span data-ttu-id="8c87a-112">Защита от угроз (Майкрософт) соединяет точки от отдельных оповещений.</span><span class="sxs-lookup"><span data-stu-id="8c87a-112">Microsoft Threat Protection connects the dots on individual alerts.</span></span> <span data-ttu-id="8c87a-113">Вредоносные события в указанных ниже объектах выводятся в Центре безопасности Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="8c87a-113">Malicious events on the following entities are surfaced in the Microsoft 365 security center:</span></span>
- <span data-ttu-id="8c87a-114">Устройства</span><span class="sxs-lookup"><span data-stu-id="8c87a-114">Devices</span></span>
- <span data-ttu-id="8c87a-115">Пользователи</span><span class="sxs-lookup"><span data-stu-id="8c87a-115">Users</span></span>
- <span data-ttu-id="8c87a-116">Почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="8c87a-116">Mailboxes</span></span>

<span data-ttu-id="8c87a-117">Подозрительные события, которые демонстрируют характеристики принадлежности к массированной атаке, объединяются в инцидент.</span><span class="sxs-lookup"><span data-stu-id="8c87a-117">Suspicious events that show characteristics of being part of a larger attack are aggregated into an incident.</span></span> 

<span data-ttu-id="8c87a-118">У вас будет точная информация о месте начала атаки и сведения, позволяющие понять весь объем атаки.</span><span class="sxs-lookup"><span data-stu-id="8c87a-118">You'll know exactly where an attack started and other details to help you see the extent of the attack.</span></span>

<span data-ttu-id="8c87a-119">Эта платформа предоставляет защитников безопасности с корректными визуальными элементами и презентациями для понимания и устранения сложных межобъектных угроз.</span><span class="sxs-lookup"><span data-stu-id="8c87a-119">The platform provides security defenders with the right visuals and data representations to understand and address complex cross-entity threats.</span></span> 

<span data-ttu-id="8c87a-120">У вас будет представление не только о масштабах атаки, но также у вас будет доступ к службам, которые позволят предпринять тактические шаги для сдерживания инцидента.</span><span class="sxs-lookup"><span data-stu-id="8c87a-120">Not only will you have visibility on the scope of an attack, but you'll also have access to services that will allow you to take tactical steps to contain an incident.</span></span>


## <a name="related-topics"></a><span data-ttu-id="8c87a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8c87a-121">Related topics</span></span>
- [<span data-ttu-id="8c87a-122">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="8c87a-122">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="8c87a-123">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="8c87a-123">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="8c87a-124">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="8c87a-124">Manage incidents</span></span>](manage-incidents.md)
