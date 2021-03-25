---
title: Оценка безопасности устройства
description: Извлекает безопасную оценку для устройства организации.
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.openlocfilehash: 921334c937e3f211b032a5d24d4244d9a6fb3d61
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166884"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="d73a8-104">Оценка безопасности устройства</span><span class="sxs-lookup"><span data-stu-id="d73a8-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d73a8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d73a8-105">**Applies to:**</span></span>
- [<span data-ttu-id="d73a8-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d73a8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d73a8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d73a8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="d73a8-108">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d73a8-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="d73a8-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d73a8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d73a8-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d73a8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="d73a8-111">Извлекает свой [microsoft Secure Score для устройств.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="d73a8-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="d73a8-112">Более высокий показатель microsoft Secure Score для устройств означает, что конечные точки более устойчивы к атакам угроз кибербезопасности.</span><span class="sxs-lookup"><span data-stu-id="d73a8-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="d73a8-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="d73a8-113">Permissions</span></span>

<span data-ttu-id="d73a8-114">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="d73a8-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d73a8-115">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d73a8-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="d73a8-116">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="d73a8-116">Permission type</span></span> |   <span data-ttu-id="d73a8-117">Разрешение</span><span class="sxs-lookup"><span data-stu-id="d73a8-117">Permission</span></span>  |   <span data-ttu-id="d73a8-118">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="d73a8-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d73a8-119">Приложение</span><span class="sxs-lookup"><span data-stu-id="d73a8-119">Application</span></span> |   <span data-ttu-id="d73a8-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="d73a8-120">Score.Read.Alll</span></span> |   <span data-ttu-id="d73a8-121">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="d73a8-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="d73a8-122">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="d73a8-122">Delegated (work or school account)</span></span> | <span data-ttu-id="d73a8-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="d73a8-123">Score.Read</span></span> | <span data-ttu-id="d73a8-124">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="d73a8-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="d73a8-125">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="d73a8-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="d73a8-126">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="d73a8-126">Request headers</span></span>

<span data-ttu-id="d73a8-127">Имя</span><span class="sxs-lookup"><span data-stu-id="d73a8-127">Name</span></span> | <span data-ttu-id="d73a8-128">Тип</span><span class="sxs-lookup"><span data-stu-id="d73a8-128">Type</span></span> | <span data-ttu-id="d73a8-129">Описание</span><span class="sxs-lookup"><span data-stu-id="d73a8-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="d73a8-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="d73a8-130">Authorization</span></span> | <span data-ttu-id="d73a8-131">Строка</span><span class="sxs-lookup"><span data-stu-id="d73a8-131">String</span></span> | <span data-ttu-id="d73a8-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d73a8-132">Bearer {token}.</span></span> <span data-ttu-id="d73a8-133">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="d73a8-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d73a8-134">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="d73a8-134">Request body</span></span>

<span data-ttu-id="d73a8-135">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="d73a8-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d73a8-136">Отклик</span><span class="sxs-lookup"><span data-stu-id="d73a8-136">Response</span></span>

<span data-ttu-id="d73a8-137">В случае успешной работы этот метод возвращает 200 ОК с защищенными данными о оценках устройства в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="d73a8-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="d73a8-138">Пример</span><span class="sxs-lookup"><span data-stu-id="d73a8-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="d73a8-139">Запрос</span><span class="sxs-lookup"><span data-stu-id="d73a8-139">Request</span></span>

<span data-ttu-id="d73a8-140">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="d73a8-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="d73a8-141">Отклик</span><span class="sxs-lookup"><span data-stu-id="d73a8-141">Response</span></span>

<span data-ttu-id="d73a8-142">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="d73a8-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="d73a8-143">Список ответов, показанный здесь, может быть усечен для краткости.</span><span class="sxs-lookup"><span data-stu-id="d73a8-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="d73a8-144">См. также</span><span class="sxs-lookup"><span data-stu-id="d73a8-144">See also</span></span>

- [<span data-ttu-id="d73a8-145">Запросы OData в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d73a8-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
