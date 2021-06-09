---
title: Получить все уязвимости
description: Извлекает список всех уязвимостей, влияющих на организацию
keywords: apis, api graph, supported apis, get, vulnerability information, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 4be87e296739020c80babb864c57bc803f10d3e0
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843690"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="eae26-104">Список уязвимостей</span><span class="sxs-lookup"><span data-stu-id="eae26-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eae26-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="eae26-105">**Applies to:**</span></span>
- [<span data-ttu-id="eae26-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="eae26-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eae26-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eae26-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="eae26-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="eae26-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eae26-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="eae26-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="eae26-110">Извлекает список всех уязвимостей, влияющих на организацию.</span><span class="sxs-lookup"><span data-stu-id="eae26-110">Retrieves a list of all the vulnerabilities affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="eae26-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="eae26-111">Permissions</span></span>
<span data-ttu-id="eae26-112">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="eae26-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="eae26-113">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="eae26-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="eae26-114">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="eae26-114">Permission type</span></span> |   <span data-ttu-id="eae26-115">Разрешение</span><span class="sxs-lookup"><span data-stu-id="eae26-115">Permission</span></span>  |   <span data-ttu-id="eae26-116">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="eae26-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="eae26-117">Для приложений</span><span class="sxs-lookup"><span data-stu-id="eae26-117">Application</span></span> |   <span data-ttu-id="eae26-118">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="eae26-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="eae26-119">'Read Threat and Vulnerability Management vulnerability information'</span><span class="sxs-lookup"><span data-stu-id="eae26-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="eae26-120">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="eae26-120">Delegated (work or school account)</span></span> | <span data-ttu-id="eae26-121">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="eae26-121">Vulnerability.Read</span></span> |   <span data-ttu-id="eae26-122">'Read Threat and Vulnerability Management vulnerability information'</span><span class="sxs-lookup"><span data-stu-id="eae26-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="eae26-123">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="eae26-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="eae26-124">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="eae26-124">Request headers</span></span>

<span data-ttu-id="eae26-125">Имя</span><span class="sxs-lookup"><span data-stu-id="eae26-125">Name</span></span> | <span data-ttu-id="eae26-126">Тип</span><span class="sxs-lookup"><span data-stu-id="eae26-126">Type</span></span> | <span data-ttu-id="eae26-127">Описание</span><span class="sxs-lookup"><span data-stu-id="eae26-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="eae26-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="eae26-128">Authorization</span></span> | <span data-ttu-id="eae26-129">String</span><span class="sxs-lookup"><span data-stu-id="eae26-129">String</span></span> | <span data-ttu-id="eae26-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="eae26-130">Bearer {token}.</span></span> <span data-ttu-id="eae26-131">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="eae26-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="eae26-132">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="eae26-132">Request body</span></span>
<span data-ttu-id="eae26-133">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="eae26-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="eae26-134">Отклик</span><span class="sxs-lookup"><span data-stu-id="eae26-134">Response</span></span>
<span data-ttu-id="eae26-135">В случае успеха этот метод возвращает 200 ОК со списком уязвимостей в теле.</span><span class="sxs-lookup"><span data-stu-id="eae26-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="eae26-136">Пример</span><span class="sxs-lookup"><span data-stu-id="eae26-136">Example</span></span>

<span data-ttu-id="eae26-137">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="eae26-137">**Request**</span></span>

<span data-ttu-id="eae26-138">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="eae26-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="eae26-139">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="eae26-139">**Response**</span></span>

<span data-ttu-id="eae26-140">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="eae26-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Vulnerabilities",
    "value": [
        {
            "id": "CVE-2019-0608",
            "name": "CVE-2019-0608",
            "description": "A spoofing vulnerability exists when Microsoft Browsers does not properly parse HTTP content. An attacker who successfully exploited this vulnerability could impersonate a user request by crafting HTTP queries. The specially crafted website could either spoof content or serve as a pivot to chain an attack with other vulnerabilities in web services.To exploit the vulnerability, the user must click a specially crafted URL. In an email attack scenario, an attacker could send an email message containing the specially crafted URL to the user in an attempt to convince the user to click it.In a web-based attack scenario, an attacker could host a specially crafted website designed to appear as a legitimate website to the user. However, the attacker would have no way to force the user to visit the specially crafted website. The attacker would have to convince the user to visit the specially crafted website, typically by way of enticement in an email or instant message, and then convince the user to interact with content on the website.The update addresses the vulnerability by correcting how Microsoft Browsers parses HTTP responses.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 4,
            "publishedOn": "2019-10-08T00:00:00Z",
            "updatedOn": "2019-12-16T16:20:00Z",
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

## <a name="see-also"></a><span data-ttu-id="eae26-141">См. также</span><span class="sxs-lookup"><span data-stu-id="eae26-141">See also</span></span>
- [<span data-ttu-id="eae26-142">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="eae26-142">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="eae26-143">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="eae26-143">Vulnerabilities in your organization</span></span>](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
