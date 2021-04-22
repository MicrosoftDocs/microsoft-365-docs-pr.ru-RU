---
title: Список программного обеспечения
description: Извлечение списка инвентаризации программного обеспечения
keywords: apis, api graph, supported apis, get, list, file, information, software inventory, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 6522b546dfde7447a03b3c417be93d288e261908
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934013"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="8a299-104">Список API инвентаризации программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="8a299-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8a299-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="8a299-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="8a299-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8a299-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8a299-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8a299-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="8a299-108">Извлекает инвентаризацию программного обеспечения организации.</span><span class="sxs-lookup"><span data-stu-id="8a299-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="8a299-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="8a299-109">Permissions</span></span>
<span data-ttu-id="8a299-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="8a299-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8a299-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8a299-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="8a299-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="8a299-112">Permission type</span></span> |   <span data-ttu-id="8a299-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="8a299-113">Permission</span></span>  |   <span data-ttu-id="8a299-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="8a299-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8a299-115">Приложение</span><span class="sxs-lookup"><span data-stu-id="8a299-115">Application</span></span> |<span data-ttu-id="8a299-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="8a299-116">Software.Read.All</span></span> |    <span data-ttu-id="8a299-117">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="8a299-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="8a299-118">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="8a299-118">Delegated (work or school account)</span></span> | <span data-ttu-id="8a299-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="8a299-119">Software.Read</span></span> |    <span data-ttu-id="8a299-120">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="8a299-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="8a299-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="8a299-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="8a299-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="8a299-122">Request headers</span></span>

<span data-ttu-id="8a299-123">Имя</span><span class="sxs-lookup"><span data-stu-id="8a299-123">Name</span></span> | <span data-ttu-id="8a299-124">Тип</span><span class="sxs-lookup"><span data-stu-id="8a299-124">Type</span></span> | <span data-ttu-id="8a299-125">Описание</span><span class="sxs-lookup"><span data-stu-id="8a299-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="8a299-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="8a299-126">Authorization</span></span> | <span data-ttu-id="8a299-127">String</span><span class="sxs-lookup"><span data-stu-id="8a299-127">String</span></span> | <span data-ttu-id="8a299-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8a299-128">Bearer {token}.</span></span> <span data-ttu-id="8a299-129">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="8a299-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8a299-130">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="8a299-130">Request body</span></span>
<span data-ttu-id="8a299-131">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="8a299-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8a299-132">Отклик</span><span class="sxs-lookup"><span data-stu-id="8a299-132">Response</span></span>
<span data-ttu-id="8a299-133">В случае успешного с помощью инвентаризации программного обеспечения в теле этот метод возвращает 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="8a299-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="8a299-134">Пример</span><span class="sxs-lookup"><span data-stu-id="8a299-134">Example</span></span>

<span data-ttu-id="8a299-135">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="8a299-135">**Request**</span></span>

<span data-ttu-id="8a299-136">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="8a299-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="8a299-137">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="8a299-137">**Response**</span></span>

<span data-ttu-id="8a299-138">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="8a299-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="8a299-139">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="8a299-139">Related topics</span></span>
- [<span data-ttu-id="8a299-140">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="8a299-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="8a299-141">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="8a299-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
