---
title: Оценка экспозиции списка по группе устройств
description: Извлекает список результатов воздействия по группе устройств.
keywords: apis, graph api, supported apis, get, exposure score, device group, device group exposure score
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: a7f343db64174fe3c48eaf8b584b03b53921edcb
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843618"
---
# <a name="list-exposure-score-by-device-group"></a><span data-ttu-id="f541f-104">Оценка экспозиции списка по группе устройств</span><span class="sxs-lookup"><span data-stu-id="f541f-104">List exposure score by device group</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f541f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f541f-105">**Applies to:**</span></span>
- [<span data-ttu-id="f541f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f541f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f541f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f541f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f541f-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f541f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f541f-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f541f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f541f-110">Извлекает коллекцию оповещений, связанных с заданным доменным адресом.</span><span class="sxs-lookup"><span data-stu-id="f541f-110">Retrieves a collection of alerts related to a given domain address.</span></span>

## <a name="permissions"></a><span data-ttu-id="f541f-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="f541f-111">Permissions</span></span>

<span data-ttu-id="f541f-112">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="f541f-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f541f-113">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f541f-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f541f-114">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="f541f-114">Permission type</span></span> |   <span data-ttu-id="f541f-115">Разрешение</span><span class="sxs-lookup"><span data-stu-id="f541f-115">Permission</span></span>  |   <span data-ttu-id="f541f-116">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="f541f-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f541f-117">Для приложений</span><span class="sxs-lookup"><span data-stu-id="f541f-117">Application</span></span> | <span data-ttu-id="f541f-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="f541f-118">Score.Read.All</span></span> | <span data-ttu-id="f541f-119">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="f541f-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="f541f-120">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="f541f-120">Delegated (work or school account)</span></span> | <span data-ttu-id="f541f-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="f541f-121">Score.Read</span></span> | <span data-ttu-id="f541f-122">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="f541f-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="f541f-123">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="f541f-123">HTTP request</span></span>

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a><span data-ttu-id="f541f-124">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="f541f-124">Request headers</span></span>

| <span data-ttu-id="f541f-125">Имя</span><span class="sxs-lookup"><span data-stu-id="f541f-125">Name</span></span>        | <span data-ttu-id="f541f-126">Тип</span><span class="sxs-lookup"><span data-stu-id="f541f-126">Type</span></span> | <span data-ttu-id="f541f-127">Описание</span><span class="sxs-lookup"><span data-stu-id="f541f-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="f541f-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="f541f-128">Authorization</span></span> | <span data-ttu-id="f541f-129">String</span><span class="sxs-lookup"><span data-stu-id="f541f-129">String</span></span> | <span data-ttu-id="f541f-130">Bearer {token}. **Обязательно**.</span><span class="sxs-lookup"><span data-stu-id="f541f-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f541f-131">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="f541f-131">Request body</span></span>

<span data-ttu-id="f541f-132">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="f541f-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f541f-133">Отклик</span><span class="sxs-lookup"><span data-stu-id="f541f-133">Response</span></span>

<span data-ttu-id="f541f-134">В случае успешной работы этот метод возвращает 200 ОК со списком показателей экспозиции на данные группы устройств в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="f541f-134">If successful, this method returns 200 OK, with a list of exposure score per device group data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="f541f-135">Пример</span><span class="sxs-lookup"><span data-stu-id="f541f-135">Example</span></span>

### <a name="request"></a><span data-ttu-id="f541f-136">Запрос</span><span class="sxs-lookup"><span data-stu-id="f541f-136">Request</span></span>

<span data-ttu-id="f541f-137">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="f541f-137">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a><span data-ttu-id="f541f-138">Отклик</span><span class="sxs-lookup"><span data-stu-id="f541f-138">Response</span></span>

<span data-ttu-id="f541f-139">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="f541f-139">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="f541f-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f541f-140">Related topics</span></span>

- [<span data-ttu-id="f541f-141">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="f541f-141">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="f541f-142">Оценка & уязвимости</span><span class="sxs-lookup"><span data-stu-id="f541f-142">Threat & Vulnerability exposure score</span></span>](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
