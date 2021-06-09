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
ms.openlocfilehash: 2b7375f04094cdb56b0801adf2c1c0b7a8ab3098
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844278"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="93faf-104">Список API инвентаризации программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="93faf-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="93faf-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="93faf-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="93faf-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="93faf-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="93faf-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="93faf-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="93faf-108">Извлекает инвентаризацию программного обеспечения организации.</span><span class="sxs-lookup"><span data-stu-id="93faf-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="93faf-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="93faf-109">Permissions</span></span>
<span data-ttu-id="93faf-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="93faf-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="93faf-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="93faf-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="93faf-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="93faf-112">Permission type</span></span> |   <span data-ttu-id="93faf-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="93faf-113">Permission</span></span>  |   <span data-ttu-id="93faf-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="93faf-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="93faf-115">Для приложений</span><span class="sxs-lookup"><span data-stu-id="93faf-115">Application</span></span> |<span data-ttu-id="93faf-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="93faf-116">Software.Read.All</span></span> |    <span data-ttu-id="93faf-117">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="93faf-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="93faf-118">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="93faf-118">Delegated (work or school account)</span></span> | <span data-ttu-id="93faf-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="93faf-119">Software.Read</span></span> |    <span data-ttu-id="93faf-120">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="93faf-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="93faf-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="93faf-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="93faf-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="93faf-122">Request headers</span></span>

<span data-ttu-id="93faf-123">Имя</span><span class="sxs-lookup"><span data-stu-id="93faf-123">Name</span></span> | <span data-ttu-id="93faf-124">Тип</span><span class="sxs-lookup"><span data-stu-id="93faf-124">Type</span></span> | <span data-ttu-id="93faf-125">Описание</span><span class="sxs-lookup"><span data-stu-id="93faf-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="93faf-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="93faf-126">Authorization</span></span> | <span data-ttu-id="93faf-127">String</span><span class="sxs-lookup"><span data-stu-id="93faf-127">String</span></span> | <span data-ttu-id="93faf-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="93faf-128">Bearer {token}.</span></span> <span data-ttu-id="93faf-129">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="93faf-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="93faf-130">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="93faf-130">Request body</span></span>
<span data-ttu-id="93faf-131">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="93faf-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="93faf-132">Отклик</span><span class="sxs-lookup"><span data-stu-id="93faf-132">Response</span></span>
<span data-ttu-id="93faf-133">В случае успешного с помощью инвентаризации программного обеспечения в теле этот метод возвращает 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="93faf-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="93faf-134">Пример</span><span class="sxs-lookup"><span data-stu-id="93faf-134">Example</span></span>

<span data-ttu-id="93faf-135">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="93faf-135">**Request**</span></span>

<span data-ttu-id="93faf-136">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="93faf-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="93faf-137">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="93faf-137">**Response**</span></span>

<span data-ttu-id="93faf-138">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="93faf-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="93faf-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="93faf-139">Related topics</span></span>
- [<span data-ttu-id="93faf-140">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="93faf-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="93faf-141">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="93faf-141">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
