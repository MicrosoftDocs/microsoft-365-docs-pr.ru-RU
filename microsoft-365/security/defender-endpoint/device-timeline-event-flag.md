---
title: Флаги событий событий Microsoft Defender для конечных устройств
description: Используйте флаги событий Времени событий Microsoft Defender для конечных устройств
keywords: Защитник для хронологии устройств конечной точки, флаги событий
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165157"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a><span data-ttu-id="8e59d-104">Флаги событий событий Microsoft Defender для конечных устройств</span><span class="sxs-lookup"><span data-stu-id="8e59d-104">Microsoft Defender for Endpoint device timeline event flags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8e59d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8e59d-105">**Applies to:**</span></span>
- [<span data-ttu-id="8e59d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8e59d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8e59d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e59d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8e59d-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8e59d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8e59d-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8e59d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="8e59d-110">Флаги событий в временной шкале устройств Defender для конечных точек помогают фильтровать и организовывать определенные события при расследовании возможных атак.</span><span class="sxs-lookup"><span data-stu-id="8e59d-110">Event flags in the Defender for Endpoint device timeline help you filter and organize specific events when you're  investigate potential attacks.</span></span>

<span data-ttu-id="8e59d-111">В временной шкале устройства Defender для конечных точек предоставляется хронологическое представление событий и связанных оповещений, наблюдаемых на устройстве.</span><span class="sxs-lookup"><span data-stu-id="8e59d-111">The Defender for Endpoint device timeline provides a chronological view of the events and associated alerts observed on a device.</span></span> <span data-ttu-id="8e59d-112">Этот список событий обеспечивает полную видимость любых событий, файлов и IP-адресов, наблюдаемых на устройстве.</span><span class="sxs-lookup"><span data-stu-id="8e59d-112">This list of events provides full visibility into any events, files, and IP addresses observed on the device.</span></span> <span data-ttu-id="8e59d-113">Иногда список может быть длительным.</span><span class="sxs-lookup"><span data-stu-id="8e59d-113">The list can sometimes be lengthy.</span></span> <span data-ttu-id="8e59d-114">Флаги событий временной шкалы устройств помогают отслеживать события, которые могут быть связаны.</span><span class="sxs-lookup"><span data-stu-id="8e59d-114">Device timeline event flags help you track events that could be related.</span></span> 

<span data-ttu-id="8e59d-115">После того как вы прошли временную шкалу устройства, вы можете сортировать, фильтровать и экспортировать определенные события, которые вы помечены.</span><span class="sxs-lookup"><span data-stu-id="8e59d-115">After you've gone through a device timeline, you can sort, filter, and export the specific events that you flagged.</span></span>

<span data-ttu-id="8e59d-116">Во время навигации по временной шкале устройства можно искать и фильтровать определенные события.</span><span class="sxs-lookup"><span data-stu-id="8e59d-116">While navigating the device timeline, you can search and filter for specific events.</span></span> <span data-ttu-id="8e59d-117">Вы можете установить флаги событий по:</span><span class="sxs-lookup"><span data-stu-id="8e59d-117">You can set event flags by:</span></span> 

- <span data-ttu-id="8e59d-118">Выделение наиболее важных событий</span><span class="sxs-lookup"><span data-stu-id="8e59d-118">Highlighting the most important events</span></span> 
- <span data-ttu-id="8e59d-119">Маркировка событий, которые требуют глубокого погружения</span><span class="sxs-lookup"><span data-stu-id="8e59d-119">Marking events that requires deep dive</span></span> 
- <span data-ttu-id="8e59d-120">Создание хронологии чистого нарушения</span><span class="sxs-lookup"><span data-stu-id="8e59d-120">Building a clean breach timeline</span></span>



## <a name="flag-an-event"></a><span data-ttu-id="8e59d-121">Пометить событие</span><span class="sxs-lookup"><span data-stu-id="8e59d-121">Flag an event</span></span>
1. <span data-ttu-id="8e59d-122">Найдите событие, которое необходимо пометить</span><span class="sxs-lookup"><span data-stu-id="8e59d-122">Find the event that you want to flag</span></span>
2. <span data-ttu-id="8e59d-123">Щелкните значок флага в столбце Флаг.</span><span class="sxs-lookup"><span data-stu-id="8e59d-123">Click the flag icon in the Flag column.</span></span> 
<span data-ttu-id="8e59d-124">![Изображение флага временной шкалы устройства](images/device-flags.png)</span><span class="sxs-lookup"><span data-stu-id="8e59d-124">![Image of device timeline flag](images/device-flags.png)</span></span>

## <a name="view-flagged-events"></a><span data-ttu-id="8e59d-125">Просмотр помеченных событий</span><span class="sxs-lookup"><span data-stu-id="8e59d-125">View flagged events</span></span>  
1. <span data-ttu-id="8e59d-126">В разделе **Фильтры временной шкалы** в включить **помеченные события.**</span><span class="sxs-lookup"><span data-stu-id="8e59d-126">In the timeline **Filters** section, enable **Flagged events**.</span></span>
2. <span data-ttu-id="8e59d-127">Нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="8e59d-127">Click **Apply**.</span></span> <span data-ttu-id="8e59d-128">Отображаются только помеченные события.</span><span class="sxs-lookup"><span data-stu-id="8e59d-128">Only flagged events are displayed.</span></span>
<span data-ttu-id="8e59d-129">Дополнительные фильтры можно применить, нажав на планку времени.</span><span class="sxs-lookup"><span data-stu-id="8e59d-129">You can apply additional filters by clicking on the time bar.</span></span> <span data-ttu-id="8e59d-130">В этом случае будут показываться события только до помеченного события.</span><span class="sxs-lookup"><span data-stu-id="8e59d-130">This will only show events prior to the flagged event.</span></span>  
<span data-ttu-id="8e59d-131">![Изображение флага временной шкалы устройства с фильтром](images/device-flag-filter.png)</span><span class="sxs-lookup"><span data-stu-id="8e59d-131">![Image of device timeline flag with filter on](images/device-flag-filter.png)</span></span>
