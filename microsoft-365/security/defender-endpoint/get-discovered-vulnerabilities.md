---
title: Получить обнаруженные уязвимости
description: Извлекает коллекцию обнаруженных уязвимостей, связанных с данным ID устройства.
keywords: apis, graph api, supported apis, get, list, file, information, discovered vulnerabilities, threat & управление уязвимостями api, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: cd3b1343711a5bed9ad606a6b8dc754f223ed279
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430784"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="c4c2e-104">Получить обнаруженные уязвимости</span><span class="sxs-lookup"><span data-stu-id="c4c2e-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c4c2e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c4c2e-105">**Applies to:**</span></span>
- [<span data-ttu-id="c4c2e-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c4c2e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c4c2e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4c2e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c4c2e-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c4c2e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c4c2e-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c4c2e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="c4c2e-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="c4c2e-110">API description</span></span>
<span data-ttu-id="c4c2e-111">Извлекает коллекцию обнаруженных уязвимостей, связанных с данным ID устройства.</span><span class="sxs-lookup"><span data-stu-id="c4c2e-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="c4c2e-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c4c2e-112">Limitations</span></span>
1. <span data-ttu-id="c4c2e-113">Ограничения скорости для этого API : 50 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="c4c2e-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="c4c2e-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="c4c2e-114">Permissions</span></span>

<span data-ttu-id="c4c2e-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="c4c2e-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c4c2e-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c4c2e-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c4c2e-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="c4c2e-117">Permission type</span></span> | <span data-ttu-id="c4c2e-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="c4c2e-118">Permission</span></span> | <span data-ttu-id="c4c2e-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="c4c2e-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c4c2e-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="c4c2e-120">Application</span></span> |<span data-ttu-id="c4c2e-121">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="c4c2e-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="c4c2e-122">'Read Threat and Vulnerability Management vulnerability information'</span><span class="sxs-lookup"><span data-stu-id="c4c2e-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="c4c2e-123">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="c4c2e-123">Delegated (work or school account)</span></span> | <span data-ttu-id="c4c2e-124">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="c4c2e-124">Vulnerability.Read</span></span> | <span data-ttu-id="c4c2e-125">'Read Threat and Vulnerability Management vulnerability information'</span><span class="sxs-lookup"><span data-stu-id="c4c2e-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="c4c2e-126">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="c4c2e-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="c4c2e-127">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="c4c2e-127">Request headers</span></span>

<span data-ttu-id="c4c2e-128">Имя</span><span class="sxs-lookup"><span data-stu-id="c4c2e-128">Name</span></span> | <span data-ttu-id="c4c2e-129">Тип</span><span class="sxs-lookup"><span data-stu-id="c4c2e-129">Type</span></span> | <span data-ttu-id="c4c2e-130">Описание</span><span class="sxs-lookup"><span data-stu-id="c4c2e-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="c4c2e-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="c4c2e-131">Authorization</span></span> | <span data-ttu-id="c4c2e-132">String</span><span class="sxs-lookup"><span data-stu-id="c4c2e-132">String</span></span> | <span data-ttu-id="c4c2e-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c4c2e-133">Bearer {token}.</span></span> <span data-ttu-id="c4c2e-134">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="c4c2e-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c4c2e-135">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="c4c2e-135">Request body</span></span>

<span data-ttu-id="c4c2e-136">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="c4c2e-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c4c2e-137">Отклик</span><span class="sxs-lookup"><span data-stu-id="c4c2e-137">Response</span></span>

<span data-ttu-id="c4c2e-138">В случае успеха этот метод возвращает 200 ОК с обнаруженной информацией об уязвимости в теле.</span><span class="sxs-lookup"><span data-stu-id="c4c2e-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="c4c2e-139">Пример</span><span class="sxs-lookup"><span data-stu-id="c4c2e-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="c4c2e-140">Запрос</span><span class="sxs-lookup"><span data-stu-id="c4c2e-140">Request</span></span>

<span data-ttu-id="c4c2e-141">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="c4c2e-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="c4c2e-142">Отклик</span><span class="sxs-lookup"><span data-stu-id="c4c2e-142">Response</span></span>

<span data-ttu-id="c4c2e-143">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="c4c2e-143">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="c4c2e-144">См. также</span><span class="sxs-lookup"><span data-stu-id="c4c2e-144">See also</span></span>

- [<span data-ttu-id="c4c2e-145">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="c4c2e-145">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="c4c2e-146">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="c4c2e-146">Vulnerabilities in your organization</span></span>](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
