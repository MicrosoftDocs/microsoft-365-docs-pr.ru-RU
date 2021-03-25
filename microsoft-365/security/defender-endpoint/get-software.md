---
title: Список программного обеспечения
description: Извлечение списка инвентаризации программного обеспечения
keywords: apis, api graph, supported apis, get, list, file, information, software inventory, threat & vulnerability management api, mdatp tvm api
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
ms.openlocfilehash: 867fb57f61bd98b7c0afabd20b27e68d6bf45ef7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198569"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="73a24-104">Список API инвентаризации программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="73a24-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="73a24-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="73a24-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="73a24-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="73a24-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="73a24-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="73a24-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="73a24-108">Извлекает инвентаризацию программного обеспечения организации.</span><span class="sxs-lookup"><span data-stu-id="73a24-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="73a24-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="73a24-109">Permissions</span></span>
<span data-ttu-id="73a24-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="73a24-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="73a24-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="73a24-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="73a24-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="73a24-112">Permission type</span></span> |   <span data-ttu-id="73a24-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="73a24-113">Permission</span></span>  |   <span data-ttu-id="73a24-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="73a24-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="73a24-115">Application</span><span class="sxs-lookup"><span data-stu-id="73a24-115">Application</span></span> |<span data-ttu-id="73a24-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="73a24-116">Software.Read.All</span></span> |    <span data-ttu-id="73a24-117">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="73a24-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="73a24-118">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="73a24-118">Delegated (work or school account)</span></span> | <span data-ttu-id="73a24-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="73a24-119">Software.Read</span></span> |    <span data-ttu-id="73a24-120">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="73a24-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="73a24-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="73a24-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="73a24-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="73a24-122">Request headers</span></span>

<span data-ttu-id="73a24-123">Имя</span><span class="sxs-lookup"><span data-stu-id="73a24-123">Name</span></span> | <span data-ttu-id="73a24-124">Тип</span><span class="sxs-lookup"><span data-stu-id="73a24-124">Type</span></span> | <span data-ttu-id="73a24-125">Описание</span><span class="sxs-lookup"><span data-stu-id="73a24-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="73a24-126">Авторизация</span><span class="sxs-lookup"><span data-stu-id="73a24-126">Authorization</span></span> | <span data-ttu-id="73a24-127">Строка</span><span class="sxs-lookup"><span data-stu-id="73a24-127">String</span></span> | <span data-ttu-id="73a24-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="73a24-128">Bearer {token}.</span></span> <span data-ttu-id="73a24-129">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="73a24-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="73a24-130">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="73a24-130">Request body</span></span>
<span data-ttu-id="73a24-131">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="73a24-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="73a24-132">Отклик</span><span class="sxs-lookup"><span data-stu-id="73a24-132">Response</span></span>
<span data-ttu-id="73a24-133">В случае успешного с помощью инвентаризации программного обеспечения в теле этот метод возвращает 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="73a24-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="73a24-134">Пример</span><span class="sxs-lookup"><span data-stu-id="73a24-134">Example</span></span>

<span data-ttu-id="73a24-135">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="73a24-135">**Request**</span></span>

<span data-ttu-id="73a24-136">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="73a24-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="73a24-137">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="73a24-137">**Response**</span></span>

<span data-ttu-id="73a24-138">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="73a24-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="73a24-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="73a24-139">Related topics</span></span>
- [<span data-ttu-id="73a24-140">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="73a24-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="73a24-141">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="73a24-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)