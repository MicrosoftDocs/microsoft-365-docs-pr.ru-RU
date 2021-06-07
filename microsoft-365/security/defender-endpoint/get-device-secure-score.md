---
title: Получить оценку безопасности устройства
description: Извлекает безопасную оценку для устройства организации.
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.openlocfilehash: dd9def688619b6079d947cb76069aa0f77d768de
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772309"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="45ff9-104">Получить оценку безопасности устройства</span><span class="sxs-lookup"><span data-stu-id="45ff9-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="45ff9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="45ff9-105">**Applies to:**</span></span>
- [<span data-ttu-id="45ff9-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="45ff9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="45ff9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45ff9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="45ff9-108">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="45ff9-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="45ff9-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="45ff9-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="45ff9-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="45ff9-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="45ff9-111">Извлекает свой [microsoft Secure Score для устройств.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="45ff9-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="45ff9-112">Более высокий показатель microsoft Secure Score для устройств означает, что конечные точки более устойчивы к атакам угроз кибербезопасности.</span><span class="sxs-lookup"><span data-stu-id="45ff9-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="45ff9-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="45ff9-113">Permissions</span></span>

<span data-ttu-id="45ff9-114">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="45ff9-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="45ff9-115">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="45ff9-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="45ff9-116">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="45ff9-116">Permission type</span></span> |   <span data-ttu-id="45ff9-117">Разрешение</span><span class="sxs-lookup"><span data-stu-id="45ff9-117">Permission</span></span>  |   <span data-ttu-id="45ff9-118">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="45ff9-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="45ff9-119">Приложение</span><span class="sxs-lookup"><span data-stu-id="45ff9-119">Application</span></span> |   <span data-ttu-id="45ff9-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="45ff9-120">Score.Read.Alll</span></span> |   <span data-ttu-id="45ff9-121">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="45ff9-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="45ff9-122">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="45ff9-122">Delegated (work or school account)</span></span> | <span data-ttu-id="45ff9-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="45ff9-123">Score.Read</span></span> | <span data-ttu-id="45ff9-124">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="45ff9-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="45ff9-125">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="45ff9-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="45ff9-126">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="45ff9-126">Request headers</span></span>

<span data-ttu-id="45ff9-127">Имя</span><span class="sxs-lookup"><span data-stu-id="45ff9-127">Name</span></span> | <span data-ttu-id="45ff9-128">Тип</span><span class="sxs-lookup"><span data-stu-id="45ff9-128">Type</span></span> | <span data-ttu-id="45ff9-129">Описание</span><span class="sxs-lookup"><span data-stu-id="45ff9-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="45ff9-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="45ff9-130">Authorization</span></span> | <span data-ttu-id="45ff9-131">String</span><span class="sxs-lookup"><span data-stu-id="45ff9-131">String</span></span> | <span data-ttu-id="45ff9-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="45ff9-132">Bearer {token}.</span></span> <span data-ttu-id="45ff9-133">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="45ff9-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="45ff9-134">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="45ff9-134">Request body</span></span>

<span data-ttu-id="45ff9-135">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="45ff9-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="45ff9-136">Отклик</span><span class="sxs-lookup"><span data-stu-id="45ff9-136">Response</span></span>

<span data-ttu-id="45ff9-137">В случае успешной работы этот метод возвращает 200 ОК с защищенными данными о оценках устройства в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="45ff9-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="45ff9-138">Пример</span><span class="sxs-lookup"><span data-stu-id="45ff9-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="45ff9-139">Запрос</span><span class="sxs-lookup"><span data-stu-id="45ff9-139">Request</span></span>

<span data-ttu-id="45ff9-140">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="45ff9-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="45ff9-141">Отклик</span><span class="sxs-lookup"><span data-stu-id="45ff9-141">Response</span></span>

<span data-ttu-id="45ff9-142">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="45ff9-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="45ff9-143">Список ответов, показанный здесь, может быть усечен для краткости.</span><span class="sxs-lookup"><span data-stu-id="45ff9-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="45ff9-144">См. также</span><span class="sxs-lookup"><span data-stu-id="45ff9-144">See also</span></span>

- [<span data-ttu-id="45ff9-145">Запросы OData в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="45ff9-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
