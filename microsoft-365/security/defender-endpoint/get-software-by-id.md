---
title: Получить программное обеспечение по ID
description: Извлекает список результатов воздействия по группе устройств.
keywords: apis, graph api, supported apis, get, software, mdatp tvm api
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
ms.openlocfilehash: 57d6ccd2c5387d478b75cfb6fb32a5b1052e491c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198593"
---
# <a name="get-software-by-id"></a><span data-ttu-id="8322e-104">Получить программное обеспечение по ID</span><span class="sxs-lookup"><span data-stu-id="8322e-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8322e-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="8322e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="8322e-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8322e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8322e-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8322e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8322e-108">Извлекает сведения о программном обеспечении по ID.</span><span class="sxs-lookup"><span data-stu-id="8322e-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="8322e-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="8322e-109">Permissions</span></span>
<span data-ttu-id="8322e-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="8322e-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8322e-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8322e-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="8322e-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="8322e-112">Permission type</span></span> |   <span data-ttu-id="8322e-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="8322e-113">Permission</span></span>  |   <span data-ttu-id="8322e-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="8322e-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8322e-115">Application</span><span class="sxs-lookup"><span data-stu-id="8322e-115">Application</span></span> | <span data-ttu-id="8322e-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="8322e-116">Software.Read.All</span></span> | <span data-ttu-id="8322e-117">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="8322e-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="8322e-118">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="8322e-118">Delegated (work or school account)</span></span> | <span data-ttu-id="8322e-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="8322e-119">Software.Read</span></span> | <span data-ttu-id="8322e-120">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="8322e-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="8322e-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="8322e-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="8322e-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="8322e-122">Request headers</span></span>

| <span data-ttu-id="8322e-123">Имя</span><span class="sxs-lookup"><span data-stu-id="8322e-123">Name</span></span>        | <span data-ttu-id="8322e-124">Тип</span><span class="sxs-lookup"><span data-stu-id="8322e-124">Type</span></span> | <span data-ttu-id="8322e-125">Описание</span><span class="sxs-lookup"><span data-stu-id="8322e-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="8322e-126">Авторизация</span><span class="sxs-lookup"><span data-stu-id="8322e-126">Authorization</span></span> | <span data-ttu-id="8322e-127">Строка</span><span class="sxs-lookup"><span data-stu-id="8322e-127">String</span></span> | <span data-ttu-id="8322e-128">Bearer {token}. **Обязательно**.</span><span class="sxs-lookup"><span data-stu-id="8322e-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8322e-129">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="8322e-129">Request body</span></span>
<span data-ttu-id="8322e-130">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="8322e-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8322e-131">Отклик</span><span class="sxs-lookup"><span data-stu-id="8322e-131">Response</span></span>
<span data-ttu-id="8322e-132">В случае успеха этот метод возвращает 200 ОК с указанными данными программного обеспечения в теле.</span><span class="sxs-lookup"><span data-stu-id="8322e-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="8322e-133">Пример</span><span class="sxs-lookup"><span data-stu-id="8322e-133">Example</span></span>

<span data-ttu-id="8322e-134">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="8322e-134">**Request**</span></span>

<span data-ttu-id="8322e-135">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="8322e-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="8322e-136">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="8322e-136">**Response**</span></span>

<span data-ttu-id="8322e-137">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="8322e-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="8322e-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8322e-138">Related topics</span></span>
- [<span data-ttu-id="8322e-139">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="8322e-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="8322e-140">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="8322e-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
