---
title: Поддерживаемые API-интерфейсы защитника Microsoft 365
description: Поддерживаемые API-интерфейсы защитника Microsoft 365
keywords: MTP, API, API
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
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844964"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="acfc7-104">Поддерживаемые API-интерфейсы защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="acfc7-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="acfc7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="acfc7-105">**Applies to:**</span></span>
- <span data-ttu-id="acfc7-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="acfc7-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="acfc7-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="acfc7-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="acfc7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="acfc7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="acfc7-109">URI конечных точек:</span><span class="sxs-lookup"><span data-stu-id="acfc7-109">End Point URIs:</span></span>

- <span data-ttu-id="acfc7-110">Базовый URI службы: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="acfc7-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="acfc7-111">Для повышения производительности можно использовать сервер ближе к географическому расположению:</span><span class="sxs-lookup"><span data-stu-id="acfc7-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="acfc7-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="acfc7-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="acfc7-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="acfc7-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="acfc7-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="acfc7-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="acfc7-115">Ресурс для получения маркера должен быть следующим: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="acfc7-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="acfc7-116">Все API в ```/api``` пути являются API OData.</span><span class="sxs-lookup"><span data-stu-id="acfc7-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="acfc7-117">т. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="acfc7-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="acfc7-118">Список доступных API:</span><span class="sxs-lookup"><span data-stu-id="acfc7-118">List of available APIs:</span></span>

<span data-ttu-id="acfc7-119">Статья</span><span class="sxs-lookup"><span data-stu-id="acfc7-119">Topic</span></span> | <span data-ttu-id="acfc7-120">Описание</span><span class="sxs-lookup"><span data-stu-id="acfc7-120">Description</span></span>
:---|:---
[<span data-ttu-id="acfc7-121">Программный интерфейс расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="acfc7-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="acfc7-122">Выполнение расширенных запросов на поиск с API.</span><span class="sxs-lookup"><span data-stu-id="acfc7-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="acfc7-123">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="acfc7-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="acfc7-124">Запускать вызовы API, связанные с инцидентами, такие как: Список инцидентов, обновление инцидента и многое другое.</span><span class="sxs-lookup"><span data-stu-id="acfc7-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
