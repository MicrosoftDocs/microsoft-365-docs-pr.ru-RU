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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b2239b960106d756cbd29504af05af77a553067d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068974"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="fbb4d-104">Поддерживаемые API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbb4d-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="fbb4d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="fbb4d-105">**Applies to:**</span></span>
- <span data-ttu-id="fbb4d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbb4d-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fbb4d-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="fbb4d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="fbb4d-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="fbb4d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="fbb4d-109">Список доступных API</span><span class="sxs-lookup"><span data-stu-id="fbb4d-109">List of available APIs</span></span>

<span data-ttu-id="fbb4d-110">Статья</span><span class="sxs-lookup"><span data-stu-id="fbb4d-110">Article</span></span> | <span data-ttu-id="fbb4d-111">Описание</span><span class="sxs-lookup"><span data-stu-id="fbb4d-111">Description</span></span>
-|-
[<span data-ttu-id="fbb4d-112">Программный интерфейс расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="fbb4d-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="fbb4d-113">Запустите расширенные запросы на охоту.</span><span class="sxs-lookup"><span data-stu-id="fbb4d-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="fbb4d-114">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="fbb4d-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="fbb4d-115">Список и обновление инцидентов, а также другие практические задачи.</span><span class="sxs-lookup"><span data-stu-id="fbb4d-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="fbb4d-116">URL-адреса конечной точки</span><span class="sxs-lookup"><span data-stu-id="fbb4d-116">Endpoint URIs</span></span>

<span data-ttu-id="fbb4d-117">Базовый URI для обоих основных API: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="fbb4d-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="fbb4d-118">Чтобы улучшить производительность, используйте сервер ближе к геолокации:</span><span class="sxs-lookup"><span data-stu-id="fbb4d-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="fbb4d-119">США: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fbb4d-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="fbb4d-120">Европа: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fbb4d-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="fbb4d-121">Великобритания: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fbb4d-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="fbb4d-122">Маркеры можно приобрести путем доступа https://api.security.microsoft.com к .</span><span class="sxs-lookup"><span data-stu-id="fbb4d-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="fbb4d-123">Все API на `/api` пути используют [протокол OData;](/odata/overview) https://api.security.microsoft.com/api/incidents например.</span><span class="sxs-lookup"><span data-stu-id="fbb4d-123">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fbb4d-124">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="fbb4d-124">Related articles</span></span>

- [<span data-ttu-id="fbb4d-125">Обзор API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fbb4d-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="fbb4d-126">Доступ к API microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fbb4d-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="fbb4d-127">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="fbb4d-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="fbb4d-128">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="fbb4d-128">Understand error codes</span></span>](api-error-codes.md)