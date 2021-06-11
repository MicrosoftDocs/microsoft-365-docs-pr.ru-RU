---
title: Получить показатель уязвимости
description: Извлекает оценку экспозиции организации.
keywords: apis, graph api, supported apis, get, exposure score, organizational exposure score
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
ms.openlocfilehash: 071b0e7597d334fe06d5045e06a5c4d82dd65609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845394"
---
# <a name="get-exposure-score"></a><span data-ttu-id="94f78-104">Получить показатель уязвимости</span><span class="sxs-lookup"><span data-stu-id="94f78-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="94f78-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="94f78-105">**Applies to:**</span></span>
- [<span data-ttu-id="94f78-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="94f78-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="94f78-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94f78-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="94f78-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="94f78-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="94f78-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="94f78-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="94f78-110">Извлекает оценку экспозиции организации.</span><span class="sxs-lookup"><span data-stu-id="94f78-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="94f78-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="94f78-111">Permissions</span></span>

<span data-ttu-id="94f78-112">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="94f78-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="94f78-113">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="94f78-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="94f78-114">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="94f78-114">Permission type</span></span> | <span data-ttu-id="94f78-115">Разрешение</span><span class="sxs-lookup"><span data-stu-id="94f78-115">Permission</span></span> | <span data-ttu-id="94f78-116">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="94f78-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="94f78-117">Приложение</span><span class="sxs-lookup"><span data-stu-id="94f78-117">Application</span></span> | <span data-ttu-id="94f78-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="94f78-118">Score.Read.All</span></span> | <span data-ttu-id="94f78-119">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="94f78-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="94f78-120">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="94f78-120">Delegated (work or school account)</span></span> | <span data-ttu-id="94f78-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="94f78-121">Score.Read</span></span> | <span data-ttu-id="94f78-122">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="94f78-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="94f78-123">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="94f78-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="94f78-124">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="94f78-124">Request headers</span></span>

<span data-ttu-id="94f78-125">Имя</span><span class="sxs-lookup"><span data-stu-id="94f78-125">Name</span></span> | <span data-ttu-id="94f78-126">Тип</span><span class="sxs-lookup"><span data-stu-id="94f78-126">Type</span></span> | <span data-ttu-id="94f78-127">Описание</span><span class="sxs-lookup"><span data-stu-id="94f78-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="94f78-128">Авторизация</span><span class="sxs-lookup"><span data-stu-id="94f78-128">Authorization</span></span> | <span data-ttu-id="94f78-129">String</span><span class="sxs-lookup"><span data-stu-id="94f78-129">String</span></span> | <span data-ttu-id="94f78-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="94f78-130">Bearer {token}.</span></span> <span data-ttu-id="94f78-131">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="94f78-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="94f78-132">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="94f78-132">Request body</span></span>

<span data-ttu-id="94f78-133">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="94f78-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="94f78-134">Отклик</span><span class="sxs-lookup"><span data-stu-id="94f78-134">Response</span></span>

<span data-ttu-id="94f78-135">В случае успешной работы этот метод возвращает 200 ОК с данными экспозиции в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="94f78-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="94f78-136">Пример</span><span class="sxs-lookup"><span data-stu-id="94f78-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="94f78-137">Запрос</span><span class="sxs-lookup"><span data-stu-id="94f78-137">Request</span></span>

<span data-ttu-id="94f78-138">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="94f78-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="94f78-139">Отклик</span><span class="sxs-lookup"><span data-stu-id="94f78-139">Response</span></span>

<span data-ttu-id="94f78-140">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="94f78-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="94f78-141">Список ответов, показанный здесь, может быть усечен для краткости.</span><span class="sxs-lookup"><span data-stu-id="94f78-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="94f78-142">См. также</span><span class="sxs-lookup"><span data-stu-id="94f78-142">See also</span></span>

- [<span data-ttu-id="94f78-143">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="94f78-143">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="94f78-144">Оценка & уязвимости</span><span class="sxs-lookup"><span data-stu-id="94f78-144">Threat & Vulnerability exposure score</span></span>](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
