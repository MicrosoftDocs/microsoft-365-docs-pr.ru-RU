---
title: Список распространения версий программного обеспечения
description: Извлечение списка распространения программной версии вашей организации
keywords: apis, graph api, supported apis, get, software version distribution, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: e47a97477500491f634e3f5134a32241bd68985b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935297"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="b2afa-104">Список распространения версий программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b2afa-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b2afa-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b2afa-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b2afa-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b2afa-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b2afa-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b2afa-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b2afa-108">Извлекает список распространения программной версии вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b2afa-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="b2afa-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="b2afa-109">Permissions</span></span>
<span data-ttu-id="b2afa-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="b2afa-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b2afa-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b2afa-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="b2afa-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="b2afa-112">Permission type</span></span> |   <span data-ttu-id="b2afa-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="b2afa-113">Permission</span></span>  |   <span data-ttu-id="b2afa-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="b2afa-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b2afa-115">Приложение</span><span class="sxs-lookup"><span data-stu-id="b2afa-115">Application</span></span> | <span data-ttu-id="b2afa-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="b2afa-116">Software.Read.All</span></span> | <span data-ttu-id="b2afa-117">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="b2afa-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="b2afa-118">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="b2afa-118">Delegated (work or school account)</span></span> | <span data-ttu-id="b2afa-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="b2afa-119">Software.Read</span></span> | <span data-ttu-id="b2afa-120">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="b2afa-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b2afa-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="b2afa-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="b2afa-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="b2afa-122">Request headers</span></span>

| <span data-ttu-id="b2afa-123">Имя</span><span class="sxs-lookup"><span data-stu-id="b2afa-123">Name</span></span>        | <span data-ttu-id="b2afa-124">Тип</span><span class="sxs-lookup"><span data-stu-id="b2afa-124">Type</span></span> | <span data-ttu-id="b2afa-125">Описание</span><span class="sxs-lookup"><span data-stu-id="b2afa-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="b2afa-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="b2afa-126">Authorization</span></span> | <span data-ttu-id="b2afa-127">String</span><span class="sxs-lookup"><span data-stu-id="b2afa-127">String</span></span> | <span data-ttu-id="b2afa-128">Bearer {token}. **Обязательно**.</span><span class="sxs-lookup"><span data-stu-id="b2afa-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b2afa-129">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="b2afa-129">Request body</span></span>
<span data-ttu-id="b2afa-130">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="b2afa-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b2afa-131">Отклик</span><span class="sxs-lookup"><span data-stu-id="b2afa-131">Response</span></span>
<span data-ttu-id="b2afa-132">В случае успеха этот метод возвращает 200 ОК со списком данных о распространениях программного обеспечения в теле.</span><span class="sxs-lookup"><span data-stu-id="b2afa-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="b2afa-133">Пример</span><span class="sxs-lookup"><span data-stu-id="b2afa-133">Example</span></span>

<span data-ttu-id="b2afa-134">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="b2afa-134">**Request**</span></span>

<span data-ttu-id="b2afa-135">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="b2afa-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="b2afa-136">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="b2afa-136">**Response**</span></span>

<span data-ttu-id="b2afa-137">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="b2afa-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="b2afa-138">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="b2afa-138">Related topics</span></span>
- [<span data-ttu-id="b2afa-139">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="b2afa-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b2afa-140">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="b2afa-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
