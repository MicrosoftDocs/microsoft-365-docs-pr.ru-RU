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
ms.openlocfilehash: f2c66dca326589807f5712c5548c177a0d08ade0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935729"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="fba88-104">Поддерживаемые API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fba88-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="fba88-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="fba88-105">**Applies to:**</span></span>
- <span data-ttu-id="fba88-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fba88-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fba88-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="fba88-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="fba88-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="fba88-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="fba88-109">Список доступных API</span><span class="sxs-lookup"><span data-stu-id="fba88-109">List of available APIs</span></span>

<span data-ttu-id="fba88-110">Статья</span><span class="sxs-lookup"><span data-stu-id="fba88-110">Article</span></span> | <span data-ttu-id="fba88-111">Описание</span><span class="sxs-lookup"><span data-stu-id="fba88-111">Description</span></span>
-|-
[<span data-ttu-id="fba88-112">Программный интерфейс расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="fba88-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="fba88-113">Запустите расширенные запросы на охоту.</span><span class="sxs-lookup"><span data-stu-id="fba88-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="fba88-114">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="fba88-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="fba88-115">Список и обновление инцидентов, а также другие практические задачи.</span><span class="sxs-lookup"><span data-stu-id="fba88-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="fba88-116">URL-адреса конечной точки</span><span class="sxs-lookup"><span data-stu-id="fba88-116">Endpoint URIs</span></span>

<span data-ttu-id="fba88-117">Базовый URI для обоих основных API: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="fba88-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="fba88-118">Чтобы улучшить производительность, используйте сервер ближе к геолокации:</span><span class="sxs-lookup"><span data-stu-id="fba88-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="fba88-119">США: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fba88-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="fba88-120">Европа: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fba88-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="fba88-121">Великобритания: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fba88-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="fba88-122">Маркеры можно приобрести путем доступа https://api.security.microsoft.com к .</span><span class="sxs-lookup"><span data-stu-id="fba88-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="fba88-123">Все API на `/api` пути используют [протокол OData;](/odata/overview) https://api.security.microsoft.com/api/incidents например.</span><span class="sxs-lookup"><span data-stu-id="fba88-123">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fba88-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fba88-124">Related articles</span></span>

- [<span data-ttu-id="fba88-125">Обзор API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fba88-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="fba88-126">Доступ к API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fba88-126">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="fba88-127">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="fba88-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="fba88-128">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="fba88-128">Understand error codes</span></span>](api-error-codes.md)