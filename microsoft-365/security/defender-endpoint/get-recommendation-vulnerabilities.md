---
title: Список уязвимостей по рекомендации
description: Извлекает список уязвимостей, связанных с рекомендацией по безопасности.
keywords: apis, graph api, supported apis, get, list of vulnerabilities, security recommendation, security recommendation for vulnerabilities, threat and vulnerability management, threat and vulnerability management api
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
ms.openlocfilehash: b41ee2886d758ab0ab70b78ee6d6d863d0d482a7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198605"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="2a99b-104">Список уязвимостей по рекомендации</span><span class="sxs-lookup"><span data-stu-id="2a99b-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2a99b-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2a99b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="2a99b-106">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="2a99b-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2a99b-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="2a99b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="2a99b-108">Извлекает список уязвимостей, связанных с рекомендацией по безопасности.</span><span class="sxs-lookup"><span data-stu-id="2a99b-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="2a99b-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="2a99b-109">Permissions</span></span>
<span data-ttu-id="2a99b-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="2a99b-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2a99b-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2a99b-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="2a99b-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="2a99b-112">Permission type</span></span> |   <span data-ttu-id="2a99b-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="2a99b-113">Permission</span></span>  |   <span data-ttu-id="2a99b-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="2a99b-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2a99b-115">Application</span><span class="sxs-lookup"><span data-stu-id="2a99b-115">Application</span></span> |   <span data-ttu-id="2a99b-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="2a99b-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="2a99b-117">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="2a99b-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="2a99b-118">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="2a99b-118">Delegated (work or school account)</span></span> | <span data-ttu-id="2a99b-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="2a99b-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="2a99b-120">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="2a99b-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="2a99b-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="2a99b-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="2a99b-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="2a99b-122">Request headers</span></span>

<span data-ttu-id="2a99b-123">Имя</span><span class="sxs-lookup"><span data-stu-id="2a99b-123">Name</span></span> | <span data-ttu-id="2a99b-124">Тип</span><span class="sxs-lookup"><span data-stu-id="2a99b-124">Type</span></span> | <span data-ttu-id="2a99b-125">Описание</span><span class="sxs-lookup"><span data-stu-id="2a99b-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="2a99b-126">Авторизация</span><span class="sxs-lookup"><span data-stu-id="2a99b-126">Authorization</span></span> | <span data-ttu-id="2a99b-127">Строка</span><span class="sxs-lookup"><span data-stu-id="2a99b-127">String</span></span> | <span data-ttu-id="2a99b-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2a99b-128">Bearer {token}.</span></span> <span data-ttu-id="2a99b-129">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="2a99b-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="2a99b-130">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="2a99b-130">Request body</span></span>
<span data-ttu-id="2a99b-131">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="2a99b-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2a99b-132">Отклик</span><span class="sxs-lookup"><span data-stu-id="2a99b-132">Response</span></span>
<span data-ttu-id="2a99b-133">В случае успешной работы этот метод возвращает 200 ОК со списком уязвимостей, связанных с рекомендацией по безопасности.</span><span class="sxs-lookup"><span data-stu-id="2a99b-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="2a99b-134">Пример</span><span class="sxs-lookup"><span data-stu-id="2a99b-134">Example</span></span>

<span data-ttu-id="2a99b-135">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="2a99b-135">**Request**</span></span>

<span data-ttu-id="2a99b-136">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="2a99b-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="2a99b-137">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="2a99b-137">**Response**</span></span>

<span data-ttu-id="2a99b-138">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="2a99b-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
     ]
}
```

## <a name="related-topics"></a><span data-ttu-id="2a99b-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2a99b-139">Related topics</span></span>
- [<span data-ttu-id="2a99b-140">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="2a99b-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2a99b-141">Рекомендация по & уязвимости</span><span class="sxs-lookup"><span data-stu-id="2a99b-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)