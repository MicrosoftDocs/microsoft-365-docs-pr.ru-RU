---
title: Поддерживаемые API Microsoft 365 Defender
description: Поддерживаемые API Microsoft 365 Defender
keywords: Microsoft 365 Defender, API, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c10b2863503a5bda829cbf67379a606b687ac2e3
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730946"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="73587-104">Поддерживаемые API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73587-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="73587-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="73587-105">**Applies to:**</span></span>
- <span data-ttu-id="73587-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73587-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73587-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="73587-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="73587-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="73587-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="73587-109">Список доступных API</span><span class="sxs-lookup"><span data-stu-id="73587-109">List of available APIs</span></span>

<span data-ttu-id="73587-110">Статья</span><span class="sxs-lookup"><span data-stu-id="73587-110">Article</span></span> | <span data-ttu-id="73587-111">Описание</span><span class="sxs-lookup"><span data-stu-id="73587-111">Description</span></span>
-|-
[<span data-ttu-id="73587-112">Программный интерфейс расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="73587-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="73587-113">Запустите расширенные запросы на охоту.</span><span class="sxs-lookup"><span data-stu-id="73587-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="73587-114">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="73587-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="73587-115">Список и обновление инцидентов, а также другие практические задачи.</span><span class="sxs-lookup"><span data-stu-id="73587-115">List and update incidents, along with other practical tasks.</span></span>
<span data-ttu-id="73587-116">[Потоковый API](../defender-endpoint/raw-data-export.md) (Предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="73587-116">[Streaming API](../defender-endpoint/raw-data-export.md) (Preview)</span></span> | <span data-ttu-id="73587-117">Отгрузка событий и оповещений в режиме реального времени в едином потоке данных.</span><span class="sxs-lookup"><span data-stu-id="73587-117">Ship real-time events and alerts as they occur in a single data stream.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="73587-118">URL-адреса конечной точки</span><span class="sxs-lookup"><span data-stu-id="73587-118">Endpoint URIs</span></span>

<span data-ttu-id="73587-119">Базовый URI для обоих основных API: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="73587-119">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="73587-120">Чтобы улучшить производительность, используйте сервер ближе к геолокации:</span><span class="sxs-lookup"><span data-stu-id="73587-120">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="73587-121">США: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="73587-121">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="73587-122">Европа: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="73587-122">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="73587-123">Великобритания: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="73587-123">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="73587-124">Маркеры можно приобрести путем доступа https://api.security.microsoft.com к .</span><span class="sxs-lookup"><span data-stu-id="73587-124">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="73587-125">Все API на `/api` пути используют [протокол OData;](/odata/overview) https://api.security.microsoft.com/api/incidents например.</span><span class="sxs-lookup"><span data-stu-id="73587-125">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="73587-126">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="73587-126">Related articles</span></span>

- [<span data-ttu-id="73587-127">Microsoft 365 Обзор API defender</span><span class="sxs-lookup"><span data-stu-id="73587-127">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="73587-128">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73587-128">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="73587-129">Потоковый API</span><span class="sxs-lookup"><span data-stu-id="73587-129">Streaming API</span></span>](../defender-endpoint/raw-data-export.md)
- [<span data-ttu-id="73587-130">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="73587-130">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="73587-131">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="73587-131">Understand error codes</span></span>](api-error-codes.md)
