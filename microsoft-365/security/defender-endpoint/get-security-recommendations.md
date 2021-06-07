---
title: Получить рекомендации по безопасности
description: Извлекает коллекцию рекомендаций по безопасности, связанных с данным ID устройства.
keywords: apis, graph api, supported apis, get, list, file, information, security recommendation per device, threat & управление уязвимостями api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 44f64334d08d8d0d6a5ed1e8e06baa2880859ad2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771133"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="a8dc5-104">Получить рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="a8dc5-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a8dc5-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a8dc5-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="a8dc5-106">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a8dc5-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a8dc5-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a8dc5-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a8dc5-108">Извлекает коллекцию рекомендаций по безопасности, связанных с данным ID устройства.</span><span class="sxs-lookup"><span data-stu-id="a8dc5-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="a8dc5-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="a8dc5-109">Permissions</span></span>
<span data-ttu-id="a8dc5-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="a8dc5-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a8dc5-111">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a8dc5-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a8dc5-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="a8dc5-112">Permission type</span></span> |   <span data-ttu-id="a8dc5-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="a8dc5-113">Permission</span></span>  |   <span data-ttu-id="a8dc5-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="a8dc5-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a8dc5-115">Приложение</span><span class="sxs-lookup"><span data-stu-id="a8dc5-115">Application</span></span> | <span data-ttu-id="a8dc5-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="a8dc5-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="a8dc5-117">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="a8dc5-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="a8dc5-118">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="a8dc5-118">Delegated (work or school account)</span></span> | <span data-ttu-id="a8dc5-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="a8dc5-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="a8dc5-120">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="a8dc5-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="a8dc5-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="a8dc5-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="a8dc5-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="a8dc5-122">Request headers</span></span>

<span data-ttu-id="a8dc5-123">Имя</span><span class="sxs-lookup"><span data-stu-id="a8dc5-123">Name</span></span> | <span data-ttu-id="a8dc5-124">Тип</span><span class="sxs-lookup"><span data-stu-id="a8dc5-124">Type</span></span> | <span data-ttu-id="a8dc5-125">Описание</span><span class="sxs-lookup"><span data-stu-id="a8dc5-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="a8dc5-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="a8dc5-126">Authorization</span></span> | <span data-ttu-id="a8dc5-127">String</span><span class="sxs-lookup"><span data-stu-id="a8dc5-127">String</span></span> | <span data-ttu-id="a8dc5-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a8dc5-128">Bearer {token}.</span></span> <span data-ttu-id="a8dc5-129">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="a8dc5-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a8dc5-130">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="a8dc5-130">Request body</span></span>
<span data-ttu-id="a8dc5-131">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="a8dc5-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a8dc5-132">Отклик</span><span class="sxs-lookup"><span data-stu-id="a8dc5-132">Response</span></span>
<span data-ttu-id="a8dc5-133">В случае успеха этот метод возвращает 200 ОК с рекомендациями безопасности в теле.</span><span class="sxs-lookup"><span data-stu-id="a8dc5-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="a8dc5-134">Пример</span><span class="sxs-lookup"><span data-stu-id="a8dc5-134">Example</span></span>

<span data-ttu-id="a8dc5-135">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="a8dc5-135">**Request**</span></span>

<span data-ttu-id="a8dc5-136">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="a8dc5-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="a8dc5-137">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="a8dc5-137">**Response**</span></span>

<span data-ttu-id="a8dc5-138">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="a8dc5-138">Here is an example of the response.</span></span>


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a><span data-ttu-id="a8dc5-139">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="a8dc5-139">Related topics</span></span>
- [<span data-ttu-id="a8dc5-140">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="a8dc5-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="a8dc5-141">Рекомендация по & уязвимости</span><span class="sxs-lookup"><span data-stu-id="a8dc5-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
