---
title: Обзор возможностей обнаружения конечных точек и ответов
ms.reviewer: ''
description: Узнайте о возможностях обнаружения конечных точек и ответов в ATP Microsoft Defender
keywords: ''
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 858ea0f8d46ac2489dd6ef5c10caf2ce0879e4fb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076518"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="d201b-103">Обзор обнаружения конечных точек и ответа</span><span class="sxs-lookup"><span data-stu-id="d201b-103">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d201b-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d201b-104">**Applies to:**</span></span>
- [<span data-ttu-id="d201b-105">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d201b-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="d201b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d201b-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d201b-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d201b-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d201b-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d201b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d201b-109">Функции обнаружения конечных точек и ответов Defender для конечной точки предоставляют расширенные обнаружения атак, которые находятся в режиме реального времени и могут быть готовы к действию.</span><span class="sxs-lookup"><span data-stu-id="d201b-109">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="d201b-110">Аналитики систем безопасности могут эффективно определять приоритеты предупреждений, получать полную картину всех возможных брешей в системе безопасности, а также предпринимать действия по реагированию для устранения угроз.</span><span class="sxs-lookup"><span data-stu-id="d201b-110">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="d201b-111">При обнаружении угрозы в системе создаются предупреждения, которые затем исследуются аналитиками.</span><span class="sxs-lookup"><span data-stu-id="d201b-111">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="d201b-112">Предупреждения, относящиеся к одинаковым методам атаки или к одному и тому же злоумышленнику, система агрегирует в объект, называемый _инцидентом_.</span><span class="sxs-lookup"><span data-stu-id="d201b-112">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="d201b-113">Агрегирование предупреждений таким способом упрощает аналитикам выполнение обобщенных расследований угроз и реагирование на такие угрозы.</span><span class="sxs-lookup"><span data-stu-id="d201b-113">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="d201b-114">Вдохновленный мышлением "предположить нарушение", Defender for Endpoint непрерывно собирает поведенческую кибер-телеметрию.</span><span class="sxs-lookup"><span data-stu-id="d201b-114">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="d201b-115">Сюда входят сведения о процессах, действиях в сети, глубокий анализ ядра и диспетчера памяти, информация о действиях по входу в систему, об изменениях в реестре и файловой системе, а также о других действиях.</span><span class="sxs-lookup"><span data-stu-id="d201b-115">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="d201b-116">Информация хранится в течение шести месяцев, благодаря чему аналитики могут изучать события вплоть до начала атаки.</span><span class="sxs-lookup"><span data-stu-id="d201b-116">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="d201b-117">Затем аналитик может создать различные сводные представления и провести расследование в нескольких направлениях.</span><span class="sxs-lookup"><span data-stu-id="d201b-117">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="d201b-118">Функции реагирования позволяют быстро устранять угрозы, выполняя действия над затронутыми объектами.</span><span class="sxs-lookup"><span data-stu-id="d201b-118">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d201b-119">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d201b-119">Related topics</span></span>
- [<span data-ttu-id="d201b-120">Панель мониторинга операций безопасности</span><span class="sxs-lookup"><span data-stu-id="d201b-120">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="d201b-121">Очередь инцидентов</span><span class="sxs-lookup"><span data-stu-id="d201b-121">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="d201b-122">Очередь оповещений</span><span class="sxs-lookup"><span data-stu-id="d201b-122">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="d201b-123">Список устройств</span><span class="sxs-lookup"><span data-stu-id="d201b-123">Devices list</span></span>](machines-view-overview.md)

