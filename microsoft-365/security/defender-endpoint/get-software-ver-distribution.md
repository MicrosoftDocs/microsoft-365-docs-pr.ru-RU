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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7ac7fdf4c38846e2e8be614567ddb87a98e3a96c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772129"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="1d29c-104">Список распространения версий программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="1d29c-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d29c-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1d29c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1d29c-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1d29c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d29c-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1d29c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1d29c-108">Извлекает список распространения программной версии вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1d29c-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="1d29c-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="1d29c-109">Permissions</span></span>
<span data-ttu-id="1d29c-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="1d29c-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1d29c-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1d29c-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="1d29c-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="1d29c-112">Permission type</span></span> |   <span data-ttu-id="1d29c-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="1d29c-113">Permission</span></span>  |   <span data-ttu-id="1d29c-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="1d29c-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1d29c-115">Приложение</span><span class="sxs-lookup"><span data-stu-id="1d29c-115">Application</span></span> | <span data-ttu-id="1d29c-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="1d29c-116">Software.Read.All</span></span> | <span data-ttu-id="1d29c-117">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="1d29c-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="1d29c-118">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="1d29c-118">Delegated (work or school account)</span></span> | <span data-ttu-id="1d29c-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="1d29c-119">Software.Read</span></span> | <span data-ttu-id="1d29c-120">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="1d29c-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1d29c-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="1d29c-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="1d29c-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="1d29c-122">Request headers</span></span>

| <span data-ttu-id="1d29c-123">Имя</span><span class="sxs-lookup"><span data-stu-id="1d29c-123">Name</span></span>        | <span data-ttu-id="1d29c-124">Тип</span><span class="sxs-lookup"><span data-stu-id="1d29c-124">Type</span></span> | <span data-ttu-id="1d29c-125">Описание</span><span class="sxs-lookup"><span data-stu-id="1d29c-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="1d29c-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="1d29c-126">Authorization</span></span> | <span data-ttu-id="1d29c-127">String</span><span class="sxs-lookup"><span data-stu-id="1d29c-127">String</span></span> | <span data-ttu-id="1d29c-128">Bearer {token}. **Обязательно**.</span><span class="sxs-lookup"><span data-stu-id="1d29c-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="1d29c-129">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="1d29c-129">Request body</span></span>
<span data-ttu-id="1d29c-130">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="1d29c-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1d29c-131">Отклик</span><span class="sxs-lookup"><span data-stu-id="1d29c-131">Response</span></span>
<span data-ttu-id="1d29c-132">В случае успеха этот метод возвращает 200 ОК со списком данных о распространениях программного обеспечения в теле.</span><span class="sxs-lookup"><span data-stu-id="1d29c-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="1d29c-133">Пример</span><span class="sxs-lookup"><span data-stu-id="1d29c-133">Example</span></span>

<span data-ttu-id="1d29c-134">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="1d29c-134">**Request**</span></span>

<span data-ttu-id="1d29c-135">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="1d29c-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="1d29c-136">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="1d29c-136">**Response**</span></span>

<span data-ttu-id="1d29c-137">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="1d29c-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="1d29c-138">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="1d29c-138">Related topics</span></span>
- [<span data-ttu-id="1d29c-139">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="1d29c-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1d29c-140">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="1d29c-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
