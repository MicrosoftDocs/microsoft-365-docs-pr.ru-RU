---
title: Получить API коллекции KB
description: Извлечение сведений из коллекции баз знаний (KB) и KB с помощью Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167179"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="307d0-104">Получить API коллекции KB</span><span class="sxs-lookup"><span data-stu-id="307d0-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="307d0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="307d0-105">**Applies to:**</span></span>
- [<span data-ttu-id="307d0-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="307d0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="307d0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="307d0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="307d0-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="307d0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="307d0-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="307d0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="307d0-110">Извлекает коллекцию сведений о КБ и КБ.</span><span class="sxs-lookup"><span data-stu-id="307d0-110">Retrieves a collection of KB's and KB details.</span></span>

## <a name="permissions"></a><span data-ttu-id="307d0-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="307d0-111">Permissions</span></span>
<span data-ttu-id="307d0-112">Пользователю нужны разрешения на чтение.</span><span class="sxs-lookup"><span data-stu-id="307d0-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="307d0-113">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="307d0-113">HTTP request</span></span>
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a><span data-ttu-id="307d0-114">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="307d0-114">Request headers</span></span>

<span data-ttu-id="307d0-115">Заголовок</span><span class="sxs-lookup"><span data-stu-id="307d0-115">Header</span></span> | <span data-ttu-id="307d0-116">Значение</span><span class="sxs-lookup"><span data-stu-id="307d0-116">Value</span></span> 
:---|:---
<span data-ttu-id="307d0-117">Авторизация</span><span class="sxs-lookup"><span data-stu-id="307d0-117">Authorization</span></span> | <span data-ttu-id="307d0-118">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="307d0-118">Bearer {token}.</span></span> <span data-ttu-id="307d0-119">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="307d0-119">**Required**.</span></span>
<span data-ttu-id="307d0-120">Тип содержимого</span><span class="sxs-lookup"><span data-stu-id="307d0-120">Content type</span></span> | <span data-ttu-id="307d0-121">application/json</span><span class="sxs-lookup"><span data-stu-id="307d0-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="307d0-122">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="307d0-122">Request body</span></span>
<span data-ttu-id="307d0-123">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="307d0-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="307d0-124">Отклик</span><span class="sxs-lookup"><span data-stu-id="307d0-124">Response</span></span>
<span data-ttu-id="307d0-125">Если успешно - 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="307d0-125">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="307d0-126">Пример</span><span class="sxs-lookup"><span data-stu-id="307d0-126">Example</span></span>

<span data-ttu-id="307d0-127">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="307d0-127">**Request**</span></span>

<span data-ttu-id="307d0-128">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="307d0-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

<span data-ttu-id="307d0-129">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="307d0-129">**Response**</span></span>

<span data-ttu-id="307d0-130">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="307d0-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
