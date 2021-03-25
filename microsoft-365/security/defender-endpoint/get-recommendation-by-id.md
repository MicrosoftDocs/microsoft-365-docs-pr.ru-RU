---
title: Получить рекомендации по ID
description: Извлекает рекомендации по безопасности по его ID.
keywords: apis, graph api, supported apis, get, security recommendation, security recommendation by ID, threat and vulnerability management, threat and vulnerability management api
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
ms.openlocfilehash: 45a151fc5855a4a2b1ba63a50b54737c90e6bdd1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199517"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="35538-104">Получить рекомендации по ID</span><span class="sxs-lookup"><span data-stu-id="35538-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="35538-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="35538-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="35538-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="35538-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="35538-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="35538-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="35538-108">Извлекает рекомендации по безопасности по его ID.</span><span class="sxs-lookup"><span data-stu-id="35538-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="35538-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="35538-109">Permissions</span></span>
<span data-ttu-id="35538-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="35538-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="35538-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="35538-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="35538-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="35538-112">Permission type</span></span> |   <span data-ttu-id="35538-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="35538-113">Permission</span></span>  |   <span data-ttu-id="35538-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="35538-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="35538-115">Application</span><span class="sxs-lookup"><span data-stu-id="35538-115">Application</span></span> |   <span data-ttu-id="35538-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="35538-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="35538-117">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="35538-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="35538-118">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="35538-118">Delegated (work or school account)</span></span> | <span data-ttu-id="35538-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="35538-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="35538-120">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="35538-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="35538-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="35538-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="35538-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="35538-122">Request headers</span></span>

<span data-ttu-id="35538-123">Имя</span><span class="sxs-lookup"><span data-stu-id="35538-123">Name</span></span> | <span data-ttu-id="35538-124">Тип</span><span class="sxs-lookup"><span data-stu-id="35538-124">Type</span></span> | <span data-ttu-id="35538-125">Описание</span><span class="sxs-lookup"><span data-stu-id="35538-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="35538-126">Авторизация</span><span class="sxs-lookup"><span data-stu-id="35538-126">Authorization</span></span> | <span data-ttu-id="35538-127">Строка</span><span class="sxs-lookup"><span data-stu-id="35538-127">String</span></span> | <span data-ttu-id="35538-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="35538-128">Bearer {token}.</span></span> <span data-ttu-id="35538-129">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="35538-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="35538-130">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="35538-130">Request body</span></span>
<span data-ttu-id="35538-131">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="35538-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="35538-132">Отклик</span><span class="sxs-lookup"><span data-stu-id="35538-132">Response</span></span>
<span data-ttu-id="35538-133">В случае успеха этот метод возвращает 200 ОК с рекомендациями безопасности в теле.</span><span class="sxs-lookup"><span data-stu-id="35538-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="35538-134">Пример</span><span class="sxs-lookup"><span data-stu-id="35538-134">Example</span></span>

<span data-ttu-id="35538-135">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="35538-135">**Request**</span></span>

<span data-ttu-id="35538-136">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="35538-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="35538-137">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="35538-137">**Response**</span></span>

<span data-ttu-id="35538-138">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="35538-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a><span data-ttu-id="35538-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="35538-139">Related topics</span></span>
- [<span data-ttu-id="35538-140">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="35538-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="35538-141">Рекомендация по & уязвимости</span><span class="sxs-lookup"><span data-stu-id="35538-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
