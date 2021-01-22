---
title: Поддерживаемые API Microsoft 365 Defender
description: Поддерживаемые API Microsoft 365 Defender
keywords: MTP, API, api
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926202"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="01cb1-104">Поддерживаемые API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01cb1-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="01cb1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="01cb1-105">**Applies to:**</span></span>
- <span data-ttu-id="01cb1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01cb1-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01cb1-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="01cb1-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="01cb1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="01cb1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="01cb1-109">Список доступных API</span><span class="sxs-lookup"><span data-stu-id="01cb1-109">List of available APIs</span></span>

<span data-ttu-id="01cb1-110">Статья</span><span class="sxs-lookup"><span data-stu-id="01cb1-110">Article</span></span> | <span data-ttu-id="01cb1-111">Описание</span><span class="sxs-lookup"><span data-stu-id="01cb1-111">Description</span></span>
-|-
[<span data-ttu-id="01cb1-112">Программный интерфейс расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="01cb1-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="01cb1-113">Выполнение запросов "Расширенный поиск".</span><span class="sxs-lookup"><span data-stu-id="01cb1-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="01cb1-114">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="01cb1-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="01cb1-115">Список и обновление инцидентов, а также другие практические задачи.</span><span class="sxs-lookup"><span data-stu-id="01cb1-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="01cb1-116">IS конечных точек</span><span class="sxs-lookup"><span data-stu-id="01cb1-116">Endpoint URIs</span></span>

<span data-ttu-id="01cb1-117">Базовый URI для обоих основных API: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="01cb1-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="01cb1-118">Для улучшения производительности используйте сервер, ближе к географическому местонахождению:</span><span class="sxs-lookup"><span data-stu-id="01cb1-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="01cb1-119">США: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="01cb1-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="01cb1-120">Европа: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="01cb1-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="01cb1-121">Соединенное Королевство: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="01cb1-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="01cb1-122">Маркеры можно получить с помощью https://api.security.microsoft.com доступа.</span><span class="sxs-lookup"><span data-stu-id="01cb1-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="01cb1-123">Все API на пути используют протокол `/api` [OData,](https://docs.microsoft.com/odata/overview) например https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="01cb1-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="01cb1-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="01cb1-124">Related articles</span></span>

- [<span data-ttu-id="01cb1-125">Обзор API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01cb1-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="01cb1-126">Доступ к API Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="01cb1-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="01cb1-127">Узнайте об ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="01cb1-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="01cb1-128">Коды ошибок</span><span class="sxs-lookup"><span data-stu-id="01cb1-128">Understand error codes</span></span>](api-error-codes.md)
