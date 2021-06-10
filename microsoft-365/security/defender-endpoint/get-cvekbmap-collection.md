---
title: Получить API карты CVE-KB
description: Узнайте, как использовать API карты Get CVE-KB для получения карты CVE в сведениях KB и CVE в Microsoft Defender for Endpoint.
keywords: apis, api graph, supported apis, get, cve, kb
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
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166891"
---
# <a name="get-cve-kb-map-api"></a><span data-ttu-id="f6cab-104">Получить API карты CVE-KB</span><span class="sxs-lookup"><span data-stu-id="f6cab-104">Get CVE-KB map API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f6cab-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f6cab-105">**Applies to:**</span></span>
- [<span data-ttu-id="f6cab-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f6cab-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f6cab-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6cab-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f6cab-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f6cab-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f6cab-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f6cab-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f6cab-110">Извлекает карту CVE в сведения kB и CVE.</span><span class="sxs-lookup"><span data-stu-id="f6cab-110">Retrieves a map of CVE's to KB's and CVE details.</span></span>

## <a name="permissions"></a><span data-ttu-id="f6cab-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="f6cab-111">Permissions</span></span>
<span data-ttu-id="f6cab-112">Пользователю нужны разрешения на чтение.</span><span class="sxs-lookup"><span data-stu-id="f6cab-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="f6cab-113">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="f6cab-113">HTTP request</span></span>
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a><span data-ttu-id="f6cab-114">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="f6cab-114">Request headers</span></span>

<span data-ttu-id="f6cab-115">Заголовок</span><span class="sxs-lookup"><span data-stu-id="f6cab-115">Header</span></span> | <span data-ttu-id="f6cab-116">Значение</span><span class="sxs-lookup"><span data-stu-id="f6cab-116">Value</span></span> 
:---|:---
<span data-ttu-id="f6cab-117">Авторизация</span><span class="sxs-lookup"><span data-stu-id="f6cab-117">Authorization</span></span> | <span data-ttu-id="f6cab-118">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f6cab-118">Bearer {token}.</span></span> <span data-ttu-id="f6cab-119">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="f6cab-119">**Required**.</span></span>
<span data-ttu-id="f6cab-120">Тип содержимого</span><span class="sxs-lookup"><span data-stu-id="f6cab-120">Content type</span></span> | <span data-ttu-id="f6cab-121">application/json</span><span class="sxs-lookup"><span data-stu-id="f6cab-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="f6cab-122">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="f6cab-122">Request body</span></span>
<span data-ttu-id="f6cab-123">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="f6cab-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f6cab-124">Отклик</span><span class="sxs-lookup"><span data-stu-id="f6cab-124">Response</span></span>
<span data-ttu-id="f6cab-125">Если успешно и карта существует - 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="f6cab-125">If successful and map exists - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="f6cab-126">Пример</span><span class="sxs-lookup"><span data-stu-id="f6cab-126">Example</span></span>

<span data-ttu-id="f6cab-127">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="f6cab-127">**Request**</span></span>

<span data-ttu-id="f6cab-128">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="f6cab-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

<span data-ttu-id="f6cab-129">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="f6cab-129">**Response**</span></span>

<span data-ttu-id="f6cab-130">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="f6cab-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
