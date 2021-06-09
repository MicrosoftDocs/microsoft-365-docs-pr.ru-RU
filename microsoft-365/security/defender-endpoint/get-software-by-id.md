---
title: Получить программное обеспечение по ID
description: Извлекает список результатов воздействия по группе устройств.
keywords: apis, graph api, supported apis, get, software, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: d9a7d97cea96f919f1ec7cd1e37e7a8f27042c79
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845094"
---
# <a name="get-software-by-id"></a><span data-ttu-id="93871-104">Получить программное обеспечение по ID</span><span class="sxs-lookup"><span data-stu-id="93871-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="93871-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="93871-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="93871-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="93871-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="93871-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="93871-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="93871-108">Извлекает сведения о программном обеспечении по ID.</span><span class="sxs-lookup"><span data-stu-id="93871-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="93871-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="93871-109">Permissions</span></span>
<span data-ttu-id="93871-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="93871-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="93871-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="93871-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="93871-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="93871-112">Permission type</span></span> |   <span data-ttu-id="93871-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="93871-113">Permission</span></span>  |   <span data-ttu-id="93871-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="93871-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="93871-115">Для приложений</span><span class="sxs-lookup"><span data-stu-id="93871-115">Application</span></span> | <span data-ttu-id="93871-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="93871-116">Software.Read.All</span></span> | <span data-ttu-id="93871-117">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="93871-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="93871-118">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="93871-118">Delegated (work or school account)</span></span> | <span data-ttu-id="93871-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="93871-119">Software.Read</span></span> | <span data-ttu-id="93871-120">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="93871-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="93871-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="93871-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="93871-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="93871-122">Request headers</span></span>

| <span data-ttu-id="93871-123">Имя</span><span class="sxs-lookup"><span data-stu-id="93871-123">Name</span></span>        | <span data-ttu-id="93871-124">Тип</span><span class="sxs-lookup"><span data-stu-id="93871-124">Type</span></span> | <span data-ttu-id="93871-125">Описание</span><span class="sxs-lookup"><span data-stu-id="93871-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="93871-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="93871-126">Authorization</span></span> | <span data-ttu-id="93871-127">String</span><span class="sxs-lookup"><span data-stu-id="93871-127">String</span></span> | <span data-ttu-id="93871-128">Bearer {token}. **Обязательно**.</span><span class="sxs-lookup"><span data-stu-id="93871-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="93871-129">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="93871-129">Request body</span></span>
<span data-ttu-id="93871-130">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="93871-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="93871-131">Отклик</span><span class="sxs-lookup"><span data-stu-id="93871-131">Response</span></span>
<span data-ttu-id="93871-132">В случае успеха этот метод возвращает 200 ОК с указанными данными программного обеспечения в теле.</span><span class="sxs-lookup"><span data-stu-id="93871-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="93871-133">Пример</span><span class="sxs-lookup"><span data-stu-id="93871-133">Example</span></span>

<span data-ttu-id="93871-134">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="93871-134">**Request**</span></span>

<span data-ttu-id="93871-135">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="93871-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="93871-136">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="93871-136">**Response**</span></span>

<span data-ttu-id="93871-137">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="93871-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a><span data-ttu-id="93871-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="93871-138">Related topics</span></span>
- [<span data-ttu-id="93871-139">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="93871-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="93871-140">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="93871-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
