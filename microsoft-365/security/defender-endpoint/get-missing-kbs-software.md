---
title: Отсутствие KBs по программному ИД
description: Извлечение отсутствующих обновлений безопасности с помощью программного ИД
keywords: apis, api graph, supported apis, get, list, file, information, software id, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 25ac8ce2c9fb17b2576f86dae1da984865b19018
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933893"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="97dbb-104">Отсутствие KBs по программному ИД</span><span class="sxs-lookup"><span data-stu-id="97dbb-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="97dbb-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="97dbb-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="97dbb-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="97dbb-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="97dbb-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="97dbb-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="97dbb-108">Извлечение отсутствующих KBs (обновлений безопасности) по программному ID</span><span class="sxs-lookup"><span data-stu-id="97dbb-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="97dbb-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="97dbb-109">Permissions</span></span>

<span data-ttu-id="97dbb-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="97dbb-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="97dbb-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="97dbb-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="97dbb-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="97dbb-112">Permission type</span></span> |   <span data-ttu-id="97dbb-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="97dbb-113">Permission</span></span>   |   <span data-ttu-id="97dbb-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="97dbb-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="97dbb-115">Приложение</span><span class="sxs-lookup"><span data-stu-id="97dbb-115">Application</span></span> |<span data-ttu-id="97dbb-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="97dbb-116">Software.Read.All</span></span> |   <span data-ttu-id="97dbb-117">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="97dbb-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="97dbb-118">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="97dbb-118">Delegated (work or school account)</span></span> | <span data-ttu-id="97dbb-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="97dbb-119">Software.Read</span></span> |   <span data-ttu-id="97dbb-120">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="97dbb-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="97dbb-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="97dbb-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="97dbb-122">Заготвка запроса</span><span class="sxs-lookup"><span data-stu-id="97dbb-122">Request header</span></span>

<span data-ttu-id="97dbb-123">Имя</span><span class="sxs-lookup"><span data-stu-id="97dbb-123">Name</span></span> | <span data-ttu-id="97dbb-124">Тип</span><span class="sxs-lookup"><span data-stu-id="97dbb-124">Type</span></span> | <span data-ttu-id="97dbb-125">Описание</span><span class="sxs-lookup"><span data-stu-id="97dbb-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="97dbb-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="97dbb-126">Authorization</span></span> | <span data-ttu-id="97dbb-127">String</span><span class="sxs-lookup"><span data-stu-id="97dbb-127">String</span></span> | <span data-ttu-id="97dbb-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="97dbb-128">Bearer {token}.</span></span> <span data-ttu-id="97dbb-129">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="97dbb-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="97dbb-130">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="97dbb-130">Request body</span></span>

<span data-ttu-id="97dbb-131">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="97dbb-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="97dbb-132">Отклик</span><span class="sxs-lookup"><span data-stu-id="97dbb-132">Response</span></span>

<span data-ttu-id="97dbb-133">В случае успешного успеха этот метод возвращает 200 ОК, при этом указанное программное обеспечение не хватает данных кб в теле.</span><span class="sxs-lookup"><span data-stu-id="97dbb-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="97dbb-134">Пример</span><span class="sxs-lookup"><span data-stu-id="97dbb-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="97dbb-135">Запрос</span><span class="sxs-lookup"><span data-stu-id="97dbb-135">Request</span></span>

<span data-ttu-id="97dbb-136">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="97dbb-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="97dbb-137">Отклик</span><span class="sxs-lookup"><span data-stu-id="97dbb-137">Response</span></span>

<span data-ttu-id="97dbb-138">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="97dbb-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="97dbb-139">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="97dbb-139">Related topics</span></span>

- [<span data-ttu-id="97dbb-140">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="97dbb-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="97dbb-141">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="97dbb-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
