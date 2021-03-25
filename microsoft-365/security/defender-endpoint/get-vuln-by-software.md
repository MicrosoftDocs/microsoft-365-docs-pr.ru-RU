---
title: Список уязвимостей по программному обеспечению
description: Извлечение списка уязвимостей в установленном программном обеспечении.
keywords: apis, graph api, supported apis, get, vulnerabilities list, mdatp tvm api
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
ms.openlocfilehash: 8f05c1a67c845e7f88cbcb3ee88cf7a664d5a4bf
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167208"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="677b8-104">Список уязвимостей по программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="677b8-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="677b8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="677b8-105">**Applies to:**</span></span>
- [<span data-ttu-id="677b8-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="677b8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="677b8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="677b8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="677b8-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="677b8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="677b8-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="677b8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="677b8-110">Извлечение списка уязвимостей в установленном программном обеспечении.</span><span class="sxs-lookup"><span data-stu-id="677b8-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="677b8-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="677b8-111">Permissions</span></span>
<span data-ttu-id="677b8-112">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="677b8-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="677b8-113">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="677b8-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="677b8-114">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="677b8-114">Permission type</span></span> |   <span data-ttu-id="677b8-115">Разрешение</span><span class="sxs-lookup"><span data-stu-id="677b8-115">Permission</span></span>  |   <span data-ttu-id="677b8-116">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="677b8-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="677b8-117">Приложение</span><span class="sxs-lookup"><span data-stu-id="677b8-117">Application</span></span> | <span data-ttu-id="677b8-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="677b8-118">Software.Read.All</span></span> | <span data-ttu-id="677b8-119">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="677b8-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="677b8-120">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="677b8-120">Delegated (work or school account)</span></span> | <span data-ttu-id="677b8-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="677b8-121">Software.Read</span></span> | <span data-ttu-id="677b8-122">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="677b8-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="677b8-123">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="677b8-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="677b8-124">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="677b8-124">Request headers</span></span>

| <span data-ttu-id="677b8-125">Имя</span><span class="sxs-lookup"><span data-stu-id="677b8-125">Name</span></span>        | <span data-ttu-id="677b8-126">Тип</span><span class="sxs-lookup"><span data-stu-id="677b8-126">Type</span></span> | <span data-ttu-id="677b8-127">Описание</span><span class="sxs-lookup"><span data-stu-id="677b8-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="677b8-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="677b8-128">Authorization</span></span> | <span data-ttu-id="677b8-129">Строка</span><span class="sxs-lookup"><span data-stu-id="677b8-129">String</span></span> | <span data-ttu-id="677b8-130">Bearer {token}. **Обязательно**.</span><span class="sxs-lookup"><span data-stu-id="677b8-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="677b8-131">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="677b8-131">Request body</span></span>
<span data-ttu-id="677b8-132">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="677b8-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="677b8-133">Отклик</span><span class="sxs-lookup"><span data-stu-id="677b8-133">Response</span></span>
<span data-ttu-id="677b8-134">В случае успеха этот метод возвращает 200 ОК со списком уязвимостей, открытых указанным программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="677b8-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="677b8-135">Пример</span><span class="sxs-lookup"><span data-stu-id="677b8-135">Example</span></span>

<span data-ttu-id="677b8-136">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="677b8-136">**Request**</span></span>

<span data-ttu-id="677b8-137">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="677b8-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="677b8-138">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="677b8-138">**Response**</span></span>

<span data-ttu-id="677b8-139">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="677b8-139">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
            {
                "id": "CVE-2017-0140",
                "name": "CVE-2017-0140",
                "description": "A security feature bypass vulnerability exists when Microsoft Edge improperly handles requests of different origins. The vulnerability allows Microsoft Edge to bypass Same-Origin Policy (SOP) restrictions, and to allow requests that should otherwise be ignored. An attacker who successfully exploited the vulnerability could force the browser to send data that would otherwise be restricted.In a web-based attack scenario, an attacker could host a specially crafted website that is designed to exploit the vulnerability through Microsoft Edge and then convince a user to view the website. The attacker could also take advantage of compromised websites, and websites that accept or host user-provided content or advertisements. These websites could contain specially crafted content that could exploit the vulnerability.The security update addresses the vulnerability by modifying how affected Microsoft Edge handles different-origin requests.",
                "severity": "Medium",
                "cvssV3": 4.2,
                "exposedMachines": 1,
                "publishedOn": "2017-03-14T00:00:00Z",
                "updatedOn": "2019-10-03T00:03:00Z",
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

