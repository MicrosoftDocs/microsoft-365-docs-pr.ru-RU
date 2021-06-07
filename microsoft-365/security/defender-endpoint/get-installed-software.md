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
ms.openlocfilehash: 35cbeedc5d13f5eeb99718b4f98e2d8aabe1e965
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770161"
---
# <a name="get-installed-software"></a><span data-ttu-id="465f4-104">Получить установленное программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="465f4-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="465f4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="465f4-105">**Applies to:**</span></span>
- [<span data-ttu-id="465f4-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="465f4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="465f4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="465f4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="465f4-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="465f4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="465f4-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="465f4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="465f4-110">Извлекает коллекцию установленного программного обеспечения, связанного с данным ID устройства.</span><span class="sxs-lookup"><span data-stu-id="465f4-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="465f4-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="465f4-111">Permissions</span></span>
<span data-ttu-id="465f4-112">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="465f4-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="465f4-113">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="465f4-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="465f4-114">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="465f4-114">Permission type</span></span> |   <span data-ttu-id="465f4-115">Разрешение</span><span class="sxs-lookup"><span data-stu-id="465f4-115">Permission</span></span>  |   <span data-ttu-id="465f4-116">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="465f4-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="465f4-117">Приложение</span><span class="sxs-lookup"><span data-stu-id="465f4-117">Application</span></span> |<span data-ttu-id="465f4-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="465f4-118">Software.Read.All</span></span> |    <span data-ttu-id="465f4-119">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="465f4-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="465f4-120">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="465f4-120">Delegated (work or school account)</span></span> | <span data-ttu-id="465f4-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="465f4-121">Software.Read</span></span> |    <span data-ttu-id="465f4-122">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="465f4-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="465f4-123">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="465f4-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="465f4-124">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="465f4-124">Request headers</span></span>

<span data-ttu-id="465f4-125">Имя</span><span class="sxs-lookup"><span data-stu-id="465f4-125">Name</span></span> | <span data-ttu-id="465f4-126">Тип</span><span class="sxs-lookup"><span data-stu-id="465f4-126">Type</span></span> | <span data-ttu-id="465f4-127">Описание</span><span class="sxs-lookup"><span data-stu-id="465f4-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="465f4-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="465f4-128">Authorization</span></span> | <span data-ttu-id="465f4-129">String</span><span class="sxs-lookup"><span data-stu-id="465f4-129">String</span></span> | <span data-ttu-id="465f4-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="465f4-130">Bearer {token}.</span></span> <span data-ttu-id="465f4-131">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="465f4-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="465f4-132">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="465f4-132">Request body</span></span>
<span data-ttu-id="465f4-133">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="465f4-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="465f4-134">Отклик</span><span class="sxs-lookup"><span data-stu-id="465f4-134">Response</span></span>
<span data-ttu-id="465f4-135">В случае успеха этот метод возвращает 200 ОК с установленной информацией о программном обеспечении в теле.</span><span class="sxs-lookup"><span data-stu-id="465f4-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="465f4-136">Пример</span><span class="sxs-lookup"><span data-stu-id="465f4-136">Example</span></span>

<span data-ttu-id="465f4-137">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="465f4-137">**Request**</span></span>

<span data-ttu-id="465f4-138">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="465f4-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="465f4-139">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="465f4-139">**Response**</span></span>

<span data-ttu-id="465f4-140">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="465f4-140">Here is an example of the response.</span></span>


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

## <a name="see-also"></a><span data-ttu-id="465f4-141">См. также</span><span class="sxs-lookup"><span data-stu-id="465f4-141">See also</span></span>

- [<span data-ttu-id="465f4-142">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="465f4-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="465f4-143">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="465f4-143">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
