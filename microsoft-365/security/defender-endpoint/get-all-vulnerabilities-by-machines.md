---
title: Получите все уязвимости с помощью компьютера и программного обеспечения
description: Извлекает список всех уязвимостей, влияющих на организацию машиной и программным обеспечением
keywords: apis, graph api, supported apis, get, vulnerability information, mdatp tvm api
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
ms.technology: mde
ms.openlocfilehash: f7d67948e3b3e7a1a878386a397d2f4a6e8e998e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166903"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a><span data-ttu-id="ef216-104">Список уязвимостей с помощью компьютера и программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="ef216-104">List vulnerabilities by machine and software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ef216-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ef216-105">**Applies to:**</span></span>
- [<span data-ttu-id="ef216-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ef216-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ef216-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef216-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ef216-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ef216-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ef216-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ef216-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="ef216-110">Извлекает список всех уязвимостей, влияющих на организацию каждого компьютера [и](machine.md) [программного обеспечения.](software.md)</span><span class="sxs-lookup"><span data-stu-id="ef216-110">Retrieves a list of all the vulnerabilities affecting the organization per [machine](machine.md) and [software](software.md).</span></span>
- <span data-ttu-id="ef216-111">Если уязвимость имеет исправление КБ, она появится в ответе.</span><span class="sxs-lookup"><span data-stu-id="ef216-111">If the vulnerability has a fixing KB, it will appear in the response.</span></span>
- <span data-ttu-id="ef216-112">Поддерживает [запросы OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="ef216-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
- <span data-ttu-id="ef216-113">OData ```$filter``` поддерживается во всех свойствах.</span><span class="sxs-lookup"><span data-stu-id="ef216-113">The OData ```$filter``` is supported on all properties.</span></span>

>[!Tip]
><span data-ttu-id="ef216-114">Это отличный API для [интеграции Power BI](api-power-bi.md).</span><span class="sxs-lookup"><span data-stu-id="ef216-114">This is great API for [Power BI integration](api-power-bi.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="ef216-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="ef216-115">Permissions</span></span>
<span data-ttu-id="ef216-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="ef216-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ef216-117">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ef216-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="ef216-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="ef216-118">Permission type</span></span> |   <span data-ttu-id="ef216-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="ef216-119">Permission</span></span>  |   <span data-ttu-id="ef216-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="ef216-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ef216-121">Приложение</span><span class="sxs-lookup"><span data-stu-id="ef216-121">Application</span></span> |   <span data-ttu-id="ef216-122">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="ef216-122">Vulnerability.Read.All</span></span> |    <span data-ttu-id="ef216-123">'Read Threat and Vulnerability Management vulnerability information'</span><span class="sxs-lookup"><span data-stu-id="ef216-123">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="ef216-124">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="ef216-124">Delegated (work or school account)</span></span> | <span data-ttu-id="ef216-125">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="ef216-125">Vulnerability.Read</span></span> |   <span data-ttu-id="ef216-126">'Read Threat and Vulnerability Management vulnerability information'</span><span class="sxs-lookup"><span data-stu-id="ef216-126">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="ef216-127">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="ef216-127">HTTP request</span></span>
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="ef216-128">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="ef216-128">Request headers</span></span>

<span data-ttu-id="ef216-129">Имя</span><span class="sxs-lookup"><span data-stu-id="ef216-129">Name</span></span> | <span data-ttu-id="ef216-130">Тип</span><span class="sxs-lookup"><span data-stu-id="ef216-130">Type</span></span> | <span data-ttu-id="ef216-131">Описание</span><span class="sxs-lookup"><span data-stu-id="ef216-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="ef216-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="ef216-132">Authorization</span></span> | <span data-ttu-id="ef216-133">Строка</span><span class="sxs-lookup"><span data-stu-id="ef216-133">String</span></span> | <span data-ttu-id="ef216-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ef216-134">Bearer {token}.</span></span> <span data-ttu-id="ef216-135">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="ef216-135">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ef216-136">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="ef216-136">Request body</span></span>
<span data-ttu-id="ef216-137">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="ef216-137">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ef216-138">Отклик</span><span class="sxs-lookup"><span data-stu-id="ef216-138">Response</span></span>
<span data-ttu-id="ef216-139">В случае успеха этот метод возвращает 200 ОК со списком уязвимостей в теле.</span><span class="sxs-lookup"><span data-stu-id="ef216-139">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="ef216-140">Пример</span><span class="sxs-lookup"><span data-stu-id="ef216-140">Example</span></span>

<span data-ttu-id="ef216-141">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="ef216-141">**Request**</span></span>

<span data-ttu-id="ef216-142">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="ef216-142">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

<span data-ttu-id="ef216-143">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="ef216-143">**Response**</span></span>

<span data-ttu-id="ef216-144">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="ef216-144">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="ef216-145">См. также</span><span class="sxs-lookup"><span data-stu-id="ef216-145">See also</span></span>

- [<span data-ttu-id="ef216-146">Управление угрозами и уязвимостью на основе рисков</span><span class="sxs-lookup"><span data-stu-id="ef216-146">Risk-based threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="ef216-147">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="ef216-147">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
