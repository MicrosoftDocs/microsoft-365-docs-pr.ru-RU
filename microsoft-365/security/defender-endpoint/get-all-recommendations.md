---
title: Список всех рекомендаций
description: Извлекает список всех рекомендаций по безопасности, влияющих на организацию.
keywords: apis, graph api, supported apis, get, security recommendations, Microsoft Defender for Endpoint tvm api, контроль угроз и уязвимостей, контроль угроз и уязвимостей api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: eb009a01e36739ab5e9ec009d053a7bd4e177907
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841538"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="73ca9-104">Список всех рекомендаций</span><span class="sxs-lookup"><span data-stu-id="73ca9-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="73ca9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="73ca9-105">**Applies to:**</span></span>
- [<span data-ttu-id="73ca9-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="73ca9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="73ca9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73ca9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="73ca9-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="73ca9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="73ca9-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="73ca9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="73ca9-110">Извлекает список всех рекомендаций по безопасности, влияющих на организацию.</span><span class="sxs-lookup"><span data-stu-id="73ca9-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="73ca9-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="73ca9-111">Permissions</span></span>
<span data-ttu-id="73ca9-112">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="73ca9-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="73ca9-113">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="73ca9-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="73ca9-114">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="73ca9-114">Permission type</span></span> |   <span data-ttu-id="73ca9-115">Разрешение</span><span class="sxs-lookup"><span data-stu-id="73ca9-115">Permission</span></span>  |   <span data-ttu-id="73ca9-116">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="73ca9-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="73ca9-117">Для приложений</span><span class="sxs-lookup"><span data-stu-id="73ca9-117">Application</span></span> |   <span data-ttu-id="73ca9-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="73ca9-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="73ca9-119">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="73ca9-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="73ca9-120">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="73ca9-120">Delegated (work or school account)</span></span> | <span data-ttu-id="73ca9-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="73ca9-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="73ca9-122">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="73ca9-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="73ca9-123">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="73ca9-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="73ca9-124">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="73ca9-124">Request headers</span></span>

<span data-ttu-id="73ca9-125">Имя</span><span class="sxs-lookup"><span data-stu-id="73ca9-125">Name</span></span> | <span data-ttu-id="73ca9-126">Тип</span><span class="sxs-lookup"><span data-stu-id="73ca9-126">Type</span></span> | <span data-ttu-id="73ca9-127">Описание</span><span class="sxs-lookup"><span data-stu-id="73ca9-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="73ca9-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="73ca9-128">Authorization</span></span> | <span data-ttu-id="73ca9-129">String</span><span class="sxs-lookup"><span data-stu-id="73ca9-129">String</span></span> | <span data-ttu-id="73ca9-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="73ca9-130">Bearer {token}.</span></span> <span data-ttu-id="73ca9-131">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="73ca9-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="73ca9-132">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="73ca9-132">Request body</span></span>
<span data-ttu-id="73ca9-133">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="73ca9-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="73ca9-134">Отклик</span><span class="sxs-lookup"><span data-stu-id="73ca9-134">Response</span></span>
<span data-ttu-id="73ca9-135">В случае успеха этот метод возвращает 200 ОК со списком рекомендаций по безопасности в теле.</span><span class="sxs-lookup"><span data-stu-id="73ca9-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="73ca9-136">Пример</span><span class="sxs-lookup"><span data-stu-id="73ca9-136">Example</span></span>

<span data-ttu-id="73ca9-137">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="73ca9-137">**Request**</span></span>

<span data-ttu-id="73ca9-138">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="73ca9-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="73ca9-139">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="73ca9-139">**Response**</span></span>

<span data-ttu-id="73ca9-140">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="73ca9-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10",
            "productName": "windows_10",
            "recommendationName": "Update Windows 10",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10"
        }
        ...
     ]
}
```
## <a name="see-also"></a><span data-ttu-id="73ca9-141">См. также</span><span class="sxs-lookup"><span data-stu-id="73ca9-141">See also</span></span>
- [<span data-ttu-id="73ca9-142">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="73ca9-142">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="73ca9-143">Рекомендация по & уязвимости</span><span class="sxs-lookup"><span data-stu-id="73ca9-143">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

