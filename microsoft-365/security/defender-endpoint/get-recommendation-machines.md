---
title: Список устройств по рекомендации
description: Извлекает список устройств, связанных с рекомендацией по безопасности.
keywords: apis, graph api, supported apis, get, security recommendation for vulnerable devices, контроль угроз и уязвимостей, контроль угроз и уязвимостей api
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
ms.openlocfilehash: 6c762a15051444ec950e92998317db4f7e51783c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771817"
---
# <a name="list-devices-by-recommendation"></a><span data-ttu-id="aae43-104">Список устройств по рекомендации</span><span class="sxs-lookup"><span data-stu-id="aae43-104">List devices by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aae43-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="aae43-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="aae43-106">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="aae43-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aae43-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="aae43-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="aae43-108">Извлекает список устройств, связанных с рекомендацией по безопасности.</span><span class="sxs-lookup"><span data-stu-id="aae43-108">Retrieves a list of devices associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="aae43-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="aae43-109">Permissions</span></span>
<span data-ttu-id="aae43-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="aae43-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="aae43-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="aae43-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="aae43-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="aae43-112">Permission type</span></span> |   <span data-ttu-id="aae43-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="aae43-113">Permission</span></span>  |   <span data-ttu-id="aae43-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="aae43-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="aae43-115">Приложение</span><span class="sxs-lookup"><span data-stu-id="aae43-115">Application</span></span> |   <span data-ttu-id="aae43-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="aae43-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="aae43-117">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="aae43-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="aae43-118">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="aae43-118">Delegated (work or school account)</span></span> | <span data-ttu-id="aae43-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="aae43-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="aae43-120">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="aae43-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="aae43-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="aae43-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a><span data-ttu-id="aae43-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="aae43-122">Request headers</span></span>

<span data-ttu-id="aae43-123">Имя</span><span class="sxs-lookup"><span data-stu-id="aae43-123">Name</span></span> | <span data-ttu-id="aae43-124">Тип</span><span class="sxs-lookup"><span data-stu-id="aae43-124">Type</span></span> | <span data-ttu-id="aae43-125">Описание</span><span class="sxs-lookup"><span data-stu-id="aae43-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="aae43-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="aae43-126">Authorization</span></span> | <span data-ttu-id="aae43-127">String</span><span class="sxs-lookup"><span data-stu-id="aae43-127">String</span></span> | <span data-ttu-id="aae43-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="aae43-128">Bearer {token}.</span></span> <span data-ttu-id="aae43-129">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="aae43-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="aae43-130">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="aae43-130">Request body</span></span>
<span data-ttu-id="aae43-131">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="aae43-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="aae43-132">Отклик</span><span class="sxs-lookup"><span data-stu-id="aae43-132">Response</span></span>
<span data-ttu-id="aae43-133">В случае успеха этот метод возвращает 200 ОК со списком устройств, связанных с рекомендацией по безопасности.</span><span class="sxs-lookup"><span data-stu-id="aae43-133">If successful, this method returns 200 OK with the list of devices associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="aae43-134">Пример</span><span class="sxs-lookup"><span data-stu-id="aae43-134">Example</span></span>

<span data-ttu-id="aae43-135">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="aae43-135">**Request**</span></span>

<span data-ttu-id="aae43-136">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="aae43-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

<span data-ttu-id="aae43-137">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="aae43-137">**Response**</span></span>

<span data-ttu-id="aae43-138">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="aae43-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "e058770379bc199a9c179ce52a23e16fd44fd2ee",
            "computerDnsName": "niw_pc",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="aae43-139">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="aae43-139">Related topics</span></span>
- [<span data-ttu-id="aae43-140">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="aae43-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="aae43-141">Рекомендация по & уязвимости</span><span class="sxs-lookup"><span data-stu-id="aae43-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
