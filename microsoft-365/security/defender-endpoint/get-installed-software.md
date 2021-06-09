---
title: Получить установленное программное обеспечение
description: Извлекает коллекцию установленного программного обеспечения, связанного с данным ID устройства.
keywords: apis, graph api, supported apis, get, list, file, information, software inventory, installed software per device, threat & управление уязвимостями api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: e13e2072ad1c18f3c6bf1abbbe95c95bb519dc3e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841118"
---
# <a name="get-installed-software"></a><span data-ttu-id="e1d3c-104">Получить установленное программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="e1d3c-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e1d3c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e1d3c-105">**Applies to:**</span></span>
- [<span data-ttu-id="e1d3c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e1d3c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e1d3c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1d3c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e1d3c-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e1d3c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e1d3c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e1d3c-110">Извлекает коллекцию установленного программного обеспечения, связанного с данным ID устройства.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="e1d3c-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="e1d3c-111">Permissions</span></span>
<span data-ttu-id="e1d3c-112">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e1d3c-113">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e1d3c-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e1d3c-114">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="e1d3c-114">Permission type</span></span> |   <span data-ttu-id="e1d3c-115">Разрешение</span><span class="sxs-lookup"><span data-stu-id="e1d3c-115">Permission</span></span>  |   <span data-ttu-id="e1d3c-116">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="e1d3c-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e1d3c-117">Для приложений</span><span class="sxs-lookup"><span data-stu-id="e1d3c-117">Application</span></span> |<span data-ttu-id="e1d3c-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="e1d3c-118">Software.Read.All</span></span> |    <span data-ttu-id="e1d3c-119">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="e1d3c-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="e1d3c-120">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="e1d3c-120">Delegated (work or school account)</span></span> | <span data-ttu-id="e1d3c-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="e1d3c-121">Software.Read</span></span> |    <span data-ttu-id="e1d3c-122">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="e1d3c-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="e1d3c-123">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="e1d3c-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="e1d3c-124">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="e1d3c-124">Request headers</span></span>

<span data-ttu-id="e1d3c-125">Имя</span><span class="sxs-lookup"><span data-stu-id="e1d3c-125">Name</span></span> | <span data-ttu-id="e1d3c-126">Тип</span><span class="sxs-lookup"><span data-stu-id="e1d3c-126">Type</span></span> | <span data-ttu-id="e1d3c-127">Описание</span><span class="sxs-lookup"><span data-stu-id="e1d3c-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="e1d3c-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="e1d3c-128">Authorization</span></span> | <span data-ttu-id="e1d3c-129">String</span><span class="sxs-lookup"><span data-stu-id="e1d3c-129">String</span></span> | <span data-ttu-id="e1d3c-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-130">Bearer {token}.</span></span> <span data-ttu-id="e1d3c-131">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e1d3c-132">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="e1d3c-132">Request body</span></span>
<span data-ttu-id="e1d3c-133">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="e1d3c-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e1d3c-134">Отклик</span><span class="sxs-lookup"><span data-stu-id="e1d3c-134">Response</span></span>
<span data-ttu-id="e1d3c-135">В случае успеха этот метод возвращает 200 ОК с установленной информацией о программном обеспечении в теле.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="e1d3c-136">Пример</span><span class="sxs-lookup"><span data-stu-id="e1d3c-136">Example</span></span>

<span data-ttu-id="e1d3c-137">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="e1d3c-137">**Request**</span></span>

<span data-ttu-id="e1d3c-138">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="e1d3c-139">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="e1d3c-139">**Response**</span></span>

<span data-ttu-id="e1d3c-140">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-140">Here is an example of the response.</span></span>


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="e1d3c-141">См. также</span><span class="sxs-lookup"><span data-stu-id="e1d3c-141">See also</span></span>

- [<span data-ttu-id="e1d3c-142">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="e1d3c-142">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="e1d3c-143">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="e1d3c-143">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
