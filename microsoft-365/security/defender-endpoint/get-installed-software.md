---
title: Получить установленное программное обеспечение
description: Извлекает коллекцию установленного программного обеспечения, связанного с данным ID устройства.
keywords: apis, api графика, поддерживаемые apis, get, list, file, information, software inventory, installed software per device, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: ebd689fd53dd804f857c6bec7a412c27988835d0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935117"
---
# <a name="get-installed-software"></a><span data-ttu-id="05a09-104">Получить установленное программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="05a09-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="05a09-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="05a09-105">**Applies to:**</span></span>
- [<span data-ttu-id="05a09-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="05a09-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="05a09-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05a09-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="05a09-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="05a09-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="05a09-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="05a09-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="05a09-110">Извлекает коллекцию установленного программного обеспечения, связанного с данным ID устройства.</span><span class="sxs-lookup"><span data-stu-id="05a09-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="05a09-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="05a09-111">Permissions</span></span>
<span data-ttu-id="05a09-112">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="05a09-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="05a09-113">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="05a09-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="05a09-114">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="05a09-114">Permission type</span></span> |   <span data-ttu-id="05a09-115">Разрешение</span><span class="sxs-lookup"><span data-stu-id="05a09-115">Permission</span></span>  |   <span data-ttu-id="05a09-116">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="05a09-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="05a09-117">Приложение</span><span class="sxs-lookup"><span data-stu-id="05a09-117">Application</span></span> |<span data-ttu-id="05a09-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="05a09-118">Software.Read.All</span></span> |    <span data-ttu-id="05a09-119">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="05a09-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="05a09-120">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="05a09-120">Delegated (work or school account)</span></span> | <span data-ttu-id="05a09-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="05a09-121">Software.Read</span></span> |    <span data-ttu-id="05a09-122">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="05a09-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="05a09-123">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="05a09-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="05a09-124">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="05a09-124">Request headers</span></span>

<span data-ttu-id="05a09-125">Имя</span><span class="sxs-lookup"><span data-stu-id="05a09-125">Name</span></span> | <span data-ttu-id="05a09-126">Тип</span><span class="sxs-lookup"><span data-stu-id="05a09-126">Type</span></span> | <span data-ttu-id="05a09-127">Описание</span><span class="sxs-lookup"><span data-stu-id="05a09-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="05a09-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="05a09-128">Authorization</span></span> | <span data-ttu-id="05a09-129">String</span><span class="sxs-lookup"><span data-stu-id="05a09-129">String</span></span> | <span data-ttu-id="05a09-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="05a09-130">Bearer {token}.</span></span> <span data-ttu-id="05a09-131">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="05a09-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="05a09-132">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="05a09-132">Request body</span></span>
<span data-ttu-id="05a09-133">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="05a09-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="05a09-134">Отклик</span><span class="sxs-lookup"><span data-stu-id="05a09-134">Response</span></span>
<span data-ttu-id="05a09-135">В случае успеха этот метод возвращает 200 ОК с установленной информацией о программном обеспечении в теле.</span><span class="sxs-lookup"><span data-stu-id="05a09-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="05a09-136">Пример</span><span class="sxs-lookup"><span data-stu-id="05a09-136">Example</span></span>

<span data-ttu-id="05a09-137">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="05a09-137">**Request**</span></span>

<span data-ttu-id="05a09-138">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="05a09-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="05a09-139">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="05a09-139">**Response**</span></span>

<span data-ttu-id="05a09-140">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="05a09-140">Here is an example of the response.</span></span>


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

## <a name="see-also"></a><span data-ttu-id="05a09-141">См. также</span><span class="sxs-lookup"><span data-stu-id="05a09-141">See also</span></span>

- [<span data-ttu-id="05a09-142">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="05a09-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="05a09-143">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="05a09-143">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
