---
title: Получить программное обеспечение по ИД
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
ms.openlocfilehash: 31203e83570dbeb2404c9f1578301b5d6c18223c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934313"
---
# <a name="get-software-by-id"></a><span data-ttu-id="41fa3-104">Получить программное обеспечение по ИД</span><span class="sxs-lookup"><span data-stu-id="41fa3-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41fa3-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="41fa3-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="41fa3-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="41fa3-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="41fa3-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="41fa3-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="41fa3-108">Извлекает сведения о программном обеспечении по ID.</span><span class="sxs-lookup"><span data-stu-id="41fa3-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="41fa3-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="41fa3-109">Permissions</span></span>
<span data-ttu-id="41fa3-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="41fa3-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="41fa3-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="41fa3-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="41fa3-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="41fa3-112">Permission type</span></span> |   <span data-ttu-id="41fa3-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="41fa3-113">Permission</span></span>  |   <span data-ttu-id="41fa3-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="41fa3-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="41fa3-115">Приложение</span><span class="sxs-lookup"><span data-stu-id="41fa3-115">Application</span></span> | <span data-ttu-id="41fa3-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="41fa3-116">Software.Read.All</span></span> | <span data-ttu-id="41fa3-117">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="41fa3-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="41fa3-118">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="41fa3-118">Delegated (work or school account)</span></span> | <span data-ttu-id="41fa3-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="41fa3-119">Software.Read</span></span> | <span data-ttu-id="41fa3-120">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="41fa3-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="41fa3-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="41fa3-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="41fa3-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="41fa3-122">Request headers</span></span>

| <span data-ttu-id="41fa3-123">Имя</span><span class="sxs-lookup"><span data-stu-id="41fa3-123">Name</span></span>        | <span data-ttu-id="41fa3-124">Тип</span><span class="sxs-lookup"><span data-stu-id="41fa3-124">Type</span></span> | <span data-ttu-id="41fa3-125">Описание</span><span class="sxs-lookup"><span data-stu-id="41fa3-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="41fa3-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="41fa3-126">Authorization</span></span> | <span data-ttu-id="41fa3-127">String</span><span class="sxs-lookup"><span data-stu-id="41fa3-127">String</span></span> | <span data-ttu-id="41fa3-128">Bearer {token}. **Обязательно**.</span><span class="sxs-lookup"><span data-stu-id="41fa3-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="41fa3-129">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="41fa3-129">Request body</span></span>
<span data-ttu-id="41fa3-130">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="41fa3-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="41fa3-131">Отклик</span><span class="sxs-lookup"><span data-stu-id="41fa3-131">Response</span></span>
<span data-ttu-id="41fa3-132">В случае успеха этот метод возвращает 200 ОК с указанными данными программного обеспечения в теле.</span><span class="sxs-lookup"><span data-stu-id="41fa3-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="41fa3-133">Пример</span><span class="sxs-lookup"><span data-stu-id="41fa3-133">Example</span></span>

<span data-ttu-id="41fa3-134">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="41fa3-134">**Request**</span></span>

<span data-ttu-id="41fa3-135">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="41fa3-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="41fa3-136">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="41fa3-136">**Response**</span></span>

<span data-ttu-id="41fa3-137">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="41fa3-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="41fa3-138">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="41fa3-138">Related topics</span></span>
- [<span data-ttu-id="41fa3-139">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="41fa3-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="41fa3-140">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="41fa3-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
