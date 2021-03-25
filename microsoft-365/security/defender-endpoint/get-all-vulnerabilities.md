---
title: Получить все уязвимости
description: Извлекает список всех уязвимостей, влияющих на организацию
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
ms.openlocfilehash: c97b70b682351e5ad9d92435068b97622032f769
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166896"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="f52c1-104">Уязвимости списка</span><span class="sxs-lookup"><span data-stu-id="f52c1-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f52c1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f52c1-105">**Applies to:**</span></span>
- [<span data-ttu-id="f52c1-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f52c1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f52c1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f52c1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f52c1-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f52c1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f52c1-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f52c1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f52c1-110">Извлекает список всех уязвимостей, влияющих на организацию.</span><span class="sxs-lookup"><span data-stu-id="f52c1-110">Retrieves a list of all the vulnerabilities affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="f52c1-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="f52c1-111">Permissions</span></span>
<span data-ttu-id="f52c1-112">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="f52c1-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f52c1-113">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f52c1-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="f52c1-114">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="f52c1-114">Permission type</span></span> |   <span data-ttu-id="f52c1-115">Разрешение</span><span class="sxs-lookup"><span data-stu-id="f52c1-115">Permission</span></span>  |   <span data-ttu-id="f52c1-116">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="f52c1-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f52c1-117">Приложение</span><span class="sxs-lookup"><span data-stu-id="f52c1-117">Application</span></span> |   <span data-ttu-id="f52c1-118">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="f52c1-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="f52c1-119">'Read Threat and Vulnerability Management vulnerability information'</span><span class="sxs-lookup"><span data-stu-id="f52c1-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="f52c1-120">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="f52c1-120">Delegated (work or school account)</span></span> | <span data-ttu-id="f52c1-121">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="f52c1-121">Vulnerability.Read</span></span> |   <span data-ttu-id="f52c1-122">'Read Threat and Vulnerability Management vulnerability information'</span><span class="sxs-lookup"><span data-stu-id="f52c1-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="f52c1-123">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="f52c1-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="f52c1-124">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="f52c1-124">Request headers</span></span>

<span data-ttu-id="f52c1-125">Имя</span><span class="sxs-lookup"><span data-stu-id="f52c1-125">Name</span></span> | <span data-ttu-id="f52c1-126">Тип</span><span class="sxs-lookup"><span data-stu-id="f52c1-126">Type</span></span> | <span data-ttu-id="f52c1-127">Описание</span><span class="sxs-lookup"><span data-stu-id="f52c1-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="f52c1-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="f52c1-128">Authorization</span></span> | <span data-ttu-id="f52c1-129">Строка</span><span class="sxs-lookup"><span data-stu-id="f52c1-129">String</span></span> | <span data-ttu-id="f52c1-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f52c1-130">Bearer {token}.</span></span> <span data-ttu-id="f52c1-131">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="f52c1-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f52c1-132">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="f52c1-132">Request body</span></span>
<span data-ttu-id="f52c1-133">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="f52c1-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f52c1-134">Отклик</span><span class="sxs-lookup"><span data-stu-id="f52c1-134">Response</span></span>
<span data-ttu-id="f52c1-135">В случае успеха этот метод возвращает 200 ОК со списком уязвимостей в теле.</span><span class="sxs-lookup"><span data-stu-id="f52c1-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="f52c1-136">Пример</span><span class="sxs-lookup"><span data-stu-id="f52c1-136">Example</span></span>

<span data-ttu-id="f52c1-137">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="f52c1-137">**Request**</span></span>

<span data-ttu-id="f52c1-138">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="f52c1-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="f52c1-139">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="f52c1-139">**Response**</span></span>

<span data-ttu-id="f52c1-140">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="f52c1-140">Here is an example of the response.</span></span>


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

## <a name="see-also"></a><span data-ttu-id="f52c1-141">См. также</span><span class="sxs-lookup"><span data-stu-id="f52c1-141">See also</span></span>
- [<span data-ttu-id="f52c1-142">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="f52c1-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="f52c1-143">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="f52c1-143">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)