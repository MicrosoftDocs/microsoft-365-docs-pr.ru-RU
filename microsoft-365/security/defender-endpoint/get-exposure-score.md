---
title: Получить оценку экспозиции
description: Извлекает оценку экспозиции организации.
keywords: apis, graph api, supported apis, get, exposure score, organizational exposure score
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7037e49a7f750597af15cfb16e1552aeb98859a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166860"
---
# <a name="get-exposure-score"></a><span data-ttu-id="6e82f-104">Получить оценку экспозиции</span><span class="sxs-lookup"><span data-stu-id="6e82f-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6e82f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6e82f-105">**Applies to:**</span></span>
- [<span data-ttu-id="6e82f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6e82f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6e82f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e82f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6e82f-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="6e82f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6e82f-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="6e82f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6e82f-110">Извлекает оценку экспозиции организации.</span><span class="sxs-lookup"><span data-stu-id="6e82f-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="6e82f-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="6e82f-111">Permissions</span></span>

<span data-ttu-id="6e82f-112">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="6e82f-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6e82f-113">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6e82f-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6e82f-114">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="6e82f-114">Permission type</span></span> | <span data-ttu-id="6e82f-115">Разрешение</span><span class="sxs-lookup"><span data-stu-id="6e82f-115">Permission</span></span> | <span data-ttu-id="6e82f-116">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="6e82f-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6e82f-117">Приложение</span><span class="sxs-lookup"><span data-stu-id="6e82f-117">Application</span></span> | <span data-ttu-id="6e82f-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="6e82f-118">Score.Read.All</span></span> | <span data-ttu-id="6e82f-119">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="6e82f-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="6e82f-120">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="6e82f-120">Delegated (work or school account)</span></span> | <span data-ttu-id="6e82f-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="6e82f-121">Score.Read</span></span> | <span data-ttu-id="6e82f-122">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="6e82f-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="6e82f-123">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="6e82f-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="6e82f-124">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="6e82f-124">Request headers</span></span>

<span data-ttu-id="6e82f-125">Имя</span><span class="sxs-lookup"><span data-stu-id="6e82f-125">Name</span></span> | <span data-ttu-id="6e82f-126">Тип</span><span class="sxs-lookup"><span data-stu-id="6e82f-126">Type</span></span> | <span data-ttu-id="6e82f-127">Описание</span><span class="sxs-lookup"><span data-stu-id="6e82f-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="6e82f-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="6e82f-128">Authorization</span></span> | <span data-ttu-id="6e82f-129">Строка</span><span class="sxs-lookup"><span data-stu-id="6e82f-129">String</span></span> | <span data-ttu-id="6e82f-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6e82f-130">Bearer {token}.</span></span> <span data-ttu-id="6e82f-131">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="6e82f-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="6e82f-132">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="6e82f-132">Request body</span></span>

<span data-ttu-id="6e82f-133">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="6e82f-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6e82f-134">Отклик</span><span class="sxs-lookup"><span data-stu-id="6e82f-134">Response</span></span>

<span data-ttu-id="6e82f-135">В случае успешной работы этот метод возвращает 200 ОК с данными экспозиции в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="6e82f-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="6e82f-136">Пример</span><span class="sxs-lookup"><span data-stu-id="6e82f-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="6e82f-137">Запрос</span><span class="sxs-lookup"><span data-stu-id="6e82f-137">Request</span></span>

<span data-ttu-id="6e82f-138">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="6e82f-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="6e82f-139">Отклик</span><span class="sxs-lookup"><span data-stu-id="6e82f-139">Response</span></span>

<span data-ttu-id="6e82f-140">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="6e82f-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="6e82f-141">Список ответов, показанный здесь, может быть усечен для краткости.</span><span class="sxs-lookup"><span data-stu-id="6e82f-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="6e82f-142">См. также</span><span class="sxs-lookup"><span data-stu-id="6e82f-142">See also</span></span>

- [<span data-ttu-id="6e82f-143">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="6e82f-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="6e82f-144">Оценка & уязвимости</span><span class="sxs-lookup"><span data-stu-id="6e82f-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
