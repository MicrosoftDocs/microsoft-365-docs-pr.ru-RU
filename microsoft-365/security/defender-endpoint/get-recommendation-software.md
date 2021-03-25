---
title: Получить рекомендации по программному обеспечению
description: Извлекает рекомендации по безопасности, связанные с определенным программным обеспечением.
keywords: apis, graph api, supported apis, get, security recommendation, security recommendation for software, threat and vulnerability management, threat and vulnerability management api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 82479b0248ceee95321d269e3f48a4eeea3ad193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199505"
---
# <a name="get-recommendation-by-software"></a><span data-ttu-id="f630f-104">Получить рекомендации по программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="f630f-104">Get recommendation by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f630f-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f630f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="f630f-106">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f630f-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f630f-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f630f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f630f-108">Извлекает рекомендации по безопасности, связанные с определенным программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="f630f-108">Retrieves a security recommendation related to a specific software.</span></span>

## <a name="permissions"></a><span data-ttu-id="f630f-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="f630f-109">Permissions</span></span>
<span data-ttu-id="f630f-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="f630f-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f630f-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f630f-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="f630f-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="f630f-112">Permission type</span></span> |   <span data-ttu-id="f630f-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="f630f-113">Permission</span></span>  |   <span data-ttu-id="f630f-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="f630f-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f630f-115">Application</span><span class="sxs-lookup"><span data-stu-id="f630f-115">Application</span></span> |   <span data-ttu-id="f630f-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="f630f-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="f630f-117">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="f630f-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="f630f-118">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="f630f-118">Delegated (work or school account)</span></span> | <span data-ttu-id="f630f-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="f630f-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="f630f-120">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="f630f-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="f630f-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="f630f-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a><span data-ttu-id="f630f-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="f630f-122">Request headers</span></span>

<span data-ttu-id="f630f-123">Имя</span><span class="sxs-lookup"><span data-stu-id="f630f-123">Name</span></span> | <span data-ttu-id="f630f-124">Тип</span><span class="sxs-lookup"><span data-stu-id="f630f-124">Type</span></span> | <span data-ttu-id="f630f-125">Описание</span><span class="sxs-lookup"><span data-stu-id="f630f-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="f630f-126">Авторизация</span><span class="sxs-lookup"><span data-stu-id="f630f-126">Authorization</span></span> | <span data-ttu-id="f630f-127">Строка</span><span class="sxs-lookup"><span data-stu-id="f630f-127">String</span></span> | <span data-ttu-id="f630f-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f630f-128">Bearer {token}.</span></span> <span data-ttu-id="f630f-129">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="f630f-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f630f-130">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="f630f-130">Request body</span></span>
<span data-ttu-id="f630f-131">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="f630f-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f630f-132">Отклик</span><span class="sxs-lookup"><span data-stu-id="f630f-132">Response</span></span>
<span data-ttu-id="f630f-133">В случае успеха этот метод возвращает 200 ОК с программным обеспечением, связанным с рекомендациями по безопасности в теле.</span><span class="sxs-lookup"><span data-stu-id="f630f-133">If successful, this method returns 200 OK with the software associated with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="f630f-134">Пример</span><span class="sxs-lookup"><span data-stu-id="f630f-134">Example</span></span>

<span data-ttu-id="f630f-135">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="f630f-135">**Request**</span></span>

<span data-ttu-id="f630f-136">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="f630f-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

<span data-ttu-id="f630f-137">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="f630f-137">**Response**</span></span>

<span data-ttu-id="f630f-138">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="f630f-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a><span data-ttu-id="f630f-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f630f-139">Related topics</span></span>
- [<span data-ttu-id="f630f-140">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="f630f-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="f630f-141">Рекомендация по & уязвимости</span><span class="sxs-lookup"><span data-stu-id="f630f-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
