---
title: Список уязвимостей по программному обеспечению
description: Извлечение списка уязвимостей в установленном программном обеспечении.
keywords: apis, graph api, supported apis, get, vulnerabilities list, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 18a2cf87cd0e6b898a9f2aa4d6ecd47a86a8c7f6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769921"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="f30d3-104">Список уязвимостей по программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="f30d3-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f30d3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f30d3-105">**Applies to:**</span></span>
- [<span data-ttu-id="f30d3-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f30d3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f30d3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f30d3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f30d3-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f30d3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f30d3-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f30d3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f30d3-110">Извлечение списка уязвимостей в установленном программном обеспечении.</span><span class="sxs-lookup"><span data-stu-id="f30d3-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="f30d3-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="f30d3-111">Permissions</span></span>
<span data-ttu-id="f30d3-112">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="f30d3-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f30d3-113">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f30d3-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="f30d3-114">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="f30d3-114">Permission type</span></span> |   <span data-ttu-id="f30d3-115">Разрешение</span><span class="sxs-lookup"><span data-stu-id="f30d3-115">Permission</span></span>  |   <span data-ttu-id="f30d3-116">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="f30d3-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f30d3-117">Приложение</span><span class="sxs-lookup"><span data-stu-id="f30d3-117">Application</span></span> | <span data-ttu-id="f30d3-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="f30d3-118">Software.Read.All</span></span> | <span data-ttu-id="f30d3-119">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="f30d3-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="f30d3-120">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="f30d3-120">Delegated (work or school account)</span></span> | <span data-ttu-id="f30d3-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="f30d3-121">Software.Read</span></span> | <span data-ttu-id="f30d3-122">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="f30d3-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="f30d3-123">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="f30d3-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="f30d3-124">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="f30d3-124">Request headers</span></span>

| <span data-ttu-id="f30d3-125">Имя</span><span class="sxs-lookup"><span data-stu-id="f30d3-125">Name</span></span>        | <span data-ttu-id="f30d3-126">Тип</span><span class="sxs-lookup"><span data-stu-id="f30d3-126">Type</span></span> | <span data-ttu-id="f30d3-127">Описание</span><span class="sxs-lookup"><span data-stu-id="f30d3-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="f30d3-128">Авторизация</span><span class="sxs-lookup"><span data-stu-id="f30d3-128">Authorization</span></span> | <span data-ttu-id="f30d3-129">String</span><span class="sxs-lookup"><span data-stu-id="f30d3-129">String</span></span> | <span data-ttu-id="f30d3-130">Bearer {token}. **Обязательно**.</span><span class="sxs-lookup"><span data-stu-id="f30d3-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f30d3-131">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="f30d3-131">Request body</span></span>
<span data-ttu-id="f30d3-132">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="f30d3-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f30d3-133">Отклик</span><span class="sxs-lookup"><span data-stu-id="f30d3-133">Response</span></span>
<span data-ttu-id="f30d3-134">В случае успеха этот метод возвращает 200 ОК со списком уязвимостей, открытых указанным программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="f30d3-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="f30d3-135">Пример</span><span class="sxs-lookup"><span data-stu-id="f30d3-135">Example</span></span>

<span data-ttu-id="f30d3-136">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="f30d3-136">**Request**</span></span>

<span data-ttu-id="f30d3-137">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="f30d3-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="f30d3-138">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="f30d3-138">**Response**</span></span>

<span data-ttu-id="f30d3-139">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="f30d3-139">Here is an example of the response.</span></span>

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

