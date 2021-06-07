---
title: Список программного обеспечения
description: Извлечение списка инвентаризации программного обеспечения
keywords: apis, graph api, supported apis, get, list, file, information, software inventory, threat & управление уязвимостями api, Microsoft Defender for Endpoint tvm api
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f7e71c58396fd4b3ed40ba88aab5c2757ae41a41
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771085"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="44b45-104">Список API инвентаризации программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="44b45-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="44b45-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="44b45-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="44b45-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="44b45-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="44b45-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="44b45-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="44b45-108">Извлекает инвентаризацию программного обеспечения организации.</span><span class="sxs-lookup"><span data-stu-id="44b45-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="44b45-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="44b45-109">Permissions</span></span>
<span data-ttu-id="44b45-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="44b45-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="44b45-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="44b45-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="44b45-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="44b45-112">Permission type</span></span> |   <span data-ttu-id="44b45-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="44b45-113">Permission</span></span>  |   <span data-ttu-id="44b45-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="44b45-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="44b45-115">Приложение</span><span class="sxs-lookup"><span data-stu-id="44b45-115">Application</span></span> |<span data-ttu-id="44b45-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="44b45-116">Software.Read.All</span></span> |    <span data-ttu-id="44b45-117">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="44b45-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="44b45-118">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="44b45-118">Delegated (work or school account)</span></span> | <span data-ttu-id="44b45-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="44b45-119">Software.Read</span></span> |    <span data-ttu-id="44b45-120">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="44b45-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="44b45-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="44b45-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="44b45-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="44b45-122">Request headers</span></span>

<span data-ttu-id="44b45-123">Имя</span><span class="sxs-lookup"><span data-stu-id="44b45-123">Name</span></span> | <span data-ttu-id="44b45-124">Тип</span><span class="sxs-lookup"><span data-stu-id="44b45-124">Type</span></span> | <span data-ttu-id="44b45-125">Описание</span><span class="sxs-lookup"><span data-stu-id="44b45-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="44b45-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="44b45-126">Authorization</span></span> | <span data-ttu-id="44b45-127">String</span><span class="sxs-lookup"><span data-stu-id="44b45-127">String</span></span> | <span data-ttu-id="44b45-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="44b45-128">Bearer {token}.</span></span> <span data-ttu-id="44b45-129">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="44b45-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="44b45-130">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="44b45-130">Request body</span></span>
<span data-ttu-id="44b45-131">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="44b45-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="44b45-132">Отклик</span><span class="sxs-lookup"><span data-stu-id="44b45-132">Response</span></span>
<span data-ttu-id="44b45-133">В случае успешного с помощью инвентаризации программного обеспечения в теле этот метод возвращает 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="44b45-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="44b45-134">Пример</span><span class="sxs-lookup"><span data-stu-id="44b45-134">Example</span></span>

<span data-ttu-id="44b45-135">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="44b45-135">**Request**</span></span>

<span data-ttu-id="44b45-136">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="44b45-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="44b45-137">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="44b45-137">**Response**</span></span>

<span data-ttu-id="44b45-138">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="44b45-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="44b45-139">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="44b45-139">Related topics</span></span>
- [<span data-ttu-id="44b45-140">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="44b45-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="44b45-141">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="44b45-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
